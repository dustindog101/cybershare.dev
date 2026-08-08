# Content & Voice Guide

How cybershare.dev talks to its four audiences: the local business owner (buyer), their customer (the end user), Google (SEO), and the site's own maintainers (you).

## The one-sentence pitch

> Fast, phone-first websites for restaurants, auto shops, and local businesses. One fixed price; you own everything.

Every section should support this. If copy doesn't push toward "fixed price + own it + built for Main Street," it gets cut.

## Voice rules

1. **Plain, not clever.** Short sentences. No jargon (no "leverage," "synergies," "KPIs"). The audience is a business owner who may be older, busy, or speak English as a second language. Read it out loud; if it would sound odd at a kitchen table, rewrite it.
2. **No em dashes.** In visible copy, never. Use periods and short sentences instead. (The page <title> and CSS comments are the only exceptions.)
3. **No AI-tells.** Never: "in today's...", leverage, seamless, elevate, unlock, cutting-edge, world-class, "empower", three-part adjective lists ("fast, friendly, reliable"), "so you can focus on what you do best". One specific, verifiable detail beats three adjectives.
4. **Concrete, not abstract.** "Menu that reads well on a phone" beats "digital menu optimization."
5. **No superlatives we can't prove.** No "#1", "best", "top-rated". We cite review counts of the spotlight businesses, and the disclaimer says quotes are condensed from public reviews.
6. **Numbers are sacred.** Days, review counts, the 3-in-4 same-day-visit stat: if on the page, they're literal and current. Change them in BOTH copy and docs if they move.
7. **One clear action per section** — a call, an email, a link. Use the same CTA words everywhere ("Get your price").

## Sections & their rules

### Hero
- H1 says "searchers → regulars", the actual transaction.
- The Harbor Kitchen mock in the hero is fictional — the chip says "EXAMPLE SITE"; no client is implied.
- Stats rail (14 days to launch, 100% yours, 30 days free changes, 1 price agreed up front) — these map to AD-05.

### Why a website (first pitch section)
- Four honest reasons with real sources: people look online first (3 in 4 same-day visit), Facebook is not enough, competitors already have sites, a site never misses a call.
- Sources are printed in small type under the section (always keep that line when you edit).

### Services (bento)
- No prices on the cards. Three segments: restaurants and cafés, auto shops and repair, every other local business.
- The auto card stays the dark inverted card — keeps the section from feeling like a menu.

### Everything is included
- The floor: made for phones, findable on Google, map + one-tap call, two languages, plain-English help, 30 days of free changes.
- Do not slip these into paid extras — that would nullify AD-05.

### Your price
- No price lists. The section explains that the price depends on the size of the site, what the business needs, and the extras, and that you see the exact price before any build.
- Rule: never publish prices on the site until there is a demand to do so, and never hide fees behind a "starting at".

### Locals
- Real DMV businesses we would build for. (See RESEARCH.md for the data.) Quotes are condensed from public Google reviews and labeled. A business gets re-selected when its rating leaves the 4.6 to 4.9 band; update the table in RESEARCH.md too.

### How it works
- Four steps, simple: Tell us → We build → You look, we fix → Live. "Live" includes 30 days of free changes.

### CTA & contact
- `hello@cybershare.dev` (mailto with subject). Add no phone number until one exists to answer it. No forms until a backend exists.

## Numbers registry (single source of truth)

| Fact | Value | Used in |
|---|---|---|
| Public prices on the site | none | nowhere. Go see AD-05 |
| Price is communicated | after a short call, before any build | Pricing / CTA / Process |
| Same-day visit stat | 3 in 4 local searches on a phone | Why |
| Small-business-shops site stat | 8 in 10 | Why |
| Free changes window | 30 days | Hero + Process + Included |
| You own the site | 100%, always stated | anywhere |
| Time to launch | 2 weeks for a first version | Hero + Process |
| Example site prices (fictional) | Harbor Kitchen menu $7 to $23 | Hero mock only, for realism |

(When your numbers change, update the table and re-check every component that references it — the site has no central config for these yet.)

## SEO meta

- Title (index): "Cybershare Design — Websites for Restaurants, Auto Shops & Local Business" — set in `src/layouts/BaseLayout.astro`, overridable per page via the `title` prop. The em dash in the title is the one allowed dash on the site.
- Only one H1; sections H2; card titles H3. Keeps hierarchy honest for screen readers + local SEO.