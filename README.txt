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
  store.html                       Gumroad-backed downloads (Start-Up Pack, Templates)

CONTENT
  blog.html                        Blog index
  blog-first-tender-guide.html     SEO article — pricing your first tender (HowTo schema)
  blog-margin-leaks.html           SEO article — 6 margin leaks
  blog-outsourced-cost.html        SEO article — in-house vs outsourced cost

==========================================
SHARED STYLESHEET
==========================================
  styles.css                       Shared design system (tokens, reset, nav,
                                   footer, buttons + homepage components). Linked
                                   by every page — edit shared styling here ONCE.
                                   Page-specific rules stay in each page's inline
                                   <style> and override the shared sheet.
                                   NOTE: the colour palette is unified on the
                                   homepage values; the blog/store pages had
                                   drifted to a slightly different blue/grey and
                                   are now consistent with the rest of the site.

==========================================
2 BINARY ASSETS (must travel with HTML)
==========================================
  hero-switchroom.mp4              Homepage hero animation (8s, 720p, ~3.2 MB)
  REMC-Estimating-Guide.pdf        Email-gated lead magnet (~230 KB)

==========================================
NOT DEPLOYED — FULFILMENT ONLY
==========================================
  _private/products/               Paid store products (The Estimator, The Enquiry
                                   Register spreadsheets). Kept OUT of the public
                                   web root so they aren't freely downloadable —
                                   deliver them via Gumroad after purchase (Gumroad
                                   hosts the files directly once products are set up
                                   there; these should then be removed from the repo).

See GO-LIVE.md for the full pre-launch checklist. Search the HTML for
"GO-LIVE TODO" to jump straight to each thing that still needs wiring.

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

GUMROAD (store.html)
  - Comment at top of file flags exactly where to swap in real values
  - Create both products on Gumroad (Start-Up Pack £150, Commercial Templates £100),
    attaching the files from _private/products/
  - Replace the two GUMROAD_REPLACE_... permalinks with the real product URLs
  - Once both products are live on Gumroad, remove _private/products/ from this repo

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
  - Gumroad product permalinks in store.html (search for "REPLACE" in comments)
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
1. Drop the web-root files into the web root, preserving filenames (the 12 .html,
   styles.css, hero-switchroom.mp4, REMC-Estimating-Guide.pdf, logo + OG images).
   DO NOT deploy the _private/ folder (paid products — see above).
2. Set up URL routing per the URL STRUCTURE section above
3. Add robots.txt, sitemap.xml, favicons
4. Wire Gumroad with live product permalinks
5. Test all CTAs and Calendly popup end-to-end

==========================================
CONTACT
==========================================
REMC Ltd · Glasgow, Scotland · United Kingdom
enquire@remc.uk · +44 7822 033278
linkedin.com/company/remc-uk
