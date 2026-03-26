# TikTok Creative Fatigue Detector

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Identify which TikTok ad creatives are entering, mid-stage, or fully in creative fatigue — defined as the degradation of performance metrics over time due to audience overexposure — before they become net-negative budget drains. This skill uses trend analysis across hook rate, CTR, CPM, frequency, and CPA to generate an early-warning fatigue signal and a replacement readiness score for each creative.

## When to Use
- A creative that was performing well has shown declining metrics over 5–10 consecutive days
- CPMs are rising on a specific creative or ad set without budget increases or audience changes
- CTR is declining while impressions remain flat or grow — a textbook fatigue signature on TikTok
- You are managing a high-volume creative pipeline and need to systematically forecast replacement timing
- Post-launch (day 7–14) review of all new creatives to identify which need iteration before full fatigue sets in

## Inputs Required
- 21–30 days of TikTok Ads Manager data broken down by day, at the creative level: Impressions, Reach, Frequency (or calculated from Impressions/Reach), 2-Second Video Views, CTR, CPM, CPC, Spend, Conversions, CPA
- Creative launch date for each ad
- Ad set frequency cap settings (if any)
- Audience size estimate per ad set (from TikTok audience estimates)
- Creative format labels: UGC, Spark, non-Spark, branded, influencer-style, product demo

## What This Skill Does
This skill performs time-series trend analysis on each creative's core metrics, calculates week-over-week and 3-day rolling average changes, detects fatigue signatures (rising CPM + falling CTR + rising CPA on the same creative), and assigns a Fatigue Score (0–100) and a Replacement Urgency classification (Green / Yellow / Red) to each creative. It also projects a "kill date" based on current degradation trajectory and provides a replacement timing recommendation.

## Analysis Workflow
1. Ingest 21–30 days of daily creative-level data. Organize each creative into a time-series table. Calculate days since launch for each creative.
2. Calculate 7-day rolling averages for: CTR, CPM, Hook Rate (2s view rate), CPA. Compute week-over-week delta for each metric across all 3 rolling windows.
3. Flag fatigue signatures using a 3-signal detection model:
   - Signal 1: CTR decline of 15%+ week-over-week
   - Signal 2: CPM increase of 20%+ week-over-week (algorithm is paying more to find receptive viewers)
   - Signal 3: CPA degradation of 25%+ week-over-week
   A creative triggering 1 signal = Yellow. 2 signals = Orange. 3 signals = Red (active fatigue, immediate action required).
4. Calculate estimated audience frequency. If frequency reaches 2.5+ within the target audience size, flag regardless of metric status — overexposure is imminent.
5. Cross-reference fatigue signal with creative age. A 30-day-old creative showing Yellow signals is in normal decay. A 7-day-old creative showing Yellow signals indicates the audience was already saturated or the creative was never differentiated.
6. For each Red-signal creative, calculate the spend waste rate: daily spend × number of days CPA has been above target. This is the cost of delayed replacement.
7. Assign Fatigue Score (0–100): weight CTR decline (35%), CPM increase (30%), CPA degradation (25%), frequency level (10%).
8. Classify: Score 0–30 = Green (healthy), 31–55 = Yellow (monitor closely), 56–75 = Orange (begin replacement prep), 76–100 = Red (pause or replace within 48 hours).
9. Generate replacement timeline recommendation: when to launch replacement creative and what variant types to test based on the fatiguing creative's best-performing elements.

## Output Requirements
- Creative-level fatigue scorecard: Fatigue Score, Urgency Classification, Days Live, estimated Frequency, week-over-week CTR/CPM/CPA delta
- Red and Orange creative list with estimated daily spend waste and recommended kill/replace date
- Replacement readiness brief per Red creative: preserve these elements (hook mechanic, format, offer), change these elements (visual style, hook opening, pacing)
- Projected creative runway for Green/Yellow creatives based on current trajectory
- Pipeline gap analysis: if all Red and Orange creatives are killed, how many replacement creatives are needed to maintain current spend levels?

## Platform-Specific Best Practices
- TikTok audiences fatigue faster than Meta due to the For You Page's high content velocity. A strong creative may peak in days 3–7 and enter decay by day 14 on a narrowly targeted ad set.
- Spark Ads tend to fatigue more slowly than non-Spark because organic engagement activity (likes, shares, comments) continues to accumulate, creating social proof that sustains CTR longer.
- Creative velocity — the rate at which new creatives are introduced to the account — is the primary defense against fatigue-driven performance collapse. High-performing TikTok accounts maintain a 3–5 new creative introductions per week cadence.
- Rotating creative angles within the same campaign can extend the effective life of a concept. Fresh hooks on proven offer structures reduce full replacement costs.
- CPM spikes are TikTok's most reliable early fatigue indicator. The algorithm must bid higher to find users who haven't been overexposed — this is the platform's signal that the creative is losing relevance.
- Broad audiences (Broad Targeting in TikTok) experience slower frequency build-up and therefore extend creative runway significantly compared to narrow interest stacks.

## Guardrails
- Do not pause a high-CPA creative solely on frequency grounds if it is still converting below CPA target — frequency tolerance varies by audience size and campaign type.
- Do not interpret a single bad day as fatigue onset. Require at least 3 consecutive days of multi-signal decline before escalating to Orange or Red.
- Do not apply the same fatigue benchmarks to a $500/day account and a $50/day account — frequency builds at dramatically different rates.
- Never replace a fatiguing creative without preserving and testing its highest-performing structural elements in the iteration.

## Example Requests
1. "Here's 30 days of daily creative-level data across 8 ads. Tell me which ones are fatigued, which ones are about to fatigue, and what I need to do about each one right now."
2. "My best performing creative is 22 days old and CPA has climbed 40% over the last week. Is this fatigue or something else? Walk me through a full fatigue diagnosis."
3. "I have a $1,500/day TikTok account with 5 active creatives. Build me a fatigue risk report and tell me how many new creatives I need in the pipeline this week."
