# Shared task register

Updated 2026-10-17. "Proposed" is not accepted ownership or permission to deploy.
Before starting, fetch current state, check overlapping branches/PRs and push a task claim.
Statuses: backlog / claimed / in-progress / review / blocked / done. Track deployment separately.

| ID | Priority | Task | Owner | Status | Acceptance |
|---|---|---|---|---|---|
| YAA-001 | P0 | Reconcile existing Claude project, commits and deployed work | Claude Code, one session per Claude project. Reconciled: Sales (claude/YAA-001), E-commerce (claude/YAA-001-ecommerce), Marketing (claude/YAA-001-marketing), Retention (claude/YAA-001-retention). Not reconciled: Roadmap, Operations | done for those four lanes: merged to main 2026-10-20 at Jian's request; Roadmap and Operations still open | Handover lists local/remote changes, prior approvals and completed work; no overwrites |
| YAA-002 | P0 | Confirm authoritative shipping, production and delivery promises; draft consistent wording | Codex + user business facts | blocked | User confirms real rules; draft distinguishes production/transit/preorder |
| YAA-003 | P0 | Verify size-guide page and product sizing path | Unassigned until YAA-001 | backlog | Fresh evidence; identify wrong template only if reproduced; prepare local fix |
| YAA-004 | P0 | Explain September purchase without reached-checkout and blank-source additions | Codex | backlog | Definitions, date/consent/express paths checked; unresolved causes labeled |
| YAA-005 | P1 | Audit US desktop Direct traffic and current UTM links | Codex | backlog | Evidence-backed source classification; no assumed bot exclusion |
| YAA-006 | P1 | Measure mobile performance and prepare minimal image/script fixes | Claude Code (proposed) | blocked | Reconciliation first; fixed-condition 3-run baseline; no live changes |
| YAA-007 | P1 | Draft cart/discount/shipping/payment QA matrix | Codex | backlog | Countries/devices/stock/preorder cases; state-changing tests need approval |
| YAA-008 | P1 | Verify testimonial and product claim evidence | Codex + user source records | blocked | Authenticity/permission and use conditions documented without customer PII |
| YAA-009 | P1 | Calculate promotion contribution margin | Codex + user costs | blocked | Costs, shipping, fees and stacking rules verified |
| YAA-010 | P2 | Prepare a minimal implementation PR after reconciliation | Unassigned | blocked | Precise diff, validation, risks, rollback and scoped approval request |

No task is marked deployed. Do not treat the audit's suggested 7-day/30-day dates as automatic execution or authorization.

## Sales-plan lane (added by Claude Code, YAA-001, 2026-10-17)
Source: "Sales plan" Claude project (plan: You Are Angel – 50 Sales a Day Plan, 2026-10-11). Owners are proposals until accepted. Deployment is tracked separately; nothing here authorizes store changes.

