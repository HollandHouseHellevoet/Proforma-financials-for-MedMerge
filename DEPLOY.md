# Deploying to Netlify

This repo is configured to deploy to Netlify as a static site using **docsify** — the markdown renders client-side, so there's no build step. CSVs are downloadable directly.

## One-time setup (in the Netlify dashboard)

1. **Log in to Netlify** → "Add new site" → "Import an existing project"
2. **Connect to GitHub** and pick `HollandHouseHellevoet/proforma-financials-for-medmerge`
3. **Branch to deploy:** the branch you want public (e.g. `main`, or `claude/medmerge-captive-proforma-jCcEG` while reviewing)
4. **Build settings** (auto-detected from `netlify.toml`):
   - Build command: (none — placeholder echo)
   - Publish directory: `.`
5. Click **Deploy site**

That's it. Netlify will publish the site at a `*.netlify.app` URL within ~30 seconds.

## Recommended: gate access (since this contains sensitive financial detail)

Captive proformas are confidential. In the Netlify dashboard, after deploy:

- **Site settings → Visitor access → Site protection** → enable **Site password** (free tier) or **Single sign-on / Identity** (paid tier) for per-user access
- Or restrict by **Role-based access control** if you connect to your IdP
- Optionally lock down to a custom domain (e.g. `proforma.medmerge.com`) under **Domain management**

## Local preview

```bash
# Option A: any static file server
npx serve .

# Option B: docsify-cli
npm i -g docsify-cli
docsify serve .
```

Then visit http://localhost:3000.

## What gets served

| File | Role |
|---|---|
| `index.html` | Docsify entrypoint; loads markdown client-side |
| `README.md` | Homepage (executive summary) |
| `_coverpage.md` | Splash page with headline numbers |
| `_sidebar.md` | Navigation |
| `proforma.md` | Full proforma document |
| `assumptions.md` | Assumptions log |
| `data/*.csv` | Source data — served as downloadable CSV (per `netlify.toml`) |
| `netlify.toml` | Netlify build config + security headers + CSV content-type |

## Updating the site

Push to the deployed branch. Netlify auto-rebuilds within seconds. No build cache to clear.
