# Copilot Instructions

## Repository Overview

This is a static personal website (GitHub Pages) for Jeffrey J. Berg, a Doctoral Researcher at New York University. The site is built on the "Aerial" template from HTML5 UP and consists of plain HTML, CSS (with Sass sources), and JavaScript — no build system or package manager is used.

## Repository Structure

- `index.html` — Main landing page
- `g3-youtube-engagement.html` — Secondary page for G3 & YouTube engagement content
- `assets/` — CSS, JavaScript, fonts, and Sass source files
- `cv/` — PDF CV file
- `favicon/` — Favicon images in various sizes
- `LICENSE.txt` — CCA 3.0 license from HTML5 UP
- `README.txt` — Template documentation from HTML5 UP

## Development Guidelines

- **No build step required.** All changes to HTML and CSS are made directly; the site is served as-is by GitHub Pages.
- **Sass sources** are in `assets/sass/`. If you modify styles, prefer editing the Sass source files and regenerating `assets/css/main.css`, but direct CSS edits are acceptable for small changes.
- **No JavaScript framework** is used. Keep JS minimal and vanilla.
- **Maintain accessibility** — use semantic HTML elements and meaningful link labels.
- **Do not introduce external dependencies** (npm packages, CDN scripts, etc.) without a compelling reason.
- **Keep the single-page aesthetic** — the site intentionally uses a minimal, fullscreen landing page design.

## Coding Style

- Use tabs for indentation in HTML files (consistent with existing code).
- Keep CSS class names consistent with the existing HTML5 UP template conventions.
- Prefer relative URLs for internal links (e.g., `/cv/CV_JeffreyJBerg.pdf`).

## Testing

There is no automated test suite. To verify changes:
1. Open the HTML files directly in a browser or use a local static file server (e.g., `python3 -m http.server`).
2. Confirm the page renders correctly on desktop and mobile viewports.
3. Check that all navigation links resolve correctly.
