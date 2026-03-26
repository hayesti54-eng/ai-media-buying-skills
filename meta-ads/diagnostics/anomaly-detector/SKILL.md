# Campaign Anomaly Detector

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Detect, classify, and triage unexpected performance deviations in Meta Ads campaigns — including sudden CPM spikes, CTR drops, delivery collapses, conversion rate anomalies, and frequency-driven fatigue events. Anomaly detection separates signal from noise, identifies whether a deviation is platform-side, audience-side, creative-side, or external, and prescribes the correct investigative path for each.

## When to Use

- When campaign performance changes significantly (>25% shift in key metrics) without an obvious explanation
- When spend drops suddenly without manual budget changes
- When CPM spikes without a seasonal or competitive explanation
- When CTR (link click-through rate) or Outbound CTR drops while impressions remain stable
- When conversion rate drops but ad platform metrics (CTR, landing page views) appear normal
- During weekly performance reviews to identify emerging issues before they compound
- After account-level changes (new payment method, policy flag, pixel event change) that may have unintended downstream effects
- When a campaign suddenly stops spending despite being active, in-budget, and targeting a broad audience

## Inputs Required

- Campaign, adset, and ad-level performance data: impressions, reach, frequency, CPM, CPC (all), Outbound CPC, CTR (all), Outbound CTR, landing page views, cost per result, ROAS
- Delivery status and any warning flags in Ads Manager
- Date range of the anomaly and comparison period (same window from prior week or prior month)
- Recent account changes: budget edits, creative swaps, audience changes, pixel changes, bid strategy changes
- External context: seasonality, promotions, inventory changes, website issues, product pricing changes
- Account-level spend history and any policy review notices

## What This Skill Does

This skill applies a structured diagnostic tree to campaign anomalies, working from platform-level factors (delivery throttle, auction dynamics) down through audience-level factors (saturation, overlap) to creative-level factors (fatigue, format mismatch) and external factors (landing page issues, product unavailability). It produces a root cause hypothesis ranked by probability and a specific validation step for each hypothesis.

## Analysis Workflow

1. Establish the anomaly baseline: define the metric(s) that changed, the magnitude of change, the date the change occurred, and whether the change was gradual or sudden. Sudden = platform or structural. Gradual = creative fatigue or audience saturation.
2. Check Ads Manager delivery status for all affected campaigns, adsets, and ads. Look for: "Learning Limited," "Off," "Paused," any policy flags, payment failures, or "Restricted" status. These are immediate disqualifiers — if present, address before investigating further.
3. Pull CPM trend for the anomaly period vs. baseline period. If CPM increased sharply, the cause is auction-side: increased competition (seasonal, competitive entrant), audience exhaustion, or a significant change in audience targeting that moved the campaign into a more expensive segment.
4. If CPM is stable but CTR (all) dropped, the cause is creative-side: ad fatigue, creative refresh needed, or a new ad format performing below baseline. Check frequency first — if frequency exceeds 3.5+ in 7 days for cold audiences, creative fatigue is the primary suspect.
5. If CTR (all) is stable but Outbound CTR dropped, the cause is post-click: landing page issue, checkout error, product out of stock, URL redirect failure, or mobile page load speed degradation.
6. If Outbound CTR is stable but conversion rate dropped, the cause is on-site or attribution-side: pixel firing failure, CAPI gap, landing page conversion element removed, price change, or offer change.
7. If all click metrics appear normal but reported ROAS dropped, check for an attribution window change, a pixel event misconfiguration (e.g., Purchase event firing on page load instead of order confirmation), or a change in Conversions API deduplication.
8. Check frequency for the affected adsets. Frequency above 2.5 in 7 days for cold audiences and above 5.0 in 7 days for warm audiences indicates saturation-driven performance decay.
9. Cross-reference the anomaly date with: Meta system status (check Meta Business Help Center for reported outages), seasonal events (holidays, competitor sales), and account change log.
10. Produce a hypothesis stack ranked by probability, a validation test for each hypothesis, and an immediate action recommendation for the highest-probability cause.

## Output Requirements

- Anomaly summary: metric affected, magnitude, onset date, duration
- Root cause hypothesis stack: ranked list with probability rating (high/medium/low) and supporting evidence
- Validation step for each hypothesis: specific data point or action that confirms or eliminates it
- Immediate action recommendation: what to change now to stop the bleeding
- Monitoring plan: which metrics to watch over the next 48-72 hours to confirm the fix worked

## Platform-Specific Best Practices

- Meta's auction dynamics shift daily. A CPM increase of 10-20% over 7 days during competitive seasons (Q4, Valentine's Day, Mother's Day) is expected and not an anomaly requiring action.
- Frequency is calculated at the adset level using 7-day reach and impressions. Always check frequency in the same time window as the anomaly — lifetime frequency is not a useful diagnostic metric.
- The first-time impression ratio (available in breakdown reports) shows what percentage of your impressions are reaching users for the first time. A declining first-time impression ratio is a leading indicator of audience saturation before frequency metrics catch up.
- Delivery drops after creative additions are common — new ads go through a brief approval and impression allocation period that temporarily reduces delivery to existing ads in the adset.
- Meta's automated rules and Advantage Campaign Budget changes can reduce adset spend without triggering manual edit notifications. Always check automated rule logs when diagnosing unexplained spend drops.

## Guardrails

- Do not make multiple account changes simultaneously in response to an anomaly. Change one variable at a time so the cause can be isolated.
- Do not turn off campaigns purely based on a 1-2 day performance dip without checking for platform-side delivery noise.
- Anomaly detection requires a sufficient baseline period. Campaigns with fewer than 7 days of data do not have enough history to distinguish anomaly from normal learning phase variance.

## Example Requests

1. "My top-performing adset's CPA went from $18 to $47 over 5 days with no changes on my end. Walk me through figuring out what happened."
2. "My campaign dropped from $800/day spend to $200/day spend overnight. Delivery status shows Active and there are no flags. What's causing this?"
3. "My Outbound CTR stayed flat but my purchase conversion rate dropped 60% in 3 days. Is this a pixel problem or something else?"
