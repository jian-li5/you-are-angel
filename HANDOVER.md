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
Files changed: TASKS.md (YAA-001 status note; new "E-commerce-plan lane" section, YAA-040..046), HANDOVER.md (this entry), DECISIONS.md (appended pre-repo e-commerce record).

### Repository and local state found
- This project had **no local clone, commits or branches** before today. Its work lived in one project chat (11 Oct) and one live store change.
- Fresh shallow clone of main `23deff5`, clean tree. Only remote `origin` → github.com/jian-li5/you-are-angel, unchanged. Remote branches found: `main`, `claude/YAA-001` (sales lane, pushed 20:21 today, status review). Found after my claim: `claude/YAA-001-marketing` (claim only, 20:29) and `claude/YAA-001-retention` (reconciliation, 20:30). Both also branch from `claude/YAA-001`. Retention proposes YAA-023/024/025 for this lane; see TASKS.md.
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
| Countdown timer | **Still enabled** on product.json and product.yaa-template-product-page.json; homepage collections have show_countdown true | Template JSON | YAA-040. Whether it actually renders is unverified (hypothesis: only when a sale end date exists) |
| Replace expiring promotion | **Done (wording)** by sales lane/Jian 14 Oct: bar now reads B2G1 + free shipping + 7–10 working days + size link, no expiry date | sections/header-group.json | Offer itself open in YAA-011 |
| Pixels (TikTok, Meta) and purchase events | **Missing data.** API read denied (needs read_pixels). Clarity app embed present | webPixel query error; settings_data | YAA-042 |
| Mobile speed and checkout on a phone | **Not done.** No measurement; no checkout test (needs approval) | — | YAA-006, YAA-007/015 |

"Build next" items found already live on the yaa product template (used by all active products per a template_suffix count of 143/143; that filter was unreliable for the sales lane, so treat as likely, not confirmed): size-guide popup, cost-per-wear and Preorder block, trust line, Shipping tab, Refund & Exchange tab, low-stock bar disabled. Not live: reviews block (disabled; Judge.me badge only), homepage customer photos, cart prompt, TikTok landing page.

Other findings still open from 11 Oct: header mega-menu demo text ("All Skin Care / UP TO 30% OFF", "All Body Care / FREE SHPPING") and the "Stawberry Bloom" title (YAA-041). 13 designs priced below the plan's $29.99 floor were kept as entry items by Jian's sales-lane decision; no action here.

### Checks actually run today (read-only)
- git: clone, status, remote -v, branch -a, ls-remote (twice, before branching), fetch, log and diff of `claude/YAA-001`.
- Read AGENTS.md, CLAUDE.md, README.md, PROJECT_STATUS.md, TASKS.md, HANDOVER.md, DECISIONS.md and the sales execution log. The audit HTML was not re-read in full.
- Shopify GraphQL reads: themes; three sample variants; MAIN header-group, footer-group, settings_data, product.json and product.yaa-template-product-page.json; active product counts. webPixel read denied.
- Not run: storefront render, mobile speed, cart/checkout, discounts and shipping rates (not re-read today; see sales entry for 17 Oct discount state). No app tests apply.

### Prepared / reviewed / approved / deployed / verified
Compare-at fix: approved (pre-repo, in chat), deployed, verified by sample. Everything else from this lane: not prepared. Nothing was changed in Shopify, deployed or published in this session.

### Dependencies
- YAA-011 (main offer) blocks YAA-040 timer wording, YAA-043, YAA-045, YAA-046.
- YAA-012 draft decision blocks YAA-040 and YAA-041 (one draft for both lanes).
- YAA-018 (admin access) blocks YAA-042 and any theme-editor check.
- YAA-008 blocks YAA-044. YAA-002 owns all delivery wording.

### Blockers
- Pixel status needs Jian (Shopify admin › Settings › Customer events) or a read_pixels scope.
- No agent browser path into Shopify admin (YAA-018).

