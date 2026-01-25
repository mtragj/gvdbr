# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Jekyll-based static website for the Grand Valley Dirt Bike Rally (GVDBR), an annual event hosted by the Motorcycle Trail Riding Association (MTRA). Deployed to GitHub Pages at `https://mtragj.github.io/gvdbr/`.

## Build Commands

```bash
# Install dependencies
bundle install

# Run local development server
bundle exec jekyll server --config _config.yml,_config_dev.yml
# Access at http://127.0.0.1:4000/gvdbr/
```

The site auto-regenerates on content file changes. For template/layout changes, restart the server.

## Architecture

### Template Hierarchy

Layouts inherit from `compress.html` → `default.html` → specialized layouts (`page.html`, `ride.html`, `frontpage.html`, etc.). All layouts are in `_layouts/`.

### Includes Convention

Two types of includes in `_includes/`:
- **Template includes** (prefixed with `_`): structural components like `_head.html`, `_footer.html`, `_navigation.html`
- **Command includes** (no prefix, no `.html` in usage): reusable content blocks used in posts/pages, e.g., `{% include alert success="Message" %}`, `{% include gallery %}`

### Content Organization

- `_posts/rides/` - Trail ride descriptions with frontmatter for difficulty, distance, location
- `_posts/news/` - News articles
- `pages/` - Static markdown pages
- `_data/` - YAML data files for navigation, authors, social media, i18n strings

### Styling

SCSS files in `_sass/` using Foundation framework. Numbered files indicate load order (01-11). Compiled CSS output goes to `assets/css/`.

## Deployment

Automatic via GitHub Actions on push to `main`. The workflow builds Jekyll with baseurl `/gvdbr` and deploys to GitHub Pages.
