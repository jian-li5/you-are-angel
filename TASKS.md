# Shared task register

Updated 2026-10-17. "Proposed" is not accepted ownership or permission to deploy.
Before starting, fetch current state, check overlapping branches/PRs and push a task claim.
Statuses: backlog / claimed / in-progress / review / blocked / done. Track deployment separately.

| ID | Priority | Task | Owner | Status | Acceptance |
|---|---|---|---|---|---|
| YAA-001 | P0 | Reconcile existing Claude project, commits and deployed work | Claude Code (acknowledged 2026-10-17; sales-plan project done — other Claude projects not yet reconciled) | review (branch claude/YAA-001); e-commerce-plan project: claimed 2026-10-17 on branch claude/YAA-001-ecommerce | Handover lists local/remote changes, prior approvals and completed work; no overwrites |
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
Source: "E-Commerce plan" Claude project (plan section 5, You Are Angel – 50 Sales a Day Plan, 2026-10-11). Note: the plan itself named "the web lane (Codex and ChatGPT)" for these items; ownership below is a proposal for Jian and Codex to accept. Nothing here authorizes store changes. IDs start at YAA-019 to avoid the sales lane's YAA-011..018.

| ID | Priority | Task | Owner | Status | Depends on / overlaps | Acceptance |
|---|---|---|---|---|---|---|
| YAA-019 | P1 | Countdown timer ("Hurry up! Sale ends in") still enabled on both product templates; homepage collection sections have show_countdown on | Claude e-commerce lane prepares (proposed) | backlog | Same draft as YAA-012 (one draft, not two); YAA-011 (no timer unless a real end date) | Rendered check shows whether it displays; removed or tied to a real end date in a draft; publish approval in DECISIONS.md |
| YAA-020 | P2 | Theme demo text in live header mega-menu ("All Skin Care / UP TO 30% OFF", "All Body Care / FREE SHPPING"); product title typo "Stawberry Bloom" | Claude e-commerce lane prepares (proposed) | backlog | YAA-012 draft; title edit is a live product change | Text removed in draft; title fix listed for approval |
| YAA-021 | P1 | Verify TikTok and Meta pixels and that purchase events fire | Jian checks Customer events; Claude e-commerce lane documents (proposed) | blocked | API read denied (no read_pixels scope); YAA-018 admin access; overlaps YAA-004/005 and Marketing Spark/retargeting ads | Each pixel listed connected/not, with evidence; no test purchase without approval |
| YAA-022 | P1 | Signup popup with the one welcome offer, shown after 8–10 s or on exit | Display: Claude e-commerce lane (proposed). Offer: sales lane. Flows: Retention | blocked | YAA-011; WELCOME10 vs SW- popup codes (sales C4); Trustoo popup app is active, theme popup is disabled | One popup, one code, timing set; no duplicate first-order codes |
| YAA-023 | P1 | Customer photos and reviews on homepage and product pages | Claude e-commerce lane (proposed) | blocked | YAA-008 (claim evidence); Judge.me badge is on the product template but its reviews block is disabled | Only verified reviews shown; placement prepared in draft |
| YAA-024 | P2 | Cart prompt: plan's free-shipping progress bar is moot (free shipping on every order); replace with a "second set" prompt | Claude e-commerce lane (proposed) | blocked | YAA-011 (which bundle); YAA-007/009; Monster Cart Upsell app already installed | Prompt matches the confirmed offer; no new app |
| YAA-025 | P2 | TikTok landing page (best sellers, proof, one offer) | Claude e-commerce lane (proposed) | backlog | YAA-011, YAA-014 (UTMs), Marketing creative | Page prepared unpublished; tracked link defined |

### Completed e-commerce-lane items (evidence in HANDOVER.md)
- 2026-10-11: read-only store audit against plan section 5.
- 2026-10-11: compare-at price 0.00 cleared on 30 products / 136 variants. Also logged by the sales lane (126 variants); same fix, counted once.
- Done on the live theme since, by the sales lane or Jian (14 Oct), not by this lane: announcement-bar wording, delivery time, cost-per-wear block, size-guide popup, returns tab, trust line, low-stock bar disabled on the product template in use, Clarity.

### Proposed ownership of existing shared tasks (needs Codex/Jian acceptance; not started)
- YAA-003 (size guide) and YAA-006 (mobile performance): Claude e-commerce lane.
- YAA-010 / YAA-012 (theme draft): Claude e-commerce lane rebuilds one draft from current MAIN (203435966728) carrying YAA-012, YAA-019 and YAA-020 together. **Overlap:** the sales lane prepared draft 203557044488 and proposed "YAA-010 owner decides". Not starting until accepted.

### Overlaps flagged before starting any task
- Theme work: one draft only, shared by the sales and e-commerce lanes (YAA-012/019/020).
- Delivery and shipping wording stays with YAA-002 (Codex).
- Welcome codes and popup: sales (offer), Retention (flows), this lane (display only).
- Pixels and tracking: YAA-004/005 (Codex) and Marketing ads.
