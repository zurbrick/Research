# Test Coverage Analysis Report

## Executive Summary

**Current Test Coverage: 0%**

This repository has **no formal test infrastructure** in place. The codebase consists primarily of Jupyter notebooks (28 files) for research and analysis, plus one production Python script (`generate_social_media_thumbnails.py`, 195 lines) that runs every 3 hours via GitHub Actions.

---

## Current State

### Codebase Structure

| Category | Files | Lines of Code | Test Coverage |
|----------|-------|---------------|---------------|
| Production Code | 1 | ~195 | 0% |
| Research Notebooks | 28 | N/A (interactive) | N/A |
| Test Files | 0 | 0 | - |

### Testing Infrastructure

- **Test Framework**: None configured
- **Test Files**: None exist
- **CI/CD Testing**: No test step in GitHub Actions workflow
- **Coverage Tools**: None configured

---

## Critical Areas Requiring Tests

### 1. Production Script: `Explore/generate_social_media_thumbnails.py`

This is the **highest priority** for testing as it runs automatically in production every 3 hours.

#### 1.1 Security Vulnerability: `eval()` Usage (Line 17-18)

```python
def __get_json_content(url: str) -> List:
    content = __get_text_content(url) \
        .replace("null", "None").replace("true", "True").replace("false", "False")
    try:
        return eval(content)  # DANGEROUS: Arbitrary code execution risk
    except:
        exit(f'Invalid content for {url}')
```

**Risk Level**: HIGH
**Issue**: Using `eval()` on external API content is a security vulnerability that could allow arbitrary code execution.
**Tests Needed**:
- Test with valid JSON responses
- Test with malicious payloads to verify sanitization
- Replace `eval()` with `json.loads()` and add appropriate tests

#### 1.2 Network Request Functions (Lines 10-11, 21-27)

```python
def __get_text_content(url: str) -> str:
    return get(url).content.decode('utf-8')

def __get_profile(url: str) -> Image:
    if not url or 'icon' in url:
        return None
    image = get(url.replace("\\",""), stream=True)
    if image.status_code != 200:
        return None
```

**Tests Needed**:
- Unit tests with mocked HTTP responses
- Network timeout handling
- Invalid URL handling
- HTTP error codes (404, 500, etc.)
- Connection failure scenarios
- Empty response handling
- Non-UTF8 content handling

#### 1.3 Image Processing Functions (Lines 21-40, 42-67)

```python
def __get_profile(url: str) -> Image:
    # Creates circular profile picture with alpha channel

def __get_equity_curve(strategy, width=1200, height=400) -> Image:
    # Generates Plotly chart as image
```

**Tests Needed**:
- Various image formats (JPEG, PNG, GIF, WebP)
- Corrupted image handling
- Different image dimensions
- Missing/null statistics data
- Empty sparkline data
- Edge cases in equity curve generation

#### 1.4 Template Rendering Functions (Lines 69-151)

```python
def __create_landscape(template, strategy, profile) -> Image:
def __create_square(template, strategy, profile) -> Image:
```

**Tests Needed**:
- Text overflow handling (currently splits at 530px/650px)
- Very long strategy names
- Very long author names
- Missing category handling
- Unicode/emoji in text fields
- None/null values in strategy dict
- Template image loading failures

#### 1.5 Error Handling (Throughout)

**Current Issues**:
- Bare `except` blocks (line 18)
- Silent failures with `return None`
- No logging
- `exit()` on parse errors kills the entire process

**Tests Needed**:
- Verify appropriate exceptions are raised
- Verify error messages are informative
- Verify partial failures don't crash entire batch

---

## Proposed Test Structure

### Recommended Directory Structure

```
Research/
├── tests/
│   ├── __init__.py
│   ├── conftest.py                    # Shared fixtures
│   ├── test_social_media_thumbnails.py
│   ├── fixtures/
│   │   ├── sample_strategy.json       # Mock API response
│   │   ├── sample_profile.png         # Test profile image
│   │   └── mock_sparkline.json        # Test chart data
│   └── integration/
│       └── test_thumbnail_generation.py
├── pytest.ini
└── requirements-dev.txt
```

### Recommended Testing Stack

```
# requirements-dev.txt
pytest>=7.0.0
pytest-cov>=4.0.0
pytest-mock>=3.10.0
responses>=0.22.0      # For mocking HTTP requests
Pillow>=9.3.0          # For image assertions
freezegun>=1.2.0       # For time-based tests
```

---

## Specific Test Recommendations

