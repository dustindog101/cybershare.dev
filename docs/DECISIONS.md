# Design & Architecture Decisions

Every decision below was made deliberately during the initial build. When you change one, update or supersede it here.

## AD-01 — Astro 7, static output (no framework SPA)

**Decision.** Build a plain static Astro site. Zero runtime JS framework.

**Why.**
- The site is a brochure with one primary job: get local businesses to email us.
- Static HTML + CSS + one 30-line inline script; no hydration tax, no framework re-renders, ~50 KB total.
- Deploys to any static host; Vercel serves it serverless with a ~$0 bill at our traffic level.
- Astro gives component architecture (`.astro` files) and Vite tooling for free.

**Superseded by:** nothing yet.

## AD-02 — Self-hosted Geist fonts, no CDN

**Decision.** Bundle `@fontsource-variable/geist` + `geist-mono` via npm; no Google Fonts or external font CDN.

**Why.** The site sells speed and ownership to clients — it should eat its own dog food. Self-hosting removes third-party DNS/JS/PET dependencies, avoids layout shift, and keeps the site behind-privacy clean. Variable fonts keep payload small.

## AD-03 — Design language: warm paper + ink + one burnt-orange accent

**Decision.** Palette in `src/styles/global.css`: paper `#faf8f5`, ink `#1d1a16`, accent `#c74a18`. Pill buttons, 16 px card radius, one dark inverted section (pricing-note + CTA).

**Why.** The audience is restaurant/auto-shop owners and their customers. Warm neutral reads "local, trustworthy, appetizing," not "startup template." Single accent keeps restraint — the local spots we represent earn trust through calm, not noise.

## AD-04 — Copy: real local businesses featured, with honesty guardrails

**Decision.** "Local favorites" section features real DMV businesses (Sheba Ethiopian, Temari Café, Regina's, Kenwood Sunoco, Japanese Car Care, JB Auto Repair) with real ratings and *condensed* real quotes from public Google reviews. A disclaim that sticks ("Quotes condensed from public Google reviews") sits directly beneath.

**Why.** Social proof works, fabricating reviews is both risky and wrong. These businesses are not clients (yet) — the section says "the businesses we build for", not "our clients". The sample client "Harbor Kitchen" in the hero is explicitly fictional.

## AD-05 — No public prices; price comes after contact (supersedes old price tiers)

**Decision (revised).** The site no longer lists dollar amounts. The price section says we send one clear price after a short conversation, and that the price depends on the size of the site, the extras, and nothing else hidden.

**Why.** The original build published tiers (Start $395 / Grow $1,100 / Own $1,400) and "from $599" service prices. The audience is very small, has no customer base yet, and sells to owners who often are older or speak English as a second language. For them a list of three plans reads as an upsell. A plain "you get your price before we build, and it depends on what you need" builds more trust and lets each quote be scoped to the business. The old tiers remain the internal pricing baseline (see RESEARCH.md); they are just not published.

## AD-10 — Plain-English rewrite: why-first, no em dashes, no AI-tells

**Decision.** The whole site was rewritten for the actual buyer: owners who may be older, busy, or not fluent in English. Rules:

- **No em dashes** in any visible copy (page title and CSS comments excepted).
- **No AI-sounding phrases**: leverage, seamless, elevate, unlock, cutting-edge, world-class, "in today's...", three-part adjective lists, generic superlatives.
- **Short sentences, active voice, present tense**, per plainlanguage.gov / WebAIM guidance. Target: about an 8th-grade reading level.
- **Why-first structure**: a new "Why does your business need a website?" section leads the pitch with honest, sourced numbers (76% of local searches visit a business the same day, Google/Nectafy; 8 of 10 small businesses have a site, NFIB 2025; many owners use Facebook instead of a website, Small Business Majority 2024). Sources are printed in small type under the section.
- **Price on request**: see AD-05.
- **Two languages**: a site can be built in English plus a second language for owners whose customers speak another language (added to Included).

**Why.** The site must capture a person who has never bought a website and is not tech-curious. Plain language and honest numbers out-perform clever marketing for this buyer (per the AI-copy research in RESEARCH.md, "coffee table test" and specificity rules).

## AD-06 — No hero stock photo; a live browser-mockup preview instead

**Decision.** The hero shows a rendered browser-chrome mock of a client restaurant site (Harbor Kitchen) with menu rows, review stars, tap-to-call buttons.

**Why.** A screenshot of the actual product you will get beats a stock photo. It demonstrates exactly what the service produces — a phone-first restaurant site — before a single pitch word.

## AD-07 — Scroll-reveal via one IntersectionObserver, resistant to JS failure

**Decision.** Content starts at `opacity: 0` and reveals when ~12% visible. Works without image libraries; honors `prefers-reduced-motion` by showing everything instantly; degrades to visible if JS is disabled in `index.astro`... (actually: if `IntersectionObserver` is missing, elements are shown immediately; CSS forces full opacity under `prefers-reduced-motion`).

## AD-08 — Honest SEO guarantees, kept small

**Decision.** `robots.txt`, `sitemap-index.xml` (via `@astrojs/sitemap`), schema.org `ProfessionalService` JSON-LD in the layout, self-describing meta title. No wild claims ("#1 in Maryland") anywhere.

**Why.** SEO is a selling point, but overpromising is how local sites earn bad reviews. The Included section promises honest deliverables (mobile-first, map+click-to-call, sitemap, analytics access), not rankings.

## AD-09 — Repository hygiene

**Decision.** `.gitignore` excludes `dist/`, `.astro/`, `node_modules/`, `.playwright-cli/` (verification screenshots comment). No secrets: no API keys, no analytics IDs, contact via mailto only.

---

See also: `docs/RESEARCH.md` (why these prices, these segments), `docs/CONTENT.md` (copy decisions and voice).