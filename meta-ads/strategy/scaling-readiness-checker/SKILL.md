# Meta Campaign Scaling Readiness Checker

**Platform:** Meta Ads
**Category:** strategy
**Tier:** pro

## Purpose

Assess whether a Meta Ads campaign is structurally and operationally ready to scale — meaning a significant budget increase (25%+ or more) — without triggering a learning phase reset, exhausting the available audience, degrading cost per result beyond acceptable thresholds, or collapsing the signal integrity that the current performance depends on. Premature scaling is one of the most common ways high-performing campaigns are broken.

## When to Use

- Before any budget increase of 20% or more on an active campaign
- When a client approves additional budget and wants to know how fast to deploy it
- When a campaign has been performing at or above target for 2+ consecutive weeks
- When evaluating whether to horizontal scale (new audiences) vs. vertical scale (higher budget on existing audiences)
- When a campaign is in the learning phase and there is pressure to accelerate scaling
- After a successful creative test that suggests a new creative has strong scaling potential
- Before major seasonal periods (Q4, holidays) where budget increases are planned in advance

## Inputs Required

- Current daily budget per campaign or adset
- Current weekly optimization event volume per adset
- Delivery status: Stable, Learning, or Learning Limited
- Current CPA or ROAS and trend over the past 14 days (improving, stable, or deteriorating)
- Audience type and estimated size
- Frequency for the past 7 days
- Bid strategy: Lowest Cost, Cost Cap, or Bid Cap
- Creative library: number of active ads and when the most recent creative was launched
- First-time impression ratio trend (if available)
- EMQ scores and CAPI health status

## What This Skill Does

This skill evaluates a campaign against seven scaling readiness criteria, produces a scaling readiness score, identifies the specific constraints that would be exacerbated by a budget increase, and prescribes the correct scaling method (vertical vs. horizontal), scaling pace (percentage increase per week), and pre-scaling actions required to protect performance during the scaling process.

## Analysis Workflow

1. Confirm delivery status is Stable. A campaign in the learning phase or Learning Limited status should not be scaled. Increasing budget while in learning extends the learning phase and increases CPA variance. If the campaign is not Stable, the first action is to exit learning before scaling.
2. Confirm consistent CPA trend. Calculate the 7-day rolling average CPA for the past 14 days. If CPA is trending up (deteriorating), scaling will amplify the deterioration. Scale only when the CPA trend is stable or improving. A 10%+ week-over-week CPA increase is a disqualifying signal.
3. Assess conversion volume headroom. At the current budget level, how many conversions per week is the adset generating? The algorithm needs a buffer — at 50-60 conversions/week, the adset is at the minimum viable threshold. Scaling without additional conversion volume to feed the algorithm creates instability. Target 80-100+ weekly conversions before scaling aggressively.
4. Assess audience size headroom. Calculate the estimated percentage of the audience already reached: total reach ÷ audience size estimate. If penetration is above 35-40%, scaling will accelerate saturation. Audience expansion (horizontal scaling) should precede or accompany vertical budget scaling when penetration is high.
5. Assess creative refresh readiness. The current best-performing creative is likely the single highest-frequency creative in the adset. If this creative has been running for more than 21 days in a cold audience context, it is likely approaching fatigue. Scaling will accelerate frequency and accelerate fatigue. Have fresh creative assets ready to launch before or immediately after a scale event.
6. Check bid strategy compatibility with scaling. Lowest Cost scales well — the algorithm will increase bids automatically to spend more budget. Cost Cap scales more carefully — if the cap is set at $30 and scaling forces the algorithm to find conversions in less efficient audience segments, delivery may not increase proportionally to budget increase. For Cost Cap campaigns, consider a temporary cap increase (10-15%) during the scaling phase to allow delivery room.
7. Assess CAPI signal integrity before scaling. If the conversion signal is already degraded (low EMQ, poor deduplication), scaling will amplify the signal quality problem. The algorithm will optimize more aggressively toward an imprecise signal, which wastes proportionally more budget at higher spend levels. Confirm EMQ is above 6.0 and deduplication rate is above 90% before scaling.
8. Select the scaling method: Vertical scaling = increase budget on the existing campaign/adset (simpler, higher risk of saturation and learning resets). Horizontal scaling = duplicate the campaign to new audiences, new creatives, or new markets (lower risk per adset, requires more management complexity). The optimal approach is typically a combination.
9. Determine safe scaling pace for vertical scaling: a 20% weekly budget increase is the safest pace that avoids triggering a learning reset. A 50% increase is possible but carries learning reset risk. A 100%+ increase almost always triggers a learning reset and a temporary CPA spike.
10. Produce a scaling readiness scorecard, recommended scaling method, pace, and pre-scaling action list.

## Output Requirements

- Scaling readiness score: pass/fail per criterion with overall readiness rating (Ready / Conditionally Ready / Not Ready)
- Scaling constraints: specific factors that will limit performance at higher budget levels
- Recommended scaling method: vertical, horizontal, or hybrid — with specific budget targets
- Safe scaling pace: percentage increase per week with rationale
- Pre-scaling action list: steps to take before increasing budget (creative refresh, audience expansion, CAPI check)
- Risk assessment: what can go wrong during the scale and how to detect it within the first 72 hours

## Platform-Specific Best Practices

- The 20% budget increase rule as a single-week ceiling is a starting guideline, not a hard limit. Some stable, high-signal campaigns can absorb 30-40% increases without a learning reset. Monitor delivery status for 48 hours after any increase above 20%.
- Horizontal scaling through audience duplication is the lower-risk path: create a new adset or campaign targeting a new audience (new Lookalike, new geo, new interest stack) rather than pushing more budget through the existing audience.
- For Advantage+ Shopping Campaigns, budget scaling behaves differently — ASC does not have traditional adset-level learning phase mechanics. ASC budget can typically be scaled more aggressively (up to 2x in a single increase) without the same risk of triggering a learning reset that standard campaigns carry.
- Always monitor the first 72 hours after a scale event. Watch: delivery status (did it flip back to Learning?), CPM (did it spike significantly?), CPA (is it within 20% of the pre-scale baseline?). If any metric is outside expected range, stabilize before continuing the scaling sequence.
- Scaling during a peak performance period (e.g., a strong selling day) provides misleading data. Scale during a representative baseline period to assess true incremental performance.

## Guardrails

- Do not scale a campaign that is in the learning phase, Learning Limited, or showing a deteriorating CPA trend over the past 7 days.
- Do not scale while simultaneously making creative changes, audience changes, or bid strategy changes. One variable at a time.
- Do not assume that a campaign that performed well at $200/day will perform equally well at $2,000/day. Audience pools, auction dynamics, and algorithm behavior all change materially with 10x budget increases.
- Do not skip the pre-scaling action list items in the interest of speed. Scaling into a fatigued creative or a low-EMQ signal environment is a predictable way to destroy a campaign's performance baseline.

## Example Requests

1. "My campaign has been hitting a $28 CPA for 3 straight weeks on $150/day. My client just approved $600/day. How do I scale without blowing up performance?"
2. "I want to go from $500/day to $2,500/day on my top campaign in the next 30 days. Build me a step-by-step scaling plan."
3. "I increased my budget by 80% last week and now my CPA doubled and the adset is back in learning. What did I do wrong and how do I recover?"
