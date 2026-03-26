# Breakdown Analysis Reporter

**Platform:** Meta Ads
**Category:** reporting
**Tier:** pro

## Purpose

Extract actionable insights from Meta Ads breakdown data — segmented by age, gender, placement, device, region, time of day, and impression device — to identify which audience segments are most efficient, where budget is being wasted, and how to optimize targeting, scheduling, and creative strategy using granular segmentation data.

## When to Use

- When overall campaign performance looks acceptable but there may be hidden efficiency disparities across segments
- When preparing for bid adjustment decisions by age, gender, or placement
- When diagnosing why two campaigns with similar targeting show different performance
- When a client asks which age or gender segment is converting best
- When evaluating whether to narrow or expand targeting after a campaign has accumulated sufficient data
- When reviewing placement efficiency to decide whether to exclude specific placements
- When analyzing device-level performance to diagnose mobile vs. desktop conversion rate differences
- After accumulating at least 14 days of campaign data at meaningful spend levels (minimum $1,000 total or 50+ conversions)

## Inputs Required

- Ads Manager breakdown data with at least one of: age/gender, placement, device, region/DMA, impression device, time of day
- Minimum reporting period: 14 days (30 days preferred for statistical reliability)
- Campaign objective and primary KPI: cost per result, ROAS, or Outbound CTR
- Total spend per segment for the period
- Number of conversions or results per segment
- Target cost per result or target ROAS
- Whether CBO or ABO is in use (affects how to interpret spend allocation across segments)

## What This Skill Does

This skill applies statistical rigor to Meta breakdown data, identifies segments that are significantly over or underperforming the account average, flags segments with insufficient spend to draw conclusions, distinguishes between delivery bias (Meta is spending more on certain segments by algorithm choice) and genuine performance differences, and recommends targeting or bidding adjustments based on the analysis.

## Analysis Workflow

1. Pull breakdown data from Ads Manager for the selected dimension (start with age/gender, then placement, then device). Export all columns: impressions, reach, CPM, CTR (all), Outbound CTR, cost per result, ROAS, spend, results.
2. Calculate a weighted account-average cost per result. This is the baseline against which each segment is compared. Do not compare segments against each other — compare each segment against the account baseline.
3. Flag segments with insufficient data for conclusions: less than 500 impressions, less than 10 conversions, or less than $100 in spend. These segments cannot support actionable decisions and must be labeled as "inconclusive."
4. For age/gender breakdown: identify which age-gender combinations are performing more than 20% above or below the account average cost per result. Segments performing 20-40% above average are overspend candidates for exclusion or separate lower-bid targeting. Segments performing 20-40% below average (more efficient) are expansion candidates.
5. For placement breakdown: calculate cost per result per placement. Common finding: Facebook Feed and Instagram Feed drive the majority of results; Audience Network often shows the lowest CPM but weak conversion rates. Flag any placement where spend exceeds 10% of total budget but cost per result is more than 2x the account average.
6. For device breakdown: compare mobile vs. desktop cost per result. For e-commerce, mobile traffic often generates more clicks but desktop sessions often convert at higher rates due to checkout complexity. A mobile/desktop conversion rate gap of more than 2x warrants investigation of mobile checkout UX, not just targeting adjustments.
7. For time of day breakdown: identify peak efficiency windows (hours with both high volume and low cost per result). Identify dead windows (high spend, high cost per result, low volume). Use this to inform dayparting decisions — but require at least 30 days of data before dayparting, as day-of-week and time-of-day variation is high in short windows.
8. For region/DMA breakdown: identify whether certain geographic markets are underperforming. High-CPM markets (New York, Los Angeles, San Francisco) may not be worth the premium for most advertisers. Tier-2 and Tier-3 markets often have lower CPMs and acceptable conversion rates.
9. Assess whether observed performance differences are driven by Meta's delivery algorithm (the algorithm is sending more budget to segments it predicts will convert) vs. genuine segment quality differences. In CBO campaigns, the algorithm's spending choices reflect its optimization signal — trust delivery allocation unless cost per result data contradicts it.
10. Produce a segment efficiency matrix with specific targeting recommendations.

## Output Requirements

- Segment efficiency matrix: dimension, segment, spend, results, cost per result, vs. account average, efficiency rating (Outperforming / Aligned / Underperforming / Inconclusive)
- Budget waste estimate: spend in underperforming segments that exceeds 2x target cost per result
- Quick targeting wins: specific exclusions or inclusions with estimated cost per result improvement
- Inconclusive segments: list with minimum additional spend required to reach a conclusion
- Dayparting opportunity: if time of day data supports it, specific hour windows with efficiency scores

## Platform-Specific Best Practices

- Age and gender targeting exclusions reduce the audience pool available to Meta's algorithm. Only exclude a segment if you have statistically significant data showing poor performance over 30+ days and 100+ conversions. Premature exclusions can damage delivery.
- CPM varies dramatically by placement. Never compare Audience Network CPM to Facebook Feed CPM as evidence of performance difference — they serve completely different inventory.
- Advantage+ Audience removes the ability to analyze breakdowns by explicitly defined audience segment because the targeting is algorithm-defined, not user-defined. In Advantage+ campaigns, breakdown data reflects algorithmic choices, not your targeting parameters.
- The device breakdown in Ads Manager reflects the device on which the ad was seen, not the device used to convert. Cross-device attribution means a mobile impression may lead to a desktop conversion — keep this in mind when interpreting device-level cost per result.
- Meta's breakdown data is sampled at high scale, especially for smaller segments. Breakdowns with fewer than 1,000 impressions in a segment should be treated as directional, not definitive.

## Guardrails

- Do not make targeting exclusions based on fewer than 30 days of data or fewer than 50 conversions per segment.
- Do not exclude the highest-CPM segment by default. High CPM can indicate high-value users — evaluate cost per result, not CPM in isolation.
- Do not apply dayparting to campaigns still in the learning phase. Delivery restrictions during learning extend the time to exit learning.

## Example Requests

1. "My campaign is targeting 25-65 age range. Break down my cost per lead by age bracket and tell me which age groups to exclude and which to scale."
2. "My Audience Network placement is spending 25% of my budget at a $12 CPM but my cost per purchase is $85 vs. $38 on Feed. Should I exclude it and how do I do that?"
3. "I want to implement dayparting for my lead gen campaign. I have 45 days of data. Walk me through analyzing my time-of-day breakdown to find the optimal schedule."
