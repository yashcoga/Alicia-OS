# Funnel: Black Friday Mega Bundle sales page (Nov 2026)

Status (2026-11-06): **design v2: real images from the design team placed**; v1 built from the final outline (`copy/outline.md`, v4), for review. Same branding as the AI Life Summit and waitlist pages. Headline option C (user).

| Step | Page | Design | GHL code |
|---|---|---|---|
| /[PATH] | Sales page + Whop checkout | `design/sales.html` · `preview/1-sales.html` | `ghl/sales.ghl.html` (scope `ghl-mbsales`) |
| /[PATH] | Welcome / confirmation (after payment) | `design/welcome.html` · `preview/2-welcome.html` | `ghl/welcome.ghl.html` (scope `ghl-mbwelcome`) |

Page background `#111111` for both. Screenshots: `qa/shots/`. **Set Whop's post-purchase redirect to the welcome page URL.**
- Domain: **aliciasmegabundle.com** (same as last year) · path [PATH] · live Nov 18 to **Nov 30, 11:59 p.m. PT**
- **Checkout: Whop**, no calendar / no book-a-call (user, 2026-11-06). Every button jumps to `#checkout`.

## Page (top to bottom)
Hero (logo, pre-headline, headline C, sub, mockup + buy card with countdown/price/button; phone-only button under the sub) → Advise/Build/Create/Grow → Part 1: 3 program sections → button → Part 2: 5 bonus sections → offer stack + Whop checkout (pay-in-full / 2-payments switch) → Meet Alicia + proof strip + 3 community posts → FAQ (4) → final CTA with countdown → footer. Phones: sticky "Get the Mega Bundle · $5,000" bar (shows after the hero, hides at the checkout).

## Config in the page code (`CHECKOUT_CONFIG`)
- `CLOSES_AT` = `2026-11-30T23:59:00-08:00` (all 3 countdowns), `CLOSED_TEXT`
- `WHOP_PLAN_FULL` / `WHOP_PLAN_SPLIT`: Whop plan IDs → Whop embedded checkout (`data-whop-checkout-plan-id` + `js.whop.com/static/checkout/loader.js`). **Check the embed against Whop's current docs when the plan IDs arrive.**
- Or `WHOP_LINK_FULL` / `WHOP_LINK_SPLIT`: Whop checkout links → shows a pink button instead.
- Until filled: dashed placeholder.

## Checked 2026-11-06
- 1440, 390, 360 px: no sideways scroll, no text under 12 px, no script errors, all images load.
- Desktop 1440 × 900: hero "Get the Mega Bundle" button above the fold (bottom at 700 px). Phones: the pink button under the subheadline is above the fold.

## Placeholders still on the page
TikTok intro video + instructor name · mastermind date/place/format (bonus 1 + FAQ) · Whop plan IDs · bundle refund policy (footer) · images to upload (`assets/UPLOAD-LIST.md`, 14 files).

## Images (2026-11-06)
Lean's zip had all 12 requested images (2 logos, group mockup with and without Alicia, 8 item mockups) + 2 PSDs. Placed: logo with ribbon (hero), group with Alicia (hero), group mockup (offer stack, user's request), the 8 mockups in their sections. TikTok: mockup on the left, the instructor-video slot under the bullets.

## Copy sources
Consultant: becomeanaiconsultant.com notes · Agents: theaiagentscourse.com notes · Avatar: aibusinesssummit.com/order-aiavatar (Base contents; Base vs VIP in the bundle not confirmed) · Micro Drama: aimicrodramaadsacademy.com notes · values as approved for the waitlist. Community posts: same 3 images already on the AI Life Summit registration page.

## Welcome page (2026-11-06)
Logo → "Payment confirmed" → "Welcome to the Black Friday Mega Bundle 🎉" → group mockup with Alicia → 3 next steps (check email for the Whop receipt; logins for the 3 programs; mastermind + AI Agents Live details) → everything that's now yours (8 items) → Alicia's quote → help line support@aiinnovision.com → footer. No countdown, noindex. Placeholders: second-payment timing, when/from where logins arrive, mastermind details.

## Mobile + behaviour check (2026-11-06)
360, 390, 768, 1440 px: no sideways scroll, no text under 12 px, tap targets 40 px+, no script errors. Hero button above the fold on all widths (phone/tablet: pink button under the subheadline, shown up to 1000 px). Sticky phone bar appears after the hero and hides at the checkout. Pay-in-full / 2-payments switch, FAQ and in-page buttons work. Under 1000 px the price + checkout card comes before the item list.
