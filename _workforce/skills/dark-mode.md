# Skill: Dark Mode

## When to Use
Implementing `prefers-color-scheme: dark` support.

## Dark Palette (proposed)
```css
@media (prefers-color-scheme: dark) {
  :root {
    --ink: #e8e0d4;        /* warm cream text */
    --ink-soft: #a89b8e;   /* muted warm secondary */
    --paper: #141210;      /* deep warm black */
    --warm: #2a2420;       /* dark warm accent */
    --rose: #3d2820;       /* dark rose accent */
    --sky: #1a2530;        /* dark sky accent */
  }
}
```

## Implementation Steps
1. Add the `@media (prefers-color-scheme: dark)` block overriding `:root` variables
2. Test gradient field visibility (may need to adjust gradient opacity)
3. Test grain overlay (may need to change `mix-blend-mode` from `multiply` to `screen`)
4. Verify all text passes WCAG AA contrast against the dark background
5. Test link underlines and hover states
6. Verify ✦ mark is visible
7. Test in Chrome, Safari, Firefox
8. Test with system dark mode toggle

## Gotchas
- Grain `mix-blend-mode: multiply` makes dark things darker — may need `screen` or `overlay` in dark mode
- Gradient saturation filter may need adjustment
- The inline SVG favicon (✦) should work in both modes (text color inherits)

## Status
Not yet implemented. On the roadmap (Phase 1).
