# macrotool.app

Static website for **macrotool** — Google Workspace add-ons by Raul Araw.
Plain HTML/CSS/JS, no build step. Hosted free on GitHub Pages with the custom domain `macrotool.app`.

## Pages

| URL | File | Use it for |
| --- | --- | --- |
| `/` | `index.html` | Home, app list, developer profile |
| `/apps/tab-transfer/` | `apps/tab-transfer/index.html` | Tab Transfer product page (Marketplace "Application URL") |
| `/apps/tab-transfer/help/` | `apps/tab-transfer/help/index.html` | Setup guide (Marketplace "Help URL") |
| `/privacy/` | `privacy/index.html` | Privacy Policy (Marketplace + OAuth consent screen) |
| `/terms/` | `terms/index.html` | Terms of Service (Marketplace + OAuth consent screen) |
| `/support/` | `support/index.html` | Support page (Marketplace "Support URL") |

## Go live on GitHub Pages (free)

1. Repo **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main` / `(root)`.
2. Custom domain: `macrotool.app` (already set by the `CNAME` file). Tick **Enforce HTTPS** once the certificate is issued.
3. Namecheap → Domain List → macrotool.app → **Advanced DNS**. Remove the default parking records, then add:

   | Type | Host | Value |
   | --- | --- | --- |
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | raularaw.github.io. |

4. Email: Namecheap → **Redirect Email** → forward `support@macrotool.app` to your Gmail (free).
5. Google Search Console → add `macrotool.app` as a Domain property → add the TXT record it gives you in Namecheap. Required to list `macrotool.app` as an authorised domain on the OAuth consent screen.

`.app` domains are HTTPS-only, so the site won't load until GitHub has issued the certificate (usually under an hour after DNS resolves).

## Adding a new app

Copy `apps/tab-transfer/` to `apps/<new-app>/`, edit the copy, and add a card in the `#apps` section of `index.html`, plus a section in `privacy/index.html`.

When Tab Transfer's Marketplace listing is live, replace the "Coming soon to Google Workspace Marketplace" tag in `apps/tab-transfer/index.html` with an install button linking to the listing.
