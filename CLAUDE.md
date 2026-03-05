# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**spots-mobile-webapp** is a static GitHub Pages site hosting legal disclosures for the Spots mobile app (Google Play Store requirements: Privacy Policy, Terms of Service, etc.).

No build step — files are served directly by GitHub Pages.

## Tech Stack

- Plain HTML, CSS, and JavaScript (no framework)
- Hosted on GitHub Pages from the `main` branch root

## Development

Open any `.html` file directly in a browser, or use a local static server:

```
npx serve .
# or
python3 -m http.server 8080
```

## Structure

- `index.html` — landing page linking to all disclosure documents
- `legal/privacy-policy.html` — Privacy Policy
- `legal/terms-and-conditions.html` — Terms & Conditions
- `legal/dpa/` — signed DPA agreements (PDF)
- `images/icons/` — favicon and app icons (PNG at 16, 32, 48, 96, 180, 192, 512px)
- `manifest.webmanifest` — PWA manifest; references 192px, 512px, and 512px maskable icons
- `configs/browserconfig.xml` — Windows tile config; referenced explicitly by all HTML pages via `msapplication-config`
- `.nojekyll` — disables Jekyll processing on GitHub Pages (required for correct `.webmanifest` MIME type)

The source markdown content for the legal docs lives in `terms_and_conditions.txt` and `simple_privacy_policy.txt` at the repo root.

## Favicon / Icon Notes

Every HTML page includes three `<link rel="icon">` tags: sized 32x32, sized 16x16, and one generic (no `sizes`) as a browser fallback. The generic one must appear **last** so modern browsers prefer the sized versions while older browsers fall back to it.

A `favicon.ico` at the repo root is not yet present. Browsers auto-request `/favicon.ico`; its absence causes a 404 in the network tab and may suppress the tab icon in some browsers. Generate one from `spots_favicon_32x32.png` (e.g. via [favicon.io](https://favicon.io)) and place it at the root when possible.

## Page Conventions

- All pages share the same CSS reset and font stack defined inline (no external stylesheet yet)
- Use the system font stack: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
- Max content width: `680px`, centered with `margin: 0 auto`
- Include `<meta name="viewport" content="width=device-width, initial-scale=1.0">` on every page
