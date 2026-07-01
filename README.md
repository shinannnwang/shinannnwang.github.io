# shinanwang.com

Personal academic website — static HTML/CSS, no build step. Same structure as a
GitHub Pages + custom-domain setup (like the reference site).

## Files
- `index.html` — home / bio
- `research.html` — papers
- `cv.html` — embedded CV PDF viewer
- `assets/site.css` — all styling (light/dark theme, Northwestern purple accent)
- `assets/portrait.svg` — **placeholder** headshot (initials). Replace with a real photo.
- `assets/favicon.svg` — favicon
- `CNAME` — tells GitHub Pages to serve the custom domain `shinanwang.com`

## Before you publish — things to fill in (search for `TODO` in the .html files)
1. **Photo** — replace `assets/portrait.svg` with a square photo. Either name it
   `portrait.svg`, or add `portrait.jpg` and change the `<img src>` in `index.html`.
2. **CV** — drop your CV in the root as `shinan-wang_cv.pdf`.
3. **Paper statuses** — verify the venue/status lines in `research.html`
   (I marked the remote-work paper "Forthcoming at ASQ" — confirm and adjust).
4. **LinkedIn** — set the real URL in `index.html`, or delete that link block.
5. **Bio** — optional background paragraph + job-market line are stubbed as comments.

## Preview locally
```bash
cd shinanwang.com
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy on GitHub Pages (same host as the reference site)
1. Create a GitHub repo (any name, e.g. `shinanwang.com`).
2. Push these files to the `main` branch:
   ```bash
   cd shinanwang.com
   git init && git add . && git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / `/ (root)`.
4. Under **Custom domain**, enter `shinanwang.com` (the `CNAME` file already sets this).
5. At your domain registrar, point DNS to GitHub Pages:
   - Four `A` records for the apex `@`: `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - (Optional) `CNAME` record for `www` → `<you>.github.io`
6. Wait for DNS to propagate, then enable **Enforce HTTPS** in the Pages settings.
