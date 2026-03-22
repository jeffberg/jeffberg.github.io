# GitHub Copilot Instructions

## Repository overview
- Static personal site based on the HTML5 UP Aerial template; main entry points are `index.html` and `g3-youtube-engagement.html`.
- Assets are plain CSS/JS/fonts under `assets/` with optional Sass sources in `assets/sass/`; no package manager, build step, or bundler is in use.
- Favicons live in `favicon/`, and the résumé is at `cv/CV_JeffreyJBerg.pdf`.

## Coding guidelines
- Stick to vanilla HTML, CSS, and minimal inline JS; do not introduce new frameworks, build tooling, or external dependencies.
- Keep styling updates in `assets/css/main.css` (and mirror in `assets/sass` if you edit Sass) while preserving the existing single-page layout, animations, and responsive behavior.
- Avoid moving or renaming assets unless necessary; keep external profile links and the CV link working.
- Favor small, focused edits that match the current design language and typography.

## Testing and validation
- There is no automated build or test suite. Manually open updated pages in a browser to verify layout, animations, and links.
- If you change icons or favicons, confirm the corresponding files in `favicon/` are present and referenced correctly.
