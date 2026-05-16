# Pulse Social — Agency Website

A single-file, dependency-free marketing site for a fictional social media management agency. Built as one `index.html` with embedded CSS and vanilla JS — no build step, no frameworks.

## Preview

Open the file in a browser:

```bash
open index.html
```

Or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## What's inside

- **5 sections** with sticky-nav anchor routing: Home, About, Services, Careers, Portfolio
- **Hero** with animated stat cards and a "Book a Call" CTA
- **Quick stats bar** — 50+ Clients · 1M+ Reach · 3 Yrs
- **About / Team** with mission statement and 3 team cards (placeholder avatars + social icons)
- **Services** — 6-card grid (Management, Content, Paid Ads, Strategy, Influencer, Analytics) with hover lift
- **Careers** — 3 sample job listings (Coordinator, Content Creator, Designer) with `mailto:` apply CTAs
- **Portfolio** — 6 case-study cards with hover overlay
- **CTA banner + footer** with quick links, social icons, and contact email

## Design

- **Palette:** deep navy primary, coral/orange accent, white text
- **Type:** Inter (body), Poppins (headings) via Google Fonts
- **Style:** clean, modern agency vibe — bold type, subtle gradients, soft shadows, smooth hover transitions
- **Motion:** smooth scroll between sections, IntersectionObserver fade-ins on scroll, animated pulse dot in the hero eyebrow
- **Accessibility:** semantic landmarks, ARIA labels on icon buttons, respects `prefers-reduced-motion`

## Responsive

Mobile-first layout with breakpoints at 720px and 960px. Mobile nav collapses into a hamburger menu; multi-column grids fold to 2-up and then 1-up.

## Stack

- Single `index.html` file
- Embedded `<style>` and `<script>` — no external CSS/JS dependencies
- Only network call is the Google Fonts stylesheet

## Customizing

- **Brand name / logo:** search for `Pulse Social` and the `.logo-mark` letter
- **Colors:** edit the CSS custom properties in `:root` (`--navy-900`, `--coral`, etc.)
- **Copy / team / jobs / portfolio:** all content lives directly in the markup — no JSON or templating
- **Contact email:** replace `hello@pulsesocial.example` and `careers@pulsesocial.example`
