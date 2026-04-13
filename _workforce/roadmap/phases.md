# Development Phases

## Phase 0 — A Small Page (DONE)
Single poetic landing page. Warm paper palette, drifting gradient, grain texture,
italic serif typography. Jeff's poem as centerpiece. Matching 404 page.
Accessibility fixes applied. Intentionally invisible to search engines.

## Phase 1 — Polish
- Dark mode (`prefers-color-scheme: dark`)
- Open Graph meta tags (so shared links preview nicely)
- Favicon refinement (custom SVG or small PNG?)
- Self-hosted web font (Cormorant Garamond) for consistent rendering

## Phase 2 — A Second Page
- Add `/about`, `/work`, or `/us` — whichever Jeff wants first
- Minimal navigation (subtle footer link between pages)
- Same aesthetic, different content
- Consider: is this a page about Jeff, about the work, or about the people?

## Phase 3 — A Quiet Journal
- Micro-notes or journal entries
- Could be a single page with dated entries (simplest)
- Or individual HTML files with a lightweight index
- No CMS — just HTML files committed to the repo
- RSS feed for anyone who wants to follow along

## Phase 4 — Found (When Ready)
- Remove `noindex`/`nofollow` when Jeff decides to be visible
- Enable privacy-respecting analytics (Plausible or Cabin)
- Add JSON-LD structured data (Person schema)
- Custom domain setup (if Jeff owns one)
- Sitemap.xml

## Phase 5 — Art
- Generative or interactive art element
- Canvas or SVG — something that responds to the viewer
- Could be: particle system, generative typography, ambient visuals
- Must honor reduced-motion
- Must not add significant page weight
