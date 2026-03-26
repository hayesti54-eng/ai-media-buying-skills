# Retargeting Structure Reviewer

**Platform:** Meta Ads
**Category:** funnel
**Tier:** pro

## Purpose

Audit and optimize the retargeting architecture within a Meta Ads account — including audience window sizing, funnel stage sequencing, exclusion logic, offer differentiation by audience temperature, frequency management, and budget allocation relative to prospecting. A poorly structured retargeting program either under-invests in high-intent audiences (leaving easy conversions on the table) or over-invests in small, saturated audiences (wasting budget on users who have made their decision). This skill builds the optimal retargeting structure.

## When to Use

- When retargeting campaigns are not generating a materially lower CPA than prospecting
- When retargeting audiences appear small and are showing high frequency and saturation signals
- When a new account has no retargeting campaigns and needs them built
- When the retargeting and prospecting campaigns are showing audience overlap
- When preparing to scale prospecting spend and need to ensure retargeting is ready to capture the increased top-of-funnel volume
- When a client complains about seeing the same ads too many times (frequency complaint)
- When retargeting budget exceeds 30% of total Meta spend without a corresponding CPA advantage

## Inputs Required

- Website traffic volume: monthly unique visitors, broken down by page type (homepage, product pages, cart, checkout) if available
- Customer list size (if applicable)
- Past video viewers, page engagers, and Instagram profile interactions count
- Current retargeting campaign list: audience definitions, time windows, ad content, budget
- Current exclusions applied to retargeting campaigns
- Conversion volume: monthly purchases, leads, or bookings
- Average consideration period for the product (time between first visit and conversion)

## What This Skill Does

This skill designs or audits a multi-stage retargeting architecture that sequences audiences by funnel position, applies correct time windows for each stage, differentiates the offer and message by audience temperature, enforces proper exclusions to prevent retargeting converted users and overlapping with prospecting, and sizes budget relative to audience pool to avoid structural saturation.

## Analysis Workflow

1. Map all available retargeting audiences by temperature (warm = engaged but not converted; hot = high-intent, cart/checkout abandoner; very hot = recent high-intent visit within 7 days). Create a temperature matrix: audience type, estimated size, last-active window.
2. Audit existing time window choices. Common error: using a 180-day website visitor window for all retargeting. Users who visited your site 150 days ago have materially different intent than users who visited 3 days ago. Recommended window structure: 1-7 days (very hot), 8-30 days (hot), 31-90 days (warm), 91-180 days (cool — often better excluded or moved to lower-priority).
3. Verify exclusion logic. Each retargeting adset must exclude: (a) audiences at a hotter stage within the same funnel (7-day visitors excluded from 30-day visitors adset to prevent overlap); (b) past purchasers or converters (retargeting people who already converted wastes budget and creates negative brand experience); (c) prospecting campaign audiences must exclude all retargeting audiences.
4. Evaluate offer differentiation by audience temperature. Very hot audiences (cart abandoners, checkout abandoners) need urgency-based offers: limited-time discount, free shipping threshold, payment plan. Warm audiences (viewed a specific product) need consideration-stage content: social proof, comparison content, benefit reinforcement. Cool audiences (visited homepage 60+ days ago) are close to the prospecting temperature and should receive near-prospecting creative.
5. Calculate the maximum viable budget per retargeting audience: estimated audience size × expected frequency (max 5 per 7 days for warm audiences) × (CPM ÷ 1000) × 7 = maximum weekly budget for that audience. If actual budget exceeds this, structural saturation will occur within days.
6. Audit frequency caps. Meta does not apply automatic frequency caps to retargeting campaigns. If no frequency cap is set and the audience is small, a campaign will serve the same ad to the same user 10+ times per week. Set campaign-level frequency caps: 3-4 per week for cart abandoners; 2-3 per week for warm audiences; 1-2 per week for cool audiences.
7. Assess the prospecting-to-retargeting budget ratio. The retargeting pool size is determined by prospecting volume. If prospecting is underfunded, the retargeting audience will be small and will saturate quickly. Optimal ratio varies by business but a common starting point is 70-80% prospecting / 20-30% retargeting by budget.
8. Evaluate video view retargeting: if the account is running video ads, audiences of 25%, 50%, 75%, and 95% video viewers are available. These are warm audiences based on content engagement, not site behavior. Check if these audiences are being utilized and whether they are excluded from cold prospecting campaigns.
9. Assess cross-channel retargeting hygiene: if the business also runs Google Ads, email, or SMS retargeting, the user may be retargeted across all channels simultaneously. Evaluate whether Meta retargeting is complementing or overlapping with other channels' retargeting efforts.
10. Produce a retargeting architecture blueprint with recommended audiences, time windows, offer angles, frequency caps, and budget allocation.

## Output Requirements

- Retargeting audience matrix: audience type, time window, estimated size, current CPA, recommended budget, frequency cap
- Exclusion audit: current exclusions vs. required exclusions, gaps identified
- Offer differentiation map: audience temperature → recommended offer angle
- Budget allocation recommendation: split across audience stages and vs. prospecting
- Saturation risk assessment: which audiences are at risk of over-frequency
- Architecture blueprint: complete retargeting structure with sequence, windows, offers, and budget

## Platform-Specific Best Practices

- Cart and checkout abandoners (7-day window) are the highest-value retargeting segment and should always be prioritized for budget when audience size allows.
- Custom audience match rates for website visitor audiences depend on the overlap between site visitors and Meta users. In B2B industries, match rates can be as low as 20-40% because business decision-makers are less likely to have personal Meta profiles linked to business email addresses.
- Engagement-based retargeting (Page engagers, Instagram profile visitors, video viewers) is valuable for businesses with low website traffic volumes. These audiences can be significantly larger than site visitor audiences and have demonstrated brand interest.
- For very small retargeting audiences (under 5,000 people): consider consolidating into a single "all warm audiences" adset rather than segmenting by time window. Segmentation requires minimum audience size to function.
- Facebook's Advantage+ Shopping Campaigns (ASC) have built-in retargeting logic. When using ASC, do not run separate retargeting campaigns targeting the same products — they will overlap with ASC's internal retargeting.

## Guardrails

- Do not retarget converted customers with prospecting or consideration messaging. Build a separate customer retention/upsell campaign for this segment.
- Do not set a retargeting adset budget without first estimating audience size and maximum viable weekly budget. A $200/day budget on a 3,000-person audience will saturate the audience within 2 days.
- Do not skip exclusion layers to simplify structure. The efficiency loss from overlapping retargeting and prospecting campaigns outweighs the complexity of maintaining exclusion audiences.

## Example Requests

1. "I have 1,500 monthly site visitors and I'm currently running one retargeting campaign targeting all visitors from the past 180 days. How should I restructure this?"
2. "My retargeting CPA is $48 vs. prospecting CPA of $62. The gap is smaller than expected. What's likely causing retargeting to underperform and how do I fix it?"
3. "I'm about to scale my prospecting budget from $5K to $15K per month. How do I adjust my retargeting structure to handle the increased audience volume?"
