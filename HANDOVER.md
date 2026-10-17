# Shared handover

## 2026-10-17 — Codex — repository bootstrap
- Completed: private repository; shared rules, task register, status, decision log, Claude entry point and audit reference.
- Shopify changes: none during this audit/setup.
- Tests: documentation only; verified repository visibility and uploaded file reads. No app tests apply.
- Current implementation task: none claimed.
- Claude's current local work: unknown; no direct session access.
- Next: Claude reconciles its existing local project before any implementation claim.
- Dependencies: confirm business shipping/delivery facts; current mobile measurements and cart/checkout QA missing.

## Append future entries using this template
Date/time/timezone:
Agent:
Task ID:
Branch and commit:
Files changed:
Evidence and checks actually run:
Prepared / reviewed / approved / deployed / verified state:
Approval reference and scope (if any):
Blockers:
Next action / proposed owner:

## 2026-10-17 20:30 Asia/Shanghai — Claude Code ("Sales plan" Claude project) — YAA-001 reconciliation
Date/time/timezone: 2026-10-17, about 20:30 Asia/Shanghai (12:30 UTC).
Agent: Claude Code, working for the "Sales plan" Claude project only. Other Claude projects (Roadmap, Operations, Marketing, Retention, e-commerce/web lane) are not reconciled here. Their work is listed only where it overlaps the sales lane.
Task ID: YAA-001 (sales-plan scope).
Branch and commit: `claude/YAA-001` (claim commit pushed first, then this reconciliation commit). No changes to `main`.
Files changed: HANDOVER.md (this entry), TASKS.md (YAA-001 status, new sales-lane section, overlap list), DECISIONS.md (appended record of the sales-plan approvals given before this repo existed, plus the open offer conflict), docs/sales-plan/execution-log-2026-10.md (new; the original project log with a status note).

### Repository and local state found
- This Claude project had **no local clone, no commits and no branches** for this repo before today. Its work lived in the Claude project docs (`claude/sales-execution-log.md`) and in live Shopify changes.
- The repo was cloned fresh (shallow) at main `23deff5`. Working tree clean. Only remote: `origin` → github.com/jian-li5/you-are-angel, which was not changed. Only remote branch before this session: `main`.

### Completed sales-plan work: live store changes made 11–16 Oct 2026, before this repo and its read-only rules existed
Jian explicitly directed and approved these in the Sales plan Claude project chat (see DECISIONS.md). **State as of 2026-10-17 (all checks read-only):**

| Date (2026) | Change | Evidence now | Current state |
|---|---|---|---|
| 11 Oct | Removed the €0,00 compare-at price from 126 variants on 30 products | Sample variant 52134564266248: compareAtPrice null | Deployed; still in place |
| 11 Oct | "Free Shipping for all orders!" automatic discount renamed "Free shipping on every order"; now combines with order and product discounts | updatedAt 2026-10-11T13:20:01Z; combines order+product true | Deployed; still in place |
| 11 Oct | Popup 10% codes (SW-…) and the "20% off $199+" offer set to combine with free shipping | SW discount updatedAt 13:20:01Z, shipping combine true | Deployed |
| 11 Oct | BUY 2 GET 1 FREE end date set to 15 Oct 23:59 CDT | **Reversed later**: endsAt null, updatedAt 2026-10-11T15:16:11Z | **Superseded outside this project** (see conflict C1) |
| 11 Oct | "Any 2 sets – 15% off" automatic discount created, scheduled from 16 Oct | discountNode 2179171746056 returns **null (deleted)** | **Superseded outside this project** (C1) |
| 11 Oct | Inventory policy set to CONTINUE ("made to order") for every variant of 139 products; the brochure was excluded | Sample variant shows CONTINUE; theme shows a "Preorder" button | Deployed. The aggregate count query was inconclusive (the filter returned the total for both policies) |
| 11 Oct | Created the collection "Angel Essentials – Your First Set" (13 products at $25.99) | collection exists, 13 products | Deployed |
| 11 Oct | Scheduled task "YAA Monday sales scorecard" (Mon 08:52 Asia/Shanghai, read-only) | Scheduled task trig_01LTZEjbUAiGpSAHnoSYoeGb | Active. **Its prompt was edited by another session at 2026-10-11T15:16:29Z** to treat B2G1 as the single main offer |
| 14 Oct | New Shopify market "United States" in USD, taxes added at checkout; US removed from International | markets query: United States / USD / ACTIVE | Deployed; checked live on 14 Oct (Petal Parade showed $35.99 USD) |
| 14 Oct | Cost-per-wear and "Preorder = hand-made, +5–7 days" Custom Liquid block on template `product.yaa-template-product-page` | Live page checked 14 Oct; MAIN theme updatedAt 2026-10-14T08:45:05Z | Deployed. **Jian pasted it in the theme editor** using text Claude drafted |
| 14 Oct | Product Shipping tab changed to "Delivered in 7–10 working days" (+5–7 days for Preorder sizes) | Live page checked 14 Oct 08:33 UTC | Deployed by Jian with text Claude drafted. **Conflicts with the Shipping Policy** (7–15 working days production + 7–20 transit, per the Codex audit), see C2 |
| 14 Oct | Microsoft Clarity installed through its Shopify app (project ID yxig89stuu) | App embed in settings_data; tracking code checked loading 14 Oct | Deployed by Jian; checked by Claude |
| 14 Oct | Checked that back-in-stock buttons hide on Preorder sizes | Checked in a real browser: hidden when the variant is available | No change needed |

