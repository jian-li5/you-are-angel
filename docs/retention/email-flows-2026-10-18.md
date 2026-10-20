# You Are Angel — eight email flows: copy and build specification
Prepared 2026-10-18, Asia/Shanghai. Task YAA-070; implementation follow-up to retention YAA-060.

STATE: PREPARED ONLY. Not installed, activated, test-sent or sent.
Platform selected by Claude retention reconciliation: Shopify Messaging. Current admin automation state has not been inspected. Available connected tools do not expose email automation creation/activation. No discounts changed.
Welcome flow is out of scope: reportedly underway; do not recreate it.
This branch supplements claude/YAA-001-retention; it does not supersede its decisions or silently merge it.

## Reconciliation
Read retention branch TASKS.md and HANDOVER.md on 18 Oct.
That branch reports ANGELRETURNS ($10 off 2+ items) and ANGELGLOW15 (15%) already active, past buyers only, once per customer, shipping-combinable only, 0 uses on 17 Oct. These are Claude's recorded checks, not a new live verification here.
Review current discounts before using them. Never create a second code with the same purpose.
Open dependencies: authoritative delivery promise YAA-002; main offer YAA-011; shared versus customer-specific UGC reward YAA-063; current automation inventory and active welcome/review flows.

## Global build rules
- Inspect current automations first: name, ID, status, trigger, delay, audience, exit rules, template and owner. Reuse/edit drafts only within approved scope. Do not create overlapping flows.
- All promotional sends: subscribed and not unsubscribed/suppressed, bounced or complained. Recheck eligibility immediately before every send. Keep unsubscribe and sender identity/address components.
- P1 below is service-only and belongs in the existing shipping confirmation; avoid a duplicate shipping email. Keep order/tracking access available for service recipients.
- Customer-facing text has one main CTA. Bracketed labels below describe required dynamic links/blocks, not ready-to-send placeholder text. Resolve all before review.
- Do not paste recovery tokens/customer URLs into git. Recovery links must be platform-generated for that checkout. Order links must belong to the recipient.
- User's approval must specify exact drafts, recipients/eligibility, schedule, offers and activation. Sending a test is also an email send and requires an approved test address.
- Set one timestamp for each sequence. A2 is 24 hours from abandonment (23 hours after A1); A3 is 48 hours total (24 hours after A2). Verify when Shopify's abandonment trigger fires; do not add an assumed extra hour to an already delayed trigger.
- Before each abandonment send, exit if purchase/recovery occurred, checkout is invalid, no purchasable item remains, or eligibility was withdrawn. Show only valid purchasable options; do not promise inventory reservation.
- One recovery sequence per checkout; new activity must not create concurrent sequences for the same person. Suppress win-back during recovery. Recommended starting frequency cap: one marketing email per customer per 24 hours, prioritizing recovery over win-back and newsletter. Confirm how Messaging implements this; default template exclusions must not silently block A2/A3.
- No historical backfill on activation without separate approval.
- Persist sequence/customer deduplication state in supported platform mechanisms, not customer data in this repo.

## A — Abandoned checkout (marketing)
Trigger: eligible identified customer abandons checkout. Do not trigger merely on adding to cart.

### A1 — target 1 hour after abandonment
Subject: You left something beautiful behind
Preview: Pick up where you left off.
Body:
Your next little piece of wearable art is waiting to be discovered.

You can return to your checkout below. Availability and prices are confirmed when you check out.

[Dynamic product block: image, selected size, current price]
CTA: Return to checkout [recipient-specific recovery link]

### A2 — target 24 hours after abandonment
Subject: A little help finding your fit
Preview: Let's make choosing your size feel easier.
Body:
Not sure which size to choose?

Our standard sizes list the width of each nail. Measure your natural nails and compare them with the widths on your chosen set.

Need a hand? Reply with your measurements and the design you're considering—we'll help you choose.

CTA: Return to checkout [recovery link]
Secondary text link: View the size guide [verified working measurement guide]

No reviews inserted until genuine text, source and permission are verified (YAA-008). Do not claim "most questions" or a two-minute completion time without evidence. If guide is broken, block this version until repaired or replace guide link with support-only copy.

