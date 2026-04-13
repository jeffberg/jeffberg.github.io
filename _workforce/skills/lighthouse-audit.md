# Skill: Lighthouse Audit (Manual)

## When to Use
Periodic health check on performance and accessibility. No build tools needed.

## Performance Checks
- [ ] Page weight under 50KB (check with `wc -c *.html`)
- [ ] Zero external HTTP requests (no CDN, no fonts, no scripts)
- [ ] Zero JavaScript (unless explicitly added)
- [ ] CSS is inline (no `<link rel="stylesheet">`)
- [ ] Images use data URIs or are lazy-loaded
- [ ] No render-blocking resources

## Accessibility Checks
- [ ] `<html lang="en">` present
- [ ] One `<main>` per page
- [ ] Heading hierarchy is sequential (h1 → h2 → h3)
- [ ] All `<img>` have `alt` attributes
- [ ] Decorative elements have `aria-hidden="true"`
- [ ] Color contrast ≥ 4.5:1 for normal text
- [ ] Color contrast ≥ 3:1 for large text (≥18px bold or ≥24px)
- [ ] `focus-visible` styles on all interactive elements
- [ ] `prefers-reduced-motion` disables animation
- [ ] No keyboard traps (Tab cycles naturally through all focusable elements)

## SEO Checks (inverted — we want to be invisible)
- [ ] `noindex, nofollow, noarchive, nosnippet` on every page
- [ ] `robots.txt` blocks all crawlers
- [ ] No sitemap.xml exists

## How to Run
If you have access to a browser: Lighthouse → run audit.
Otherwise: manually verify each checkbox against the HTML source.
