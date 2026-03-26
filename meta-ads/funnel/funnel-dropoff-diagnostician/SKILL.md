# Meta Funnel Drop-off Diagnostician

**Platform:** Meta Ads
**Category:** funnel
**Tier:** pro

## Purpose

Identify and diagnose the specific stage in the Meta advertising funnel where user drop-off is occurring — from impression to click, click to landing page view, landing page view to initiate checkout, initiate checkout to purchase — and prescribe targeted interventions for each drop-off point. Funnel drop-off analysis prevents the common mistake of attributing a conversion rate problem to the wrong stage and applying the wrong fix.

## When to Use

- When overall ROAS or CPA is below target and the cause is not immediately obvious
- When Outbound CTR is strong but cost per result is poor (problem is post-click)
- When landing page view rate is high but conversion rate is low (problem is on-page)
- When add-to-cart rate is strong but checkout completion rate is low (problem is checkout friction)
- When setting up a new campaign and wanting to establish funnel benchmarks before optimization
- When a client reports that sales are down and wants to know if Meta ads are contributing
- When diagnosing whether a performance problem is in the ad creative, the landing page, or the offer

## Inputs Required

- Funnel stage metrics from Ads Manager and Events Manager:
  - Impressions
  - Outbound CTR and link clicks
  - Landing page views (LPV rate = LPVs ÷ link clicks)
  - ViewContent events (if applicable)
  - AddToCart events
  - InitiateCheckout events
  - Purchase events (or Lead, CompleteRegistration, etc.)
- Cost per result and ROAS
- Average order value (for e-commerce)
- Google Analytics or equivalent data for on-site behavior (bounce rate, session duration, pages per session) — if available
- Campaign type: e-commerce, lead gen, or app install

## What This Skill Does

This skill builds a full conversion funnel map from impression to final conversion, calculates drop-off rates at each stage, compares stage-specific drop-off against industry benchmarks, identifies the single highest-leverage drop-off point, and prescribes the correct diagnostic question and intervention for each. It distinguishes between ad-side problems (low CTR, creative fatigue), technical problems (pixel misfires, slow landing pages), UX/offer problems (form friction, checkout complexity), and audience problems (wrong targeting, wrong funnel stage).

## Analysis Workflow

1. Build the funnel map. Pull from Ads Manager: impressions → link clicks → landing page views → (ViewContent or AddToCart if applicable) → conversion event. Calculate the rate at each transition: CTR from impressions, LPV rate from clicks, event-to-event conversion rates through the funnel.
2. Identify the funnel stage with the highest absolute drop-off (in volume). This is where most users are lost and where intervention has the highest leverage on total conversion volume.
3. Stage 1 diagnosis — Impressions to Clicks (CTR): if CTR (all) is below 1.0% for Feed placements, the creative is not capturing attention. If Outbound CTR is below 0.8% for prospecting campaigns, the offer is not compelling click intent. Below-benchmark CTR is a creative and offer problem, not a post-click problem.
4. Stage 2 diagnosis — Clicks to Landing Page Views: the LPV rate (LPVs ÷ link clicks) should be 70-85% for most campaigns. A rate below 60% indicates landing page load speed issues (mobile page loads over 3 seconds lose 50%+ of users before the page fully loads) or URL tracking parameter errors causing redirect failures.
5. Stage 3 diagnosis — Landing Page Views to AddToCart (e-commerce) or Lead Form Start: a conversion rate below 2% from LPV to AddToCart suggests an on-page problem: offer clarity, price positioning, product description, social proof absence, or CTA placement. This is a landing page and offer problem, not a media problem.
6. Stage 4 diagnosis — AddToCart to InitiateCheckout: drop-off above 60% at this stage indicates consideration friction (user added to cart but hesitated). Interventions: retargeting with urgency, social proof emphasis, guarantee or free shipping offer.
7. Stage 5 diagnosis — InitiateCheckout to Purchase: drop-off above 40% at this stage indicates checkout friction: too many required fields, no trusted payment methods, no order summary visible, unexpected shipping costs added late, required account creation. This is a UX/development problem, not a media problem.
8. Calculate the funnel efficiency metric: if each stage operated at benchmark, what would the resulting cost per purchase be? Compare this to actual cost per purchase to quantify the total performance gap caused by below-benchmark stage performance.
9. Identify whether the problem is symmetric (all audiences, all creatives) or asymmetric (one adset, one creative, one device type). Symmetric problems indicate systemic issues (landing page, pixel); asymmetric problems indicate targeting or creative-specific issues.
10. Rank drop-off stages by leverage: the stage where fixing the drop-off rate produces the largest decrease in cost per result gets the highest priority.

## Output Requirements

- Funnel map: each stage with volume, rate, and benchmark comparison
- Drop-off severity per stage: rate vs. benchmark, volume lost, estimated CPA impact
- Primary bottleneck identification: the single stage responsible for the largest performance loss
- Stage-specific diagnosis: what type of problem (creative, technical, UX, offer, audience) is causing the drop-off
- Prioritized intervention list: specific actions per stage, ordered by estimated CPA improvement
- Funnel efficiency calculation: potential CPA if all stages hit benchmark

## Platform-Specific Best Practices

- Landing page view rate is one of the most underused diagnostics in Meta Ads. A high CTR with a low LPV rate always indicates a technical issue that should be resolved before creative optimization.
- Meta reports "link clicks" and "landing page views" separately because LPV tracking requires the pixel to fire on the destination page. If LPV count is zero, the pixel is not installed on the landing page.
- For mobile e-commerce, the InitiateCheckout to Purchase completion rate is typically 50-65%. Rates below 40% signal a mobile-specific UX problem in the checkout flow.
- ViewContent-to-AddToCart rate benchmarks: ecommerce average is 8-12%. Below 5% indicates a product-page problem (price, description, imagery, social proof). Above 20% indicates highly motivated traffic, often a warm audience.
- The first-time impression ratio affects funnel efficiency: high-frequency audiences (frequency 4+) behave differently in the funnel — they have seen the ad before, so CTR may be lower but conversion rate may be higher for those who do click (they are pre-qualified by prior exposure).

## Guardrails

- Do not attempt funnel analysis with fewer than 500 impressions per stage. Data below this threshold is not statistically meaningful.
- Do not assume that improving the weakest funnel stage will automatically improve overall conversion volume — fixing one bottleneck often reveals the next bottleneck.
- Do not attribute checkout drop-off to media without auditing the checkout UX first. Checkout abandonment is almost always a UX or offer problem, not a targeting problem.

## Example Requests

1. "My CTR is 1.8% but my cost per purchase is $120 against a $45 target. Where is the funnel breaking down and what do I fix first?"
2. "My landing page view rate is 52% even though my link click rate is strong. What's causing the gap and how do I fix it?"
3. "My add-to-cart rate is good but my checkout completion rate is 25%. Is this a media problem or something else, and what should I do?"
