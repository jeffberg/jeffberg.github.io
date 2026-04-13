# Skill: Deploy

## When to Use
Shipping changes to the live site.

## Steps
1. **Branch**: create or switch to a feature branch
   ```
   git checkout -b feature/description
   ```
2. **Commit**: stage specific files, write a clear message
   ```
   git add index.html 404.html
   git commit -m "description of what changed and why"
   ```
3. **Push**: push the branch
   ```
   git push -u origin feature/description
   ```
4. **PR**: create a pull request targeting `main`
   - Title: short, descriptive
   - Body: what changed, why, what to test
5. **Review**: CI validates HTML structure, meta tags, accessibility basics
6. **Merge**: squash merge to `main`
7. **Deploy**: GitHub Pages auto-deploys from `main` within ~60 seconds

## Rollback
If something breaks:
```
git revert HEAD
git push origin main
```
GitHub Pages will redeploy with the reverted commit.

## Notes
- `.nojekyll` is present — GitHub Pages skips Jekyll processing
- No build step — what you commit is what gets served
- The `_workforce/` directory is ignored by Pages (underscore prefix)
