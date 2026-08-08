# cybershare.dev

Fixed-price websites for local business — restaurants, auto shops, and everything on Main Street. Built with [Astro](https://astro.build), deployed serverless on Vercel.

## Stack

- Astro 7 (static output)
- Geist Variable fonts, self-hosted
- `@astrojs/sitemap`
- Zero runtime dependencies; one inline reveal-on-scroll script

## Dev

```bash
npm install
npm run dev      # local dev
npm run build    # outputs to dist/
npm run preview  # serve the build
```

## Deploy (Vercel)

Repo-connected Vercel project:

- Framework preset: **Astro**
- Build command: `npm run build`
- Output directory: `dist`
- Domain: `https://cybershare.dev`

## Structure

```
src/
  components/   Hero, Services, Included, Pricing, Process, Locals, CTA, Header, Footer
  layouts/      BaseLayout (SEO meta, fonts, schema.org JSON-LD)
  pages/        index.astro
  styles/       global.css — design tokens + component styles
public/         favicon.svg, robots.txt, schema.json
```