### Prepared, not deployed
- **Draft theme `DRAFT 16 Oct – social links + 2 sets 15% off`** (OnlineStoreTheme/203557044488, UNPUBLISHED, last updated 2026-10-15T20:08:23Z). It is a copy of the MAIN theme with:
  - Instagram, TikTok and YouTube links
  - a FOLLOW US footer column with social icons
  - "Any 2 sets 15% off" text in the announcement bar, its dropdown panel and the product-page scrolling text

  **Do not publish as-is.** Its offer text no longer matches the live discounts (C1). The homepage "Free shipping on orders over $59.00" line was not fixed in it. Publishing would also wipe out any MAIN-theme edits made after 2026-10-15. Under AGENTS.md it needs a fresh, explicit, scoped approval.

### Checks actually run today (read-only)
- git: clone, status, remote -v, branch -a, ls-remote.
- Read AGENTS.md, CLAUDE.md, README.md, PROJECT_STATUS.md, TASKS.md, HANDOVER.md, DECISIONS.md and the text of reports/You_Are_Angel_Audit_2026-10-17.html.
- Shopify GraphQL reads:
  - themes, active/scheduled discounts, markets, the collection
  - specific discount nodes: B2G1, free shipping, popup code, deleted bundle, and three codes created 11 Oct
  - one sample variant
- ShopifyQL: sessions by day, 11–17 Oct (shop timezone). 70 sessions, 5 cart-addition sessions, 5 reached-checkout sessions, 0 completed. Sessions from team testing are not excluded.
- Listed this account's scheduled tasks.

Not run: storefront render of the draft theme (the computer link and Chrome extension dropped, and storefront fetches are blocked from the container); no cart or checkout tests; no app tests (none apply).

### Conflicts and overlaps (flagged, not resolved)
- **C1 — Main offer (P0, Jian to decide).** Jian's decision in the Sales plan project (11 Oct): "Any 2 sets – 15% off" replaces B2G1 from 16 Oct. The store now has B2G1 active with no end date and no 15% bundle (changed 2026-10-11T15:16Z). Other lanes now assume B2G1 is the main offer:
  - the Roadmap cross-plan review scheduled task
  - the edited sales scorecard prompt
  - the Operations daily check: Black Friday bundle 27–30 Nov, B2G1 paused, back 1 Dec

  Sales lane takes no action until Jian confirms which is current. Related: YAA-009 (promotion margin).
