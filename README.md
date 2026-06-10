# dovrin-site

Marketing site for **Dovrin** ("the trust layer between AI and your ERP"). **Prototype / test run** —
served via GitHub Pages. This repo is intentionally separate from the (private) product repo; it
contains only the public page, no product IP.

- **Live (Pages):** https://esimmer12.github.io/dovrin-site/
- **Status:** prototype. `index.html` carries `<meta name="robots" content="noindex">` so search
  engines stay off it until real launch.
- **Source of truth:** edited as `site/index.html` in the product repo, copied here to deploy.

## Go-live runbook — pointing dovrin.com (Namecheap) here

Do this only when ready (content final + trademark filing in):

1. **In this repo:** add a file named `CNAME` (no extension) containing exactly:
   ```
   dovrin.com
   ```
   and **remove the `noindex` meta tag** from `index.html`. Commit + push.
2. **In Namecheap** (Domain List → dovrin.com → Advanced DNS), set:
   - `A` record · Host `@` · `185.199.108.153`
   - `A` record · Host `@` · `185.199.109.153`
   - `A` record · Host `@` · `185.199.110.153`
   - `A` record · Host `@` · `185.199.111.153`
   - `CNAME` record · Host `www` · `esimmer12.github.io.`
   (Delete Namecheap's default parking/URL-redirect records.)
3. **On GitHub:** repo → Settings → Pages → Custom domain = `dovrin.com` → save, then tick
   **Enforce HTTPS** once the certificate provisions (can take up to ~24h after DNS propagates).
4. Verify `https://dovrin.com` and `https://www.dovrin.com` both load with the padlock.