### Next action / proposed owner
1. Codex reviews `claude/YAA-001-ecommerce` (it contains `claude/YAA-001`; the marketing and retention branches do too, so the three lane branches will conflict only in TASKS.md and HANDOVER.md appends and the YAA-001 row) and accepts or changes the proposed owners.
2. Jian answers YAA-011 and checks pixels (YAA-042).
3. Once accepted, the e-commerce lane claims YAA-003 or YAA-041 (in one rebuilt draft), pushing a claim first.
4. PROJECT_STATUS.md still says Claude is unverified; left for its owner to update.
## 2026-10-17 ~21:00 Asia/Shanghai — Claude Code ("Marketing plan" Claude project) — YAA-001 reconciliation, marketing-plan lane
Agent: Claude Code for the "Marketing plan" Claude project only. Not covered: the Sales-plan lane (entry above, preserved unchanged) and the Roadmap, Operations, Retention and e-commerce/web projects.
Task ID: YAA-001 (marketing-plan scope).
Branch and commit: `claude/YAA-001-marketing`, branched from `origin/claude/YAA-001` (67a6516) so the Sales-lane entry is kept. Claim commit pushed first, then this reconciliation commit. `main` and `claude/YAA-001` were not touched.
Files changed:
- HANDOVER.md: this entry
- TASKS.md: the YAA-001 owner cell, and an appended marketing-lane section (YAA-050 to YAA-057; first pushed as 019–026, renumbered because the Retention lane claimed those IDs first)
- DECISIONS.md: an appended marketing-project record
- docs/marketing-plan/marketing-plan-v2-summary.md: new, with a status note

- Fresh shallow clone of main `23deff5`; working tree clean. Only remote is `origin` → github.com/jian-li5/you-are-angel (unchanged).
- Remote branches were `main` and `claude/YAA-001` (pushed 2026-10-17 20:21 +08:00 by the Sales-plan Claude session). No PRs could be listed: `gh pr list` uses GraphQL, which is blocked here, and the REST check was not run.
- This project had no earlier clone, commits or branches. Its work lives in:
  - Claude project docs: `claude/marketing-plan-v2-summary.md` and the v1 plan .docx
  - a Claude Doc: Marketing Plan v2
  - two scheduled check-ins in its chat

### Completed marketing-lane work (none of it changed the store)
| Date (2026) | Item | State | Evidence |
| 11 Oct | Marketing Plan v2 (keep/add/cut decisions, channel mix, offers and budget, 8-week plan, scorecard) | Prepared; Jian read it and gave feedback 11 Oct; not approved as store changes | Claude Doc ac313752-5de4-48e0-b76c-349019b48e49; summary at docs/marketing-plan/ |
| 11 Oct | Project summary `claude/marketing-plan-v2-summary.md` | Prepared | Claude project doc |
| 11 Oct | Week 1 checklist rewritten after Jian's feedback (5 Halloween designs, 3–4 videos, B2G1 test ticked from Jian's report) | Prepared | Doc rev 10 |
| 11 Oct | Proposed skill "yaa-weekly-scorecard" (review card) | Unknown whether Jian saved it; duplicates YAA-016, so do not use it | Chat |
| 14 Oct | Mid-week check (scheduled trigger trig_01PGG2H9zPFjxHvSDkt47gMv, read-only) | Done | Discount tiers EXPIRED; `seen-on-tiktok` absent; 39 of 48 sessions 12–14 Oct landed on `/`; no orders |
| 18 Oct (pending) | Week 1 review (trig_01Rd822QGcFnDAght5QA253w, 12:00 UTC) | Scheduled; read-only Shopify plus ticks in the marketing doc | Will log to that chat |

User-made live changes reported in this project: Jian tested B2G1 at checkout (11 Oct) and expired the 10%/$99 and 20%/$199 tiers (seen EXPIRED on 14 Oct). See DECISIONS.md.

