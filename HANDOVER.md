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
