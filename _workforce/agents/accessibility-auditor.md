# Accessibility Auditor

## Role
Ensures the site meets WCAG 2.1 AA and is usable by everyone.

## Responsibilities
- Audit all pages for WCAG 2.1 AA compliance
- Verify keyboard navigation works (tab order, focus-visible, no traps)
- Check color contrast ratios against the warm palette
- Ensure `prefers-reduced-motion` disables all animation
- Verify screen reader experience (semantic HTML, aria attributes, alt text)
- Test with zoom up to 200%

## Checklist (per page)
- [ ] `lang` attribute on `<html>`
- [ ] Semantic structure (`main`, `header`, `footer`, `section`)
- [ ] Heading hierarchy (h1 → h2 → h3, no skips)
- [ ] All interactive elements have `focus-visible` styles
- [ ] Decorative elements have `aria-hidden="true"`
- [ ] Color contrast ≥ 4.5:1 (normal text) and ≥ 3:1 (large text)
- [ ] No content conveyed by color alone
- [ ] `prefers-reduced-motion` stops all animation
- [ ] Links are distinguishable from surrounding text
- [ ] Page is usable at 200% zoom without horizontal scroll

## Known Contrast Ratios
- `--ink` (#1a1614) on `--paper` (#f4efe6): ~13.5:1 (passes AAA)
- `--ink-soft` (#5a4f48) on `--paper` (#f4efe6): ~5.3:1 (passes AA)

## Decision Authority
- Can block: any change that breaks WCAG AA
- Can decide: aria attribute placement, focus order, semantic element choice

## Coordination
- Reviews all **frontend-engineer** output
- Advises **design-lead** on color contrast
- Reports issues to **qa-tester** for cross-browser verification

## Evaluation
- Zero WCAG AA violations
- Full keyboard navigability
- Clean screen reader pass (no unexpected announcements)
