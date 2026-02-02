# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

"Electro-Terrestrials" - Jekyll-based single-page site for an Area 51 road trip event for electric vehicle enthusiasts. Live at https://area51.rivianites.online. Features automatic light/dark mode based on system preferences.

## Development Commands

```bash
# Install dependencies
bundle install

# Local development
bundle exec jekyll serve
# Runs at http://localhost:4000/rivianites/

# Build for production
bundle exec jekyll build
```

Deployment: Automatic via GitHub Pages on push to `main`.

## Project Structure

```
/
├── _config.yml              # Jekyll config
├── _layouts/
│   └── default.html         # Base template (fonts, analytics, CSS)
├── assets/
│   ├── css/main.css         # All styles with light/dark variables
│   └── images/
│       └── area51-banner.png
├── index.html               # Main event page content
├── Gemfile                  # github-pages gem
├── CNAME                    # Custom domain
├── *.pdf                    # Route maps and guides (excluded from build)
├── *.kmz                    # GPS route file (excluded from build)
└── *.png                    # Event graphics
```

## Configuration

From `_config.yml`:
- **Title**: "Electro-Terrestrials: An Area 51 Road Trip"
- **URL**: `https://area51.rivianites.online`
- **Baseurl**: `` (empty)
- **Excluded**: Gemfile*, README, CLAUDE.md, PDFs, KMZ files

## CSS Theme System

Automatic light/dark mode using `prefers-color-scheme`:

### Light Mode (Default)
```css
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f8fafc;
  --text-primary: #18181b;
  --text-secondary: #52525b;
  --accent-primary: #6366f1;   /* Indigo */
  --accent-secondary: #8b5cf6; /* Purple */
}
```

### Dark Mode
```css
@media (prefers-color-scheme: dark) {
  :root {
    --bg-primary: #18181b;
    --bg-secondary: #27272a;
    --text-primary: #fafafa;
    --text-secondary: #a1a1aa;
    --accent-primary: #818cf8;
    --accent-secondary: #a78bfa;
  }
}
```

### Key Variables
| Variable | Purpose |
|----------|---------|
| `--bg-primary` | Main background |
| `--bg-secondary` | Cards, sections |
| `--text-primary` | Headings, body text |
| `--text-secondary` | Muted text |
| `--accent-primary` | Links, buttons |
| `--border-color` | Dividers, borders |

## Typography

- **Primary**: Inter (Google Fonts)
- **Monospace**: JetBrains Mono (Google Fonts)
- Loaded in `_layouts/default.html`

## Analytics

Tinylytics tracker in `<head>` of `_layouts/default.html`.

## Content Notes

The site includes real-world information:
- Actual addresses and locations
- Charging station details (Tesla Supercharger, Rivian Adventure Network)
- Route-specific pricing and distances
- "Coming Soon" placeholders for future resource links

## Assets

| File | Description |
|------|-------------|
| `area51-banner.png` | Hero banner image |
| `area51.png`, `area51-1.png`, `area51-2.png` | Event graphics |
| `NTTRC01_geo.pdf` | Nevada Test and Training Range map |
| `a51vg.pdf` | Area 51 visitor guide |
| `rider.kmz` | GPS route file for navigation |

## Deployment

GitHub Pages serves from `main` branch. Custom domain configured via CNAME file.
