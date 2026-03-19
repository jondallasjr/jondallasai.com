# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML portfolio and content platform for Jon Dallas (AI Solutions Architect) at jondallasai.com. **No build tools, no npm, no framework** — just self-contained HTML files with inline CSS and minimal inline JS.

## Local Development

```bash
# Serve locally (no build step needed)
python3 -m http.server --directory output/website/ 8000
# Visit http://localhost:8000/
```

To edit: modify HTML files directly in `output/website/`. All CSS lives in each page's `<style>` block; all JS is inline in `<script>` tags.

## Deployment

Configured for Vercel (`vercel.json` sets `outputDirectory: "public"`). The site is static — deployable to any hosting platform by serving the contents of `output/website/`.

## Architecture

### Page Structure

All 11 pages in `output/website/` follow the same template pattern:
1. Meta/SEO tags (Open Graph, description)
2. Google Fonts preconnect + CDN links (`DM Serif Display`, `Inter`, `JetBrains Mono`)
3. Phosphor Icons CDN script (deferred)
4. Inline `<style>` block with CSS custom properties
5. Fixed nav header (60px, backdrop blur)
6. Page content (max-width 1200px centered)
7. Footer (dark theme `#141210`)
8. Inline `<script>` (if needed)

### Design System (CSS Custom Properties)

```css
--bg: #F7F5F1;        /* Warm off-white background */
--text: #1A1917;      /* Near-black text */
--amber: #C17B3B;     /* Terracotta primary CTA */
--sage: #5C7A5A;      /* Muted green secondary */
--muted: #8C8880;     /* Warm gray metadata */
--white: #FFFFFF;     /* Card backgrounds */
--border: #E5E2DC;    /* Light borders */
--card-bg: #FDFCFA;   /* Almost-white cards */
```

Typography: `DM Serif Display` for headings, `Inter` for body, `JetBrains Mono` for code/numbers.

### Key Pages

- `output/website/index.html` — Homepage (hero + stats + services + case studies + blog preview)
- `output/website/blog/` — Blog index + posts (long-form articles with sidebar)
- `output/website/case-studies/` — Case studies index + 3 deep-dive pages (2-col layout with sticky sidebar)
- `output/website/stories/` — Scrollystories index + interactive full-screen click-advance stories
- `output/website/about/` — Bio, skills grid, timeline, testimonials
- `output/website/contact/` — Calendly booking, newsletter signup, contact form

### Image Paths

All production images are in `images/final/`. Pages reference them with relative paths (e.g., from `blog/450-articles/index.html`: `../../../../images/final/blog-450-articles.jpg`). The `images/generated/` and `images/user/` directories are gitignored (raw source files).

### Interactive Elements

- **Newsletter forms**: `<form id="newsletter-form" data-coda-endpoint="">` — POST to Coda API (endpoint TBD)
- **Contact form**: Similar pattern, endpoint needs configuration
- **Scrollystory navigation**: Click right/left sides, arrow keys, or swipe to advance full-screen slides; progress dots at bottom

## Reference Documents

- `brief.md` — Creative brief with design specs, color palette, typography, and content outlines
- `status.md` — Project phase tracker (Phase 5: Build complete, QA pending)
- `tracker.md` — Content mapping and navigation index

## Open Work

- Coda API endpoints not yet configured for newsletter/contact forms
- Blog posts 2 & 3 need content
- Scrollystories 2-4 are stubs ("Coming soon")
