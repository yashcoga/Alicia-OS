# Funnel: AI Life Summit (Wed–Thu Nov 18–19, 2026, 1:00 PM ET)

Status (2026-11-05): Alicia's team finished the pages as Claude artifacts. We rebuild them in GHL **exactly as approved**, then connect the form, Stripe and the workflows. **Kit zip received** and unzipped to `source/highlevel-kit/ghl-kit/` (its page text matches the artifacts exactly; its brief is `CLAUDE-INSTRUCTIONS.md`). Domain: **aibusinesssummit.com**.

Spec: Alicia's email, `reference/source-docs/2026-11-05_alicia-email-summit-build-instructions.md`. Summary in `brain/04-funnel-map.md`.

| Step | Page | Source (as supplied) |
|---|---|---|
| /ailife | Registration (free) | `source/claude-pages/registration.html` · text `copy/registration-as-supplied.txt` |
| /ailife-vip | VIP upgrade $47 + Summit Notes bump | `source/claude-pages/vip.html` · `copy/vip-as-supplied.txt` |
| /ailife-confirmed | Free thank-you (after "No thanks") | built by us from the email, step 8: `design/confirmed.html` → `ghl/confirmed.ghl.html` |
| /ailife-vip-confirmed | VIP thank-you (after buying; **our addition**, not in Alicia's spec) | `design/vip-confirmed.html` → `ghl/vip-confirmed.ghl.html` (button to Bonus Downloads) |
| ⛔ extra step (suggest /ailife-wall) | Testimonial wall (opened from "More from the chat →" on registration) | `source/claude-pages/testimonial-wall.html` ✅ coded |
| ⛔ extra step (suggest /ailife-bonuses) | VIP Bonus Downloads portal (linked from the VIP email) | `source/claude-pages/bonus-downloads.html` ✅ coded |

Design: background `#111111`, pink `#F04E98` (hover `#FF6BAB`/`#FF7AB8`), off-white `#F7F6F3`, greys `#BFC3C7` `#292929` `#E5E5E5`. Fonts: Cormorant Garamond (headlines) + Montserrat (body).

## Build status (2026-11-05)

- **Registration page:** `design/registration.html` = Alicia's page with the Claude runtime removed, dates changed (table below), images split out to `assets/registration/` (27 files, `UPLOAD-LIST.md`). Test GHL output: `ghl/registration.ghl.html` (html-to-ghl converter, no warnings). **Waiting on:** GHL image links (the user uploads), then re-run with `--assets` and do the harness check.
- The form is a **GHL form embed** (iframe) in the hero slot. Set `AILIFE_CONFIG.FORM_ID` in the page code once the form exists in Sites → Forms. The form fields, SMS checkbox, pink button and the redirect to /ailife-vip are set in the GHL form builder.
- **VIP page:** split into 5 code pieces around GHL's native one-step Order Form (it can't live inside custom code). Sources `design/vip-*.html`, GHL code `ghl/vip-*.ghl.html`, images `assets/vip/` (7 new files, `UPLOAD-LIST.md`; 5 more reused from registration). Layout in GHL:
  1. Section, full width: `vip-1-top` (nav + hero; buttons jump to `#upgrade`, "No thanks" → /ailife-confirmed).
  2. Section, background `#F7F6F3`, padding 80px top/bottom, row with 2 columns (about 55/45):
     - Left column: `vip-2a-includes-left-column`.
     - Right column, background `#111111`, radius 10px, padding 32px: `vip-2b-price-box-above-order-form` → **GHL One-Step Order Form** ($47 product, Order Bump "The Summit Notes", button "Yes! Upgrade me to VIP for $47", pink `#F04E98`, on purchase → /ailife-confirmed) → `vip-2c-terms-below-order-form`.
  3. Section, full width: `vip-3-bonus-pack-to-footer` (bonus pack, reasons, proof, final CTA, FAQ, footer).
