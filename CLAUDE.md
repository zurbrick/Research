# CLAUDE.md

## Project Overview

This is a QuantConnect Research repository containing Jupyter notebooks and utilities for algorithmic trading education and analysis. It includes tutorial notebooks, production-ready strategy examples, and automated social media thumbnail generation.

## Technologies

- **Primary Language:** Python 3 (Jupyter notebooks)
- **Secondary Language:** C# (limited use in Research2Production section)
- **Key Libraries:** numpy, pandas, plotly, matplotlib, seaborn, scikit-learn, TensorFlow, Keras, Pillow
- **Platform:** QuantConnect LEAN algorithmic trading platform

## Project Structure

```
Research/
├── Research2Production/     # Tutorial series: Research to Production
│   ├── Python/              # 8 foundational strategy notebooks
│   └── CSharp/              # C# implementations
├── Analysis/                # Advanced analysis examples (5 notebooks)
├── Documentation/Python/    # Beginner documentation (7 notebooks)
├── Topical/                 # Event-driven market analysis notebooks
├── Explore/                 # Utility scripts for social media
│   ├── generate_social_media_thumbnails.py  # Main utility script
│   ├── template_landscape.png               # 1200x400 template
│   ├── template_square.png                  # Square template
│   └── Inter font/                          # Font assets
├── Scratch Notebooks/       # Draft/experimental work
└── .github/workflows/       # CI/CD automation
```

## Common Commands

### Run the thumbnail generator
```bash
python ./Explore/generate_social_media_thumbnails.py
```

### Install dependencies
```bash
pip install kaleido==0.2.1 numpy==1.24.2 Pillow==9.3.0 plotly==5.13.1
```

### Run a Jupyter notebook
```bash
jupyter notebook /path/to/notebook.ipynb
```

## Development Guidelines

- **Notebook format:** Changes to notebooks are in Jupyter notebook JSON format
- **Dependencies:** Use specific versions from `.github/workflows/gh-actions.yml`, not latest
- **Image assets:** Template and font files in `Explore/` are critical for thumbnail generation
- **API integration:** Thumbnail generator fetches from `https://www.quantconnect.com/api/v2/sharing/strategies/list/`
- **No requirements.txt:** Dependencies are defined in GitHub Actions workflow only

## CI/CD

GitHub Actions workflow (`.github/workflows/gh-actions.yml`):
- Runs on schedule (every 3 hours) and manual trigger
- Executes thumbnail generator
- Uploads results to AWS S3

## Key Files

- `Explore/generate_social_media_thumbnails.py` - Main utility for generating social media thumbnails
- `.github/workflows/gh-actions.yml` - CI/CD automation configuration
- `README.md` - Project documentation and links to notebooks
