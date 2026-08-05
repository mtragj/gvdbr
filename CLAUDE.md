# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Jekyll-based static website for the Grand Valley Dirt Bike Rally (GVDBR), an annual event hosted by the Motorcycle Trail Riding Association (MTRA). Deployed to GitHub Pages and served at the custom domain `https://grandvalleydirtbikerally.com/` (configured via the root `CNAME` file).

## Branching Workflow

**Before writing any code for a new feature or change**, always complete steps 1–2 first:

1. Fetch and checkout the latest `main` branch (`git fetch origin main && git checkout main && git pull origin main`)
2. Create a new branch named `minor/na/<feature_name>` where `feature_name` is a brief description joined by underscores (e.g., `minor/na/add_moderation_queue`)
3. Implement the changes on this branch
4. When ready, push the branch to the remote and open a PR against `main`

## Build Commands

```bash
# Install dependencies
bundle install

# Run local development server
bundle exec jekyll server --config _config.yml,_config_dev.yml
# Access at http://127.0.0.1:4000/
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

### Renaming Posts & Redirects

Post URLs come from `permalink: /:categories/:title/`, so a post's URL is its
`categories` frontmatter plus the filename slug (the leading date is stripped).
Renaming the file or editing `categories` **moves the URL and 404s any link
already shared**. Changing only the date in the filename is safe here — unlike
`mtragj`, the date is not part of the permalink.

The theme has a built-in `redirect` layout (`_layouts/redirect.html`) for this —
no plugins needed. Do **not** add `jekyll-redirect-from`.

1. Rename the post with `git mv` and update any affected frontmatter/body text.
2. Add a stub at `pages/redirects/<old-slug>.md` per old URL:
   ```yaml
   ---
   title: "<Title> (moved)"
   layout: redirect
   sitemap:
       exclude: true    # NOTE: _includes/sitemap_collection.xml checks
                        # `sitemap.exclude`, NOT the `sitemap: false` shown
                        # in the redirect layout's own header comment
   permalink: /rides/north_desert/advanced/trail-ride-old-slug/    # OLD url
   redirect_to: /rides/north_desert/advanced/trail-ride-new-slug/  # NEW url
   ---
   ```
   - This repo's `redirect.html` emits `page.redirect_to` verbatim (it does not
     prepend `site.url`/`site.baseurl`), so use **root-relative paths starting
     with `/`**. Absolute `http(s)://` URLs also work.
   - A stub is a *page*, not a post, so it never appears in `site.categories.*`
     ride listings or the search index.
   - One stub per old URL. If a post moves twice, repoint or chain the stubs so
     every previously-shared URL still resolves.
3. Verify with a production build (`bundle exec jekyll build --config _config.yml`):
   the old path's `index.html` should contain a `<meta http-equiv="refresh">` to
   the new URL, and `sitemap.xml` should not mention the old slug.

### Styling

SCSS files in `_sass/` using Foundation framework. Numbered files indicate load order (01-11). Compiled CSS output goes to `assets/css/`.

### Images for News/Ride Posts

When adding images to news or ride posts, create two sized versions:
- **Thumbnail** (~271px width): Use for the `thumb` frontmatter field
- **Title/Homepage** (1024x768): Use for both `title` and `homepage` frontmatter fields

Example frontmatter:
```yaml
image:
    thumb: my_image_271_203.jpg
    homepage: my_image_1024_768.jpg
    title: my_image_1024_768.jpg
    caption: Image description
```

Name files descriptively with dimensions: `descriptive_name_1024_768.jpg`, `descriptive_name_271_203.jpg`

## Deployment

Automatic via GitHub Actions on push to `main`. The workflow builds Jekyll with an empty baseurl (the site is served at the root of the custom domain) and deploys to GitHub Pages. The root `CNAME` file tells GitHub Pages to serve the site at `grandvalleydirtbikerally.com`.
