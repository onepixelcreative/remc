# REMC — Go-Live Checklist

Everything that must be swapped, wired, or supplied before this site is
production-ready. Search the codebase for `GO-LIVE TODO` to jump to each hook.

## Supplied in v2 ✅
- Hero video `hero-switchroom.mp4` (a brand-gradient fallback in `styles.css`
  still covers the case where it fails to load).
- Lead-magnet `REMC-Estimating-Guide.pdf` (linked from `blog-first-tender-guide.html`).

## 1. Assets still to supply
- [ ] **Founder headshot** — replace the Unsplash placeholder in `about.html`.
- [ ] **Three client portraits** — replace the Unsplash placeholders in `case-studies.html`.
- [ ] **`logo.png`** (512×512) at `https://remc.uk/logo.png` — referenced by JSON-LD on `index.html`.
- [ ] **`og-image.jpg`** (1200×630) at `https://remc.uk/og-image.jpg` — social share card.
- [ ] **`hero-poster.jpg`** *(optional)* — first-frame still; set `poster="hero-poster.jpg"`
      on the `<video>` in `index.html` to avoid a flash before playback.

## 2. Integrations to wire
- [ ] **Stripe** (`store.html`) — replace `pk_live_REPLACE_WITH_YOUR_PUBLISHABLE_KEY`
      and the two `buy_btn_REPLACE_...` button IDs with live values. Set each Buy
      Button's success URL to a thank-you page that delivers the purchased file.
- [ ] **Product delivery** — paid products live in `_private/products/` (see §3). Wire
      Stripe fulfilment to serve them from a gated/expiring link, NOT the public root.
- [ ] **Mailing list** (`blog-first-tender-guide.html`) — the email opt-in currently
      saves to `localStorage` only. Wire it to your provider at the `GO-LIVE TODO`.
- [ ] **LinkedIn slug** — confirm `linkedin.com/in/liammacleod-remc` resolves.

## 3. Deployment notes
- **Pages (12):** index, services, plans, case-studies, about, blog (+3 articles),
  store, contact, glasgow.
- **Shared CSS:** `styles.css` — linked by every page. Edit shared tokens/components
  there once; page-specific rules stay in each page's inline `<style>`.
- Deploy the web-root files only: the 12 `.html`, `styles.css`, `hero-switchroom.mp4`,
  `REMC-Estimating-Guide.pdf`, and the logo/OG images.
- **Do NOT deploy `_private/`** — it holds the paid products (The Estimator, The
  Enquiry Register). Publishing them would let anyone download paid goods for free.
- `index.html` is the canonical entry point. Keep asset filenames intact (relative paths).

## 4. Contact / config reference
- Calendly: https://calendly.com/enquire-remc
- WhatsApp: +44 7822 033278 (wa.me/447822033278)
- Email: enquire@remc.uk · Glasgow, Scotland