- **C2 — Delivery promise (overlaps YAA-002, owner Codex + user facts).** Live product tab, banner and trust line say 7–10 working days; Shipping Policy says 7–15 production + 7–20 transit; the Preorder note adds +5–7 days. Sales lane will not edit wording; YAA-002 owns it.
- **C3 — Draft theme vs YAA-010 / e-commerce lane.** Draft 203557044488 overlaps any theme work in YAA-010 and the e-commerce lane. Proposed: YAA-010 owner decides whether to rebuild the draft from the current MAIN theme with the confirmed offer.
- **C4 — Discount codes created 11 Oct, not by this project's session:**
  - WELCOME10 ("Sales · Welcome 10% first order")
  - ANGELGLOW15 (Retention: photo/video thank-you)
  - ANGELRETURNS (Retention: win-back)

  Overlaps the sales plan's welcome and UGC offers. Treat the Retention codes as owned by Retention. WELCOME10's origin is unknown; confirm its owner. The SW- popup codes are also 10% first-order offers, so check for duplicates (YAA-007).
- **C5 — Phone test order.** Listed in the sales plan, the Ops tracker (OPS-06), Marketing week 1 and YAA-007. It is a state-changing test, so it needs explicit approval and one owner. Proposed: Codex writes the QA matrix (YAA-007); Jian runs the test.
- **C6 — Tracked links / UTMs.** Sales-plan creator and bio links overlap YAA-005 (Codex UTM audit). Proposed: Codex defines the UTM convention; the sales lane applies it to creator codes and bio links.

### Prepared / reviewed / approved / deployed / verified
See the table. Pre-repo changes are approved (in chat) and deployed; verification is noted per row. Draft theme: prepared only. Nothing was changed in Shopify, deployed or published in this session.
Approval reference and scope: DECISIONS.md, "2026-10-11 to 2026-10-16 — Sales plan project (pre-repo approvals)".
Blockers:
- C1 offer decision
- creator list (name, handle, date sent, posted Y/N) for creator codes
- TikTok bio link check
- agent access to Shopify admin: Cloudflare check fails in both the Claude browser and Chrome; Jian uses Safari
Next action / proposed owner:
1. Jian resolves C1.
2. Codex reviews this branch and the overlap list, then merges or comments.
3. The sales lane then takes YAA-013 and YAA-014 when their inputs arrive.
4. PROJECT_STATUS.md still says the Claude connection is unverified; it is now verified for this project. Left for the file owner to update.

## 2026-10-17 21:00 Asia/Shanghai — Claude Code ("E-Commerce plan" Claude project) — YAA-001 reconciliation
Date/time/timezone: 2026-10-17, about 21:00 Asia/Shanghai (13:00 UTC).
Agent: Claude Code, working for the "E-Commerce plan" Claude project only (plan section 5: conversion and store). The Sales plan entry above is unchanged and still stands for its lane. Marketing, Retention, Operations and Roadmap projects are not reconciled here.
Task ID: YAA-001 (e-commerce scope).
Branch and commit: `claude/YAA-001-ecommerce`, branched from `claude/YAA-001` (67a6516) so the sales-lane changes are kept. Claim commit pushed first, then this commit. No changes to `main` or `claude/YAA-001`.
Files changed: TASKS.md (YAA-001 status note; new "E-commerce-plan lane" section, YAA-019..025), HANDOVER.md (this entry), DECISIONS.md (appended pre-repo e-commerce record).

### Repository and local state found
- This project had **no local clone, commits or branches** before today. Its work lived in one project chat (11 Oct) and one live store change.
- Fresh shallow clone of main `23deff5`, clean tree. Only remote `origin` → github.com/jian-li5/you-are-angel, unchanged. Remote branches found: `main`, `claude/YAA-001` (sales lane, pushed 20:21 today, status review).
- Project docs: only the 50-sales plan (.docx). No e-commerce project memory or execution log existed.

### Completed e-commerce work (before this repo and its read-only rules)
| Date (2026) | Work | Evidence now (read-only, 17 Oct) | State |
|---|---|---|---|
| 11 Oct | Read-only audit of plan section 5: themes, header/footer/product templates, discounts, shipping rates, markets, 90-day sessions by device | Project chat, 11 Oct | Done. Its open questions (shipping, offer, social URLs) were never answered in this project; the sales lane settled the first two on 11 Oct (see its entry), so they are superseded here |
| 11 Oct | Cleared compare-at price 0.00 on 30 products / 136 variants (incl. the 20-variant Angel Aura Shimmer Base Set) | Variants 52134564266248, 52746109092104, 52806873448712: compareAtPrice null | Deployed; still in place. **Duplicate log:** the sales entry records the same fix as 126 variants on 30 products. Both sessions ran the same change the same day; result is identical. Count it once |

