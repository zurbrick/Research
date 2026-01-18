# QuantConnect Research Repository

A collection of financial research notebooks and an automated thumbnail generation system for the QuantConnect Algorithm Explorer.

## Project Overview

This repository serves two main purposes:
1. **Educational Content**: Jupyter notebooks demonstrating quantitative finance techniques, trading strategies, and machine learning applications
2. **Thumbnail Automation**: Generates professional social media thumbnails for strategies shared on QuantConnect's Algorithm Explorer

## Tech Stack

- **Python 3** (primary language)
- **Pillow** - Image processing for thumbnail generation
- **Plotly/Kaleido** - Chart rendering for equity curves
- **NumPy** - Numerical operations
- **GitHub Actions** - Automated thumbnail generation (runs every 3 hours)
- **AWS S3** - Thumbnail storage and delivery

## Directory Structure

```
Research/
├── Analysis/              # Quantitative analysis notebooks (factor analysis, pairs trading, etc.)
├── Research2Production/   # Production-ready strategy implementations
│   ├── Python/           # Python strategy notebooks
│   └── CSharp/           # C# strategy notebooks
├── Documentation/         # Tutorials (Matplotlib, Plotly, Keras, TensorFlow, etc.)
├── Topical/              # Event-based market analysis
├── Scratch Notebooks/    # Work-in-progress drafts
├── Explore/              # Thumbnail generation system
│   ├── generate_social_media_thumbnails.py
│   ├── template_landscape.png
│   ├── template_square.png
│   ├── default_photo.png
│   └── Inter font/       # Typography assets
└── .github/workflows/    # CI/CD automation
```

## Running the Thumbnail Generator

```bash
# Install dependencies
pip install kaleido==0.2.1 numpy==1.24.2 Pillow==9.3.0 plotly==5.13.1

# Run the generator
cd Explore/
python generate_social_media_thumbnails.py
```

Output: `thumbnails/` directory with `{projectId}.png` (landscape) and `{projectId}_square.png` (square) formats.

## Key Files

| File | Purpose |
|------|---------|
| `Explore/generate_social_media_thumbnails.py` | Main thumbnail generation script |
| `.github/workflows/gh-actions.yml` | Automated workflow (3-hour schedule) |
| `Explore/template_*.png` | Base templates for thumbnails |
| `Explore/default_photo.png` | Fallback author profile image |

## Thumbnail Generator Patterns

**API Integration**: Fetches strategy data from `https://www.quantconnect.com/api/v2/sharing/strategies/list/`

**Category Colors**:
- CRYPTO: `#C39E78`
- EQUITIES: `#BF7C7C`
- US EQUITIES: `#9A74BF`
- ETF: `#B44444`
- FOREX: `#5FB26F`
- FUTURES: `#5D6586`

**Image Processing**:
- Circular profile images using luminosity masks
- RGBA channel management for transparency
- Width-aware text wrapping for strategy names

**Error Handling**:
- Gracefully handles missing/failed profile image downloads
- Falls back to `default_photo.png` when needed
- Converts images to RGB for compatibility

## Development Notes

- The thumbnail generator relies on QuantConnect's public API
- Profile images are downloaded and processed into circular format
- Font: Inter (SemiBold for titles, Regular for metadata)
- Template dimensions: Landscape ~1200x650px, Square ~1000x1000px
