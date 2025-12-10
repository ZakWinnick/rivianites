# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static event marketing website for "Rivianites / Electro-Terrestrials" - an Area 51 road trip event for electric vehicle enthusiasts (primarily Rivian owners). The site uses a neon cyberpunk aesthetic with no build system or framework.

## Development

**No build process required** - this is pure static HTML/CSS.

To run locally:
```bash
python -m http.server
# or
npx http-server
```

Then open `http://localhost:8000` (or the appropriate port).

## Architecture

**Tech Stack:**
- Vanilla HTML5/CSS3
- No JavaScript framework (only external analytics via Tinylytics)
- Google Fonts (Space Grotesk, Courier Prime, Inter)

**File Structure:**
- `index.html` - Primary/current version (505 lines, most polished)
- `index-current.html`, `index-new.html`, `index-old.html` - Design iterations
- `*.png` - Banner and background images
- `*.pdf`, `*.kmz` - Event documents and map data

**HTML Structure:**
All CSS is embedded in `<head>` within a `<style>` tag. The body contains:
1. Hero section with banner and date badge
2. Day cards (Friday, Saturday, Sunday) with activities
3. Links/resources section
4. Footer

**CSS Architecture:**
- CSS custom properties in `:root` for theming (12 color variables)
- Key colors: `--deep-space` (background), `--neon-green`, `--neon-cyan`, `--neon-pink` (accents)
- Mobile breakpoint at 768px
- Flexbox and CSS Grid for layout

## Content Notes

- Site includes real addresses, charging locations (Tesla/Rivian networks), and pricing
- KMZ file provides Google Earth route data
- "Coming Soon" placeholders exist for future content
- Footer credits "Wyld Wandering"