Approval reference: DECISIONS.md, "2026-10-11 — E-Commerce plan project (pre-repo)".

### Plan section 5 "Fix first" items — status on 17 Oct (live MAIN theme 203435966728, published 14 Oct)
| Item | Status | Evidence | Next |
|---|---|---|---|
| Social links in header/footer | **Not live.** No social URLs in MAIN settings; footer has no social column | config/settings_data.json, sections/footer-group.json (updated 14 Oct 07:24 UTC) | Prepared in sales draft 203557044488 → YAA-012 |
| Countdown timer | **Still enabled** on product.json and product.yaa-template-product-page.json; homepage collections have show_countdown true | Template JSON | YAA-019. Whether it actually renders is unverified (hypothesis: only when a sale end date exists) |
| Replace expiring promotion | **Done (wording)** by sales lane/Jian 14 Oct: bar now reads B2G1 + free shipping + 7–10 working days + size link, no expiry date | sections/header-group.json | Offer itself open in YAA-011 |
| Pixels (TikTok, Meta) and purchase events | **Missing data.** API read denied (needs read_pixels). Clarity app embed present | webPixel query error; settings_data | YAA-021 |
| Mobile speed and checkout on a phone | **Not done.** No measurement; no checkout test (needs approval) | — | YAA-006, YAA-007/015 |

"Build next" items found already live on the yaa product template (used by all active products per a template_suffix count of 143/143; that filter was unreliable for the sales lane, so treat as likely, not confirmed): size-guide popup, cost-per-wear and Preorder block, trust line, Shipping tab, Refund & Exchange tab, low-stock bar disabled. Not live: reviews block (disabled; Judge.me badge only), homepage customer photos, cart prompt, TikTok landing page.

Other findings still open from 11 Oct: header mega-menu demo text ("All Skin Care / UP TO 30% OFF", "All Body Care / FREE SHPPING") and the "Stawberry Bloom" title (YAA-020). 13 designs priced below the plan's $29.99 floor were kept as entry items by Jian's sales-lane decision; no action here.

### Checks actually run today (read-only)
- git: clone, status, remote -v, branch -a, ls-remote (twice, before branching), fetch, log and diff of `claude/YAA-001`.
- Read AGENTS.md, CLAUDE.md, README.md, PROJECT_STATUS.md, TASKS.md, HANDOVER.md, DECISIONS.md and the sales execution log. The audit HTML was not re-read in full.
- Shopify GraphQL reads: themes; three sample variants; MAIN header-group, footer-group, settings_data, product.json and product.yaa-template-product-page.json; active product counts. webPixel read denied.
- Not run: storefront render, mobile speed, cart/checkout, discounts and shipping rates (not re-read today; see sales entry for 17 Oct discount state). No app tests apply.

### Prepared / reviewed / approved / deployed / verified
Compare-at fix: approved (pre-repo, in chat), deployed, verified by sample. Everything else from this lane: not prepared. Nothing was changed in Shopify, deployed or published in this session.

### Dependencies
- YAA-011 (main offer) blocks YAA-019 timer wording, YAA-022, YAA-024, YAA-025.
- YAA-012 draft decision blocks YAA-019 and YAA-020 (one draft for both lanes).
- YAA-018 (admin access) blocks YAA-021 and any theme-editor check.
- YAA-008 blocks YAA-023. YAA-002 owns all delivery wording.

### Blockers
- Pixel status needs Jian (Shopify admin › Settings › Customer events) or a read_pixels scope.
- No agent browser path into Shopify admin (YAA-018).

### Next action / proposed owner
1. Codex reviews `claude/YAA-001-ecommerce` (it contains `claude/YAA-001`, so merging this branch merges both lanes) and accepts or changes the proposed owners.
2. Jian answers YAA-011 and checks pixels (YAA-021).
3. Once accepted, the e-commerce lane claims YAA-003 or YAA-019/020 (in one rebuilt draft), pushing a claim first.
4. PROJECT_STATUS.md still says Claude is unverified; left for its owner to update.
