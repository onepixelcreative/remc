REMC Website — Designer Handoff Bundle
======================================

Complete static site for REMC Ltd, ready for production deployment.
Open index.html in any browser to preview the full site locally.

==========================================
12 HTML PAGES
==========================================

CORE PAGES
  index.html                       Homepage — hero video, services, plans, CTA
  services.html                    Full services overview, 6 service blocks
  plans.html                       Monthly Service Plans — 4 plans + detail + FAQ
  about.html                       Founder bio (Liam Macleod, Glasgow)
  case-studies.html                3 Priority Plan client case studies (accordion)
  contact.html                     Calendly, WhatsApp, email, LinkedIn + working hours
  glasgow.html                     Glasgow location page (SEO-targeted)

COMMERCE
  store.html                       Stripe-backed downloads (Start-Up Pack, Templates)

CONTENT
  blog.html                        Blog index
  blog-first-tender-guide.html     SEO article — pricing your first tender (HowTo schema)
  blog-margin-leaks.html           SEO article — 6 margin leaks
  blog-outsourced-cost.html        SEO article — in-house vs outsourced cost

==========================================
2 BINARY ASSETS (must travel with HTML)
==========================================
  hero-switchroom.mp4              Homepage hero animation (8s, 720p, ~3.2 MB)
  REMC-Estimating-Guide.pdf        Email-gated lead magnet (~230 KB)

==========================================
NAVIGATION (CONSISTENT ACROSS ALL PAGES)
==========================================
Header: Services · Plans · Case studies · About · Blog · Store · Contact
Primary CTA: "Book a call" → contact.html (Calendly popup)
Footer: 3 columns (brand + NAP, Site links, Service areas)

==========================================
URL STRUCTURE — RECOMMENDED FOR PRODUCTION
==========================================
The files are flat for static preview compatibility. For SEO, the designer should
route the production URLs as follows:

  /                              → index.html
  /services/                     → services.html
  /plans/                        → plans.html
  /case-studies/                 → case-studies.html
  /about/                        → about.html
  /contact/                      → contact.html
  /blog/                         → blog.html
  /blog/how-to-price-your-first-electrical-tender/  → blog-first-tender-guide.html
  /blog/why-you-lose-electrical-tenders/            → blog-margin-leaks.html
  /blog/in-house-vs-outsourced-electrical-estimator/ → blog-outsourced-cost.html
  /store/                        → store.html
  /locations/glasgow/            → glasgow.html

The canonical URLs in each <head> already reflect this production routing pattern.

==========================================
THIRD-PARTY INTEGRATIONS (need wiring)
==========================================

STRIPE (store.html)
  - Comment at top of file flags exactly where to swap in real values
  - Replace publishable key (pk_live_REPLACE_WITH_YOUR_PUBLISHABLE_KEY)
  - Replace Buy Button IDs for both products (Start-Up Pack £150, Commercial Templates £100)
  - Set success URL on each Buy Button to a thank-you page that delivers the download

CALENDLY (sitewide)
  - Already wired to: https://calendly.com/enquire-remc
  - Intercepts any link with text starting "Book a", "Discuss", "Hold my"
  - To change the URL, search for "calendly.com/enquire-remc" in any HTML file

WHATSAPP (sitewide)
  - Number: +44 7822 033278 (wa.me/447822033278)
  - To change, search for "447822033278" across files

EMAIL-GATED DOWNLOAD (blog-first-tender-guide.html)
  - Currently captures email to localStorage as a placeholder
  - To wire to mailing list: search for "remc_mailing_list" in the script
  - Replace the localStorage call with fetch() to Mailchimp / ConvertKit / Mailerlite endpoint

==========================================
LOCAL SEO / SCHEMA
==========================================
  - ProfessionalService JSON-LD on index.html (Glasgow + UK service area)
  - LocalBusiness JSON-LD on glasgow.html (geo coordinates, UK areaServed)
  - Person JSON-LD on about.html (Liam Macleod, Glasgow)
  - Article + FAQPage + HowTo on blog articles
  - Service JSON-LD on services.html
  - FAQPage on plans.html
  - ContactPage on contact.html
  - Open Graph + Twitter card meta on every page

==========================================
PLACEHOLDERS TO SWAP BEFORE GOING LIVE
==========================================
  - Founder portrait (about.html) — Unsplash URL, replace with real headshot
  - Three case-study portraits (case-studies.html) — Unsplash, replace with reals
    after questionnaire responses come back from Reed/Guy/Josh
  - https://remc.uk/logo.png — drop a 512×512 logo at this path
  - https://remc.uk/og-image.jpg — create 1200×630 social share image
  - LinkedIn URL linkedin.com/in/liammacleod-remc — confirm slug
  - Stripe Buy Button IDs in store.html (search for "REPLACE" in comments)
  - Glasgow office street address in glasgow.html schema (currently placeholder)

==========================================
TECHNICAL SEO TO ADD BEFORE LAUNCH
==========================================
  - robots.txt (allow all, point to sitemap.xml)
  - sitemap.xml (list all 12 pages with priority + lastmod)
  - favicon.ico + favicon-32x32.png + apple-touch-icon.png + favicon links in <head>
  - Compress hero-switchroom.mp4 to under 1MB (or convert to AV1) to improve LCP

==========================================
DEPLOY
==========================================
1. Drop the contents of this folder into the web root, preserving filenames
2. Set up URL routing per the URL STRUCTURE section above
3. Add robots.txt, sitemap.xml, favicons
4. Wire Stripe with live keys
5. Test all CTAs and Calendly popup end-to-end

==========================================
CONTACT
==========================================
REMC Ltd · Glasgow, Scotland · United Kingdom
enquire@remc.uk · +44 7822 033278
linkedin.com/company/remc-uk
