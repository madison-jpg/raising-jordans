# CLAUDE.md — Raising Jordans (Madison Jordan)

## Who this is for
Madison Jordan is building a motherhood brand, "Raising Jordans," on TikTok @raisingjordans. She is a former au pair for a high profile family in Australia, a half-decade elementary teacher, and a lifelong childcare expert. Her goal: grow her email list, then sell a small ebook, then launch a flagship course. She is non-technical. Do the technical work for her. Never ask her to open files or run commands you can run yourself.

## What lives in this repo
- `index.html` — landing page with email capture (hero photo `madison-tyler.jpg`) + the Guidebook buy section ($9.99, links to the Stripe payment link)
- `guide.html` — the free 8-habit lead magnet (gated: localStorage flag unlocks `guide.html?unlocked=1`)
- `the-capable-toddler.html` — the Guidebook reader (unlisted URL, the paid product)
- `the-capable-toddler.pdf` — the sellable PDF, rendered from the reader HTML. IMPORTANT: after ANY content edit to `the-capable-toddler.html`, re-render this PDF (headless Chrome: `--headless --no-pdf-header-footer --virtual-time-budget=20000 --print-to-pdf`) and commit both together, or buyers get an outdated book.
- `download.html` — post-purchase success page (Stripe redirects here after payment; button downloads the PDF)
- `madison-tyler.jpg` — hero photo

## Deploy workflow (memorize this)
This repo is connected to Madison's Cloudflare Pages. To publish ANY change: edit the file, then `git add -A && git commit -m "..." && git push`. The live site at https://raising-jordans.pages.dev updates in about 30 seconds. To confirm, open that URL. There is no build step.

## The backend (do NOT change)
Both signup forms POST JSON to a Make.com webhook owned by Tyler, which writes leads to the Google Sheet "Raising Capable Kids" (tab "Landing Page leads": Timestamp, First Name, Email, Source Form). Leave the webhook URL in the HTML alone. To show Madison her leads, read that Sheet via the Google Drive connector (shared with madison@jordanacres.com). Only rebuild the backend onto Madison's own accounts if she explicitly asks.

## Brand rules (non-negotiable)
- NO emdashes, ever. Use commas, colons, or parentheses.
- Tagline: "Capable kids. Confident moms."
- Voice: confident, direct, anti-conventional, reframe-driven. ALL CAPS for emphasis is on-brand.
- Colors: cream #FAF5EE, clay #B85C38, ink #1F1A14, sage #7A8B6F. Fonts: Fraunces (display), Inter (body).
- Locked bio language: "elementary teacher" (not primary), "au pair" (not nanny), "high profile family in Australia" (not Forbes-list, not American), "half a decade" teaching (not a decade), traveled the world solo as an au pair (NOT with the family).
- Canonical hero intro: "I'm Madison. I spent years as an au pair for a high profile family in Australia. Half a decade as an elementary teacher. A lifetime in childcare before becoming a mom myself. I help mothers raise capable, confident, resilient kids without the chaos."
- Signature framework: Capable Kid Equation = Connection / Regulation / Skill. Ebook expands it into "Foundation Before Freedom."

## The funnel and the roadmap
Current: TikTok > landing page > email > free guide (LIVE). LIVE as of July 2026: "The Capable Toddler" Guidebook sells for $9.99 via Stripe payment link `https://buy.stripe.com/cNieVf1mY7yr3P108r5ZC00` (Tyler's Stripe account); after payment Stripe redirects to `/download` which serves the PDF. Always call it the "Guidebook" in user-facing copy, never "e-book". Next: MailerLite + ManyChat. Flagship: "Raising Capable Kids" course, $97 to $197 (scaffold on request). Build any stage only when Madison asks.

## How to work with Madison
She speaks in plain language ("change my headline," "show me my leads," "build the ebook checkout"). Translate that into edits, commits, and pushes. Always confirm what went live with a URL. Keep things simple and few-steps-at-a-time.