### Current state, read-only checks 2026-10-17 ~12:55 UTC (shop tz CDT, USD)
- `/collections/seen-on-tiktok`: **does not exist** (collectionByHandle null).
- BUY 2 GET 1 FREE: active, no end date; combines with shipping = true, with order and product = false. Updated 2026-10-11T15:16:11Z.
- Free shipping on every order: active; combines with order and product discounts.
- Active codes include WELCOME10, ANGELGLOW15, ANGELRETURNS and the SW- popup codes. The tier discounts are not active.
- Inventory policy on a sampled Halloween variant: CONTINUE (made-to-order).
- Sessions 12–17 Oct by landing page: 66 in total, 54 on `/` (82%). 4 cart-addition sessions, 4 reached checkout and 0 completed, all on `/`. Team or test sessions are not excluded.
- Sales by product, 12–17 Oct: no rows, so 0 orders. The Halloween push (deadline 16 Oct) produced no recorded sales. Whether the videos were posted is not verified.

### Superseded or conflicting facts in the marketing plan (flagged, not yet edited; task YAA-051)
- **M1:** v2 says overselling is blocked and B2G1 does not combine with shipping. Both changed later on 11 Oct (13:20 and 15:16 UTC). The hero-stock rule should be reframed around made-to-order lead time.
- **M2:** v2 sets B2G1 plus free shipping as the single message. That conflicts with the Sales-lane decision for "Any 2 sets – 15% off" (YAA-011, Sales C1). Jian's 11 Oct remark favours keeping B2G1, but no decision is recorded.
- **M3:** v2's Black Friday plan (B2G1 plus a gift for the first 15 orders) conflicts with the Operations lane's bundle that pauses B2G1 (YAA-055).
- **M4:** v2's week 1 included a phone test order and app installs. Under AGENTS.md these are Jian-only, approval-gated actions (YAA-015, YAA-054).
- **M5:** v2 starts Spark Ads on 26 Oct. The Codex audit says don't expand paid traffic before checkout and attribution are verified (YAA-004/007). Deferred as YAA-056.
- **M6:** v2's 90-day metrics (13 Jul–11 Oct) and the audit's (19 Jul–16 Oct) use different windows. Both are labelled; no correction is needed.

### Checks actually run today
- git: clone (depth 1), status, remote -v, branch -a, ls-remote, fetch of `claude/YAA-001`, diff main..origin/claude/YAA-001.
- Read: CLAUDE.md, AGENTS.md, README.md, PROJECT_STATUS.md, TASKS.md, HANDOVER.md, DECISIONS.md, the audit HTML text, and the project's memory and docs list.
- Shopify reads: collectionByHandle (two handles), active discountNodes, one product's variants; ShopifyQL sessions by landing page and sales by product for 12–17 Oct.
- No app tests apply. No storefront, cart or checkout tests.

- Prepared: the plan, the summary and the link convention.
- Reviewed: Jian gave chat feedback on 11 Oct.
- Approved, deployed: none by this lane.
- Verified: read-only state above.

Approval reference: DECISIONS.md, "2026-10-11 to 2026-10-14 — Marketing plan project".
Blockers: YAA-011 offer decision; Jian's hero list (YAA-050); YAA-014 link convention; the Operations Black Friday plan (YAA-055).
Next action / proposed owner:
1. Jian decides YAA-011 and the hero list.
2. Codex reviews `claude/YAA-001` and `claude/YAA-001-marketing` (this branch includes the Sales commits) and merges or comments.
3. The marketing lane then takes YAA-051 (update the plan) and drafts YAA-052 copy. It will not start creator, link, test-order or ads work owned elsewhere.
## 2026-10-17 21:00 Asia/Shanghai — Claude Code ("Retention plan" Claude project) — YAA-001 reconciliation

Agent: Claude Code, working for the "Retention plan" Claude project only. The Sales plan project's reconciliation on `claude/YAA-001` is kept unchanged underneath this branch. Other Claude projects (Roadmap, Operations, Marketing, e-commerce/web lane) are not reconciled here.

Task ID: YAA-001 (retention scope).

Branch and commit: `claude/YAA-001-retention`, branched from `origin/claude/YAA-001` at 67a6516. The claim commit was pushed first, then this reconciliation commit. No changes to `main` or `claude/YAA-001`.

