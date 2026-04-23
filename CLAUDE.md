# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is
Jeff Berg's personal website. A single poetic landing page plus a CV subpage and
hosted PDF papers. Hosted on GitHub Pages, auto-deployed from `main`.
Intentionally minimal, intentionally invisible to search engines.

## Architecture
- **Static HTML, no build step.** What you commit is what gets served — no framework, no bundler, no npm, no CDN.
- **One self-contained HTML file per page.** CSS is inlined inside `<style>` in each file. `cv/index.html` intentionally duplicates the `:root` tokens and font stacks from `index.html` rather than sharing a stylesheet. When design tokens change, update both files.
- **GitHub Pages deploys from `main`.** `.nojekyll` bypasses Jekyll. The `_workforce/` directory is ignored by Pages because of its underscore prefix.
- **Crawler-blocked.** `robots.txt` disallows all user agents, and every HTML page carries `<meta name="robots" content="noindex, nofollow, noarchive, nosnippet">`. Do not relax either without Jeff's approval.

## Commands
There is no build, test runner, or linter. CI enforces the quality bar.

- **Local preview**: open any `*.html` directly, or `python3 -m http.server 8000` from the repo root to exercise relative paths like `/cv/`.
- **CI validation** (`.github/workflows/validate.yml`, runs on push to `main` and on PRs): collects every `*.html` and checks DOCTYPE, closing `</html>`, matching `<head>`/`<body>` counts, required meta tags (charset, viewport, robots), `lang` on `<html>`, `alt` on `<img>`, valid `aria-hidden` values, non-empty `<a>`, and presence of `focus-visible` styles. Pages over **50KB** emit a warning (not a failure). Before pushing, sanity-check these locally with `grep` — CI mirrors them exactly.
- **Deploy**: merge to `main`. Pages publishes in ~60 seconds. To roll back, `git revert` and push.

## Design Language
Current values reflect `index.html` — if a workforce skill doc contradicts the code, the code wins.

- **Core palette**: `--ink #1a1614`, `--ink-soft #5a4f48`, `--paper #f4efe6`, `--warm #e8dcc4`, `--rose #d9b5a0`, `--sky #b8c9d4`
- **Extended palette on index**: `--sage`, `--spruce`, `--celery`, `--ochre`, `--pale-pink`, `--navajo`, `--lavender` — used by the gradient field
- **Typography**: `"Cormorant Garamond", "EB Garamond", Garamond, "Hoefler Text", "Times New Roman", serif` for body; `ui-sans-serif, system-ui, -apple-system, "Helvetica Neue", sans-serif` for labels/footer. No web font loading — rely on system fallbacks.
- **Voice**: lowercase, italic serif headlines, poetic, spare
- **Motion**: 32s `drift` on `.field`, 1.6s `rise` on `.center`. Both must be nullified under `prefers-reduced-motion`.
- **Grain**: inline SVG `feTurbulence` data URI, `opacity: 0.1`, `mix-blend-mode: multiply`. Hidden below 768px for GPU perf and under reduced motion.
- **Favicon**: `✦` inline SVG data URI in `<link rel="icon">`. Reuse across new pages.

## Conventions
- **Never add external dependencies** (no CDN, no Google Fonts, no JS libraries, no npm). Inline SVG data URIs are fine.
- **No JavaScript** unless Jeff explicitly approves. Every page must work with JS disabled.
- **Keep each page under 50KB** (CI warns above this threshold).
- **Use CSS custom properties from `:root`** — no raw hex in rules.
- **Every interactive element needs `:focus-visible` styles.** Decorative elements need `aria-hidden="true"`.
- **Honor `prefers-reduced-motion`** on every page: disable animations and hide the grain.
- **Semantic HTML**: `main`, `header`, `footer`, `section`, `nav`. No `<div>` soup.
- **Commit style** (see `git log`): lowercase, short scope prefix (`cv:`, `poem:`, `fix:`, `redesign:`) followed by a concise description. Branch names like `feature/description`.

## Escalation — Ask Jeff First
- Any edit to the poem in `index.html` (it's Jeff's original writing).
- Removing or weakening `noindex` / `nofollow` / `robots.txt` rules.
- Adding JavaScript, external dependencies, a build step, or a separate stylesheet.
- Removing the `✦` mark or the "a small page" tagline (part of the identity).

## Workforce
`_workforce/` contains agent/skill/roadmap docs that guide development — route work through the orchestrator's decision tree in `_workforce/agents/orchestrator.md`. These are prose references, not executable code. Keep the underscore prefix so Pages ignores the directory.

## File Map
```
index.html              — landing page (poem, gradient field, grain, links)
404.html                — not-found page (same aesthetic, simpler)
cv/index.html           — CV subpage; duplicates design tokens from index.html
papers/*.pdf            — self-hosted publication PDFs linked from the CV
robots.txt              — blocks all crawlers
.nojekyll               — skip Jekyll processing
CLAUDE.md               — this file
_workforce/             — agent definitions, skills, roadmap (ignored by Pages)
.github/workflows/      — validate.yml (HTML/meta/a11y checks on push + PR)
```
