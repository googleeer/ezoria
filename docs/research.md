# Ezoria MVP Theme Research and Project Plan

Grounded in your collected research in `research/final-research.txt` and your two briefs, this document makes a precise recommendation, explains the “why” in business and technical terms, outlines the delivery plan for a single full‑stack specialist, provides time and cost, and anticipates stakeholder questions with an FAQ.

Source research notes: [final-research.txt](assets/final-research.txt)

## Executive Summary
- Recommendation: Start MVP Phase 1 on WordPress using the Homey theme.
- Why: Homey gives the fastest time‑to‑market with the highest MVP feature coverage (villa directory, half‑map search, sticky booking box, instant/inquiry booking modes, Elementor widgets), while keeping Stripe + 365Villas in place with minimal glue code. It is affordable, stable, and Elementor‑friendly for rapid iteration.
- Outcome: Ship MVP in ≈5 weeks with one full‑stack specialist, then iterate on SEO/UX and optional features. Keep a clear path to a future headless or custom stack if/when needed.

## Why Homey for Ezoria’s MVP
Drawing from `research/final-research.txt` shortlist and your MVP+Optional scope:

- Value fit
  - Feature coverage out-of-the-box: featured villas, collections, map pins, sticky price widgets, half‑map search, favorites without login, per‑property FAQs.
  - Elementor support: rapidly build the homepage, destination pages, collection pages, and custom blocks (e.g., “Schedule a Call” CTA) without custom theme development.
  - WooCommerce + Stripe: preserves the current Stripe workflow and enables multi-currency from day one.
  - iCal sync: simple path to import availability; light custom code can map to 365Villas if/when needed.
- Delivery speed and risk
  - Turnkey demos shorten setup time (import and then tailor).
  - Minimal plugin stack avoids “plugin spaghetti,” lowers maintenance risk, and keeps performance cleaner.
- Cost efficiency
  - Theme ≈ $69 one‑time. Most required functionality ships with theme/WooCommerce/Stripe plugin.
  - Integration effort limited to mapping availability and booking confirmations with 365Villas.
- Future-proofing
  - Elementor + CPTs let you scale content models.
  - Easy to add: collections, owner landing, phone/schedule‑a‑call CTAs.
  - Clear migration path later to a headless or custom stack (see Roadmap).

## Why Not the Other Shortlisted Themes (for MVP start)
- WP Rentals
  - Pro: Most granular pricing engine; strong for complex rate rules and SMS.
  - Con: Visuals skew “portal” and need more polish hours to meet Ezoria’s premium tone.
  - Verdict: Great engine, but slightly slower initial polish for your brand goals.
- Villoz
  - Pro: Light, fast, very close to Ezoria’s moodboard.
  - Con: Missing a few native niceties (e.g., wishlist), requiring extra add-ons.
  - Verdict: Strong aesthetic pick; Homey still wins on end‑to‑end booking completeness.
- Booklium (MotoPress)
  - Pro: Bundled channel manager; Gutenberg‑first; strong plugin value.
  - Con: Plugin-driven dashboards less polished; more Gutenberg ramp‑up if your team is on Elementor.
  - Verdict: Excellent package value; choose if channel management is Day‑1 priority.
- Houzez
  - Pro: Robust structure/map clustering/CRM; future Owner CRM path.
  - Con: Instant-booking requires pairing with other plugins; steeper back‑office learning curve.
  - Verdict: Ideal if CRM-first roadmap; slightly heavier for MVP speed.

## Business Rationale
- Faster MVP launch = earlier learning loops = better ROI. Homey minimizes time-to-first-booking while protecting the 365Villas investment.
- Lower TCO at MVP: fewer custom builds, fewer licenses, lean plugin stack.
- Market‑ready UX patterns users expect (half‑map search, sticky booking panel).
- Compatible with your next steps (membership perks, owner funnel, SEO growth, multilingual).

## Technical Rationale
- Architecture (MVP)
  - WordPress + Homey + WooCommerce (+ Stripe plugin).
  - iCal sync + light custom mapping to/from 365Villas API for availability and booking signals.
  - Elementor for layout/blocks; minimal custom components for “Schedule a Call,” lead capture, and FAQs.
- Integration
  - Availability: Consume 365Villas iCal; cron import every 1–4 hours. Optional: push/pull via API for near‑real‑time updates.
  - Bookings: Keep Stripe session via WooCommerce; post‑payment webhook to notify 365Villas; store reference IDs on each booking.
- Performance and SEO
  - Optimize Core Web Vitals: image lazy‑load, critical CSS, cache policy, preconnects, and server caching.
  - Clean semantic markup and metadata per page; ensure fast TTFB via proper hosting.