- TASKS.md: YAA-001 owner/status note; new Retention lane section YAA-060 to YAA-066; overlap list R-O1 to R-O8; proposed per-lane ID blocks.
- DECISIONS.md: appended record of retention approvals given before this repo; open conflicts.
- HANDOVER.md: this entry.
- docs/retention/status-2026-10-17.md: new; sanitized lane state.

- This Claude project had **no local clone, commits or branches** for this repo before today. Its work lived in two places:
  - claude.ai docs: the Retention Playbook, the Decision Log, and a project status note (`claude/Retention lane - status 2026-10-11.md`)
  - the live Shopify changes listed below
- Clone (shallow) of main at `23deff5`: working tree clean. Remote `origin` → github.com/jian-li5/you-are-angel, unchanged.
- Remote branches found: `main` and `claude/YAA-001` (Sales plan project, 2 commits, in review). This branch builds on the latter and does not edit its entries.
- Found during this session: `claude/YAA-001-ecommerce` (e-commerce reconciliation, now 15e2da5) and `claude/YAA-001-marketing` (marketing reconciliation, now d9d15ff). Both branch from `claude/YAA-001` and pushed while this session was working.
  - Retention IDs moved 019→040→060 because the lanes were renumbering at the same time. E-commerce now uses 040–046 and Marketing 050–057 (4dab5b2).
  - TASKS.md proposes one ID block per lane.
  - The e-commerce entry still cites retention's first numbers (023, 024, 025). They now map to: the popup cap, folded into e-commerce YAA-043; YAA-064 (nail size); YAA-065 (catalogue tags).
  - The SendWILL sign-up cap was folded into e-commerce YAA-043.
  - New overlaps R-O7 and the popup-app evidence conflict were added to TASKS.md (R-O3).

### Completed retention work
| Date (2026) | Item | Evidence on 17 Oct (read-only) | State |
| 11 Oct | 3 segments: first-time buyers, win-back 45+ days, subscribed never bought | Segment IDs 1174384378120 / 1174384345352 / 1174384410888; 5 / 4 / 38 members | Deployed; in place |
| 11 Oct | ANGELRETURNS: $10 off 2+ items, past buyers only, once each, shipping-combinable only | DiscountCodeNode 2179166339336, ACTIVE, 0 uses, updatedAt 2026-10-11T12:48:49Z | Deployed. Minimum changed from $60 to 2 items the same day |
| 11 Oct | ANGELGLOW15: 15% photo/video thank-you, same limits | DiscountCodeNode 2179166372104, ACTIVE, 0 uses | Deployed |
| 11 Oct | Customer metafield definition `angel.nail_size` (pinned); values and size tags on 2 customers | MetafieldDefinition 502407332104 | Deployed |
| 11 Oct | Retention Playbook: welcome (4), abandoned checkout (3), post-purchase (3), win-back (2), weekly campaigns, parcel card, scorecard | claude.ai doc | Prepared |
| 17 Oct | Halloween removed; calendar re-planned for Black Friday 27–30 Nov | Playbook revision | Prepared |
| 17 Oct | Cross-project Decision Log doc | claude.ai doc | Prepared; overlaps DECISIONS.md (R-O1) |
| 17 Oct | Setup checklist: final paste-ready copy for Shopify Messaging, plus a fast version | Playbook "Setup checklist" tab | Prepared; Jian executing (YAA-060) |
| 17 Oct | Read-only catalogue tag audit (findings in the status doc) | GraphQL collection and product reads | Reported; handed to YAA-065 |

### In progress
**YAA-060, owned by Jian.** He is building the Shopify Messaging automations in Safari. The welcome flow was nearly done at 15:48 Asia/Shanghai on 17 Oct, by his report. Not verified, because the Admin API exposes no Messaging automation state to this agent.

- git: clone, status, remote -v, branch -a, ls-remote, fetch of `claude/YAA-001`, diff against main.
- Read AGENTS.md, CLAUDE.md, README.md, PROJECT_STATUS.md, TASKS.md, HANDOVER.md, DECISIONS.md, and the Sales branch's files.
- Shopify GraphQL reads: the two retention discount nodes, WELCOME10 by code, the three segments with member counts, and the customer metafield definitions in namespace `angel`.
- ShopifyQL: orders, customers and returning customers from 11 Oct to today. Result: 0 / 0 / 0. Shop timezone CDT, USD.

