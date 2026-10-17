# Shared task register

Updated 2026-10-17. "Proposed" is not accepted ownership or permission to deploy.
Before starting, fetch current state, check overlapping branches/PRs and push a task claim.
Statuses: backlog / claimed / in-progress / review / blocked / done. Track deployment separately.

| ID | Priority | Task | Owner | Status | Acceptance |
|---|---|---|---|---|---|
| YAA-001 | P0 | Reconcile existing Claude project, commits and deployed work | Claude Code (acknowledged 2026-10-17; sales-plan project done; retention project claimed 2026-10-17 on branch claude/YAA-001-retention — other Claude projects not yet reconciled) | review (claude/YAA-001); in-progress (claude/YAA-001-retention) | Handover lists local/remote changes, prior approvals and completed work; no overwrites |
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

## Retention lane (added by Claude Code, YAA-001, 2026-10-17)
Source: "Retention plan" Claude project (plan section 6). Lane state: docs/retention/status-2026-10-17.md.
IDs YAA-019 to YAA-026 are provisional. If another branch used them first, renumber on merge and keep both.
Owners are proposals until accepted. Nothing here authorizes store changes, customer email or deployment.

| ID | Priority | Task | Owner | Status | Depends on / overlaps | Acceptance |
|---|---|---|---|---|---|---|
| YAA-019 | P0 | Switch on 4 email automations in Shopify Messaging (welcome, abandoned checkout, post-purchase, win-back) | Jian builds and switches on in Safari; Claude retention lane supplies the copy | in-progress (welcome nearly done per Jian, 17 Oct; unverified) | YAA-011 (offer line in welcome email 4); YAA-002 (7–10 working days); YAA-018 (no agent admin access); YAA-007 (which welcome code is canonical) | Each flow on and test-sent; copy matches YAA-011 and YAA-002 outcomes; recorded in HANDOVER.md |
| YAA-020 | P1 | One-to-one notes to the 2 existing paid buyers (thank-you, fit check, ANGELRETURNS / ANGELGLOW15) | Jian sends from his own inbox; Claude drafted | backlog | Draft mentions Merry Muse; one buyer is not opted in to marketing, so her note is service-only | Sent by Jian; no marketing to non-consenting customers |
| YAA-021 | P1 | Weekly subscriber campaigns 20 Oct to 29 Dec (calendar in the retention status doc) | Claude retention lane drafts; Jian approves and sends each one | backlog | YAA-011; Ops OPS-17 bundle prices; early-access date 24 vs 26 Nov (Marketing v2 vs Ops OPS-20); Marketing posting dates; YAA-008 for customer photos | Each campaign approved by Jian before sending; dates agree with Marketing and Ops |
| YAA-022 | P1 | Photo/video reward and parcel card | Retention lane (reward mechanism); Ops prints cards (OPS-13) | blocked | **Overlap:** Sales log says the UGC reward should be issued per customer, not as one shared code; retention made ANGELGLOW15 (shared code, past buyers only, once each). Jian to choose | One reward mechanism recorded in DECISIONS.md; card text matches it |
| YAA-023 | P1 | SendWILL Free plan caps sign-ups at about 30 new subscribers a month (plan needs about 600 a month at 500 visits/day × 4%) | E-commerce lane + Jian (proposed) | backlog | Popup is e-commerce scope; feeds YAA-019 welcome flow | Decision recorded: upgrade SendWILL or move the sign-up to Shopify Forms; no subscriber is lost to the cap |
| YAA-024 | P2 | Nail-size memory: Flow workflow writes `angel.nail_size` on each order; theme pre-selects the saved size | Flow: Jian (store change); theme: YAA-010 / e-commerce owner | backlog | YAA-010 (theme), YAA-018 | Size saved on new orders; theme change only with explicit approval |
| YAA-025 | P1 | Catalogue tags: add occasion/shape/length tags to 10 Silk Fan Reverie products; fix 3 shape conflicts; clean run-on tags | Proposed: catalogue/e-commerce lane (overlaps Ops OPS-03); retention lane found it read-only on 17 Oct and can prepare the tag list | blocked | Jian supplies the real shape and length; product edits need explicit approval | Every active product has exactly one shape and one length tag and at least one occasion tag; changes approved first |
| YAA-026 | P2 | Retention metrics (90-day repeat rate, repeat orders/day, subscribers, flow conversion, code uses) | Proposed: add them to the Sales lane's Monday scorecard (YAA-016) rather than a second scheduled task | backlog | YAA-016 owner | One scorecard carries the retention rows |

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
- **R-O3 Welcome code (YAA-007, Sales C4).** Three 10% first-order mechanisms exist: the SW- popup codes, WELCOME10 (Sales, created 11 Oct 12:59 UTC) and the welcome flow, which currently points to the popup code. One must be canonical.
- **R-O4 Delivery wording (YAA-002).** Retention emails say 7–10 working days. They will follow YAA-002's wording.
- **R-O5 UGC reward (YAA-022).** See the row above.
- **R-O6 Catalogue tags (YAA-025)** are not retention scope. They are flagged for the catalogue owner.
