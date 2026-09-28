# Bilva — website redesign mockup

Static HTML/CSS/JS mockup for the new bilva.us. No build step, no dependencies.
Structure and sections follow the infoservices.com reference; colors, logo and
copy are Bilva's.

## Run locally

```bash
cd ~/dev/bilva && python3 -m http.server 8765
```

Then open http://127.0.0.1:8765/. Opening the `.html` files directly with
`file://` also works in most browsers.

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home: hero, stats, four capability pillars + 11 service cards, platform tabs (Gen AI / Salesforce / SAP / ServiceNow), industries, case studies, values, process, testimonials, insights, contact |
| `services.html` | Capabilities hub. Every service has an anchor (`#cloud-and-hybrid`, `#crm-development`, …) |
| `service-artificial-intelligence.html` | Service detail template with sticky sidebar. Duplicate this file for the other ten services |
| `industries.html` | Six industries with the real copy from the current site |
| `about.html` | Vision, mission, values, stats, leadership placeholders, partners |
| `contact.html` | Discovery-call form and contact details |
| `design-template.html` | Design system: three themes, palette, type, buttons, cards, forms, icons, logo usage, tokens |

Shared header, footer, icon set and theme switcher live in `assets/js/main.js`.
All styling is in `assets/css/styles.css`.

## Themes

Three dark-mode color themes share one layout. Switch with the floating pill
(bottom right), with `?theme=gold|blue|multi` in the URL, or by setting
`data-theme` on `<html>`. The choice is remembered in `localStorage`.

| Theme | Accent | Use when |
|-------|--------|----------|
| `gold` (default) | #D9AE4E, matches the leaf-mark logo | Premium, trust-and-heritage tone |
| `blue` | #4F8DFF | Corporate, closest to the infoservices.com reference |
| `multi` | cyan → violet → pink → amber gradient | Energetic, AI-forward |

To make one theme permanent, delete the other two blocks from the top of
`styles.css` and remove `.theme-switch` from `main.js`.

## Before launch

- **Copy marked as draft.** Service descriptions, case studies, testimonials,
  insights and the leadership cards are written or placeholder copy. Real text
  from bilva.us was kept verbatim for the tagline, About (vision, mission,
  values) and Industries.
- **Stats.** "5+ years" and "110+ reviews" come from the current site. "6
  industries" and "4 platforms" are derived; confirm or change in `index.html`
  and `about.html`.
- **Address.** The old site's footer address was template text, so the mockup
  shows "address to be confirmed". Phone and email are the real ones.
- **Photos.** All images are Unsplash (royalty-free) placeholders. See
  `CREDITS.md`. Replace with brand photography before launch.
- **Logo.** `assets/img/logo.png` is the original 168×170 PNG from bilva.us.
  Ask for or recreate an SVG for crisp rendering at large sizes.
- **Forms.** Both forms are mockups (`data-demo`). Wire them to a CRM, email
  service or serverless function.
- **Social links, Privacy, Terms** point to `#`.
- **Fonts** load from Google Fonts (Sora + Inter). Self-host if needed.
