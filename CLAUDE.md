# CLAUDE.md — Raising Jordans (Madison Jordan)

## Who this is for
Madison Jordan is building a motherhood brand, "Raising Jordans," on TikTok @raisingjordans. She is a former au pair for a high profile family in Australia, a half-decade elementary teacher, and a lifelong childcare expert. Her goal: grow her email list, then sell a small ebook, then launch a flagship course. She is non-technical. Do the technical work for her. Never ask her to open files or run commands you can run yourself.

## What lives in this repo
- `index.html` — landing page with email capture (hero photo `madison-tyler.jpg`)
- `guide.html` — the free 8-habit lead magnet (gated: localStorage flag unlocks `guide.html?unlocked=1`)
- `the-capable-toddler.html` — the $4.99 ebook reader (currently unlisted, pre-launch)
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
Current: TikTok > landing page > email > free guide (LIVE). Next: $4.99 "The Capable Toddler" ebook via Stripe + MailerLite + ManyChat (planned, not built). Flagship: "Raising Capable Kids" course, $97 to $197 (scaffold on request). Build any stage only when Madison asks.

## How to work with Madison
She speaks in plain language ("change my headline," "show me my leads," "build the ebook checkout"). Translate that into edits, commits, and pushes. Always confirm what went live with a URL. Keep things simple and few-steps-at-a-time.
