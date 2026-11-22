# jeffberg.github.io — Project Intelligence

## What This Is
Jeff Berg's personal website. A single poetic page. Hosted on GitHub Pages.
Intentionally minimal. Public and indexed by search engines (since 2026-11-22).

## Architecture
- **Static HTML** — no build step, no framework, no dependencies
- **GitHub Pages** — auto-deploys from `main` branch
- **`.nojekyll`** — bypasses Jekyll processing
- **`robots.txt`** — allows all crawlers, disallows `/_workforce/`, points to `sitemap.xml`
- **`index, follow`** on `/` and `/cv/` (with description, canonical, Open Graph); `noindex` on `404.html`
- **JSON-LD `Person`** on the homepage
- **`sitemap.xml`** — update `lastmod` and add new pages when publishing

## Design Language
- **Palette**: warm paper (#f4efe6), ink (#1a1614), soft ink (#5a4f48), rose (#d9b5a0), sky (#b8c9d4)
- **Typography**: Cormorant Garamond → EB Garamond → system serif (no web font load)
- **Sans stack**: ui-sans-serif, system-ui (used for small labels/footer)
- **Voice**: lowercase, italic serif headlines, poetic, spare
- **Motion**: slow 28s gradient drift, 1.6s rise-in. Respects `prefers-reduced-motion`.
- **Grain**: SVG feTurbulence noise overlay, hidden on mobile (<768px) for GPU perf

## Content
The poem on the homepage is Jeff's original writing. Do not alter it without explicit permission.
The `✦` mark and "a small page" tagline are part of the identity.

## Rules
- Never add external dependencies (no CDN, no Google Fonts, no JS libraries)
- Every new public page needs a description, canonical URL, OG tags, and a `sitemap.xml` entry
- Keep the site to a single HTML file per page (inline CSS, no separate stylesheets)
- Prefer system font stacks over web fonts
- Every page must honor `prefers-reduced-motion` and include `focus-visible` styles
- Test accessibility: semantic HTML, `aria-hidden` on decorative elements, keyboard-navigable

## Workforce
See `_workforce/` for agent definitions that guide website development.
The `_workforce/` directory is prefixed with `_` so GitHub Pages ignores it.

## File Map
```
index.html          — the one page (poem, gradient field, grain)
404.html            — not-found page (same aesthetic)
robots.txt          — allows crawlers, points to sitemap
sitemap.xml         — public pages for search engines
cv/index.html       — curriculum vitae
papers/             — hosted publication PDFs
.nojekyll           — skip Jekyll
CLAUDE.md           — this file (project intelligence)
_workforce/         — agent definitions for website development
  agents/           — 8 specialist agents + orchestrator
  skills/           — quick-action website commands
  roadmap/          — development phases
.github/workflows/  — CI/CD
```
