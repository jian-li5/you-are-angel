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
## Retention lane (added by Claude Code, YAA-001, 2026-10-17)
Source: "Retention plan" Claude project (plan section 6). Lane state: docs/retention/status-2026-10-17.md.
Retention uses the ID block YAA-060 to YAA-069. It renumbered twice on 17 Oct (019→040→060) because other lane branches were renumbering at the same time; Marketing has since moved to 050–057.
Proposed ID blocks per lane, to stop collisions:
- Sales: 011–018
- Marketing: 050–057
- E-commerce: 040–046
- Retention: 060–069
- Operations / Roadmap: 080+ / 100+

Codex or Jian to confirm when merging.
Owners are proposals until accepted. Nothing here authorizes store changes, customer email or deployment.

| YAA-060 | P0 | Switch on 4 email automations in Shopify Messaging (welcome, abandoned checkout, post-purchase, win-back) | Jian builds and switches on in Safari; Claude retention lane supplies the copy | in-progress (welcome nearly done per Jian, 17 Oct; unverified) | YAA-011 (offer line in welcome email 4); YAA-002 (7–10 working days); YAA-018 (no agent admin access); YAA-007 (which welcome code is canonical) | Each flow on and test-sent; copy matches YAA-011 and YAA-002 outcomes; recorded in HANDOVER.md |
| YAA-061 | P1 | One-to-one notes to the 2 existing paid buyers (thank-you, fit check, ANGELRETURNS / ANGELGLOW15) | Jian sends from his own inbox; Claude drafted | backlog | Draft mentions Merry Muse; one buyer is not opted in to marketing, so her note is service-only | Sent by Jian; no marketing to non-consenting customers |
| YAA-062 | P1 | Weekly subscriber campaigns 20 Oct to 29 Dec (calendar in the retention status doc) | Claude retention lane drafts; Jian approves and sends each one | backlog | YAA-011; Ops OPS-17 bundle prices; early-access date 24 vs 26 Nov (Marketing v2 vs Ops OPS-20); Marketing posting dates; YAA-008 for customer photos | Each campaign approved by Jian before sending; dates agree with Marketing and Ops |
| YAA-063 | P1 | Photo/video reward and parcel card | Retention lane (reward mechanism); Ops prints cards (OPS-13) | blocked | **Overlap:** Sales log says the UGC reward should be issued per customer, not as one shared code; retention made ANGELGLOW15 (shared code, past buyers only, once each). Jian to choose | One reward mechanism recorded in DECISIONS.md; card text matches it |
| YAA-064 | P2 | Nail-size memory: Flow workflow writes `angel.nail_size` on each order; theme pre-selects the saved size | Flow: Jian (store change); theme: YAA-010 / e-commerce owner | backlog | YAA-010 (theme), YAA-018 | Size saved on new orders; theme change only with explicit approval |
| YAA-065 | P1 | Catalogue tags: add occasion/shape/length tags to 10 Silk Fan Reverie products; fix 3 shape conflicts; clean run-on tags | Proposed: catalogue/e-commerce lane (overlaps Ops OPS-03); retention lane found it read-only on 17 Oct and can prepare the tag list | blocked | Jian supplies the real shape and length; product edits need explicit approval | Every active product has exactly one shape and one length tag and at least one occasion tag; changes approved first |
| YAA-066 | P2 | Retention metrics (90-day repeat rate, repeat orders/day, subscribers, flow conversion, code uses) | Proposed: add them to the Sales lane's Monday scorecard (YAA-016) rather than a second scheduled task | backlog | YAA-016 owner | One scorecard carries the retention rows |

### Completed retention-lane items (11–17 Oct 2026; evidence in HANDOVER.md)
Done in Shopify on 11 Oct, before this repo existed:
- 3 retention segments
- ANGELRETURNS and ANGELGLOW15 codes
- `angel.nail_size` customer field, with values and size tags on 2 customers

Done outside Shopify:
- Retention Playbook (all flow and campaign copy)
- Halloween removed and calendar re-planned for Black Friday (17 Oct)
- Setup checklist with final copy (17 Oct)
- Platform decision: Shopify Messaging, not SendWILL Free (17 Oct)
- Read-only catalogue-tag audit (17 Oct)

No customer email has been sent by Claude.

### Overlaps flagged by the retention lane before starting any task
- **R-O1 Coordination.** The claude.ai "Decision Log" doc (17 Oct) duplicates this repo's DECISIONS.md. Proposal: DECISIONS.md is authoritative; the doc becomes a pointer to the repo. Jian to confirm.
- **R-O2 Offer (YAA-011).** Retention copy says "buy 2, get the third free" (welcome email 4, Merry Muse 3 Nov). It will be rewritten once YAA-011 is decided. The retention codes do not stack with any product discount by design.
- **R-O3 Welcome code and popup (YAA-007, Sales C4, e-commerce YAA-043).** Three 10% first-order mechanisms exist: the SW- popup codes, WELCOME10 (Sales, created 11 Oct 12:59 UTC) and the welcome flow, which currently points to the popup code. One must be canonical. The welcome flow's day-0 email follows e-commerce YAA-043.
  - The retention lane found that **SendWILL's Free plan caps sign-ups at about 30 new subscribers a month**, against about 600 a month the plan needs at 500 visits/day × 4%. This is added to e-commerce YAA-043 rather than kept as a separate task.
  - **Evidence conflict:** the e-commerce entry says a "Trustoo" popup app is active and the theme popup is disabled. Retention evidence points to SendWILL (app handle `ecomsend`): 11 Oct customer tags "EcomSend Popups" and SW- codes titled "10%OFF-popup". The live popup app is unconfirmed; Jian or YAA-043's owner to check.
- **R-O4 Delivery wording (YAA-002).** Retention emails say 7–10 working days. They will follow YAA-002's wording.
- **R-O5 UGC reward (YAA-063).** See the row above.
- **R-O6 Catalogue tags (YAA-065)** are not retention scope. They are flagged for the catalogue owner.
- **R-O7 Reviews and photos.** E-commerce YAA-044 shows reviews and photos on the site; retention YAA-063 collects them, through the photo reward and Judge.me requests. Both must use the same permission rule (YAA-008).
- **R-O8 Marketing lane.** The marketing entry still cites retention's first numbers: YAA-021 is now YAA-062, and YAA-023 is now e-commerce YAA-043.
  - Marketing YAA-055 (Black Friday and December plan) owns the Black Friday offer and dates. Retention YAA-062 only writes the subscriber emails for it, including the early-access date (24 vs 26 Nov).
  - Marketing YAA-052 (companion offer, first-order 10%) joins R-O3's welcome-code question.
  - Marketing YAA-051 (update Marketing Plan v2) should drop Halloween, as decided on 16 Oct.