### A3 — target 48 hours after abandonment
Subject: Still thinking about your set?
Preview: A final reminder, whenever you're ready.
Body:
Here's one last reminder about the design you were exploring.

If it still feels like you, you can return to checkout below. Please check the selected size, availability and delivery information before ordering.

Questions about fit or timing? Just reply—we're happy to help.

CTA: Return to checkout [recovery link]
No false scarcity, hold deadline or delivery promise. Do not add a discount without a separate decision.

## P — Post-purchase

### P1 — on actual dispatch, service-only
Use existing shipping confirmation, not an additional marketing automation.
Subject: Your You Are Angel order is on its way
Preview: Track your parcel and get ready for your first wear.
Body:
Your order is on its way.

Track your parcel for the latest delivery updates.

While you wait, get ready for your first wear: gently push back your cuticles, lightly buff if suitable, and clean your natural nails with the prep pad. Let them dry before applying.

Use the application and removal instructions for your chosen adhesive.
CTA: Track my order [shipment-specific tracking link]
Secondary text link: Watch the application guide [verified video matching supplied adhesive]

Do not promise arrival 7–10 days after dispatch while total lead time is unresolved. Only send after actual dispatch event, not order payment. Partial fulfilment: display dispatched items and remaining items clearly; do not falsely say entire order shipped.

### P2 — 5 days after confirmed delivery (preferred)
Fallback: dispatch +12 days only if delivery status checked immediately before send. If not delivered/unknown, hold this email rather than assume arrival.
Subject: A little care for your angel nails
Preview: Tips for removal, storage and your next wear.
Body:
How is your set feeling?

To keep it ready for another occasion, follow the removal instructions for the adhesive you used. Take your time, and never pry or force a nail off.

Once removed and cleaned according to the care guide, let the nails dry and store them in size order.

If a nail didn't fit, reply with your order number and the size you tried—we'll help with the next step.

CTA: View the care guide [verified adhesive-specific guide]

Marketing-consented audience for this retention automation. Do not promise 5+ wears, universal ten-minute soak removal or a guaranteed replacement. Glue and tabs need different instructions; block guide link until verified.

### P3 — 12 days after confirmed delivery (preferred)
Fallback: dispatch +19 days only after delivery is confirmed. Suppress for unresolved fit/damage complaint, refund or return.
Subject: Show us your angel nails
Preview: We'd love to see your look.
Body:
Made them your own? We'd love to see.

Share a photo or video of your set, tag @youareangel, and reply with the link.

[APPROVED REWARD BLOCK — choose only after YAA-063 and live discount validation]
Eligible customers can receive 15% off a future order as a thank-you for sharing. We'll confirm the terms and your reward when you reply.

CTA: Share my look [mailto to confirmed monitored reply address, or supported reply action]

Optional independent text below:
You can also leave an honest review on your product page—every experience is welcome. The sharing reward isn't conditional on leaving a review.

Draft block above is not send-ready until reward terms, eligibility and fulfilment are approved. Do not show the shared ANGELGLOW15 code unless the shared-code decision is confirmed. Customer posts are not automatic permission for brand reuse: ask separately before reposting. Do not encourage only positive reviews. Check existing Judge.me review requests to avoid duplication.

## R — Win-back (marketing)
Anchor: latest qualifying purchase date. Only delivered, paid, non-cancelled, non-refunded orders; re-evaluate purchase date before each send.
Exclude unresolved support/return cases, subscribers who never purchased, and customers who already used a once-per-customer reward. A new purchase exits sequence and resets eligibility.

### R1 — day 45 after latest purchase
Subject: Find your next little piece of wearable art
Preview: Discover a new design for your next mood.
Body:
Ready for a different mood?

Explore a few designs from You Are Angel, each with its own little details to make your look feel personal.

[Three currently available designs with image, price and product link]

[OFFER BLOCK — only when validated and approved]
As a returning customer, enjoy $10 off two or more eligible sets with ANGELRETURNS.
Add two eligible sets at checkout, then enter your code.
[Validated currency, exclusions, once-per-customer, combination and expiry terms]

