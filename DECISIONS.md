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
