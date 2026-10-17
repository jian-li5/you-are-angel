> **Status note added 2026-10-17 (YAA-001 reconciliation):** this is the original Sales-plan project log, copied as written (11–16 Oct 2026, Asia/Shanghai). Some entries are now **superseded by later store changes made outside this project**. Read-only Shopify checks on 2026-10-17: "Any 2 sets – 15% off" no longer exists; BUY 2 GET 1 FREE is active with no end date (last updated 2026-10-11T15:16:11Z); the draft theme is still unpublished. See HANDOVER.md (2026-10-17, Claude, YAA-001) for the current state and the open conflict.

# You Are Angel: Sales Execution Log

Plan: *You Are Angel – 50 Sales a Day Plan (2026-10-11)*. Week 1 starts Mon 12 Oct 2026.

## 2026-10-11: Week 0 setup (done in Shopify)

### Audit findings (live store, last 30 days)
- 387 sessions, 6 add-to-carts, 2 reached checkout, 0 orders. 70% of sessions are "direct", Instagram sent 86, TikTok sent 0.
- Shipping: an automatic "Free shipping for all orders" discount was already active, but the site said "free over $59". The discount also could not combine with any code or with Buy 2 Get 1, so a welcome code could make an order cost more.
- 137 of 140 products had at least one size sold out. Extra-small was in stock on only 2 designs.
- 30 products (126 sizes) showed a crossed-out compare-at price of €0,00.
- Main market is the EU (EUR). The US sits inside "International".
- 13 designs are priced at $25.99, below the plan's $29.99 floor.
- A 10% popup welcome code already exists (SW-… codes, one use per customer).

### Changes made
| Change | Detail | How to undo |
|---|---|---|
| Removed the €0,00 compare-at price | 126 sizes on 30 products set to no compare-at price | Not needed (it was a display bug) |
| Free shipping on every order | Renamed "Free shipping on every order"; now combines with product and order discounts | Discounts › edit combinations |
| Buy 2 Get 1 Free ends | 15 Oct 23:59 US Central (it had no end date before) | Discounts › edit end date |
| **New: Any 2 sets – 15% off** | Automatic discount, starts 16 Oct 00:00 US Central, minimum 2 items, combines with free shipping | Discounts › deactivate |
| Popup 10% codes + "20% off $199+" | Now combine with free shipping | Discounts › edit combinations |
| Made to order | 139 products (all sizes): keep selling when out of stock. The storage brochure was not changed | Product › variant › untick "Continue selling when out of stock" |
| New collection: Angel Essentials – Your First Set | The 13 designs at $25.99, positioned as the entry purchase | Collections › delete |
| Weekly scorecard | Scheduled task every Monday at 08:52 (Shanghai time); sends the scorecard by push and email | Scheduled tasks › pause |

Decisions taken by Jian: free shipping on all orders; Any 2 sets 15% off replaces Buy 2 Get 1 from 16 Oct; sold-out sizes become made to order; $25.99 sets stay as entry items.

## Jian to do (theme editor, about 15 minutes)

1. **Announcement bar and hero:** replace "Free shipping for order value over $59" everywhere (announcement bar, hero, the "Free shipping on orders over $59.00" feature strip).
   - Until 15 Oct: `Free shipping on every order ✦ Buy 2 Get 1 Free ends 15 Oct ✦ Handmade in your size`
   - From 16 Oct: `Free shipping on every order ✦ Any 2 sets 15% off ✦ Handmade in your size`
2. **Product page trust block:** Online Store › Customize › Products › Default product › Add block › Custom Liquid, placed under the Buy buttons. Paste:

```liquid
<div style="border:1px solid rgba(0,0,0,.12);border-radius:10px;padding:12px 14px;font-size:14px;line-height:1.55;margin-top:8px">
  <p style="margin:0 0 6px">✦ <strong>About {{ product.price | divided_by: 5 | money }} a wear</strong>: reusable 5+ times, less than one salon visit.</p>
  <p style="margin:0 0 6px">🚚 <strong>Free shipping on every order</strong> · ships in 7–10 working days</p>
  <p style="margin:0 0 6px">🤍 Size sold out? We hand-make it for you; allow 5–7 extra days.</p>
  <p style="margin:0">💞 Pick any 2 sets and save 15% · <a href="/pages/size-guide">Find your size in 2 minutes</a></p>
</div>
```
   Check the size-guide link matches your page's real URL. The 2-sets line is accurate from 16 Oct.
3. ~~US market in dollars~~: **done 14 Oct** (Claude). New "United States" market in USD, taxes added at checkout; the US was removed from International. Checked live: Petal Parade shows $35.99 USD and "About $7.19 a wear".
   - 14 Oct: cost-per-wear and Preorder note block live; Shipping tab now says "Delivered in 7–10 working days" (+5–7 days for Preorder sizes). The back-in-stock buttons are already hidden on Preorder sizes, so no change was needed.
4. **Social links:** Theme settings › Social media: add TikTok, Instagram and Pinterest so they show in the footer.
5. **Tell the maker:** sold-out sizes now sell as made to order. The Monday scorecard lists oversold sizes to produce.

- 14 Oct: Microsoft Clarity installed through the Shopify app (project ID yxig89stuu). Checked live: it loads on product pages and records visits.

- 16 Oct: Claude made a draft theme copy, "DRAFT 16 Oct – social links + 2 sets 15% off" (ID 203557044488). It has Instagram, TikTok and YouTube links in Theme settings, a FOLLOW US footer column with the social icons switched on, and "Any 2 sets 15% off" in place of the Buy 2 Get 1 text in the top bar, the top-bar dropdown panel and the product-page scrolling text. Jian still needs to fix the homepage feature line "Free shipping on orders over $59.00" in the draft, then publish it after 1 pm Shanghai time on 16 Oct. Logging in to Shopify admin from the Claude browser and from Chrome was blocked by the Cloudflare check.

## Still open
- Creator list (name, handle, date sent, posted Y/N, link) is needed to create a personal code for each creator and run the recovery messages.
- Is the TikTok bio link live, and is it tracked? (Plan open question 1.)
- UGC reward (15% off the next order for a photo or video) should be issued per customer, not as one shared code. Set it up when the post-purchase email flow is built.
