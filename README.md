# Eniola Ojo Segun — Portfolio

My personal site: a single HTML file with a planetary theme, built to show five-plus
years of production mobile engineering — and where that work is pointed next.

**Live:** <https://lucky-dream-559a.eniolaojo701.workers.dev/>

---

## About

I'm a senior mobile engineer (Flutter, Swift, real-time systems, security,
performance on constrained hardware) with a biomedical technology background, moving
toward health technology, medical imaging and applied AI.

The site makes one argument: health is the direction, not a filter. If a product has
a real problem behind it, the domain doesn't matter and the engineering standard
doesn't change.

## What's on it

| Section | Contents |
| --- | --- |
| **Hero** | Positioning, plus a ringed planet that reacts to the pointer |
| **01 — Trajectory** | Biomedical technology → mobile → health and applied AI |
| **02 — Selected work** | PingTop, Mentra, SchoolDock with live App Store and Google Play links, plus internal delivery and fintech-security work |
| **03 — Toolkit** | Seven groups: mobile, native interop, architecture, data and APIs, performance and release, design and AI, working with teams |
| **04 — Focus** | Medical imaging at the point of care, wearables and sensor data, getting models out of the notebook |
| **05 — Contact** | Email, LinkedIn, GitHub, Medium, downloadable CV |

## Highlights

- **One file.** All markup, styles and scripts live in `index.html`. No build step,
  no framework, no package manager.
- **Planetary visuals** drawn from scratch: an inline SVG ringed planet with two
  orbiting moons, a canvas starfield, a scroll-progress line and reveal-on-scroll
  animations.
- **Responsive from 280px to 1440px** with no horizontal overflow — including a
  hamburger menu on phones and a no-JavaScript fallback that shows the links.
- **Accessible.** Lighthouse 100 accessibility, visible focus states, 44px menu
  button, 55px menu rows, and full `prefers-reduced-motion` support.
- **The résumé is part of the site**, served from the same origin at
  `/Eniola-Ojo-Segun-CV.pdf`.

## Tech

Plain HTML, CSS and JavaScript. Google Fonts (Space Grotesk + Inter) are the only
external requests. Deployed as static assets on Cloudflare Workers.

```
personal-site/
├── index.html                  everything: markup, styles, scripts
├── Eniola-Ojo-Segun-CV.pdf     résumé
├── robots.txt                  allow all crawlers
└── README.md
```

## Run locally

```bash
python3 -m http.server 4173
# open http://127.0.0.1:4173
```

Opening `index.html` directly works too, but serve it over HTTP if you want the
Lighthouse SEO score to be meaningful — `robots.txt` can't be fetched from `file://`.

## Deploy

Any static host works. This runs on **Cloudflare Workers**:

1. <https://dash.cloudflare.com> → **Workers & Pages** → **Create**.
2. Upload the project folder.
3. Deploy.

Or from the terminal with `wrangler`:

```bash
npx wrangler deploy
```

**Custom domain:** Worker → **Settings → Domains & Routes → Add → Custom domain**.
TLS is issued automatically.

## Editing

Everything is in `index.html`, top to bottom: one `<style>` block, the markup inside
`<main>`, one `<script>` at the end.

| To change | Look for |
| --- | --- |
| Work cards | `<section id="work">` — each card is `<article class="card">` |
| Toolkit | `<section id="skills">` — each card is a `<ul class="tags">` |
| Focus | `<section id="focus">` |
| Contact links | `<section id="contact">` |
| Résumé | replace `Eniola-Ojo-Segun-CV.pdf`, keep the filename |
| Search metadata | the `application/ld+json` block in `<head>` |

The delivery and fintech-security cards are marked **Internal** because there's no
public link for them.

## Quality checks

| Check | Result |
| --- | --- |
| Lighthouse | 100 accessibility · 100 best practices · 100 SEO |
| Horizontal overflow | None, 280px → 1440px |
| External requests | Google Fonts only |

| Viewport | Layout |
| --- | --- |
| 941px+ | Two-column hero, inline nav, three-column toolkit |
| 721–940px | Hero stacks, inline nav, toolkit drops to two columns below 900px |
| 621–720px | Hamburger menu, two-column toolkit |
| ≤620px | Single-column toolkit |
| ≤420px | Brand shows the "EO" mark only |

## Contact

- Email: <Eniolaojo701@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/ojo-eniola-6a5590226/>
- GitHub: <https://github.com/enny007>
- Medium: <https://medium.com/@eniolaojo701>