Not run: no storefront or email render; no state-changing tests.

- Shopify items: approved in chat on 11 Oct, deployed, and verified read-only today.
- Email copy and calendar: prepared only.
- Automations: being built by Jian; not verified.

Nothing was changed in Shopify, sent or deployed in this session.

Approval reference and scope: DECISIONS.md, "2026-10-11 to 2026-10-17 — Retention plan project (pre-repo approvals)".

### Overlaps flagged before starting any further task
R-O1 to R-O8 in TASKS.md. The main ones:
- offer copy depends on YAA-011
- three overlapping 10% welcome mechanisms (YAA-007, Sales C4)
- shared vs per-customer UGC reward (YAA-063)
- delivery wording (YAA-002)
- Black Friday early-access date (24 vs 26 Nov)

- Jian's decisions on YAA-011, R-O3, R-O5 and the early-access date.
- The real shape and length of the Silk Fan Reverie products (YAA-065).
- Agent access to Shopify admin (YAA-018).

1. Jian finishes YAA-060, using the fast version for the last three flows, and resolves the open conflicts in DECISIONS.md.
2. Codex reviews this branch together with `claude/YAA-001`, `claude/YAA-001-ecommerce` and `claude/YAA-001-marketing`. All four branch from `claude/YAA-001`. Each appends its own sections to TASKS.md, HANDOVER.md and DECISIONS.md and edits the one YAA-001 row. Merge them one at a time and keep every lane's text; the YAA-001 row needs a hand merge that lists each lane's state.
3. The retention lane drafts the 20 Oct campaign (YAA-062) only after Jian confirms.

PROJECT_STATUS.md is left for its owner. It still says the Claude connection is unverified; for this project it is verified by this push.

## 2026-10-18 — Codex — YAA-070
Prepared docs/retention/email-flows-2026-10-18.md from user-supplied Claude copy after reading claude/YAA-001-retention. Eight emails plus trigger, exclusion, timing, QA and KPI rules. Existing reward codes are reported in Claude's reconciliation; not recreated or newly live-verified. Shopify Messaging selected per retention branch. No store flow, discount, test email or activation changed. Delivery/care/UGC terms and actual automation state remain blocked. Documentation reviewed for misleading claims and duplicate work; no app/code tests apply. Review branch codex/YAA-070-email-flows. Next: inspect current Shopify Messaging automation inventory and verify required links/offer terms before concrete activation approval.

## 2026-10-20 21:30 Asia/Shanghai — Claude Code ("E-Commerce plan" Claude project) — lane merge and status update
Date/time/timezone: 2026-10-20, about 21:30 Asia/Shanghai (13:30 UTC).
Agent: Claude Code, E-Commerce plan project.
Task ID: YAA-001 (merge of lane branches); updates to YAA-011, YAA-040, YAA-041, YAA-042, YAA-043, YAA-045.
Branch and commit: merge branch `claude/merge-lanes` → `main` (fast-forward, no force). Merged: `claude/YAA-001` (Sales, via the e-commerce branch), `claude/YAA-001-ecommerce`, `claude/YAA-001-marketing`, `claude/YAA-001-retention`, `codex/YAA-070-email-flows`. Lane branches left in place, not deleted.
Approval reference: Jian in the E-Commerce plan chat, 2026-10-20, asked to merge the branches so tasks are not repeated. Repository only; no store approval.
Files changed: TASKS.md, HANDOVER.md, DECISIONS.md (conflict resolution and this update). The docs/ files from the marketing, retention and Codex branches came in unchanged.

### How conflicts were resolved
- Every conflict was two lanes appending to the end of the same file. Both sides were kept in full; nothing was dropped or reworded.
- The YAA-001 row had four different owner cells. They were combined into one row listing the four reconciled lanes.
- Stale cross-references in the e-commerce sections were updated to the final IDs (retention 060–069, e-commerce 040–046).
- Not changed: other lanes' text, including their now-outdated "YAA-011 open" notes and the marketing section's old retention numbers (already flagged by retention R-O8). Each lane refreshes its own text on its next session.

