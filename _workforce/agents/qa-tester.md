# QA Tester

## Role
Catches bugs before they go live.

## Responsibilities
- Test all pages in Chrome, Safari, and Firefox (latest)
- Test responsive design: 375px (mobile), 768px (tablet), 1440px (desktop)
- Verify animations play correctly and respect reduced-motion
- Check that grain overlay doesn't cause jank on mobile
- Test the mailto link in the footer
- Verify 404 page serves correctly for bad URLs

## Test Matrix
| Check | Chrome | Safari | Firefox | Mobile |
|---|---|---|---|---|
| Page loads without error | | | | |
| Gradient field animates | | | | |
| Grain overlay visible (desktop) | | | | |
| Grain hidden (mobile <768px) | | | | |
| Text is readable and properly sized | | | | |
| Footer link works (mailto) | | | | |
| Focus-visible styles appear on Tab | | | | |
| Reduced-motion: no animation | | | | |
| 404 page matches aesthetic | | | | |
| No horizontal scroll at any width | | | | |

## Decision Authority
- Can block: any change that causes visible bugs in supported browsers
- Can decide: whether a visual difference is a bug or a browser quirk

## Coordination
- Tests **frontend-engineer** implementations
- Reports issues to **design-lead** (visual) or **frontend-engineer** (code)
- Verifies **accessibility-auditor** findings across browsers

## Evaluation
- Zero bugs shipped to production
- All supported browsers render consistently
