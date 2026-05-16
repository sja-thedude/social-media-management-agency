# Pulse Social — Agency Website

A modern, multi-page marketing site for a fictional social media management agency. Five real HTML pages with shared CSS/JS, no frameworks, no build step.

## 🔗 Live site

### 👉 **<https://pulse-social-agency.sja-affu765.workers.dev>**

Deployed to Cloudflare Workers (assets-only). Open any page directly:

- 🏠 [Home](https://pulse-social-agency.sja-affu765.workers.dev/)
- 👋 [About](https://pulse-social-agency.sja-affu765.workers.dev/about)
- 🛠️ [Services](https://pulse-social-agency.sja-affu765.workers.dev/services)
- 💼 [Careers](https://pulse-social-agency.sja-affu765.workers.dev/careers)
- 🎨 [Portfolio](https://pulse-social-agency.sja-affu765.workers.dev/portfolio)

## Pages

| Route          | File                | Highlights                                                                |
|----------------|---------------------|---------------------------------------------------------------------------|
| `/`            | `index.html`        | Hero with floating stat cards, logo strip, animated stats, value props, services preview, testimonials, CTA |
| `/about`       | `about.html`        | Story, mission/vision/values, company timeline (2023→2026), 6-person team grid, awards |
| `/services`    | `services.html`     | 6 detailed service cards with feature lists, 4-step process, platforms strip, 3-tier pricing, FAQ accordion |
| `/careers`     | `careers.html`      | Why-work-here perks (9), 5 open positions with salary bands, 4-step hiring process, team testimonials |
| `/portfolio`   | `portfolio.html`    | Filterable 9-card grid (All / IG / TikTok / LinkedIn / Ads), featured case study with metrics, testimonials |

## What's in it

- **Sticky nav** with active-page highlight, mobile hamburger menu
- **Gradient hero** on every page with mesh-light blobs and floating UI cards on home
- **Stat counters** that animate in via IntersectionObserver
- **Hover micro-interactions** on every card, button, and link
- **Pricing tiers** with featured-card emphasis
- **FAQ accordion** using native `<details>` elements
- **Portfolio filters** with JS-driven category toggling
- **Newsletter form** with optimistic UI
- **Footer** with newsletter signup, social icons, sitemap

## Design

- **Palette:** deep navy (`#0a1428` → `#1e3a6f`) primary, coral (`#ff6b4a` → `#ff8b6e`) accent
- **Type:** Inter (body), Poppins (headings) via Google Fonts
- **Motion:** scroll-triggered fade-ins, floating cards, animated stat counters, pulse indicator — all respect `prefers-reduced-motion`

## Responsive

Mobile-first with three breakpoints:
- `≤1024px` — minor footer adjustments
- `≤960px` — hero visual hides; team/services/testimonials/perks/values fold to 2-up; pricing stacks
- `≤720px` — nav collapses to hamburger; everything stacks to 1-up; FAQ and timeline simplify

## Project structure

```
public/
├── index.html          # Home
├── about.html          # About & Team
├── services.html       # Services, process, pricing, FAQ
├── careers.html        # Open roles, perks, hiring process
├── portfolio.html      # Filterable case study grid
└── assets/
    ├── styles.css      # Shared stylesheet (~30 KB)
    └── app.js          # Shared script — nav, reveals, counters, filters
wrangler.toml           # Cloudflare Worker (assets-only)
```

## Local preview

```bash
# Quick: just open a page
open public/index.html

# Better: serve so absolute paths (`/about.html`, `/assets/...`) work
python3 -m http.server -d public 8000
# then visit http://localhost:8000

# Or use wrangler dev
wrangler dev
```

## Deploy

```bash
wrangler deploy
```

Configured in [wrangler.toml](wrangler.toml). Assets-only Worker — no server code, just static files served from `./public`.

## Customizing

- **Brand name / logo:** search for `Pulse Social` and the `.logo-mark` letter
- **Colors:** edit the CSS custom properties in `:root` of `public/assets/styles.css`
- **Copy / team / jobs / portfolio:** all content lives directly in each page's markup — no JSON or templating
- **Contact email:** replace `hello@pulsesocial.example` and `careers@pulsesocial.example`
