# Working in this folder

This is the client operating system for **Alicia Lyttle**, AI strategist and CEO of **AI InnoVision** (with her sister Lorette Lyttle, COO). Her main high-ticket offer is the AI Consultant Certification (becomeanaiconsultant.com). We build her funnels (copy and design) in GoHighLevel. See [README.md](README.md) for the map.

## Before writing copy or designing anything

1. Read `brain/02-offer-and-event.md` and `brain/03-voice-and-messaging.md`. They hold the facts and the compliance rules.
2. For design, read `design/design-system.md` and look at the screenshots in `funnels/*/qa/shots/` and `reference/model-funnels/`.
3. Check `brain/06-open-items.md` for what is still unconfirmed.

## Non-negotiables

- **Education, not financial, tax or legal advice.** No income, client or "guaranteed" promises (e.g. no "make $10K/month as an AI consultant").
- **No guaranteed outcomes.** Use Alicia's own track record (facts) as proof. Student results only if approved and shown with the earnings disclaimer.
- **Never invent** credentials, figures, testimonials, bonuses, value stacks, program names, prices or dates. Use `[PLACEHOLDER]`s and add the question to `brain/06-open-items.md`.
- **One set of numbers everywhere.** Once her figures are confirmed, list them here and use only those.
- **Current campaign (Nov 2026):** **AI Life Summit**, free, **Wed–Thu, November 18–19, 2026, 1:00 PM ET**. The **Black Friday Mega Bundle** ($5,000) and the low-ticket bundle both close **November 30 at 11:59 p.m. PT**. Keep names, dates and times identical on every page, email and SMS. Full details are in `brain/02-offer-and-event.md`.
- Bundle values must be **verified** normal prices. Never promise bonuses that aren't confirmed.
- Keep politics off the pages.

## Conventions

- New funnel work lives in `funnels/<funnel-name>-<mon>-<year>/` (copy/, design/, ghl/, qa/, and source/ for raw inputs).
- Funnels shared as examples or models (not a build of ours) go in `reference/model-funnels/<name>/` with notes + screenshots.
- Dated snapshots of client docs go in `reference/source-docs/`. The client's Drive/Docs are the source of truth, so re-pull before finalizing.
- When facts change, update the relevant `brain/` file and its "Last updated" date rather than adding scattered notes.
- Shared photos and logos live in `assets/` (index in each README).
- Internal or sensitive material (team contacts, internal links, test coupon codes, strategy) goes in the local-only files listed in `.gitignore`.
- Agency-wide material (SOPs, team tasks) belongs in `COGA/SOP/`, not here.
- Use the `html-to-ghl` skill to port finished HTML into GHL, the `funnel-audit` skill for pre-launch QA, and `page-speed-optimization` for speed.
- Playwright screenshots land in `.playwright-mcp/` (ignored). Copy the ones worth keeping into `funnels/*/qa/shots/` or `reference/`.
