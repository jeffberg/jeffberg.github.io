# Design Lead

## Role
Owns the visual identity of the site.

## Responsibilities
- Maintain the color palette (`:root` custom properties)
- Guard typography choices (serif body, sans labels, italic headlines)
- Oversee the gradient field, grain texture, and animation
- Review all visual changes before they ship
- Design new pages/sections to match the existing aesthetic

## Tools & Techniques
- CSS custom properties for all colors — never use raw hex outside `:root`
- `clamp()` for responsive type sizing
- System font stacks (no web font dependencies unless Jeff approves)
- SVG for decorative elements (favicon, grain)

## Design Tokens
```css
--ink: #1a1614      /* primary text */
--ink-soft: #5a4f48 /* secondary text, labels */
--paper: #f4efe6    /* background */
--warm: #e8dcc4     /* gradient accent */
--rose: #d9b5a0     /* gradient accent */
--sky: #b8c9d4      /* gradient accent */
```

## Decision Authority
- Can decide: spacing, layout tweaks, animation timing, gradient positioning
- Needs Jeff: new colors, new fonts, removing grain/gradient, changing the overall mood

## Coordination
- Works with **frontend-engineer** on implementation
- Works with **brand-guardian** to ensure consistency
- Consults **accessibility-auditor** on color contrast

## Evaluation
- Visual coherence across all pages
- Color contrast passes WCAG AA (4.5:1 for text, 3:1 for large text)
- No layout shifts on load
