# vivekreddy049.github.io

Personal site built with [Hugo](https://gohugo.io/) and the
[PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

- **Sections:** About, Projects (with demo/source links), Contact, Search
- **Config:** `hugo.toml`
- **Content:** `content/` — edit `about.md`, `contact.md`, and files under `projects/`
- **Theme:** `themes/PaperMod` (git submodule)

## Local preview

```bash
hugo server
```

Then open http://localhost:1313/.

## How it deploys

The **built** site lives on the `gh-pages` branch, which GitHub Pages serves.
This `main` branch holds the Hugo **source**.

To rebuild and publish after editing content:

```bash
hugo --gc --minify
cd public && touch .nojekyll
git init && git checkout -b gh-pages
git add -A && git commit -m "Deploy"
git push -f https://github.com/vivekreddy049/vivekreddy049.github.io gh-pages:gh-pages
```

### Optional: automatic deploys with GitHub Actions

A ready-made workflow is in `deploy-hugo-actions.yml`. To enable push-to-deploy:

1. Move it to `.github/workflows/hugo.yml` (do this via the GitHub web UI, or
   after granting your local token the `workflow` scope: `gh auth refresh -s workflow`).
2. In **Settings → Pages → Build and deployment**, set **Source** to **GitHub Actions**.

After that, every push to `main` rebuilds and deploys automatically, and the
`gh-pages` branch is no longer needed.

## Projects / demos

Each project lives in `content/projects/*.md`. Replace the `#` placeholder in the
`[Live demo →](#)` line with the real demo URL, and update the `[Source →]` link.
