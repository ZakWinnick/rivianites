# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Jekyll-based static site for "Electro-Terrestrials" - an Area 51 road trip event for electric vehicle enthusiasts. Hosted on GitHub Pages with automatic light/dark mode based on system preferences.

## Development

```bash
# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

Site runs at `http://localhost:4000/rivianites/`

## Architecture

**Tech Stack:**
- Jekyll (GitHub Pages compatible)
- CSS with `prefers-color-scheme` for automatic light/dark mode
- Google Fonts (Inter, JetBrains Mono)
- Tinylytics analytics (in `<head>` of `_layouts/default.html`)

**Directory Structure:**
```
_config.yml          # Jekyll config, site metadata
_layouts/
  default.html       # Base layout with Tinylytics, fonts, CSS link
assets/
  css/main.css       # All styles with light/dark mode variables
  images/            # Banner and other images
index.html           # Main content with Jekyll front matter
Gemfile              # Ruby dependencies (github-pages gem)
```

**CSS Theme System:**
- Light mode: Clean white/gray palette with indigo/purple accents
- Dark mode: Dark zinc backgrounds with brighter accent variants
- Variables defined in `:root`, overridden via `@media (prefers-color-scheme: dark)`
- Key variables: `--bg-primary`, `--text-primary`, `--accent-primary`

## Content Notes

- Site includes real addresses, charging locations (Tesla/Rivian networks), and pricing
- "Coming Soon" placeholders exist for future resource links
- Footer credits "Wyld Wandering"
