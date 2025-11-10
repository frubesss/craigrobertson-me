# Project Development Guidelines

Last verified: 2025-11-10 12:35 local time

## Overview
This repository is a static site with no build step. The site is served from the project root and consists of:
- `index.html` — the single-page site
- `favicon.png` — site icon referenced by `index.html`
- `CNAME` — custom domain configuration (e.g., `craigrobertson.me`)
- `README.md`

There is no package manager or framework here; everything is plain HTML/CSS.

## Build and Configuration
- No build is required. Any static file host (including GitHub Pages) can serve this repo as-is.
- UTF-8 is required. `index.html` contains typographic characters (e.g., right single quotation mark `’`); ensure your editor saves as UTF‑8 and do not normalize punctuation inadvertently.
- Custom domain (GitHub Pages):
  - Keep `CNAME` at repo root. Deleting or moving it may break the domain.

## Additional Development Guidance
- HTML/CSS style:
  - Keep indentation and quoting consistent with existing file (`index.html` uses single quotes for some attributes like `id` and double quotes in others; tests currently rely on exact strings).
  - Inline CSS is used for simplicity; if you externalize CSS, update `<link>` tags and any tests that assume inline styles.
  - Root font-size increases via media query at `min-width: 1000px`; consider this when adjusting typography.
- Accessibility and UX:
  - Text is white on a blue background `#436DBF`; if you change colors, maintain adequate contrast.
  - Links open in new tabs (`target="_blank"`). Consider adding `rel="noopener noreferrer"` for security, and update tests if you assert it.
  - Maintain semantic structure (header, subtitle, list of links) to keep the page screen-reader friendly.
- SEO/Social:
  - Keep `<meta name="description">` and Open Graph tags in sync with visible content.
  - Update OG description if the experience years or role title change.
