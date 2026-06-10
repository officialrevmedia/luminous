# Luminous Building Maintenance, Website

Production-ready static site for luminousbm.com. No build step, no dependencies. Deployable on GitHub Pages as-is.

## Package contents

| File | Purpose |
|---|---|
| index.html | Full single-page site (SEO, schema, animations, lead form) |
| thanks.html | Form success page (no-JS fallback redirect target) |
| 404.html | Branded not-found page (GitHub Pages serves this automatically) |
| robots.txt | Allows all crawlers, points to sitemap |
| sitemap.xml | Submitted to Google Search Console |
| CNAME | Custom domain binding for GitHub Pages |
| assets/ | Logo mark, favicon set, apple touch icon |

## Deploy to GitHub Pages

1. Create a repo (for example `officialrevmedia/luminousbm`) and push these files to the root of the `main` branch.
2. Repo Settings > Pages > Source: Deploy from a branch > `main` / root. Save.
3. Testing first on `officialrevmedia.github.io/luminousbm/`? Delete the CNAME file temporarily, then restore it when pointing the real domain.

## Custom domain (www.luminousbm.com)

1. Keep the CNAME file in the repo root (already contains `www.luminousbm.com`).
2. At the DNS provider, add: CNAME record, host `www`, value `officialrevmedia.github.io` (adjust to the actual account).
3. For the apex `luminousbm.com`, add A records to GitHub Pages IPs: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
4. In repo Settings > Pages, tick Enforce HTTPS once the certificate is issued (can take up to an hour after DNS propagates).

## Lead form (goes to info@luminousbm.com)

The quote form posts to FormSubmit, which forwards submissions to info@luminousbm.com. No backend or account needed, but note:

- ACTIVATION REQUIRED: the very first submission triggers a confirmation email to info@luminousbm.com. Someone must click the activation link in that email once. Until then, submissions are held.
- Submissions arrive as a formatted table with subject "New Free Quote Request, luminousbm.com".
- Spam protection: honeypot field is enabled. If spam becomes an issue, change `_captcha` from `false` to `true` in index.html.
- JS users stay on the page and see an inline success state; no-JS users are redirected to thanks.html.

## Google crawlability checklist

Already done in this package:
- robots.txt allowing all crawlers + sitemap reference
- sitemap.xml
- `meta robots: index, follow` on index.html (thanks/404 are noindex)
- Canonical URL, Open Graph and Twitter cards
- LocalBusiness (ProfessionalService) + FAQPage JSON-LD structured data
- Single H1, semantic heading hierarchy, descriptive alt text on all images
- Mobile responsive + theme-color (mobile-first indexing ready)

To do after launch (5 minutes):
1. Go to Google Search Console > Add property > Domain or URL prefix for https://www.luminousbm.com
2. Verify (DNS TXT record, or paste the HTML meta tag into the marked comment in index.html `<head>`)
3. Submit sitemap: `https://www.luminousbm.com/sitemap.xml`
4. Request indexing on the homepage URL

Optional boosters: create/claim the Google Business Profile for 91 Skyway Avenue and link the site; the schema markup will reinforce the local pack listing.

## Before launch, verify with client

- Stats used on page: "500+ spaces maintained" and "98% client retention" (illustrative)
- Testimonials are placeholder copy, swap in real client quotes
- Short bios written for Sadaf, Hari and Arash (original site listed names/titles only)
- Wix-hosted image URLs are still used; ideally download and self-host in /assets before Wix is decommissioned
