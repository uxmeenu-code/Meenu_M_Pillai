# Portfolio — Deployment Package

This package contains everything needed to deploy the portfolio to GitHub Pages.

## What's in here
- `index.html` — the entire portfolio. Fully self-contained: fonts, images, and the
  UX Design Auditor live tool are all embedded as base64 inside this single file.
  No other assets are required.
- `.nojekyll` — tells GitHub Pages to skip Jekyll processing (safe default for a
  static single-file site; prevents GitHub from mangling any files/folders that
  start with `_`).

## Deploy to your existing repo (uxmeenu-code/Heartbeat)

### Option A — GitHub web UI (simplest)
1. Go to https://github.com/Meenu_M_Pillai
2. Click **Add file → Upload files**
3. Drag in `index.html` and `.nojekyll` (overwrite existing `index.html` if prompted)
4. Commit directly to `main` (or your Pages branch)
5. Go to **Settings → Pages**, confirm the source is `main` branch, `/ (root)`
6. Wait ~1 minute, then visit your Pages URL 

### Option B — Git command line
```bash
git clone https://github.com/uxmeenu-code/Heartbeat.git
cd Heartbeat
# copy index.html and .nojekyll from this package into the repo root, overwriting the old index.html
git add index.html .nojekyll
git commit -m "Update portfolio: UX Design Auditor case study + live tool embed"
git push origin main
```

## Notes
- **File size**: `index.html` is ~43 MB because all fonts/images/the live tool are
  embedded as base64. GitHub's per-file limit is 100 MB, so this is well within
  bounds — but initial page load will be heavier than a typical site. This is a
  known, intentional tradeoff for a fully self-contained single file.
- **Password-protected case studies**: the gate is client-side only (password is
  visible in page source). It's a soft deterrent, not real security.
- **No build step**: this is a static file. Nothing to compile — upload and it works.
