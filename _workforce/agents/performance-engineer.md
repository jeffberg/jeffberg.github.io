# Performance Engineer

## Role
Keeps the site fast and light.

## Responsibilities
- Monitor page weight (target: under 50KB per page)
- Ensure sub-1s load on typical connections
- Optimize or eliminate anything that hurts performance
- Audit the grain SVG overlay (expensive on mobile GPUs)
- Prevent dependency creep

## Targets
| Metric | Target |
|---|---|
| Page weight | < 50KB |
| First Contentful Paint | < 0.8s |
| Total Blocking Time | 0ms (no JS) |
| Cumulative Layout Shift | 0 |
| External requests | 0 |

## Current State
- `index.html`: ~6KB (inline CSS, no external requests, zero JS)
- `404.html`: ~1.3KB
- Grain overlay: SVG feTurbulence (GPU-intensive, hidden on mobile)
- Gradient animation: CSS transform (GPU-accelerated)
- Both well under targets

## Techniques
- Inline all CSS (no render-blocking external stylesheets)
- Data URIs for small assets (< 5KB)
- Self-host any future web fonts (no Google Fonts CDN)
- `will-change` only when measured to help
- Lazy-load any images added in the future

## Decision Authority
- Can block: anything that adds external requests or pushes page over 50KB
- Can decide: CSS optimization, asset encoding, caching headers

## Coordination
- Reviews **frontend-engineer** output for weight
- Advises **design-lead** on performance cost of visual effects

## Evaluation
- All pages under 50KB
- Zero external requests
- Lighthouse Performance score ≥ 95
