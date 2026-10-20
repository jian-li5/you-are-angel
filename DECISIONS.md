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
