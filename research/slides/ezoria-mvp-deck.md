---
marp: true
theme: default
paginate: true
footer: "Ezoria MVP – Recommendation Deck"
---

# Ezoria MVP
## Theme Recommendation & MVP Plan

- Recommendation: Homey (WordPress)
- Goal: Ship MVP in ≈5 weeks
- Stack: WP + Homey + WooCommerce + Stripe + 365Villas mapping

---

## Why Homey for MVP

- Fastest time‑to‑market, rich booking UX out‑of‑the‑box
- Elementor blocks for rapid layout and CTAs (e.g., "Schedule a Call")
- WooCommerce + Stripe: multi‑currency and proven flow
- iCal sync; simple mapping to 365Villas

---

## Business Rationale

- Early launch → faster learning loops and ROI
- Low TCO: fewer custom builds, minimal plugins
- Market‑ready patterns (half‑map search, sticky booking)
- Clear path to headless/custom later

---

## Technical Rationale

- Architecture: WP + Homey + Woo + Stripe
- Integrations: iCal import, booking webhooks → 365Villas
- Performance: CWV focus (LCP < 2.5s, INP < 200ms, CLS < 0.1)
- Security: hardening, WAF, backups, GDPR

---

## Milestones (high‑level)

- M0 Setup
- M1 Theme & base UI
- M2 Data & PMS integration
- M3 Search & results
- M4 Property page
- M5 Destinations/Collections
- M6 Checkout & emails
- M7 Perf & SEO
- M8 Analytics & GDPR
- M9 QA & UAT
- M10 Launch & handover

---

## Timeline & Effort

- Effort: ~180h (range 160–200h)
- Duration: ~5 weeks (1 full‑stack dev)

---

## Budget (at €50/h)

- Baseline: €9,000 (180h), range €8,000–€10,000
- Tiered:
  - €40/h – Content/config, QA, basic pages (~36h)
  - €50/h – Standard dev & integrations (~99h)
  - €60/h – Advanced integrations/perf (~45h)
  - Est. blended: ~€9,450 (+10–15% contingency)

---

## Acceptance Criteria

- Search + half‑map/grid results
- Accurate availability + sticky booking panel
- Stripe checkout, reconciled with 365Villas
- CWV thresholds met on top pages
- SEO baseline + Analytics (GTM/GA4)

---

## Risks & Mitigations

- PMS mapping edge cases → start with iCal + webhooks
- Plugin bloat → minimal stack, monitor CWV
- Design vs schedule → lock MVP patterns, backlog polish
- Multilingual complexity → EN first; GR/DE post‑MVP

---

## Next Steps

- Approve recommendation & budget
- Provide hosting access & brand assets
- Confirm initial property set & pricing rules
- Proceed with M0–M1 immediately