### Status updates (read-only checks today)
- **YAA-011 offer: decided.** Jian says the Operations plan updated the offer. That plan is not in this repo and was not read. Live discounts, all set 2026-10-19 10:40 UTC, show this schedule:
  - BUY 2 GET 1 FREE ends 26 Oct 09:00 UTC (17:00 Shanghai)
  - Bundle & Save: 2 sets 15% off (min. 2 items), 3+ sets 25% off, 26 Oct 09:00 UTC – 27 Nov 04:59 UTC
  - Black Friday: 2 sets 20%, 3+ sets 30%, 27 Nov 05:00 UTC – 1 Dec 04:59 UTC
  - Bundle & Save 15% / 25% again from 1 Dec 05:00 UTC, no end date
  - "10% off $99+" and "20% off $199+" no longer active; free shipping on every order unchanged
- **Announcement bar still says "BUY 2 GET 1 FREE"** (MAIN header updated 2026-10-20 12:02 UTC). It must change to Bundle & Save when B2G1 ends on 26 Oct. Owner unconfirmed (probably Operations, which set the schedule).
- The bar's delivery wording now reads "10–14 working days" (changed today); product templates still say 7–10. YAA-002 owns this.
- **YAA-040 timer: done.** The rendered Petal Parade page (fetched 2026-10-20) has no countdown. The block is still enabled in both product templates but has no sale end date to show.
- **YAA-041 demo text:** "All Skin Care / UP TO 30% OFF / All Body Care / FREE SHPPING" is saved on a header mega-menu block linked to a "Store" menu item. The main menu (HOME, SHOP, COLLECTIONS, JOIN US, CONTACT US) has no "Store", so it never shows; the rendered page confirms this. "Stawberry Bloom" (product 10454974890248) is still misspelled.
- **YAA-042 pixels:** Jian says Meta is connected; TikTok was connected but the TikTok Shop was closed, so it is probably not connected now. Not checked by an agent (no read_pixels scope).
- Social links: still none in MAIN theme settings (settings_data updated 2026-10-18).

### Checks actually run
git fetch, ls-remote, five merges, conflict-marker and ancestor checks. Shopify GraphQL reads: MAIN theme files, active and scheduled discounts, menus, one product. WebFetch of one live product page. No Shopify changes, no deploy.

### Next action / proposed owner
1. Banner swap to Bundle & Save on 26 Oct (Operations or Jian; theme edit).
2. YAA-043 popup: confirm which popup app is live (Trustoo embed or SendWILL) and pick WELCOME10 or the SW- code (Sales + Retention).
3. YAA-045 cart prompt, now unblocked: "add one more set to save 15% / 25%". E-commerce lane prepares it in the single draft (YAA-012) once ownership is accepted.
4. Decide whether to reconnect the TikTok pixel before any TikTok ads (YAA-056).

## 2026-10-20 21:30 Asia/Shanghai — Claude Code (E-Commerce plan) — YAA-041 title fix; YAA-002 delivery fact
Branch and commit: direct to `main` (fast-forward), documentation only.
- **Deployed:** product 10454974890248 title "Stawberry Bloom" → "Strawberry Bloom", approved by Jian (DECISIONS.md 2026-10-20). Handle and SEO unchanged. Verified by mutation response; storefront not re-fetched.
- **YAA-002:** Jian confirms 10–14 working days. Places still saying 7–10 (from the 17 and 20 Oct theme reads): product Shipping tab, the "Ships in 7–10 Days" trust line and the cost-per-wear block on product.yaa-template-product-page, and retention email copy. Shipping Policy not re-checked. No other store change made.
Next action: Jian approves updating those product-page texts (live theme edit; MAIN theme writes are blocked for agents, so Jian pastes or Claude prepares a draft). Retention lane updates its email copy.