- Security/compliance
  - Hardened WordPress, least‑privilege roles, backups, web app firewall, GDPR cookie consent, DPA with vendors.

## Delivery Plan (single full‑stack specialist)
Below is a concrete, milestone‑based plan tailored to your MVP scope.

### Milestones, Tasks, and Estimates
- M0 — Project setup (8–12h)
  - Version control, environments (staging/prod), secure hosting, SSL, CI for deploys.
- M1 — Theme procurement & base setup (12–16h)
  - Install Homey, child theme, demo import, Elementor baseline, brand tokens, typography/colors.
- M2 — Data and PMS integration (24–40h)
  - Configure CPTs/properties, import availability via iCal; map to 365Villas.
  - Webhooks for booking confirmation; store reference IDs.
- M3 — Search and results UX (16–24h)
  - Half‑map results, filters (destinations, dates, guests), SEO‑friendly URLs.
- M4 — Property detail page (12–20h)
  - Gallery, highlights, amenities, FAQs accordion, sticky booking panel, similar villas.
- M5 — Destinations & Collections (8–12h)
  - Taxonomies, landing pages, content sections; cross‑links and breadcrumbs.
- M6 — Checkout and payments (12–20h)
  - WooCommerce + Stripe configuration, test flows (inquiry vs instant book), email templates.
- M7 — Performance & SEO (12–18h)
  - Core Web Vitals pass, schema.org, metadata, sitemap/robots, image optimization.
- M8 — Analytics & GDPR (8–12h)
  - GA4 + GTM events (search, view, add-to-cart, checkout steps), consent banner, policies.
- M9 — QA, UAT, fixes (16–24h)
  - Cross‑browser/device QA, edge‑case flows, content QA, accessibility checks.
- M10 — Launch & handover (8–12h)
  - Production cutover, redirects, backup strategy, admin training.

Estimate for MVP: ≈ 160–200 hours. Baseline planning: 180 hours.

### Timeline (1 engineer)
- Duration: ≈ 5 weeks total (buffer included).
  - Week 1: M0–M1
  - Week 2: M2
  - Week 3: M3–M4
  - Week 4: M5–M7
  - Week 5: M8–M10 and launch buffer

### Budget
- Engineering
  - Baseline: 180 hours.
  - Baseline at €50/h: €9,000 (180h). Range: €8,000–€10,000 (160–200h).
  - Tiered rates by task complexity (optional):
    - €40/h — Content/config, QA, basic pages
    - €50/h — Standard development & integrations
    - €60/h — Advanced integrations, performance/architecture
    - Estimated mix for 180h: 36h basic, 99h standard, 45h advanced → ~€9,450
    - Contingency (10–15%) for unknowns: +€900–€1,400
- One‑time software
  - Homey: ≈ $69
  - WooCommerce + Stripe: €0 (Stripe plugin free)
  - Optional add‑ons (if needed): €0–€200
- Hosting
  - Production managed WP + CDN + WAF: €30–€100/month depending on SLA/traffic.

## Deliverables
- Production website with Homey, branded and configured.
- 365Villas availability integration and booking confirmation hooks.
- Search/half‑map results, property detail pages, collections/destinations.
- Stripe checkout, transactional emails, GTM/GA4 events, consent management.
- SEO baseline (sitemaps, meta, schema, redirects).
- Performance tuning to hit CWV thresholds.
- Documentation and admin training.

## Optional Add‑Ons (post‑MVP or if time remains)
- Membership perks and coupons.
- Owner funnel pages and lead capture.
- Wishlist persistence with account sync.
- Multilingual (EN → GR/DE) with WPML/Polylang.
- Advanced CRM sync (HubSpot/Pipedrive).
- PWA shell for add‑to‑home‑screen.

## Future Roadmap (beyond MVP)
Your research also considered non‑WordPress stacks for the long run. Keep these as growth paths:
- Commercial Laravel: BookingCore—feature parity with strong marketplace modules.
- Lighter Laravel: Vacation Rental Script—speed and cost wins for smaller inventories.
- Open‑source headless: Strapi API + Next.js/SvelteKit front‑end—ultimate flexibility, no vendor lock‑in, best CWV.
- Node/MERN starters: Own the stack with modern TypeScript and CI/CD.

Decision gate: Reassess after 3–6 months of traffic and editorial velocity. If content scale, multilingual, and custom features grow fast, consider a staged migration to Strapi + Next.js/SvelteKit with SSR/SSG and granular performance control.

