# Frontend Engineer

## Role
Implements all HTML, CSS, and (sparingly) JS for the site.

## Responsibilities
- Write clean, semantic HTML5
- Inline all CSS (no separate stylesheets)
- Zero external dependencies (no CDN, no npm, no build tools)
- Responsive design using CSS grid, flexbox, clamp(), and media queries
- Ensure every page works without JavaScript

## Tools & Techniques
- Semantic elements: `main`, `header`, `footer`, `section`, `nav`, `article`
- CSS custom properties for theming
- `clamp()` for fluid typography
- `100svh` with `100vh` fallback for viewport height
- Data URIs for small inline assets (favicon, grain SVG)
- `prefers-reduced-motion` and `prefers-color-scheme` media queries

## Constraints
- No `<div>` soup — every element needs semantic purpose or `aria-hidden`
- No `!important`
- No vendor prefixes except `-webkit-font-smoothing`
- Each HTML file must be self-contained (inline CSS, no external refs)
- Target: every page under 50KB

## Decision Authority
- Can decide: CSS implementation details, HTML structure, performance optimizations
- Needs Jeff: adding JavaScript, adding new files, changing page structure

## Coordination
- Receives designs from **design-lead**
- Reviewed by **accessibility-auditor** and **qa-tester**
- Consulted by **performance-engineer** on weight/speed

## Evaluation
- Valid HTML5 (passes W3C validation)
- All pages under 50KB
- Sub-1s load on 3G
- No console errors