## 2026-10-20 21:40 Asia/Shanghai — Claude Code (E-Commerce plan) — delivery wording check (YAA-002)
- Correction: the previous entry listed the product Shipping tab, trust line and cost-per-wear box as still saying 7–10. That came from the 17 Oct theme read. Jian had already changed them; MAIN template updated 2026-10-20 11:55 UTC.
- Verified now: MAIN theme files plus a rendered fetch of /products/strawberry-bloom-press-on-nails. Banner "Delivered in 10-14 working days", trust line "Delivered in 10–14 Days", Shipping tab "Delivered in 10–14 working days". Preorder +5–7 days unchanged.
- Still 7–10: the Shipping Policy page ("Your nails will arrive in 7–10 working days from the day you order"). Retention email copy also still says 7–10.
- Also seen, for the 26 Oct offer change: product-page scrolling text "BUY 2 GET 1 FREE!" and the banner dropdown "Buy any 2 sets, get a 3rd free". The default product.json template still has old blocks, but no active product uses it.
- To check under YAA-008/044: the Judge.me review widget on the product template is set to review_data "sample_data". The rendered page showed no reviews ("Be the first to review"), so no sample reviews are displayed now.
No store changes in this check.

## 2026-10-20 22:10 Asia/Shanghai — Claude Code (E-Commerce plan) — correction
The Shipping Policy already says 10–14 working days, including 2–3 days to finish and pack, plus 5–7 extra days for Preorder. Source: Admin API shopPolicies; policy updated 2026-10-20 11:54 UTC. The previous entry's "still 7–10" came from a stale cached fetch of the public page. Delivery wording is now consistent across the store; only the retention email copy still says 7–10. No store change made.


## 2026-10-30 ~16:50 Asia/Shanghai — Claude Code ("Marketing plan" project) — creator video, product ref, week 3 status
Agent: Claude Code, Marketing plan project. Branch: `main`, documentation only, following the E-commerce lane's practice since the 20 Oct merge.
Tasks: YAA-050, YAA-053, and a creator-section update.

### Store changes
| Change | Who | State | Evidence |
|---|---|---|---|
| Angel Aura Shimmer Base Set description: appended "Product Ref: YAA160" | Claude, approved by Jian (DECISIONS.md 2026-10-30) | Deployed; verified | productUpdate returned no userErrors; description ends "Product Ref: YAA160" |
| Hannah creator video (4.3 MB, compressed by Claude from 83 MB) uploaded to Files as `hannah-creator-video-540p.mp4`, plus a poster image | Jian | Deployed | Files API: Video READY, 4,264,085 bytes |
| Homepage `seen_on_tiktok_reels`: new first block with Hannah's video, linked to `angel-aura-shimmer-base-set` | Jian, in the theme editor | Deployed; verified read-only | MAIN theme 204314181896 `templates/index.json` updated 2026-10-30T08:42:24Z; block `product_L3hEji` is first in block_order |

### Marketing status (read-only)
- **YAA-050:** `/collections/seen-on-tiktok` was built 25 Oct with 10 designs. TikTok and Instagram bio links were updated 27 Oct (Jian). The first landings on the collection came 28–29 Oct (3 sessions, no referrer).
- **Orders:** 0 since 12 Oct. Sessions since 29 Oct: 40, all direct, 0 cart additions.
- **Creator codes:** 35 ANGEL-* codes exist; all had 0 uses on 29 Oct.
- **YouTube Shorts:** a 7-day plan, one YAA300–306 design per day, linking straight to each product page with `utm_source=youtube&utm_campaign=shorts`. Copy is saved on Jian's Mac at Desktop/videos/系列三/YouTube_week_YAA300-306.txt. Posting is not verified.
- **YAA-052 (companion offer)** and **YAA-055 (Black Friday offer):** overtaken by the 20 Oct offer decision (Bundle & Save; Black Friday 20%/30%). Still open: the early-access date (24 vs 26 Nov), holiday creators and featured designs, due 8 Nov.

Checks run: Shopify GraphQL reads (theme file, files, product) and ShopifyQL sessions and sales. No app tests apply.
Next: the Clarity review of homepage sessions with 0 carts (Jian); the week-4 review on 8 Nov.