## Acceptance Criteria (MVP)
- Users can search (destination, dates, guests) and view half‑map/grid results.
- Each property page shows accurate availability, gallery, details, FAQs, and sticky booking panel.
- Checkout completes with Stripe; booking references reconcile with 365Villas.
- Core Web Vitals: LCP < 2.5s, INP < 200ms, CLS < 0.1 on top pages.
- SEO: Indexable pages with correct metadata, sitemaps, and schema.org markup.
- Analytics: Events for search, property views, checkout steps, purchase.
- Admins can manage content (destinations, collections, properties fields where relevant).
- Documentation and handover provided.

## Risks and Mitigations
- 365Villas mapping edge cases
  - Mitigation: Start with iCal import and booking webhooks; formal API mapping in parallel; test backfills.
- Plugin bloat/performance regression
  - Mitigation: Minimal plugin philosophy; measure CWV weekly; use server‑side caching and CDN.
- Design polish vs schedule
  - Mitigation: Lock MVP patterns, track polish items as post‑MVP backlog.
- Multilingual complexity
  - Mitigation: Launch EN; plan GR/DE after baseline traffic validates content model.

---

# Milestones and Task Backlog
A backlog you can track in any PM tool.

- Foundation
  - Hosting + domains + SSL + staging/prod
  - Repo + CI/CD, environment config, secrets management
- Theme and UI
  - Homey + child theme, demo import
  - Brand styles, header/footer, menu, CTAs (“Schedule a Call” always visible)
  - Homepage hero search, featured villas, collections
- Data & Integrations
  - Properties model, taxonomies (destinations, collections)
  - iCal import schedule; mapping to 365Villas; booking webhooks
- Search & Results
  - Filters (destination/date/guests), half‑map/grid, empty‑state UX
  - Pagination/infinite scroll
- Property Page
  - Gallery, amenities, pricing widgets, FAQs accordion, similar properties
  - Schema.org for Accommodation
- Checkout
  - WooCommerce + Stripe; email templates; refund/hold flows
  - Terms, privacy, cancellation policy integration
- SEO & Performance
  - Sitemap/robots, meta templates
  - Image/CDN strategy, caching, DB tuning
- Analytics & Compliance
  - GTM/GA4 events, consent banner, cookie categories
- QA & Launch
  - Cross‑device QA, accessibility checks
  - UAT fixes, go‑live checklist, training
- Post‑launch
  - Hotfixes, monitoring, backlog grooming

---

# FAQ (Stakeholder‑Ready)

- Why not build custom from scratch now?
  - Time-to-market and cost. Homey delivers 80–90% of MVP features day one. Custom stacks pay off later once your traffic and unique needs are clear.

- Will this work with 365Villas?
  - Yes. Start with iCal availability and booking webhooks. If needed, extend to full API sync. This is a known pattern with low risk.

- Can we keep Stripe and multi‑currency?
  - Yes. WooCommerce + Stripe supports multi‑currency and works with the existing flow.

- How fast will the site be?
  - With a lean plugin stack, CDN, caching, and optimized media, we target CWV: LCP < 2.5s, INP < 200ms, CLS < 0.1 on critical pages.

- Is SEO covered?
  - Yes. We implement clean URLs, metadata, sitemaps, schema.org, internal linking (collections/destinations), and performance budgets.

- Can we do multilingual later?
  - Yes. Add WPML/Polylang post‑MVP once content stabilizes.

- What is the content model?
  - Properties, destinations, collections, offers; FAQs at property level; Elementor sections for editorial flexibility.

- How do we handle “Schedule a Call”?
  - Add a global CTA in header/footer and sticky on key pages, tracking via GTM; integrate Calendly or a native form with CRM zap.

- How do we manage wishlists?
  - Homey supports favorites without login. For account‑based persistence, add a light account sync post‑MVP.

- What about owner onboarding/CRM?
  - Not in MVP. If prioritized, Houzez or a CRM integration can be explored post‑launch; or plan a future headless/custom owner portal.

- What are ongoing costs?
  - Hosting €30–€100/month. Theme ~$69 once. Maintenance few hours/month for updates, backups, monitoring.

- Is there a path to headless or custom?
  - Yes. Migrate gradually to Strapi API + Next.js/SvelteKit or to BookingCore if marketplace features dominate. MVP assets (design/content) carry forward.

---

# Final Time and Money
- Engineering: ≈ 180 hours (range 160–200h)
- Timeline: ≈ 5 weeks with one full‑stack specialist
- Cost (baseline): €9,000 at €50/h (range €8,000–€10,000)
- Cost (tiered option): ~€9,450 based on estimated task mix (see Budget)
- One‑time software: ~$69 for Homey; Stripe plugin free; optional add-ons €0–€200
- Monthly: hosting €30–€100

# Next Steps
- Approve recommendation (Homey) and budget.
- Provide hosting access and brand assets.
- Confirm initial property set and any special pricing rules.
- I’ll implement the milestone plan and deliver MVP in ≈5 weeks.
