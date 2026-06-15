# PayTDS Online

Static marketing website for TDS return filing and CA services. Built with plain HTML, CSS and JavaScript — no build step. Deployed on GitHub Pages at `paytdsonline.com`.

## Structure

```
.
├── index.html            # Single-page site (all sections)
├── CNAME                 # Custom domain (paytdsonline.com)
├── .nojekyll             # Disable Jekyll processing
├── robots.txt
├── sitemap.xml
└── assets/
    ├── css/style.css     # Design system + responsive layout
    ├── js/main.js        # Nav toggle, scroll reveal, FAQ accordion
    └── img/              # logo, favicon, hero, og-image (SVG)
```

## Contact CTAs

- Call: `tel:+919818426375`
- WhatsApp: `https://wa.me/919818426375`

To change the number, find/replace `919818426375` (links) and `9818426375` (display text) across `index.html`.

## Run locally

Open `index.html` directly, or serve it:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Push to the `main` branch (root contains `index.html`).

```bash
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

2. Repo **Settings → Pages → Build and deployment**: Source = **Deploy from a branch**, Branch = `main`, Folder = `/ (root)`.
3. Under **Custom domain**, enter `paytdsonline.com` (this keeps the `CNAME` file in sync).
4. Configure DNS at your domain registrar:

   Apex domain `paytdsonline.com` — 4 `A` records:

   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   `www` subdomain — one `CNAME` record:

   ```
   www  →  <user>.github.io
   ```

5. Wait for DNS to propagate, then enable **Enforce HTTPS** in Settings → Pages.

## Notes

- No backend; leads come through WhatsApp and call.
- Images are SVG; replace `assets/img/*.svg` with branded assets when ready.