### Priority 1: Critical Security & Reliability

| Test Case | Description | Priority |
|-----------|-------------|----------|
| `test_json_parsing_without_eval` | Replace `eval()` with `json.loads()` and verify | CRITICAL |
| `test_malicious_payload_rejected` | Ensure no code execution from API | CRITICAL |
| `test_network_timeout_handling` | Add and test timeout on requests | HIGH |
| `test_http_error_codes` | Handle 400, 401, 403, 404, 500, 502, 503 | HIGH |

### Priority 2: Core Functionality

| Test Case | Description | Priority |
|-----------|-------------|----------|
| `test_get_profile_valid_image` | Verify profile extraction works | HIGH |
| `test_get_profile_missing_url` | Verify None returned for empty URL | HIGH |
| `test_get_profile_icon_url` | Verify None for icon placeholder URLs | HIGH |
| `test_get_equity_curve_valid_data` | Verify chart generation | HIGH |
| `test_get_equity_curve_empty_sparkline` | Verify empty data handling | HIGH |
| `test_create_landscape_valid_strategy` | Full landscape thumbnail | MEDIUM |
| `test_create_square_valid_strategy` | Full square thumbnail | MEDIUM |

### Priority 3: Edge Cases

| Test Case | Description | Priority |
|-----------|-------------|----------|
| `test_long_strategy_name_wrapping` | Names > 530px width | MEDIUM |
| `test_long_author_name_truncation` | Names > 250px width | MEDIUM |
| `test_missing_category` | Empty/null category handling | MEDIUM |
| `test_unicode_in_text_fields` | Non-ASCII characters | MEDIUM |
| `test_default_photo_fallback` | Missing profile uses default | LOW |

### Priority 4: Integration Tests

| Test Case | Description | Priority |
|-----------|-------------|----------|
| `test_full_pipeline_single_strategy` | End-to-end for one strategy | MEDIUM |
| `test_full_pipeline_batch` | Multiple strategies in sequence | MEDIUM |
| `test_output_file_format` | Verify PNG output is valid | MEDIUM |
| `test_output_dimensions` | Verify image sizes | LOW |

---

## CI/CD Improvements

### Current Workflow (No Tests)

```yaml
jobs:
  build:
    steps:
      - uses: actions/checkout@v2
      - name: Install dependencies
      - name: Social Media Thumbnails    # Runs script directly
      - name: Copy files to S3
```

### Recommended Workflow (With Tests)

```yaml
jobs:
  test:
    runs-on: ubuntu-20.04
    steps:
      - uses: actions/checkout@v2
      - name: Install dependencies
        run: |
          pip install -r requirements-dev.txt
      - name: Run tests with coverage
        run: |
          pytest tests/ --cov=Explore --cov-report=xml --cov-fail-under=80
      - name: Upload coverage report
        uses: codecov/codecov-action@v3

  deploy:
    needs: test
    runs-on: ubuntu-20.04
    steps:
      # ... existing deployment steps
```

---

## Estimated Effort

| Task | Estimated Effort |
|------|------------------|
| Set up pytest infrastructure | Small |
| Write unit tests for network functions | Small |
| Write unit tests for image processing | Medium |
| Write unit tests for template rendering | Medium |
| Write integration tests | Medium |
| Refactor `eval()` to `json.loads()` | Small |
| Add error handling & logging | Medium |
| Update CI/CD pipeline | Small |

---

## Recommendations Summary

### Immediate Actions (Critical)

1. **Replace `eval()` with `json.loads()`** - Security vulnerability
2. **Add request timeouts** - Prevent hung processes
3. **Set up pytest infrastructure** - Foundation for all testing

### Short-term Actions (High Priority)

4. **Add unit tests for HTTP request functions** - Mock external dependencies
5. **Add unit tests for image processing** - Verify core functionality
6. **Update CI/CD to run tests before deploy** - Prevent broken deployments

### Medium-term Actions

7. **Add integration tests** - End-to-end verification
8. **Add code coverage tracking** - Measure progress
9. **Add logging** - Improve debugging in production
10. **Add input validation** - Defensive programming

---

## Conclusion

The codebase currently has **zero test coverage** for production code that runs automatically every 3 hours. The most critical issues are:

1. **Security**: Using `eval()` on external API data
2. **Reliability**: No error handling for network failures
3. **Maintainability**: No tests to prevent regressions

Implementing even basic unit tests for the `generate_social_media_thumbnails.py` script would significantly improve the reliability and security of the automated thumbnail generation process.
