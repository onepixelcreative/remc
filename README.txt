REMC Website — Handoff Bundle
=============================

This bundle is a complete, ready-to-deploy static site for REMC Ltd.
Open index.html in any browser to preview the full site locally.

FILES INCLUDED
--------------
HTML pages (8):
  index.html                       Homepage with hero video, services, plans
  about.html                       Founder bio (Liam Macleod)
  case-studies.html                Three Priority Plan client case studies
  store.html                       Stripe-backed downloads (Start-Up Pack, Templates)
  blog.html                        Blog index
  blog-first-tender-guide.html     SEO article — pricing your first tender
  blog-margin-leaks.html           SEO article — 6 margin leaks
  blog-outsourced-cost.html        SEO article — in-house vs outsourced cost

Assets:
  hero-switchroom.mp4              Homepage hero animation (8s, 720p, MP4)
  REMC-Estimating-Guide.pdf        Lead-magnet PDF (delivered after email opt-in)

NAVIGATION
----------
All pages share the same top nav: Services · Plans · Case studies · About · Blog · Store · Contact.

DEPLOY NOTES
------------
1. Drop the contents of this folder into the web root, preserving filenames.
2. index.html is the canonical entry point.
3. Both the MP4 and PDF MUST sit alongside the HTML files (relative paths).
4. Stripe Buy Buttons in store.html are placeholders — replace with live
   publishable key + buy-button IDs from the Stripe Dashboard. Comments
   at the top of store.html flag the exact places.
5. Calendly is wired to: https://calendly.com/enquire-remc
6. WhatsApp deep link: +44 7822 033278 (wa.me/447822033278)
7. The email-gated download in blog-first-tender-guide.html captures email
   to localStorage as a placeholder. Wire it to your mailing list endpoint
   (search the file for `remc_mailing_list` to find the hook).

LOCAL SEO / SCHEMA
------------------
ProfessionalService JSON-LD on index.html (Glasgow address, UK service area).
Person schema on about.html (Liam Macleod, Glasgow).
Article + FAQPage + HowTo schema on blog articles.
Open Graph + Twitter card meta on index.html and about.html.

PLACEHOLDERS TO SWAP BEFORE GOING LIVE
--------------------------------------
- Founder portrait (about.html) — Unsplash URL, replace with real headshot.
- Three case-study portraits (case-studies.html) — Unsplash, replace with reals.
- https://remc.uk/logo.png — drop a 512×512 logo at this path.
- https://remc.uk/og-image.jpg — create 1200×630 social share image.
- LinkedIn URL linkedin.com/in/liammacleod-remc — confirm slug.
- Stripe Buy Button IDs in store.html (search for "REPLACE" in comments).

CONTACT
-------
REMC Ltd · Glasgow, Scotland · enquire@remc.uk · +44 7822 033278