| ID | Priority | Task | Owner | Status | Depends on / overlaps | Acceptance |
|---|---|---|---|---|---|---|
| YAA-011 | P0 | Decide the single main offer: BUY 2 GET 1 FREE (live now) vs "Any 2 sets – 15% off" (Jian's 11 Oct sales-plan decision, later deleted in store) | Jian (decision); Claude sales lane records | blocked | YAA-009 margin; Roadmap, Operations (Black Friday bundle), Marketing copy | One offer recorded in DECISIONS.md with date; store, theme text and all plan docs agree |
| YAA-012 | P1 | Draft theme 203557044488 (social links, FOLLOW US footer, offer text): rebuild on current MAIN or discard | Proposed: YAA-010 owner; Claude sales lane can prepare | blocked | YAA-011, YAA-002, YAA-010, e-commerce lane | Offer text matches YAA-011; homepage "$59" line fixed; diff vs MAIN reviewed; explicit publish approval in DECISIONS.md |
| YAA-013 | P1 | Creator codes (one per creator) + recovery messages for 30+ gifted creators | Claude sales lane (proposed) | blocked | Jian's creator list; overlaps Marketing creator outreach; uses YAA-014 convention | Code per creator, no duplicate of existing codes; messages drafted, not sent without approval |
| YAA-014 | P1 | Tracked bio links (TikTok, Instagram, YouTube) and creator links | Claude sales lane applies; Codex defines convention | blocked | YAA-005 UTM audit; TikTok bio link check by Jian | Every entry link carries agreed UTM; TikTok bio link confirmed opening the store |
| YAA-015 | P1 | US phone test order (single + 2/3 sets, Preorder size) | Proposed: Codex matrix (YAA-007), Jian executes | blocked | YAA-007, Ops OPS-06, Marketing week 1 | One owner; state-changing test approved in DECISIONS.md; results logged |
| YAA-016 | P2 | Maintain "YAA Monday sales scorecard" scheduled task (read-only) | Claude sales lane | in-progress | Prompt edited 11 Oct by another session to B2G1; align after YAA-011; Roadmap review uses its numbers | Prompt matches current offer and codes; runs Mondays 08:52 Asia/Shanghai |
| YAA-017 | P2 | Review 10 mobile Clarity recordings (product page, no add to cart) | Jian + Claude sales lane | backlog | YAA-004, YAA-006 | Findings logged as confirmed/hypothesis with session counts |
| YAA-018 | P2 | Agent access to Shopify admin (Cloudflare check fails in Claude browser and Chrome; Safari works) | Jian | blocked | All theme-editor tasks | One agent browser path verified, or theme work stays via drafts + Jian publish |

### Completed sales-lane items (deployed 11–16 Oct 2026, before this repo; evidence in HANDOVER.md)
Compare-at €0,00 fix; free shipping combinable with discounts; popup codes combine with shipping; made-to-order inventory policy; US market in USD; "Angel Essentials" collection; cost-per-wear + Preorder block; Shipping tab wording (conflict C2); Microsoft Clarity. Superseded outside this project: B2G1 end date and the 15% bundle (YAA-011).

### Overlaps flagged by Claude before starting any task
- YAA-002 owns delivery/shipping wording (live 7–10 working days vs Shipping Policy 7–15 + 7–20). The sales lane will not edit wording.
- YAA-007 / YAA-009 cover discount stacking and margin. The sales lane will not create or change discounts until YAA-011 is decided.
- WELCOME10, ANGELGLOW15 and ANGELRETURNS were created 11 Oct by other sessions. Treated as owned by Sales (origin unconfirmed) and Retention. The sales lane will not duplicate them.
- YAA-010 / e-commerce lane own theme changes. The draft theme is handed over as YAA-012.

## E-commerce-plan lane (added by Claude Code, YAA-001, 2026-10-17)
Source: "E-Commerce plan" Claude project (plan section 5, You Are Angel – 50 Sales a Day Plan, 2026-10-11). Note: the plan itself named "the web lane (Codex and ChatGPT)" for these items; ownership below is a proposal for Jian and Codex to accept. Nothing here authorizes store changes. IDs start at YAA-040 to avoid the sales lane's YAA-011..018.

| ID | Priority | Task | Owner | Status | Depends on / overlaps | Acceptance |
|---|---|---|---|---|---|---|
| YAA-040 | P1 | Countdown timer ("Hurry up! Sale ends in") still enabled on both product templates; homepage collection sections have show_countdown on | Claude e-commerce lane prepares (proposed) | backlog | Same draft as YAA-012 (one draft, not two); YAA-011 (no timer unless a real end date) | Rendered check shows whether it displays; removed or tied to a real end date in a draft; publish approval in DECISIONS.md |
| YAA-041 | P2 | Theme demo text in live header mega-menu ("All Skin Care / UP TO 30% OFF", "All Body Care / FREE SHPPING"); product title typo "Stawberry Bloom" | Claude e-commerce lane prepares (proposed) | backlog | YAA-012 draft; title edit is a live product change | Text removed in draft; title fix listed for approval |
| YAA-042 | P1 | Verify TikTok and Meta pixels and that purchase events fire | Jian checks Customer events; Claude e-commerce lane documents (proposed) | blocked | API read denied (no read_pixels scope); YAA-018 admin access; overlaps YAA-004/005 and Marketing Spark/retargeting ads | Each pixel listed connected/not, with evidence; no test purchase without approval |
| YAA-043 | P1 | Signup popup with the one welcome offer, shown after 8–10 s or on exit | Display: Claude e-commerce lane (proposed). Offer: sales lane. Flows: Retention | blocked | YAA-011; WELCOME10 vs SW- popup codes (sales C4); Trustoo popup app embed and SendWILL (SW- codes) are both present, theme popup is disabled; retention YAA-023 (SendWILL free-plan cap) | One popup, one code, timing set; no duplicate first-order codes |
| YAA-044 | P1 | Customer photos and reviews on homepage and product pages | Claude e-commerce lane (proposed) | blocked | YAA-008 (claim evidence); Judge.me badge is on the product template but its reviews block is disabled | Only verified reviews shown; placement prepared in draft |
| YAA-045 | P2 | Cart prompt: plan's free-shipping progress bar is moot (free shipping on every order); replace with a "second set" prompt | Claude e-commerce lane (proposed) | blocked | YAA-011 (which bundle); YAA-007/009; Monster Cart Upsell app already installed | Prompt matches the confirmed offer; no new app |
| YAA-046 | P2 | TikTok landing page (best sellers, proof, one offer) | Claude e-commerce lane (proposed) | backlog | YAA-011, YAA-014 (UTMs), Marketing creative | Page prepared unpublished; tracked link defined |

### Completed e-commerce-lane items (evidence in HANDOVER.md)
- 2026-10-11: read-only store audit against plan section 5.
- 2026-10-11: compare-at price 0.00 cleared on 30 products / 136 variants. Also logged by the sales lane (126 variants); same fix, counted once.
- Done on the live theme since, by the sales lane or Jian (14 Oct), not by this lane: announcement-bar wording, delivery time, cost-per-wear block, size-guide popup, returns tab, trust line, low-stock bar disabled on the product template in use, Clarity.

### Proposed ownership of existing shared tasks (needs Codex/Jian acceptance; not started)
- YAA-003 (size guide) and YAA-006 (mobile performance): Claude e-commerce lane.
- YAA-010 / YAA-012 (theme draft): Claude e-commerce lane rebuilds one draft from current MAIN (203435966728) carrying YAA-012, YAA-040 and YAA-041 together. **Overlap:** the sales lane prepared draft 203557044488 and proposed "YAA-010 owner decides". Not starting until accepted.

### Overlaps flagged before starting any task
- Theme work: one draft only, shared by the sales and e-commerce lanes (YAA-012/019/020).
- Delivery and shipping wording stays with YAA-002 (Codex).
- Welcome codes and popup: sales (offer), Retention (flows), this lane (display only).
- Pixels and tracking: YAA-004/005 (Codex) and Marketing ads.
- Retention-lane tasks proposed for this lane (branch claude/YAA-001-retention, not yet merged): YAA-023 popup sign-up cap (merge with YAA-043), YAA-024 theme pre-selects saved nail size (theme part), YAA-025 catalogue tags (overlaps Ops OPS-03). Accept or decline once that branch is reviewed; not started.
## Email setup follow-up — 2026-10-18

| ID | Priority | Task | Owner | Status | Acceptance |
|---|---|---|---|---|---|
| YAA-070 | P1 | Prepare the user-supplied eight retention emails and Shopify Messaging build/QA specification; implementation subtask of YAA-060 | Codex | claimed | Reconcile retention branch, avoid duplicate codes/flows, produce review PR; sending/activation remains unapproved |

Claude retention branch records Shopify Messaging as selected, codes already created and welcome flow underway. Do not duplicate its work. This task does not merge or replace that branch.
## Marketing-plan lane (added by Claude Code, YAA-001, 2026-10-17)
Source: the "Marketing plan" Claude project. Plan: *You Are Angel — Marketing Plan v2*, 2026-10-11; summary in docs/marketing-plan/. Owners are proposals until accepted. Nothing here authorizes live store changes, publishing, ads or customer email. IDs YAA-050 to YAA-057 (renumbered 2026-10-17 from 019–026, which the Retention lane claimed first; E-commerce uses 040–046).

| YAA-050 | P1 | Pick 6–8 hero designs; build `/collections/seen-on-tiktok` (newest featured design first) | Jian picks and builds (live store); Claude marketing lane prepares the shortlist | blocked | Jian's hero choice; YAA-014 links; YAA-011 offer copy; made-to-order lead time (+5–7 days, YAA-002) | Collection exists with the heroes; bio links (YAA-014) point to it; checked read-only |
| YAA-051 | P1 | Update Marketing Plan v2 for superseded facts (made-to-order, offer, combinability, Clarity, expired tiers) and for repository rules | Claude marketing lane | backlog | YAA-011; YAA-002 wording | Doc and docs/marketing-plan summary agree with store state read on the edit date; no agent-run test orders or ads in the plan |
| YAA-052 | P1 | Companion offer beside the main offer (Jian asked 11 Oct). Options drafted: "free nail kit included" messaging; first-order 10% for single-set buyers | Jian decides; Claude marketing lane drafts copy | blocked | YAA-011, YAA-009 margin; duplicate first-order codes (WELCOME10 vs SW- popup, Sales C4); YAA-007 | One choice recorded in DECISIONS.md; no new discount created by an agent without scoped approval |
| YAA-053 | P1 | Daily TikTok posting plus same-day Instagram Reel and story link sticker (content calendar, hooks, keywords) | Jian posts; Claude marketing lane plans | in-progress (posting not verified) | YAA-014 links; YAA-050 heroes | Tracked TikTok/Instagram sessions visible in Shopify by referrer or UTM; weekly read-only count logged |
| YAA-054 | P2 | Google & YouTube app (Merchant Center free listings) and Pinterest catalog sync | Jian installs (app install = live change); Claude marketing lane prepares title format | blocked | Scoped approval in DECISIONS.md; audit SEO item (P2); YAA-010 | Apps installed by Jian; listings approved; no theme edits by agents |
| YAA-055 | P2 | Black Friday (27–30 Nov) and December gifting plan: offer, creators, gift card, Christmas last-order date | Jian decides; marketing and Operations lanes draft | blocked | **Conflict:** the Operations lane plans a Black Friday bundle with B2G1 paused 27–30 Nov; Marketing v2 proposed B2G1 plus a gift for the first 15 orders. YAA-011, YAA-009; delivery promise (YAA-002) | One Black Friday offer recorded in DECISIONS.md by 8 Nov; all lanes' docs match |
| YAA-056 | P2 | TikTok Spark Ads test ($10/day; v2 had it from 26 Oct) | Jian (ads need explicit approval) | blocked | The audit says don't expand paid traffic while checkout/attribution is unverified: YAA-004, YAA-007. Also YAA-003, YAA-002 | Starts only after those tasks pass and Jian records a budget approval in DECISIONS.md |
| YAA-057 | P3 | Marketplace decision (Etsy "designed by" with production-partner disclosure, or TikTok Shop with US stock) | Jian decides; Claude marketing lane prepares the comparison | backlog | Jian: are the designs his? Operations: US stock; due 20 Nov | Go/no-go recorded in DECISIONS.md |

### Completed marketing-lane items (no live store changes by this lane; evidence in HANDOVER.md)
- Marketing Plan v2 (Claude Doc) and its project summary
- Week 1 checklist
- 14 Oct read-only mid-week check
- Proposed link convention (handed to YAA-005 / YAA-014)

### Overlaps flagged before starting any marketing task
- **Creator re-activation and codes = YAA-013 (Sales lane).** The marketing lane will not run a separate creator outreach.
- **Tracked links = YAA-005 / YAA-014.** The marketing lane only proposes a convention.
- **Phone test order = YAA-015 / YAA-007.** Removed from the marketing week 1 list as an agent task: Jian executes it under approval.
- **Weekly scorecard:** the marketing lane proposed a "yaa-weekly-scorecard" skill on 11 Oct; it duplicates YAA-016. Use YAA-016 only.
- **Week 1 review check-in** (scheduled task trig_01Rd822QGcFnDAght5QA253w, fires 2026-10-18 12:00 UTC): read-only, and it edits only the marketing doc. It must not duplicate YAA-016's report.
- **Retention lane overlaps:** subscriber early-access date 24 Nov (Marketing v2) vs 26 Nov (Ops OPS-20), raised in Retention YAA-021; the popup sign-up cap (Retention YAA-023) limits the email channel's share in Marketing v2's channel mix.
- **Main offer (YAA-011)** and **delivery wording (YAA-002)** are owned elsewhere. The marketing lane will not write offer or delivery copy until they are decided.
