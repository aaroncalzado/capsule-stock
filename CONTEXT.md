# CapsuleStock Marketing Home Page — Context

## What This Is

Marketing landing page for **CapsuleStock.com**, a vending machine service targeting Seattle property managers and building owners. The site's primary goal is lead generation via a contact form ("Request a Machine").

## Product

CapsuleStock offers modern vending machines for multifamily, commercial, and hospitality properties with a zero-cost, zero-maintenance model. They handle delivery, installation, restocking, and repairs. Locally operated in Seattle, licensed and insured.

**Target customers:** Property managers, building owners, facilities directors, hospitality managers

## Tech Stack

| Layer | Tool |
|---|---|
| Markup | HTML5 (single `index.html`) |
| Styling | Tailwind CSS (CDN) + custom CSS (`styles/globals.css`) |
| Fonts | Satoshi (CDN via cdnfonts.com) |
| Form backend | Web3Forms |
| Images | Unsplash API |
| Deployment | GitHub Pages via GitHub Actions |
| Build step | None — pure static site |

## File Structure

```
index.html              — Entire site (hero, features, locations, contact, footer)
styles/globals.css      — Design tokens + component classes
.github/workflows/      — CI/CD: auto-deploys main to GitHub Pages
CNAME                   — Custom domain: capsulestock.com
package.json            — Metadata only, no dependencies
```

## Architecture Notes

- **Single-page site** — All content lives in `index.html`. Navigation uses anchor links.
- **No JavaScript** — Form submission handled entirely by Web3Forms. No JS framework.
- **No build process** — Tailwind is loaded via CDN, not compiled. Changes deploy as-is.
- **CSS design tokens** — `globals.css` defines CSS custom properties for colors, typography, and spacing. Primary brand color is `#030213` (dark navy).
- **Component classes** — Reusable `.btn`, `.card`, `.location-card` classes in `globals.css` supplement Tailwind utilities.
- **Hover interactions** — Location cards use CSS opacity transitions to swap title text for a benefit line on hover. Images scale to 1.05 on hover.

## Page Sections

1. **Header** — Logo only, no nav links
2. **Hero** — Dark gradient, main headline, two CTAs, decorative SVG pattern
3. **Features** — 6 benefit cards (free install, no contracts, happy tenants, etc.)
4. **Perfect For** — 6 location type cards with Unsplash images (apartments, offices, gyms, student housing, hotels, co-working)
5. **Contact** — Lead gen form (name, email, phone, property name, message) → Web3Forms
6. **Footer** — Company links, services links, email, Instagram

## Deployment

Pushes to `main` trigger `.github/workflows/static.yml`, which deploys the repo to GitHub Pages. Live at `capsulestock.com` (configured via `CNAME`).

## Key Copy

- Headline: "Upgrade Your Building Amenities"
- Subheadline: "Modern vending machines. Zero cost. Zero maintenance. 100% convenience."
- Primary CTA: "Request a Machine" (appears 4× on page)
- Contact email: info@capsulestock.com