- **2026-11-05 polish:** em dashes removed from every page (headlines, placeholders, tab titles, the VIP step separator is now →). In-page buttons (#register, #upgrade) scroll smoothly, land 24px above the target and give it a short pink glow; also works when a page opens with `#register` (from the testimonial wall). All `ghl/` files regenerated.
- **VIP page, single file (reference):** `design/vip.html` → `ghl/vip.ghl.html` (scope `ghl-vip`). Whole page in one piece, with a dashed `[GHL ORDER FORM GOES HERE]` box where the checkout goes (fake card form and bump checkbox removed; "No thanks" → /ailife-confirmed). Use it to view or review the whole page. For the live GHL build, still paste the 5 pieces, because GHL's order form can't sit inside a code block.
- **Testimonial wall:** `design/testimonial-wall.html` (date → Nov 18–19; both "Save my free seat" buttons → `/ailife#register` instead of aibusinesssummit.com), GHL code `ghl/testimonial-wall.ghl.html` (scope `ghl-wall`, page background `#F7F6F3`). 32 images: 23 reused from registration, 9 new in `assets/testimonial-wall/` (`UPLOAD-LIST.md`). Preview: `preview/3-testimonial-wall.html`.
- **VIP Bonus Downloads page:** `design/bonus-downloads.html` (date → Nov 18–19), GHL code `ghl/bonus-downloads.ghl.html` (scope `ghl-bonus`). Its 3 images are reused from registration/vip; the 2 PDFs from the kit are in `assets/bonus-downloads/` (`UPLOAD-LIST.md`). The "Open the PDF" buttons get the PDF links on the `--assets` re-run (`starter-pack.pdf`, `holiday-planner.pdf`). Journal button keeps the Claude link (per the kit). Preview: `preview/5-bonus-downloads.html`.
- The HTML Summit Notes checkbox and the fake card field were removed: the bump and the card field come from the GHL order form.
- "More from the chat →" now points to `/ailife-wall` (⛔ confirm the step name for the testimonial wall).
- Filled from the team brief: time **1:00 PM ET**. Dates Nov 18-19 confirmed by Michael (2026-11-05); registration-close line removed at his request.
- Left as supplied: "Thanksgiving is nine days after the summit" (now 7–8 days) ⛔ Alicia to reword; the Refund Policy link (points to /terms).

## 1. Date changes: her files say Mon–Tue Nov 16–17; the user confirmed Wed–Thu Nov 18–19

| Where | Supplied text | Change to |
|---|---|---|
| Registration header | Nov 16–17, 2026 · Live on Zoom · Free | Nov 18–19, 2026 |
| Registration hero + final CTA (×2) | November 16–17, 2026 • [TIME & TIME ZONE] | November 18–19, 2026 • 1:00 PM ET |
| Registration hero | By Tuesday night, it's running… | By Thursday night |
| "This morning" section | You'll leave Monday night with yours. | Wednesday night |
| Results section | After November 17, you won't either. | After November 19 |
| "Why this isn't another webinar" | nothing in your life changes by Wednesday | by Friday ⛔ (confirm wording) |
| Agenda | Monday, November 16 / Tuesday, November 17 | Wednesday, November 18 / Thursday, November 19 |
| Register-now section | Register by Sunday, November 15 at 11:59 PM [TIME ZONE] | **Removed** (Michael, 2026-11-05: no registration-closing messaging). Now: "The summit is free. Register and your seat is saved for both days." |
| Final section heading | Your 2027 Starts November 16 | November 18 |
| Final section | Picture Tuesday night. | Thursday night |
| FAQ (business owners) | They'll do AI by Tuesday. | by Thursday |
| 12 jobs + VIP bonus 2 | Thanksgiving is nine days after the summit. | ⚠ Day 1 → Thanksgiving is now **8 days**, last day → **7**. Rewrite the line ⛔ |
| VIP bonus 2 + Bonus Downloads | "The nine-day countdown" (Thanksgiving planner PDF) | ⚠ The PDF is built as a 9-day countdown. Ask whether it stays as is |
| Testimonial wall CTA | Your turn. November 16–17. | November 18–19 |
| Bonus Downloads header | The AI Life Summit · November 16–17 | November 18–19 |
| Confirmation page (email step 8) | You're in. See you Monday, November 16. | See you Wednesday, November 18. |
| SMS reminders (email step 9) | Sunday night, Monday and Tuesday an hour before | Tuesday night, Wednesday and Thursday at 12:00 PM ET |

## 2. Placeholders Alicia still owes (leave the [brackets]; don't guess)

Registration: VSL video · one-line testimonial (name + city) · Story 1 · Story 2 · Zoom seat cap [X] · time zone. (The time is 1 PM ET per the team brief.)
VIP: Summit Notes $[PRICE] · guarantee / refund wording · "after you leave, the upgrade goes to [FULL PRICE OR 'is gone']" · [STATEMENT DESCRIPTOR] · recordings timing · optional VIP extra (Zoom Q&A / FB thread: confirm or delete) · [CONFIRMATION PAGE URL].

## 3. Things to fix or decide during the build

1. **Links to Claude pages:** "More from the chat →" on registration goes to the testimonial-wall Claude page, and "Open my journal" (Bonus 3, 2027 Goal Journal) goes to another Claude page (`claude.ai/artifact/FvshFrsf…`). Both need a home in GHL or a decision to keep the Claude link.
2. **Testimonial wall** "Yes! Save my free seat" links to aibusinesssummit.com, not /ailife.
3. **Legal links:** "Refund Policy" points to aiinnovision.com/**terms**; "Earnings & Results Disclaimer" is an on-page anchor. Need the real refund URL.
4. **Form field:** the email says "What do you want to fix first?" is a text field; the page has a dropdown with 6 options. Build it as a dropdown (matches the page).
5. ~~Domain~~ ✅ aibusinesssummit.com (kit brief: already connected).
6. Support email on these pages is hello@aiinnovision.com (the consultant page uses support@). Fine, but note it.
7. The Mega Bundle pitch on Day 1 isn't mentioned on these pages (expected; no change).
