# jeffberg.github.io — Project Intelligence

## What This Is
Jeff Berg's personal website. A single poetic page. Hosted on GitHub Pages.
Intentionally minimal, intentionally invisible to search engines.

## Architecture
- **Static HTML** — no build step, no framework, no dependencies
- **GitHub Pages** — auto-deploys from `main` branch
- **`.nojekyll`** — bypasses Jekyll processing
- **`robots.txt`** — blocks all crawlers
- **`noindex, nofollow, noarchive, nosnippet`** — on all HTML pages

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
- Never remove `noindex`/`nofollow` without explicit approval
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
robots.txt          — blocks all crawlers
.nojekyll           — skip Jekyll
CLAUDE.md           — this file (project intelligence)
_workforce/         — agent definitions for website development
  agents/           — 8 specialist agents + orchestrator
  skills/           — quick-action website commands
  roadmap/          — development phases
.github/workflows/  — CI/CD
```
