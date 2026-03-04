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
- `assets/` — images and other static files (add when needed)

The source markdown content for the legal docs lives in `terms_and_conditions.txt` and `simple_privacy_policy.txt` at the repo root.

## Page Conventions

- All pages share the same CSS reset and font stack defined inline (no external stylesheet yet)
- Use the system font stack: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
- Max content width: `680px`, centered with `margin: 0 auto`
- Include `<meta name="viewport" content="width=device-width, initial-scale=1.0">` on every page
