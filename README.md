# Sri Lakshmi Home Foods

Static marketing site for a home-based tiffin service. Built with plain HTML plus
Bootstrap 5.3 (CDN), with one small CSS theme file and a sprinkle of vanilla JS.
Deployed with GitHub Pages.

**Live site:** <https://vedrockerz-pixel.github.io/IIMB_WEB_DEV_Final/>

## Pages

| File | Purpose |
| --- | --- |
| `index.html` | Home — hero, why choose us, food gallery, call to action |
| `about.html` | Story, mission and what the kitchen stands for |
| `services.html` | Menu with categories, prices and per-dish order buttons |
| `contact.html` | Order enquiry form and direct contact details |
| `thanks.html` | Confirmation page after a successful form submission |
| `404.html` | Custom not-found page for GitHub Pages |
| `style.css` | Custom theme on top of Bootstrap |
| `favicon.svg` | Site icon |

## Before you go live

The site works as-is, but these values are still placeholders:

1. **Form destination email** — in `contact.html`, the form posts to
   `https://formsubmit.co/abcd@gmail.com` and the footer/contact panel show
   `abcd@gmail.com`. Replace every occurrence with the real inbox.
   After changing it, the first submission triggers a one-time FormSubmit
   activation email — click the link in it once.
2. **Phone number** — the placeholder `00000 00000` appears in `contact.html` (call
   link and visible number) and in the footer of every page. Replace the visible text
   and the `tel:0000000000` links with the real number (use a `tel:+91…` link format).
3. **Menu prices** — every price in `services.html` is a sample value and is labelled
   indicative on the page. Update to the real prices.
4. **Copyright year** — the footer says 2026 on every page.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly with `file://` mostly works, but a server is closer to
GitHub Pages (and required for the custom 404 page to resolve).

## Deploying

Commit and push to the `main` branch; GitHub Pages rebuilds automatically in about a
minute. No build step is needed.

## Fixes applied

- Renamed `Contact.html` to `contact.html` so the navigation no longer 404s on
  GitHub Pages (the filesystem is case-sensitive there).
- Loaded Bootstrap's JS bundle on every page, so the mobile hamburger menu works
  on About, Menu and Contact too.
- Consolidated the footer across all pages, with contact links.
- Corrected the `.card-body` flex rule that laid card text out side by side.
- Wired the order flow: menu "Order" buttons pre-fill the contact form via
  `?item=…`, the form validates client-side, and successful submissions redirect
  to `thanks.html`.
- Added per-page titles, meta descriptions, Open Graph/Twitter tags, a favicon and
  a `theme-color`.
- Gave every image accurate `alt` text, explicit dimensions and lazy loading, and
  requested correctly sized Unsplash files.
- Added a dark overlay behind the hero copy for contrast.
- Improved focus styles, added a skip link, `aria-current` on the active nav item
  and `prefers-reduced-motion` support.
- Upgraded Bootstrap 5.3.0 → 5.3.3.
- Added `404.html`, `.gitignore` and this README.
