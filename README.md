# Outhbox — Jekyll Site

UK-registered technology company website built with Jekyll, deployed via GitHub Pages.

## Structure

```
outhbox-jekyll/
├── _includes/
│   ├── head.html          # <head> meta, CSS links
│   ├── nav.html           # Shared navbar (all pages)
│   ├── footer.html        # Shared footer (all pages)
│   ├── scripts.html       # Webflow JS scripts
│   └── search_modal.html  # Search overlay
├── _layouts/
│   ├── default.html       # Base layout (head + nav + content + footer + scripts)
│   ├── page.html          # General pages (about, pricing, legal, partners)
│   ├── case-study.html    # Individual case study pages
│   ├── service.html       # Service pages
│   └── customers.html     # Customers index page
├── index.html             # Homepage → outhbox.com/
├── about/index.html       → outhbox.com/about/
├── pricing/index.html     → outhbox.com/pricing/
├── customers/
│   ├── index.html         → outhbox.com/customers/
│   ├── preyesbaskets/index.html
│   ├── yemi-laja/index.html
│   ├── mastercraft-global/index.html
│   └── viaje-musica/index.html
├── services/
│   ├── automation/index.html
│   ├── web-development/index.html
│   ├── cybersecurity/index.html
│   └── software/index.html
├── partners/index.html    → outhbox.com/partners/
├── legal/
│   ├── privacy/index.html
│   ├── terms/index.html
│   └── cookies/index.html
├── _config.yml
├── Gemfile
└── .gitignore
```

## Local Development

```bash
# Install dependencies
bundle install

# Serve locally
bundle exec jekyll serve

# Visit http://localhost:4000
```

## GitHub Pages Deployment

1. Push this repository to GitHub
2. Go to Settings → Pages
3. Set Source to **Deploy from a branch**
4. Select branch: `main`, folder: `/ (root)`
5. Save — GitHub will build and deploy automatically

If using a custom domain (outhbox.com):
1. Add a `CNAME` file to the root with content: `outhbox.com`
2. In your DNS settings, add:
   - A record: `@` → `185.199.108.153` (and 109, 110, 111)
   - CNAME record: `www` → `yourusername.github.io`
3. Enable "Enforce HTTPS" in GitHub Pages settings

## Adding New Pages

Create a folder with an `index.html` inside it:

```
new-page/
└── index.html
```

With front matter at the top:

```yaml
---
layout: page
title: "Page Title"
description: "Meta description for SEO."
---

<!-- Your page HTML content here -->
```

## CSS & Scripts

Stylesheets are loaded from the Webflow CDN (`cdn.prod.website-files.com`).
Scripts (jQuery, Webflow JS) load from Webflow and CloudFront CDNs.
No build step required — all assets are CDN-hosted.
