# RESEARCH-NOTES.md

Research notes appended per project rule 7 (research before new territory).

---

## 1. Functional-first agency site (2026-08-07)

**Trigger.** User asked for a full redo: no em dashes or AI-sounding copy, no on-page references/sources, functional hooks (DoorDash, Uber Eats, bookings, appointment forms) instead of SEO-only talking points, testimonial-style copy about results (orders, bookings, money after the site), and a design good enough to want to buy.

**What was researched.**
- Chowly/restaurant-tech conversion framing: 70%+ of diners ordered delivery in the past month; roughly a third prefer ordering directly from the business over apps; majority of restaurant sites get most traffic on mobile (~70%); the decisive metric is the order, not the visit. Source: Restaurant website must-have features (Chowly), fetched via webfetch.
- Top pages/features every business website needs per US Chamber of Commerce guidance: clear services, ordering/booking/call drivers, location, hours, reviews, contact. Source: uschamber.com article on top pages and features, fetched 2026-06.

**Patterns adopted + why.**
1. Hero = functional mock (menu rows, call-to-order, book-a-table, DoorDash/Uber Eats/Grubbub chips) because the product is a phone-first website; showing the product beats a stock photo (AD?).
2. Integrations/chips section ("hooks up to what you already run") to answer "will it work with my apps?" without a FAQ.
3. Services rewritten as functional bullets per vertical (restaurants: ordering; auto: appointment-question forms; others: bookings/calls/WhatsApp) mirroring the US Chamber feature list.
4. "Results" section uses outcome-shaped testimonials (orders starting week one, booked tables, fewer calls) instead of named businesses, per user request; no fake names/ratings attributed to real businesses.
5. Sources/citations removed from every component per user request; research numbers inform copy but are not cited.

**Notes.** Old "Local favorites" (real DMV spots with real Google quotes + disclaimer) fully removed per the user request to make reviews about results. Site remains static Astro, no prices on page (AD-05), no em dashes (AD-10 writes).