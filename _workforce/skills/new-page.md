# Skill: New Page

## When to Use
Adding a new HTML page to the site (e.g., /about, /work, /us).

## Steps
1. **Create the file** at the root (e.g., `about.html`)
2. **Copy the structure** from `index.html`:
   - Same `<head>` (charset, viewport, robots, title, favicon)
   - Same `:root` custom properties
   - Same `.field` gradient and `.grain` overlay
   - Same `<main>` grid with `.top`, `.center`, `.bottom`
   - Same font stacks, link styles, focus-visible, reduced-motion
3. **Replace the content** in `.center` with the new page's content
4. **Add navigation** if this is the second page:
   - Add a subtle link in the footer of both pages
   - Match the existing label style (sans, 0.78rem, lowercase, letter-spacing)
5. **Test**:
   - Valid HTML5 structure
   - Accessibility checklist passes
   - Looks correct at 375px, 768px, 1440px
   - Reduced-motion disables animation
   - Focus-visible works on all links
6. **Update CLAUDE.md** file map

## Template
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="robots" content="noindex, nofollow, noarchive, nosnippet">
<title>jeff berg — [page name]</title>
<!-- copy favicon, styles, and body structure from index.html -->
</head>
```
