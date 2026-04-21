# buckdancer.top

Personal site — terminal aesthetic. Plain HTML, no build step.

## Local preview

Just open `index.html` in a browser. That's it.

## Deploy to GitHub Pages (`<username>.github.io`)

### Option A — root user site (recommended)

1. Create a new public repo named **exactly** `<your-github-username>.github.io`
   (e.g. `buckdancer.github.io`).
2. Drop `index.html` into the repo root. Commit & push to `main`.
   ```bash
   git init
   git add index.html
   git commit -m "init site"
   git branch -M main
   git remote add origin git@github.com:<username>/<username>.github.io.git
   git push -u origin main
   ```
3. GitHub serves it automatically at `https://<username>.github.io/` within ~1 min.
   No Pages config needed for repos named `<username>.github.io`.

### Option B — project site under an existing repo

1. Push `index.html` to a repo, e.g. on a `main` branch.
2. Repo → **Settings** → **Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → Save.
3. Site goes live at `https://<username>.github.io/<repo-name>/`.

### Custom domain (`buckdancer.top`)

1. Add a file named `CNAME` to the repo root containing one line:
   ```
   buckdancer.top
   ```
2. At your DNS provider (where you bought `buckdancer.top`), add:
   - **A records** for the apex `@` pointing to these four IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **CNAME** for `www` → `<username>.github.io`
3. Repo → **Settings** → **Pages** → Custom domain: `buckdancer.top` → Save → enable **Enforce HTTPS** once the cert provisions (10–30 min).

## Editing

Everything is inline in `index.html` — HTML, CSS, and a ~15‑line script.

Common edits:
- **Content** — search for the `<div class="main">` block; all copy lives there.
- **Colors** — top of `<style>`, the `:root` custom properties.
- **Links** — `<nav class="side">` has github / rss / email anchors.
- **Meta / title** — `<title>` and the `description` meta at the top of `<head>`.

## Notes

- Loads JetBrains Mono from Google Fonts. If you want 100% offline / no‑tracker, download the font and self‑host.
- No analytics by default. Add what you like.
- No build, no framework, no package.json — intentional.
