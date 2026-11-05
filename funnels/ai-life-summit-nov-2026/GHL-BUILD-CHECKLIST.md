# AI Life Summit: GHL build checklist

Do the steps in order. Tick each box as you go. Code files are in `ghl/`.

## Step 1: Images (do this first)

- [ ] In GHL → **Media Storage**, make a folder "AI Life Summit".
- [ ] Upload all files from `assets/registration/` (27), `assets/vip/` (7), `assets/testimonial-wall/` (9) and the 2 PDFs in `assets/bonus-downloads/`.
- [ ] Copy each file's link into the 4 `UPLOAD-LIST.md` files (registration, vip, testimonial-wall, bonus-downloads), then send them to Claude.
- [ ] Claude sends back the **final** code files with the images connected. Use only those for pasting (the current files don't show images yet).

## Step 2: Products and payments

- [ ] **Payments → Products:** "AI Life Summit VIP Access", $47, one-time. Description: "Lifetime recordings of both days, chaptered by job, plus the VIP bonus pack: The Life Assistant Starter Pack, The Thanksgiving & Holiday Planner, and the 2027 Goal Journal."
- [ ] **Payments → Products:** "The Summit Notes", one-time, price ⛔ (waiting on Alicia). Description: "Every prompt and every step from both days, written out in one PDF."
- [ ] Stripe is connected to this sub-account (Payments → Integrations).

## Step 3: Registration form

- [ ] **Sites → Forms → new form** "AI Life Summit — Registration" (wording from Alicia's kit):
  1. Full Name (required)
  2. Email (required)
  3. Custom field "What do you want to fix first?" (not required). Kit allows text or dropdown; the page shows a dropdown: My inbox and calendar · Dinner and the holidays · Money and credit · A side hustle · The trip · My 2027 goal
  4. Checkbox (unchecked) saved to a new custom field "SMS reminders consent": "Text me the reminders and the Zoom link." Help text: "Msg & data rates may apply. Reply STOP to opt out, HELP for help."
  5. Phone, label "Phone (optional, for the text reminders)" (not required)
  6. Style: background `#292929`, white fields, button "Yes! Save my free seat" in `#F04E98`
- [ ] Form settings → on submit: **redirect to /ailife-vip**.
- [ ] Copy the form's **ID** (Integrate → Embed: the part after `/widget/form/`) and send it to Claude (it goes into the page code).

## Step 4: Funnel

- [ ] **Sites → Funnels → new funnel** "AI Life Summit — Nov 2026" with steps: `/ailife`, `/ailife-vip`, `/ailife-confirmed` (free thank-you), `/ailife-vip-confirmed` (VIP thank-you), plus the 2 side pages in steps 7a and 7b.
- [ ] On each page: Settings → **turn off "Optimise JavaScript"**; page background `#111111`.

## Step 5: Registration page (/ailife)

- [ ] Add a section (full width, padding 0) → row → **Custom JS/HTML** element → paste `ghl/registration.ghl.html`.
- [ ] Settings → SEO: title "The AI Life Summit: Free, Nov 18–19, 2026", description "Two free live days with Alicia Lyttle. Set up a free AI personal assistant that runs your home, your money and your schedule."

## Step 6: VIP page (/ailife-vip)

- [ ] Section 1 (full width, padding 0) → Custom JS/HTML → paste `ghl/vip-1-top.ghl.html`.
- [ ] Section 2: background `#F7F6F3`, padding 80px top and bottom. Row with **2 columns**:
  - Left column → Custom JS/HTML → paste `ghl/vip-2a-includes-left-column.ghl.html`.
  - Right column: background `#111111`, rounded corners 10px, padding 32px. Add in this order:
    1. Custom JS/HTML → paste `ghl/vip-2b-price-box-above-order-form.ghl.html`
    2. **One-Step Order Form**: product "AI Life Summit VIP Access" $47; **Order Bump** on with "The Summit Notes", bump headline "Yes, add The Summit Notes"; button "Yes! Upgrade me to VIP for $47" (`#F04E98`); after purchase → **/ailife-vip-confirmed** (the "No thanks" links already go to /ailife-confirmed)
    3. Custom JS/HTML → paste `ghl/vip-2c-terms-below-order-form.ghl.html`
  - Give the right column the element ID `upgrade` (so the top buttons jump to it).
- [ ] Section 3 (full width, padding 0) → Custom JS/HTML → paste `ghl/vip-3-bonus-pack-to-footer.ghl.html`.

## Step 7: Thank-you pages (2)

Alicia's spec had one page for everyone; we split it (decided 2026-11-05) so VIP buyers get a "You're VIP" page with a button to their bonuses. Tell Alicia.

- [ ] **/ailife-confirmed** (free, after "No thanks"): section (full width, padding 0) → Custom JS/HTML → paste `ghl/confirmed.ghl.html`.
- [ ] **/ailife-vip-confirmed** (after buying $47): same, paste `ghl/vip-confirmed.ghl.html`. Its "Open my VIP bonuses" button goes to the Bonus Downloads page (`BONUS_URL`, default `/ailife-bonuses`).
- [ ] In both, the CONFIG block at the bottom of the code holds: `ZOOM_URL` ⛔ (empty shows "[ZOOM LINK]"), `FB_GROUP_URL` (optional; empty hides the Facebook box), `DAY_LENGTH_MIN` ⛔ (how long each day runs, for the calendar entry). Both pages have "Add to Google Calendar" and "Add to Apple / Outlook" buttons for both days.

## Step 7a: Testimonial wall page

- [ ] Add a funnel step, path ⛔ (suggest `/ailife-wall`; the registration page's "More from the chat →" link already points there). Not in the sales flow: people reach it only from that link.
- [ ] Page background `#F7F6F3`. Section (full width, padding 0) → Custom JS/HTML → paste `ghl/testimonial-wall.ghl.html` (final version from Claude). Its "Save my free seat" buttons go to `/ailife#register`.

## Step 7b: VIP Bonus Downloads page

- [ ] Add a 4th funnel step, path ⛔ (suggest `/ailife-bonuses`). Not a step in the sales flow: people reach it from the VIP thank-you page button and the VIP welcome email.
- [ ] Section (full width, padding 0) → Custom JS/HTML → paste `ghl/bonus-downloads.ghl.html` (final version from Claude, with the PDF links).

## Step 8: Workflows: SKIP (not part of the funnel team's task; decided 2026-11-05). Kept below for reference only.

- [ ] "AI Life Summit — Registered": form submitted → tag `ailife-registered` → confirmation email (subject "You're in: The AI Life Summit, Nov 18–19", with the time, the Zoom link and a line that the VIP upgrade is at /ailife-vip) → if SMS consent is checked: tag `ailife-sms` → 3 texts: **Tue Nov 17, 6:00 PM ET**, **Wed Nov 18, 12:00 PM ET**, **Thu Nov 19, 12:00 PM ET** (each with the Zoom link and "Reply STOP to opt out").
- [ ] "AI Life Summit — VIP": order submitted → tag `ailife-vip` → VIP welcome email with the Bonus Downloads link and "Each day's recording lands in your portal within 24 hours" (⛔ Alicia may change this).

## Step 9: Domain

- [ ] Set the funnel's domain to **aibusinesssummit.com** (Alicia's kit says it's already connected) so the pages are aibusinesssummit.com/ailife, /ailife-vip, /ailife-confirmed.

## Step 10: Test before going live

- [ ] Register once **with** the SMS box ticked and once **without**: check tags, the consent field and the confirmation email.
- [ ] Buy VIP in Stripe **test mode**, with and without the Summit Notes bump: check tags and the VIP email.
- [ ] Open all 3 pages on a phone.
- [ ] Send the preview links to Claude for a final check, then to Alicia.

## Still waiting on Alicia (keep the [brackets] until then)

VSL video · one testimonial line · Story 1 and Story 2 · Zoom seat cap · Summit Notes price · refund wording · card statement descriptor · VIP price after this page ("full price" or "is gone") · when the recordings arrive · Zoom link · Facebook group link · new wording for "Thanksgiving is nine days after the summit".