CTA: Find my next set [verified collection link]

Do not say the size is saved: existing metafield values on two customers do not prove a working reorder preselection. Do not label products "newest" unless based on current publication/product data.
$10 must explicitly match the actual discount currency; suppress or use approved localized wording for incompatible markets.

### R2 — day 60 after latest purchase
Subject: A little hello from You Are Angel
Preview: Your next design is here when you're ready.
Body:
One last little hello from us.

If you'd like to explore a new look, browse our latest collection below.

[OFFER BLOCK — show only if current valid offer remains unused]
Your ANGELRETURNS offer is still available: $10 off two or more eligible sets.
[Same validated terms as R1; do not invent urgency or expiry]

If press-ons weren't quite right for you, reply and tell us what would have made the experience better.

CTA: Explore the collection [verified seasonal collection]

No offer version: omit offer block entirely and retain collection/help text. Do not automatically substitute a new incentive.

## Setup acceptance and test cases
1. Current active/draft flow inventory captured; no duplicate welcome, shipping, recovery or review sends.
2. Subscriber who purchases after A1 receives neither A2 nor A3.
3. Unsubscribe, bounce or suppression during a wait prevents every subsequent promotional send.
4. Repeat trigger/new checkout does not produce parallel recovery series.
5. Recovered checkout and no-longer-purchasable variant exit safely.
6. Delay totals match 1/24/48 hours from verified abandonment timestamp; default template exclusions reviewed.
7. Non-subscriber receives service shipping notice only; no retention promotion from these specs.
8. Partial fulfilment and delayed/unknown delivery do not produce "arrived" claims or early review requests.
9. New order between R1 and R2 cancels R2; once-only discount already used => omit offer/suppress as designed.
10. Reward is separate from review sentiment and brand reuse permission; no duplicate Judge.me request.
11. Discounts exist and pass eligible-customer, quantity, currency, expiry and stacking checks; no code creation.
12. Preview desktop/mobile, image alt text and readable text; every dynamic link resolves for the correct recipient.
13. Sender/reply mailbox, domain authentication and unsubscribe tested with an approved test recipient before activation.
14. No internal placeholders, fake reviews or unverified guarantees reach rendered email.
15. Store approval reference, flow IDs, template versions and activation timestamp recorded after explicit approval. Start with no backfill.

## Measurement
Per flow/email: entered, eligible, sent, delivered, unique clicks, attributed orders/net sales, unsubscribes, complaints and suppression reasons.
Use one stated attribution window; platform attributed revenue is not proven incremental revenue.
Recovery = recovered eligible checkouts / entered eligible checkouts; exclude manual/test orders and report counts.
At current order volume, start with functional QA and absolute counts; do not promise uplift or reliable A/B winners.
Monitor duplicate sends and invalid links immediately. Pause only with approved access/scope if issues appear.

## Current blockers to implementation
- No connected tool exposes Shopify Messaging flow drafting/activation; admin UI access and existing flow inventory not yet verified here.
- Reply address, care/video/guide URLs and intended audience must be verified.
- YAA-002 delivery, YAA-063 reward mechanism and current discount terms remain unresolved.
- Need approval for concrete drafts, test recipient and activation; this document does not grant it.

## Official sources checked 2026-10-18
- https://help.shopify.com/en/manual/promoting-marketing/create-marketing/shopify-messaging/marketing-automations
- https://help.shopify.com/en/manual/promoting-marketing/create-marketing/migrate-abandoned-checkout
- https://help.shopify.com/en/manual/promoting-marketing/create-marketing/shopify-messaging/marketing-automations/create?trk=article-ssr-frontend-pulse_little-text-block
- https://help.shopify.com/en/manual/shopify-flow/reference/triggers/customer-abandons-checkout?itcat=partner_blog&itterm=api_deprecation_update_2021_01&link_search=true&q=Helen+Lin

Shopify documents native marketing automations and custom workflows; default recovery audiences are subscribed customers. Exact current trigger/delay and suppression behavior must be inspected in the store before building this sequence.
