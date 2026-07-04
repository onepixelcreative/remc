# REMC site — working notes for Claude Code

This repo is the live REMC Ltd marketing site. `main` is production: every
push to `main` auto-deploys to the public site within about a minute via
`.github/workflows/deploy-pages.yml` (syncs to the `gh-pages` branch, which
GitHub Pages serves). There is no staging environment and no review gate —
whatever lands on `main` goes live.

## Editing text content

Client-facing copy changes (headlines, body text, prices, plan names, FAQ
answers, etc.) live directly in the page HTML — there is no CMS or content
data file. To make a text edit:

1. Find the right page (`index.html`, `about.html`, `services.html`,
   `plans.html`, `case-studies.html`, `blog.html` + the `blog-*.html`
   articles, `store.html`, `contact.html`, `glasgow.html`).
2. Edit the text in place, preserving surrounding HTML structure/classes —
   don't restructure markup or CSS for a copy change.
3. Commit and push directly to `main`. It goes live automatically.

If a request is ambiguous (which page, which section) or looks like a
structural/design change rather than a copy change, ask before proceeding.

## Do not touch

- `_private/products/` — the paid Gumroad product files. Never reference
  these from a public-facing page in a way that exposes a direct download
  link outside the Gumroad checkout flow. Once both products are live on
  Gumroad, these files should be removed from the repo entirely — Gumroad
  hosts them and gates download behind payment.
- `.github/workflows/deploy-pages.yml` — the deploy pipeline. It only
  publishes known web-asset extensions from the repo root and deliberately
  never recurses into subdirectories, so `_private/` is never published.
  Don't add `.xlsx` or other product file extensions to its copy list.
- `styles.css` — shared across every page. A change here affects the whole
  site, not just one page.

## Known clutter

`FILE_2043.pdf`, `FILE_3518.xlsx`, `FILE_7703.xlsx` at the repo root are
stray duplicates of `REMC-Estimating-Guide.pdf` and the two files in
`_private/products/`, left over from an earlier upload. Safe to ignore or
delete; not referenced by any page.
