# Content & Voice Guide

How cybershare.dev talks to its four audiences: the local business owner (buyer), their customer (the end user), Google (SEO), and the site's own maintainers (you).

## The one-sentence pitch

> Fast, phone-first websites for restaurants, auto shops, and local businesses. One fixed price; you own everything.

Every section should support this. If copy doesn't push toward "fixed price + own it + built for Main Street," it gets cut.

## Voice rules

1. **Plain, not cute.** Short sentences. No jargon (no "leverage," "synergies," "KPIs"). The audience reads on a phone at 7 AM before the shift starts.
2. **Concrete, not abstract.** "Menus people can actually read on a phone" beats "digital menu optimization."
3. **No superlatives we can't prove.** No "#1", "best", "top-rated". We cite the review counts of the *spotlight businesses*, and the disclaimer says quotes are condensed from public reviews.
4. **Numbers are sacred.** Prices, days, review counts: if on the page, they're literal and current. Change them in BOTH copy and README/docs if they move.
5. **One clear action per section** — a call, a booking, a link.

## Sections & their rules

### Hero
- H1 says "searchers → regulars", the actual transaction.
- The Harbor Kitchen laptop mock is fictional — keep the label "LIVE SITE" with the sample; no client is implied.
- Stats rail (14 days, 100% ownership, 30 days edits, 1 price) — these map to AD-05 offering terms.

### Services (bento)
- Restaurant / auto from $599; others from $395. The "from" price next to the feature list must stay honest: restaurants and auto sites get more pages.
- Auto card is the dark inverted card — keeps the section from feeling like a menu.

### Included on every build
- The floor: mobile-first, local SEO, map+click-to-call, analytics, simple editing, 30-day edit window. Do not slip these into add-ons — that would nullify AD-05.

### Pricing
- Start $395, Grow $1,100 ("Most chosen"), Own $1,400. All one-time. Add-ons below as post-launch steps.
- Rule: pricing copy must never say "starting at" AND "one-time" for the same number with hidden fees; scope is confirmed on a call.

### Locals
- Spotlight is: the businesses we build for. (See RESEARCH.md for source data.) Quotes are condensed from public Google reviews and labeled. A business gets re-selected when its rating leaves the 4.6–4.9 band; update the table in RESEARCH.md too.

### Process
- Four steps, simple time: Brief → Build → Refine → Launch + beyond. "Beyond" = 30 days free edits, one revision round.

### CTA & contact
- `hello@cybershare.dev` (mailto with subject). Add no phone number until one exists to answer it. No forms until a backend/email pipeline exists.

## Numbers registry (single source of truth)

| Fact | Value | Used in |
|---|---|---|
| Price Start / Grow / Own | $395 / $1,100 / $1,400 | Pricing |
| "From" restaurant/auto | $599 | Services |
| "From" other | $395 | Services |
| Add-ons | menus/ordering $250, booking $200, photo shoots $350, hosting+edits $35/mo, second lang $150 | Pricing add-ons |
| Free edits window | 30 days | Hero + Process + Included |
| Payment structure | one-time, you own files | everywhere |
| Time to launch | 14 days average | Hero |
| Email contact | hello@cybershare.dev | Header/CTA/Footer |

(When your numbers change, update the table and re-check every component that references it — the site has no central config for these yet.)

## SEO meta

- Title (index): "Cybershare Design — Websites for Restaurants, Auto Shops & Local Business" — set in `src/layouts/BaseLayout.astro`, overridable per page via the `title` prop.
- Only one H1; sections H2; card titles H3. Keeps hierarchy honest for screen readers + local SEO.