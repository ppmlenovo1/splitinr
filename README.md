# SplitINR — Permanent Deploy Package (v1.1 with Edit Expense)

Static app, no build step. `index.html` is the whole site.

## Contents
```
splitinr-deploy/
  index.html                   ← the app (edit-expense enabled)
  vercel.json                  ← Vercel static config
  netlify.toml                 ← Netlify static config (publish = ".")
  package.json                 ← `npm start` helper
  .github/workflows/pages.yml ← GitHub Pages auto-deploy on push to main
```

## Option A — GitHub + Vercel (1 click, recommended)
1. Create a new GitHub repo (e.g. `splitinr`) and upload the contents of this zip.
2. Go to https://vercel.com/new → Import the repo → Deploy (no settings to change).
3. You get `https://splitinr-xxx.vercel.app`. Free HTTPS, permanent.

## Option B — Netlify Drop (no account setup, 30 seconds)
1. Go to https://app.netlify.com/drop
2. Drag `index.html` (or the unzipped folder) onto the page.
3. You get `https://your-name.netlify.app`. Free HTTPS, permanent.

## Option C — GitHub Pages (free, stays in GitHub)
1. Push this folder to a repo's `main` branch.
2. Repo → Settings → Pages → Source: **GitHub Actions**.
3. The included workflow auto-deploys. URL: `https://<user>.github.io/<repo>/`.

## Option D — Any static host
Upload `index.html` to Cloudflare Pages, Render Static, Surge (`npx surge .`), or shared hosting. No server code needed.

## Verify after deploy
- Open the URL → Dashboard loads with demo Goa Trip data
- + Add Expense → All expenses → **Edit** a row → Update expense → balances change
- Check `Settle Up` → UPI links look like `upi://pay?pa=...&am=...&cu=INR`
