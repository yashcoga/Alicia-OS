# Funnel: Black Friday Mega Bundle Waitlist (Nov 2026)

Status (2026-11-05): copy approved (outline OK'd by the user); **design built and shortened** (4 parts: nav, hero + form, what's inside list + price box, footer) after comparing with last year's waitlist. AI Life Summit style. No mention of the AI Life Summit on these pages (user decision).

- Design: `design/waitlist.html`, `design/confirmed.html` · GHL code: `ghl/waitlist.ghl.html` (scope ghl-waitlist), `ghl/confirmed.ghl.html` · Clickable preview: `preview/1-waitlist.html` · No images to upload.
- The waitlist form is a GHL form embed: set `WAITLIST_CONFIG.FORM_ID` in the page code. Fields: name, email, optional phone, unchecked SMS consent; button "Yes! Put me on the waitlist"; redirect to the confirmation page.

- **Promotion starts:** Wednesday, Nov 11. **Offer opens:** Wednesday, Nov 18 (AI Life Summit Day 1, 1 PM ET). **Closes:** Nov 30, 11:59 p.m. PT.
- **Audience:** past VIP/Platinum buyers (6-12 months) who haven't bought the consultant program; people who booked a call and didn't buy. **Exclude current consultants** (they get the $1,000 upgrade separately).
- **Must show before they join:** all components, the $5,000 price, the verified value, the Nov 18 date, the next step (Nehemiah: fewer but more serious sign-ups).
- **Design:** match the AI Life Summit pages (`../ai-life-summit-nov-2026/design/`). The summit is where the Mega Bundle is sold (Loom 0:18 and 2:02), so it should feel like one campaign.

| Step | Page | Copy |
|---|---|---|
| /[PATH] | Waitlist page | `copy/waitlist-page.md` |
| /[PATH] | Confirmation | `copy/confirmation-page.md` |

## Verified so far

- AI Consultant Certification: $5,997 (becomeanaiconsultant.com).
- AI Agents Course: **$1,997** (theaiagentscourse.com, "Total Value $12,111"; 2 × $1,200). AI Agents Live ticket: **$1,497** value each, next event Jan 25 or 26, 2027, Atlanta (same page). Notes: `reference/model-funnels/the-ai-agents-course/`.
- Bundle: $5,000 or 2 × $2,600 (team brief).
- From the user (2026-11-05): AI Avatar Academy **$1,997**; AI Business Summit Replays **$47**; Private Micro Drama Workshop **$297** (matches the Micro-Drama add-on on Alicia's checkout). Micro Drama Academy reference: `reference/model-funnels/ai-micro-drama-ads-academy/`.
- One-Day Mastermind: **$10,000+** (user: sold for $10,000 to $12,000; we use the low end). TikTok Live Selling Training: shown as **Included**, no value, not in the total (user decision; no verified price). **Total value shown: $20,000+** (user decision 2026-11-05; items add up to $23,329).
- Still missing: TikTok instructor name, credentials and video.

## Needed from Michael / Alicia's team

Normal price and 2-3 lines on "why you need it" for each component; verified total value; mastermind details; AI Agents Live date and city; TikTok instructor name, credentials and video; the next step for waitlist members (checkout link or booked call); can they buy without attending the summit; page paths and domain.

## Decisions (2026-11-05)

- Waitlist members can buy without attending the summit (that's the point of the waitlist).
- No domain or page paths yet: keep /[PATH].

## Logo + bundle mockup (for the design team)

Logo: a "Black Friday Mega Bundle" logo (like last year's), wide format about 3:1, transparent background, for the box `#bundle-logo` at the top of both pages (it replaces the nav bar).

Mockup:

One 16:9 image of the whole bundle (like last year's mockup), for the hero box `#bundle-mockup`: AI Consultant Certification Program, AI Agents Course, AI Avatar Academy, One-Day Mastermind With Alicia, Two AI Agents Live Tickets, Micro Drama Workshop, AI Business Summit Replays, TikTok Live Selling Training. AI Life Summit colours (black #111111, pink #F04E98), title "The Black Friday Mega Bundle". Dark or transparent background.

## Countdown

Countdown sits at the **top of the left column, above the mockup**, level with the form (desktop); on phones it comes after the form, counting to **Wed Nov 18, 2026, 1:00 PM ET** (`COUNTDOWN_CONFIG.OPENS_AT` = `2026-11-18T13:00:00-05:00` in the page code). After that time it shows "The Mega Bundle is open. Check your email for your link." Change both values in the CONFIG block if the opening time changes.

## Mobile (checked 2026-11-05)

360, 390, 768 and 1440 px: no sideways scroll, no text under 12 px, tap targets 44 px+. On phones and tablets the form moves above the bundle mockup (right after the countdown).

## Above the fold (checked 2026-11-05)

The form button is above the fold at 1440 × 900, 1366 × 768 and 768 × 1024. On phones (390 × 844, 360 × 740) a pink "Join the VIP Early Access List" button under the subheadline (phones only) jumps to the form. At 1280 × 720 the form button is about 12 px below the fold. Keep the GHL form compact (4 fields + checkbox) so this still holds once the real form is in.
