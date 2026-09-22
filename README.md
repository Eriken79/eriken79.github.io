# Pinterest domain-verification test site

Minimal static site to satisfy Pinterest's "Claim website" step for catalogs.

## Deploy to GitHub Pages

1. Create a new **public** repo (name doesn't matter, e.g. `pin-verify-test`).
2. Push this folder's contents to the repo root:
   ```
   cd pinterest-verify-site
   git init
   git add .
   git commit -m "init"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root)**.
4. Your site will be live at `https://<you>.github.io/<repo>/` within a minute or two.

## Claiming it in Pinterest

Pinterest offers two verification methods — use whichever it defaults to:

**Method 1: Meta tag**
Paste the `<meta name="p:domain_verify" content="...">` tag Pinterest gives you
into `index.html` where it says `<!-- PINTEREST_VERIFY_META_TAG_HERE -->`,
then commit and push. Wait for the Pages redeploy, then click "Verify" in Pinterest.

**Method 2: HTML file upload**
If Pinterest instead gives you a file to upload (e.g. `pinterest-XXXX.html`
with specific content), just add that exact file to this folder's root
(same level as `index.html`), commit, push, and click "Verify".

## Notes

- No custom domain or purchase needed — the `github.io` subdomain is a
  fully valid public domain for Pinterest's verification purposes.
- Since you're feeding catalog data via Google Sheets or local file upload,
  you don't need this site to host anything beyond the verification tag/file
  itself — it can stay this bare.
