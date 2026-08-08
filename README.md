# cybershare.dev

Fixed-price websites for local business — restaurants, auto shops, and everything on Main Street. Built with [Astro](https://astro.build), deployed serverless on Vercel.

Live site: https://cybershare.dev · Repo: https://github.com/dustindog101/cybershare.dev

## What this is

A single-page marketing site selling a local-biz web design service, written in plain English for owners who may be older or non-native speakers: short sentences, no em dashes, no prices published (price comes after a call), and a "why you need a website" pitch with honest, sourced stats. It features a fictional example client ("Harbor Kitchen") and real DMV businesses as "local places we build for" (see docs for the honesty guardrails).

## Docs

| Doc | What's inside |
|---|---|
| [docs/DECISIONS.md](docs/DECISIONS.md) | Architecture & copy decisions, each with why (and nothing to supersede them) |
| [docs/RESEARCH.md](docs/RESEARCH.md) | Competitor analysis, segment selection, business spotlight data & pricing evidence |
| [docs/CONTENT.md](docs/CONTENT.md) | Voice rules, per-section rules, numbers registry (single source of truth for prices/facts) |

## Stack

- Astro 7 (static output — no runtime JS framework)
- Geist Variable fonts, self-hosted via `@fontsource-variable`
- `@astrojs/sitemap` → `sitemap-index.xml`
- schema.org `ProfessionalService` JSON-LD in `BaseLayout`
- One inline IntersectionObserver reveal script; everything degrades to visible without JS

## Project layout

```
src/
  components/   Hero, Why, Services, Included, Pricing, Process, Locals, CTA, Header, Footer
  layouts/      BaseLayout (SEO meta, fonts, JSON-LD)
  pages/        index.astro
  styles/       global.css — tokens + component styles
public/         favicon.svg, robots.txt, schema.json
docs/           DECISIONS.md, RESEARCH.md, CONTENT.md
```

## Dev

```bash
npm install
npm run dev      # local dev (http://localhost:4321)
npm run build    # outputs to dist/
npm run preview  # serve the production build
```

## Deploy (Vercel)

Repo-connected Vercel project:

- Framework preset: **Astro** (auto-detect)
- Build command: `npm run build`
- Output directory: `dist`
- Domain: `https://cybershare.dev`

The site is fully static — Vercel serves it serverless with no functions, no env vars, no backend.

## Contributing to the content

Prices, review counts, and press quotes live in the components **and** in `docs/CONTENT.md#numbers-registry`. When a fact changes, update both, then `npm run build`.

## Verification (maintainers only)

Screenshots + snapshots of the verified build can be produced with the Playwright CLI skill (`~/.config/opencode/skills/playwright`) against `npm run preview`. The `.playwright-cli/` output directory is git-ignored.