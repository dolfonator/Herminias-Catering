# (DEMO) Herminias-Business: Template Guide

> **CURRENT ROLE: Business-tier TEASER-DEMO** for Herminia's Food
> (prospect, no online presence; see `Prospects/Herminias-Food-Catering/`).
> Built July 12, 2026 by cloning the Business-tier template and rebranding per
> `Websites/REPLICATION-WORKFLOW.md`. Deploy target: `demo-herminias.netlify.app`
> on the **demo Netlify account** (drag-drop). **Never let this index.**

## Converting this teaser to the PAID Business build (the 3 revert steps)

1. **Re-index:** delete the `<meta name="robots" content="noindex, nofollow">` line
   in `index.html` (keep `robots.txt` as `Allow`; it already is).
2. **Live form:** remove the "teaser-demo mode" submit-intercept block in `script.js`
   (`form[name="inquiry"]` → `preventDefault`) and replace `YOUR_FORM_ID` in the form
   `action` with the client's real Formspree ID; update `_subject`/`_next` if the
   domain changes.
3. **De-demo:** remove the `.demo-banner` div in `index.html` (+ its offset block in
   `script.js`), then deploy to the **client's own Netlify account + custom domain**
   (find/replace `demo-herminias.netlify.app` across html/xml/txt/webmanifest).

## Owner-confirmation gates (must clear before ANY indexed go-live)

Pricing, sample menu, logo, and contact details are **CONFIRMED** via the client's
Partnership Deck (`Clients/herminias/Herminias_Catering_Partnership_Deck.pdf` in the
DDM project folder). Remaining blockers before any indexed go-live:

- [x] **Real per-head packages & prices** (Budget ₱650 / Standard ₱720 / Premium ₱820
      per head; confirmed via Partnership Deck)
- [x] **Real menu** (full 6-set sample menu from the Partnership Deck)
- [x] **Contact details**: Miggy, 0945 706 1487, herminiasfood@gmail.com
      (confirmed via Partnership Deck); FB page still TBD if needed
- [ ] **Booking terms**: minimum pax (~50 sample), lead time, down-payment
      (50% sample), tasting & cancellation policy, VAT-inclusive?, travel fee
- [x] **Logo**: client's real official mark (hand-drawn circular portrait + script
      wordmark), extracted from the Partnership Deck; no longer a DDM placeholder
- [ ] **Photos**: ALL photography is still stock (see `ASSET-LICENSES.md`); replace with
      the owner's real, permission-cleared event photos after a real shoot
- [ ] **Real testimonials**: reviews section is disclaimed lorem-ipsum
- [ ] **JSON-LD**: confirm street address if any; add `aggregateRating`
      ONLY once real reviews exist
- [ ] Set up the owner's **Google Business Profile** (companion move, highest-ROI)

## What differs from the base Business template (catering vertical)

- **9 sections, not 8**: new `#how` "How booking works" section (4 steps + FAQ)
  between Reviews and Contact; its styles live at the **bottom of `styles.css`**
  under "HERMINIA'S ADDITIONS" (also: `.field select` styling, `.map-embed` +
  `.map-fallback`).
- **No foodpanda / ordering**: all CTAs route to the `#book` inquiry form
  ("Get a Quote"). Nav labels: About · Events · Packages · Gallery · Reviews ·
  Booking · Contact.
- **Sections remapped:** flavors → *Events we cater* · menu → *Packages & sample
  menu* (per-head tiers) · visit → *Coverage & inquiry hours* (no storefront;
  city-level Quezon City map with styled fallback layered behind the iframe).
- **Form has catering fields:** event date + estimated guests (required) and an
  event-type `<select>`.
- **Hours table = inquiry hours** (Mon–Sat 8–6, Sun by appointment; sample);
  `data-day` attributes intact so the today-highlight JS still works.
- **JSON-LD type is `FoodEstablishment`** (schema.org has no Caterer type) with
  `areaServed: Metro Manila`; **no `aggregateRating`** until real reviews exist.
- **Brand tokens** (official, from client's Partnership Deck
  `Clients/herminias/Herminias_Catering_Partnership_Deck.pdf`; `:root` block):
  Herminia Orange `#F15A22`, Warm Peach `#FCE0C4`, Sage Leaf `#8FA888`
  (+ `#6E8A6A` sage-deep for text-safe sage), Charcoal `#2B241E`.
- **Fonts (four families):** Lora (display/headings), Hanken Grotesk (body),
  Oswald (bold condensed: dish names / tier labels / nameplates), Great Vibes
  (script accent: taglines only, 2–5 instances). This intentionally breaks the
  base template's "two typefaces only" rule because the client's brand deck
  defines the extra roles.
- **Logo:** client's real official mark in `assets/herminias-logo.png` (and derived
  icon/favicon set), not a DDM-generated placeholder; hand-drawn circular portrait
  of founder Herminia "Minnie" Mateo + script wordmark, extracted from the
  Partnership Deck.
- **Leaf-sprig motif:** small sage-colored inline-SVG accent (`#i-sprig` symbol),
  used sparingly (~4–5 places), echoing the deck's botanical leaf-sprig graphic.

## Standard swap list

Follow `Websites/REPLICATION-WORKFLOW.md` §4; it supersedes this file where they
disagree. Local preview: `herminias-business` on **:8142** in `.claude/launch.json`.
