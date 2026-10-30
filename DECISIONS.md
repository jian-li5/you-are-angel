# Decisions and approvals

## 2026-10-17 — Coordination repository
User requested a new You Are Angel project so Codex and Claude Code can read shared progress and avoid duplicate work.
Created a private GitHub repository under jian-li5. This authorizes repository setup and coordination documentation.

## External systems
The user's audit instruction requires all external store systems to remain read-only without explicit approval.
No approval for live Shopify edits, publication, customer emails, advertising or deployment is recorded.
Repository ownership/task proposals do not override that requirement.

## Coordination
Use this repository as shared persisted state. Agents do not see one another's chat sessions automatically.
Reconcile existing Claude work before implementing audit recommendations.
Do not import or replace an existing project wholesale without reviewing its status and remote.

## 2026-10-11 to 2026-10-16 — Sales plan project (pre-repo approvals)
Recorded by Claude Code during YAA-001 (2026-10-17) from the "Sales plan" Claude project chat. Jian's approvals there predate this repository's read-only rules and cover only the changes listed. They do not authorize further changes.
- 2026-10-11: Jian set the project brief to act as sales plan manager and execute the plan's tasks. In a structured question Jian chose:
  - free shipping on every order (no threshold)
  - "Any 2 sets – 15% off" replacing Buy 2 Get 1 Free from 16 Oct
  - made-to-order for sold-out sizes
  - keeping the $25.99 designs as entry items

  Claude then made the store changes listed in HANDOVER.md (2026-10-17 Claude entry).
- 2026-10-14: Jian asked Claude to create the United States market in USD ("yes please"). Jian applied the cost-per-wear block and Shipping tab text himself.
- 2026-10-16: Jian asked for footer social links. Claude prepared an unpublished draft theme. **No approval to publish it is recorded.**

### Open conflict — main offer (YAA-011)
Observed in store 2026-10-17 (read-only): BUY 2 GET 1 FREE is active with no end date (updated 2026-10-11T15:16:11Z), and the "Any 2 sets – 15% off" discount was deleted. Other Claude projects' scheduled tasks now describe B2G1 as the single main offer. Which decision is current is not recorded here. **Jian to confirm.**

## 2026-10-11 — E-Commerce plan project (pre-repo)
Recorded by Claude Code during YAA-001 (2026-10-17) from the "E-Commerce plan" Claude project chat. On 2026-10-11 Jian asked Claude to act on the plan's e-commerce section, "use any skills or app which are necessary". Under that instruction Claude cleared the 0.00 compare-at price on 30 products (136 variants), a display fix. Claude then asked for decisions on shipping, the offer and social URLs before any theme work; no answer is recorded in that project. This record does not authorize further changes, and the instruction predates this repository's read-only rules.
## 2026-10-11 to 2026-10-14 — Marketing plan project (no approvals for agent store changes)
Recorded by Claude Code during YAA-001 (marketing-plan lane, 2026-10-17) from the "Marketing plan" Claude project chat. That project's sessions made **no** Shopify changes; every Shopify call was a read.
- 2026-10-11 (~13:37 UTC): Jian said in that chat:
  - he had tested BUY 2 GET 1 FREE and it works, and wants a companion offer next to it
  - he would delete "10% off $99+" and "20% off $199+" and turn off the discount event himself

  This is evidence for YAA-011, **not** a decision between B2G1 and the 15% two-set bundle.
- 2026-10-14 12:00 UTC (read-only): both tier discounts showed status EXPIRED. Whether the discount event or timer is off has not been verified.
- The 15:16 UTC change on 2026-10-11 has no recorded author in this project. It removed B2G1's end date, made it combine with shipping, and edited the sales scorecard prompt. This project's sessions did not make it.
## 2026-10-11 to 2026-10-17 — Retention plan project (pre-repo approvals)
Recorded by Claude Code during YAA-001 (2026-10-17) from the "Retention plan" Claude project chat. These approvals predate this repository's read-only rules. They cover only the changes listed and authorize nothing further.
- **2026-10-11.** Jian asked Claude to "exercise the part for retention plan, use any skill/app as necessary". Under that request Claude created in Shopify, with each write confirmed through the Shopify app prompt:
  - 3 customer segments
  - discount codes ANGELRETURNS and ANGELGLOW15
  - customer metafield definition `angel.nail_size`
  - nail-size values and tags on 2 customer records

  Details are in docs/retention/status-2026-10-17.md. No email was sent.
- **2026-10-17.** Jian decided to skip Halloween and move straight to Black Friday (also recorded by Operations as OPS-01).
- **2026-10-17.** Email automations will run in **Shopify Messaging**. SendWILL is on its Free plan, which has no automations, so it keeps only the popup and its code email. Jian asked Claude to switch on the 4 automations. Claude could not: Shopify's Cloudflare check blocked both agent browsers, and the Admin API cannot create Messaging automations. Jian is building and switching them on himself in Safari. **Each send-capable automation is Jian's own action; Claude holds no approval to send customer email.**

### Open conflicts raised by the retention lane
- **R-O1.** The claude.ai "Decision Log" doc duplicates this file. Proposal: this file is authoritative. Jian to confirm.
- **R-O3.** Which 10% welcome mechanism is canonical: the SW- popup codes, WELCOME10, or both. Jian to decide (see YAA-007).
- **R-O5.** UGC reward: the shared ANGELGLOW15 (past buyers only, once each) or one code per customer (Sales log). Jian to decide (YAA-063).
- **Black Friday early-access date.** Marketing Plan v2 says 24 Nov; Operations OPS-20 says 26 Nov. Jian to decide.

## 2026-10-20 — Main offer (closes YAA-011)
Jian (E-Commerce plan chat, 2026-10-20): the offer was updated in the Operations plan. That plan is not in this repo. The schedule below is what the live store shows (read-only; discounts last updated 2026-10-19 10:40 UTC):
- BUY 2 GET 1 FREE until 26 Oct 09:00 UTC
- Bundle & Save: 2 sets 15% off, 3+ sets 25% off, 26 Oct – 27 Nov 04:59 UTC
- Black Friday: 2 sets 20% off, 3+ sets 30% off, 27 Nov 05:00 UTC – 1 Dec 04:59 UTC
- Bundle & Save from 1 Dec, no end date
- Free shipping on every order

The Operations lane should add its own record when it reconciles. This entry is not approval for any store change.

## 2026-10-20 — Repository merge
Jian asked the E-Commerce lane to merge the lane branches so tasks are not repeated. This approval covers this repository's main branch only.

## 2026-10-20 — Product title fix and delivery time
- **Approved and deployed:** Jian approved fixing the "Stawberry Bloom" spelling (E-Commerce plan chat, 2026-10-20 21:22 Asia/Shanghai). Claude changed the title of product 10454974890248 to "Strawberry Bloom" at about 13:25 UTC. Scope: that one title only. The handle (strawberry-bloom-press-on-nails) and SEO title were already correct and were not changed. Verified by the mutation response.
- **Business fact (YAA-002):** Jian states delivery is now 10–14 working days. This is not approval to change the other places that still say 7–10; each needs its own scoped approval.

## 2026-10-30 — Marketing plan project: product reference and creator video
- Jian, Marketing plan chat, 2026-10-30 16:38 Asia/Shanghai: "please add yaa160 to the product description". Scope: append "Product Ref: YAA160" to Angel Aura Shimmer Base Set (product 10597815320840). Nothing else changed.
- Hannah's creator video was added to the homepage "Seen on TikTok" section by Jian himself in the theme editor. Agents cannot write the MAIN theme. No agent approval was involved.
