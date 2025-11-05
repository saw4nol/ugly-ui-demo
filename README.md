# Ugly UI Demo — Static site + CI

This repository contains:

- A tiny static site (`index.html`, `styles.css`, `script.js`) showcasing an intentionally bad UI.
- An ESLint setup that enforces semicolons and other basic rules.
- A GitHub Actions workflow that lints the project and deploys to GitHub Pages (to `gh-pages`) when `main` receives a push and lint passes.

## How to create & publish this repo (commands)

1. Create repo locally and push to GitHub:

```bash
mkdir my-static-site
cd my-static-site
# copy files into the folder (from this doc)

git init
git add .
git commit -m "Initial commit: static site + CI"
# create repo on GitHub (via web or gh cli). Example with gh cli:
# gh repo create YOUR_USERNAME/ugly-ui-demo --public --source=. --remote=origin --push
```

2. After pushing, the GitHub Actions workflow will run on push to `main`. It will fail at the lint step because `script.js` has a missing semicolon.

3. Fix the lint error by adding a semicolon to `script.js` (line with `const greeting...`) or editing `.eslintrc.json` (not recommended). Commit and push — the workflow should then pass and the deploy job will publish to the `gh-pages` branch.

4. In your repository's Settings > Pages, choose the `gh-pages` branch as the source (if not automatic). The site will then be visible as `https://YOUR_USERNAME.github.io/ugly-ui-demo/`.
