# Learning Phase & Learning Limited Diagnostician

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Diagnose why an adset is stuck in the learning phase, flagged as Learning Limited, or resetting learning repeatedly. The learning phase is Meta's algorithm calibration window — mismanaging it is one of the most common causes of poor campaign performance, wasted spend, and unpredictable delivery. This skill identifies the root cause of learning instability and prescribes the minimum structural or operational change required to exit learning and reach stable delivery.

## When to Use

- When an adset has been in the learning phase for more than 7 days without reaching Stable delivery
- When the delivery column shows "Learning Limited" in Ads Manager
- When learning phase keeps resetting after minor edits
- When performance is volatile week-over-week with no clear external cause
- When a budget increase or creative swap causes delivery to collapse temporarily
- Before making account-level changes that could trigger learning resets at scale
- When onboarding a new client account with multiple adsets and identifying which are degrading overall performance

## Inputs Required

- Current delivery status per adset: Learning, Learning Limited, Stable, or Off
- Conversion events per adset over the last 7 days (from Ads Manager breakdown)
- Adset daily budget or campaign budget
- Optimization event selected (Purchase, Lead, AddToCart, etc.)
- Number of active ads per adset
- Recent edit history: budget changes, audience edits, creative swaps, bid changes, targeting changes
- Bid strategy: Lowest Cost, Cost Cap, or Bid Cap
- Audience size estimate
- Account spend level over the past 30 days

## What This Skill Does

This skill systematically works through the known causes of learning instability on Meta — insufficient conversion volume, over-segmentation, aggressive bid caps, frequent edits, audience size constraints, and mismatched optimization events — and returns a ranked diagnosis with specific corrective actions. It differentiates between "learning phase" (not yet enough data) and "Learning Limited" (structural barrier to collecting enough data) to prescribe the right fix for each.

## Analysis Workflow

1. Pull the 7-day conversion count per adset. Meta requires approximately 50 optimization events per adset per week to exit the learning phase. Flag any adset with fewer than 25 optimization events in 7 days as conversion-volume-constrained.
2. Check the optimization event selected. If the campaign is optimizing for Purchase but getting fewer than 25 purchases/week, determine if a higher-funnel event (AddToCart, InitiateCheckout, ViewContent) would generate sufficient volume while still being predictive of the actual business outcome.
3. Review the bid strategy. Cost Cap and Bid Cap strategies require more volume to calibrate than Lowest Cost. If the account is in early stages with limited data, Lowest Cost is the correct starting strategy to exit learning before switching to cost controls.
4. Examine the cost cap or bid cap level. A cap set too close to or below Meta's current efficient delivery rate will cause delivery throttling and learning stalls. Compare the cap to the campaign's actual average CPL/CPA over the last 30 days.
5. Audit the adset segmentation. Count the total number of active adsets targeting the same or overlapping audiences. Excessive segmentation fragments the data pool — each adset needs its own 50 events/week. Consolidation is typically the fastest fix for Learning Limited caused by low volume.
6. Review edit history for learning resets. The following edits reset learning: changing the optimization event, changing the bid strategy, changing the audience, changing the budget by more than 25% in a single edit, pausing and reactivating an adset, adding or removing a significant number of ads. Flag recent edits that triggered resets.
7. Check audience size. Audiences under 200,000 in a geographic market can restrict delivery to the point where 50 conversions/week is mathematically impossible at the given budget level. Calculate: estimated audience size × estimated CTR × estimated CVR vs. required conversion volume.
8. Check for Auction Overlap across adsets. If two adsets are serving the same audience simultaneously, they compete in the same auction and each receives less delivery, making it harder for either to reach 50 conversions.
9. Assess creative quantity per adset. Adsets with more than 6-8 active ads fragment impressions across creatives, each of which needs its own impression data to optimize. Reduce to 3-5 ads per adset during the learning phase.
10. Produce a diagnosis ranked by most likely root cause with a specific corrective action for each.

## Output Requirements

- Learning status per adset: current status, days in learning phase, conversions in last 7 days
- Root cause diagnosis: primary cause, secondary cause (if applicable)
- Corrective action: specific change required (not generic advice)
- Estimated time to exit learning phase after correction
- Risk assessment: which corrections require a learning reset vs. which can be done without triggering one
- Consolidation recommendation: how many adsets should remain active given current conversion volume

## Platform-Specific Best Practices

- The 50 conversions/week threshold is a target, not a guarantee. Meta's algorithm benefits from more data; 50 is the minimum floor, not the optimal operating point.
- Campaign Budget Optimization (CBO) can mask Learning Limited status at the adset level while the campaign overall appears healthy. Always check adset-level delivery status, not just campaign-level.
- Budget edits under 20% do not reset learning on Lowest Cost campaigns. Use incremental increases of 15-20% spaced at least 2 days apart to scale without triggering resets.
- Switching from Cost Cap to Lowest Cost to exit learning, then switching back to Cost Cap after stable delivery, is a valid tactical sequence.
- Advantage+ Shopping Campaigns (ASC) do not use traditional learning phase mechanics — they continuously optimize. This skill applies to standard campaign types.

## Guardrails

- Do not consolidate adsets that serve fundamentally different audiences just to reach 50 conversions/week. Forced consolidation destroys targeting signal.
- Do not increase budgets by more than 25% in a single edit to chase learning exit. The reset from the large budget edit will extend learning further.
- Learning Limited does not always mean poor performance. Some adsets deliver profitably while Learning Limited. Diagnose before prescribing a fix.
- Switching the optimization event is a last resort — it resets learning and changes what the algorithm is optimizing toward.

## Example Requests

1. "Three of my adsets have been in the learning phase for 11 days and still show Learning Limited. I'm optimizing for Purchase with a $150/day budget per adset. What's causing this and how do I fix it?"
2. "I increased my adset budget from $200/day to $400/day and now it reset back into learning. Did I do something wrong and how do I scale without this happening again?"
3. "I have 12 active adsets all targeting cold audiences in the US. Only 2 of them have exited learning. Walk me through a consolidation plan."
