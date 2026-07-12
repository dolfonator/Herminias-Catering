# (DEMO) Herminias-Business — Template Guide

> **CURRENT ROLE: Business-tier TEASER-DEMO** for Herminia's Food Catering
> (prospect, no online presence — see `Prospects/Herminias-Food-Catering/`).
> Built July 12, 2026 by cloning the Business-tier template and rebranding per
> `Websites/REPLICATION-WORKFLOW.md`. Deploy target: `demo-herminias.netlify.app`
> on the **demo Netlify account** (drag-drop). **Never let this index.**

## Converting this teaser to the PAID Business build (the 3 revert steps)

1. **Re-index:** delete the `<meta name="robots" content="noindex, nofollow">` line
   in `index.html` (keep `robots.txt` as `Allow` — it already is).
2. **Live form:** remove the "teaser-demo mode" submit-intercept block in `script.js`
   (`form[name="inquiry"]` → `preventDefault`) and replace `YOUR_FORM_ID` in the form
   `action` with the client's real Formspree ID; update `_subject`/`_next` if the
   domain changes.
3. **De-demo:** remove the `.demo-banner` div in `index.html` (+ its offset block in
   `script.js`), then deploy to the **client's own Netlify account + custom domain**
   (find/replace `demo-herminias.netlify.app` across html/xml/txt/webmanifest).

## Owner-confirmation gates (must clear before ANY indexed go-live)

Everything sample/placeholder in this build traces to the intake sheet
(`Herminias-Food-Catering-Info-Sheet.docx`). Blockers:

- [ ] **Real per-head packages & prices** (current tiers Handa/Classic/Fiesta/Grand
      ≈ ₱350–900+ are 2026 Metro Manila industry samples)
- [ ] **Real menu** (dishes per course + choices allowed per package)
- [ ] **Contact details** — mobile/Viber (`+63 900 000 0000` is a placeholder),
      email (`inquiries@herminias-catering.ph` is a placeholder), FB page (none yet)
- [ ] **Booking terms** — minimum pax (~50 sample), lead time, down-payment
      (50% sample), tasting & cancellation policy, VAT-inclusive?, travel fee
- [ ] **Logo** — the monogram badge is DDM-generated; owner must approve or supply
- [ ] **Photos** — ALL photography is stock (see `ASSET-LICENSES.md`); replace with
      the owner's real, permission-cleared event photos
- [ ] **Real testimonials** — reviews section is disclaimed lorem-ipsum
- [ ] **JSON-LD** — add real phone/email/street address; add `aggregateRating`
      ONLY once real reviews exist
- [ ] Set up the owner's **Google Business Profile** (companion move, highest-ROI)

## What differs from the base Business template (catering vertical)

- **9 sections, not 8** — new `#how` "How booking works" section (4 steps + FAQ)
  between Reviews and Contact; its styles live at the **bottom of `styles.css`**
  under "HERMINIA'S ADDITIONS" (also: `.field select` styling, `.map-embed` +
  `.map-fallback`).
- **No foodpanda / ordering** — all CTAs route to the `#book` inquiry form
  ("Get a Quote"). Nav labels: About · Events · Packages · Gallery · Reviews ·
  Booking · Contact.
- **Sections remapped:** flavors → *Events we cater* · menu → *Packages & sample
  menu* (per-head tiers) · visit → *Coverage & inquiry hours* (no storefront;
  city-level Quezon City map with styled fallback layered behind the iframe).
- **Form has catering fields:** event date + estimated guests (required) and an
  event-type `<select>`.
- **Hours table = inquiry hours** (Mon–Sat 8–6, Sun by appointment — sample);
  `data-day` attributes intact so the today-highlight JS still works.
- **JSON-LD type is `FoodEstablishment`** (schema.org has no Caterer type) with
  `areaServed: Metro Manila`; **no `aggregateRating`** and no phone/email until
  real ones exist.
- Brand: `#9C2A2A` brick red + `#D9A84E` gold (provisional, `:root` block) ·
  **Lora + Hanken Grotesk**.

## Standard swap list

Follow `Websites/REPLICATION-WORKFLOW.md` §4 — it supersedes this file where they
disagree. Local preview: `herminias-business` on **:8142** in `.claude/launch.json`.
