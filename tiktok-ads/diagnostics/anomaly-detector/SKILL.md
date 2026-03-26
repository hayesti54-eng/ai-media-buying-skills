# TikTok Campaign Anomaly Detector

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Detect sudden, unexplained shifts in TikTok campaign performance — including CPM spikes, CTR collapses, conversion tracking failures, delivery breakdowns, and bidding anomalies — distinguish them from normal creative fatigue or audience saturation, and produce a ranked cause-and-fix diagnosis to restore stable performance as quickly as possible.

## When to Use
- A campaign that was performing within normal parameters experiences a sudden 30%+ metric shift overnight or over 2–3 days without any deliberate account changes
- Spend is not being fully delivered despite available budget
- Conversion volume drops sharply while click volume remains stable — suggesting a tracking or landing page issue rather than a creative issue
- CPM spikes in isolation without corresponding creative or audience changes
- ROAS or CPA collapses on a previously stable campaign with no obvious operator-side cause

## Inputs Required
- TikTok Ads Manager 14–30 day daily export at the campaign and ad set level: Impressions, Reach, CPM, Clicks, CTR, Spend (actual vs. budget), Conversions, CPA, ROAS, Conversion Rate
- Date of anomaly onset (operator-identified or detected from data)
- Log of any recent account changes: new creatives added, budget adjustments, bid strategy changes, audience edits, pixel events modified, landing page updates
- TikTok Pixel event log if available (for conversion tracking anomaly diagnosis)
- Campaign objective, bid strategy type (Lowest Cost, Cost Cap, Bid Cap, Value-Based), and current daily budget

## What This Skill Does
This skill runs a multi-layer anomaly detection protocol that first isolates the exact metric and date of performance shift, then classifies the anomaly into one of five root cause categories: (1) Creative/Creative Fatigue, (2) Audience/Delivery Issue, (3) Tracking/Pixel Failure, (4) Bid Strategy Instability, (5) Platform/External Volatility. It produces a confidence-rated root cause diagnosis and a step-by-step resolution plan.

## Analysis Workflow
1. Establish baseline. Calculate the 7-day rolling average for each key metric in the pre-anomaly period. Define normal range as ±20% of that baseline for CPM, CTR, CPA, and Spend Delivery Rate.
2. Identify anomaly onset date. Find the first day any metric broke outside its normal range. Confirm whether the anomaly is isolated (one metric) or cascading (multiple metrics simultaneously).
3. Run anomaly classification matrix:
   - CPM spike only: suggests auction competition increase, audience saturation, or TikTok algorithm shift. Cross-check against seasonal events, competitor activity, or recent broad targeting changes.
   - CTR drop only: suggests creative fatigue or audience mismatch. Cross-check hook rate trends.
   - Conversion drop with stable clicks: suspect pixel/tracking failure first. Check pixel event logs, verify landing page Pixel code is firing, check event deduplication settings, verify conversion window alignment.
   - Spend under-delivery: check bid strategy constraints (Cost Cap or Bid Cap too tight), audience size decline, ad review policy issues, or budget pacing setting.
   - CPM spike + CTR drop simultaneously: cascading fatigue or audience exhaustion.
4. Query the change log. Any account edit within 3 days prior to anomaly onset is a prime suspect. Document each change and map it to the affected metric(s).
5. Check for TikTok platform-level events: known outages, policy enforcement waves, auction fluctuations during major shopping events or holidays.
6. For conversion tracking anomalies: verify pixel base code fires on landing page, target event fires on confirmation/thank-you page, deduplicate browser and server-side events, verify UTM parameters are intact.
7. Run bid strategy stress test: calculate actual spend vs. budget as a delivery ratio. Sub-60% delivery with no budget constraint changes suggests a bid that is too restrictive for current auction conditions.
8. Assign root cause confidence score (High / Medium / Low) to each suspected cause and rank by likelihood.
9. Produce resolution steps in priority order with expected time-to-impact for each fix.

## Output Requirements
- Anomaly summary: onset date, affected metrics, magnitude of shift vs. baseline
- Root cause classification with confidence score (High / Medium / Low) for each hypothesis
- Change log cross-reference table: which account changes correlate with which metric shifts
- Resolution playbook: ordered action steps with expected recovery timeline and success criteria per step
- Monitoring protocol: which metrics to watch hourly/daily for the next 72 hours post-fix
- Escalation flag if anomaly appears to be platform-level (outside operator control)

## Platform-Specific Best Practices
- TikTok's auction is notably more volatile than Meta's during platform-level shopping events (11.11, Black Friday, back-to-school seasons). CPM spikes of 40–80% are normal during peak auction windows — do not interpret these as account-level anomalies.
- Cost Cap bid strategies on TikTok have a known learning instability behavior: the algorithm may under-deliver for 1–3 days before finding its pacing rhythm, especially after a budget edit. This is not necessarily an anomaly.
- TikTok Pixel attribution windows default to 7-day click / 1-day view. If a landing page has been updated without re-verifying the pixel event, silent conversion tracking failures are common and often misdiagnosed as creative decline.
- TikTok's ad review system can silently restrict delivery on creatives flagged for policy review without explicit notification — always check ad-level delivery status alongside campaign-level metrics.
- Broad Targeting on TikTok can self-optimize into a narrow effective audience over time. If reach growth stalls while impression frequency climbs, the algorithm has narrowed its delivery pool.

## Guardrails
- Do not make multiple simultaneous account changes to fix an anomaly — isolate one variable at a time to avoid compounding the instability.
- Do not interpret a single-day metric drop as an anomaly — require 2 consecutive days of out-of-range performance before triggering a full investigation.
- Do not restart campaigns or reset ad sets as a first response to under-delivery — this resets the learning phase and can make short-term issues much worse.
- Never diagnose a conversion drop as a creative problem without first ruling out pixel/tracking failure — it is the most common misdiagnosis in TikTok account management.

## Example Requests
1. "My TikTok campaign CPA doubled overnight from $28 to $56 with no changes made. Nothing in the account changed. Here's 21 days of daily data — diagnose what's happening."
2. "Conversions fell off a cliff 3 days ago but click volume is actually up. I changed nothing. Walk me through every possible cause and how to verify each one."
3. "My Cost Cap campaign stopped spending yesterday — it's only delivering 20% of budget. Tell me why and give me a step-by-step fix ordered by most likely cause."
