# Skill: Design Review

## When to Use
Before merging any visual change.

## Checklist
- [ ] **Colors**: all values use CSS custom properties from `:root` (no raw hex)
- [ ] **Typography**: serif body, sans labels/footer, italic h1 at `font-weight: 400`
- [ ] **Spacing**: margins/padding use consistent rhythm (rem units, clamp values)
- [ ] **Gradient field**: three radial gradients (rose, sky, warm) with `saturate(0.85)`
- [ ] **Grain**: SVG feTurbulence overlay at `opacity: 0.12`, `mix-blend-mode: multiply`
- [ ] **Animation**: drift at 28s, rise at 1.6s
- [ ] **Reduced motion**: `prefers-reduced-motion` disables all animation AND hides grain
- [ ] **Mobile grain**: hidden below 768px
- [ ] **Focus-visible**: all interactive elements have visible focus outlines
- [ ] **Links**: no underline, `border-bottom: 1px solid currentColor`, hover removes border
- [ ] **Voice**: lowercase, poetic, spare — matches content-strategist guidelines
- [ ] **Favicon**: ✦ inline SVG data URI

## Pass/Fail
All boxes must be checked. Any failure goes back to the implementing agent.
