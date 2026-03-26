# Hook Rate Analyzer

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Diagnose the hook performance of active TikTok ad creatives by analyzing the 2-second and 3-second video view rate (thumbstop rate) against ad set spend, impressions, and downstream conversion data. This skill identifies which creative hooks are stopping the scroll versus bleeding budget, surfaces the root cause of underperformance, and produces a ranked creative action list.

## When to Use
- Hook rate (2s view rate / impressions) drops below 25% on any creative with more than 1,000 impressions
- A creative that previously performed is experiencing declining CTR with flat or increasing CPMs
- Launching a new creative batch and needing a baseline hook benchmark before scaling
- Conducting a weekly creative review and need to triage which hooks need immediate replacement
- CPAs are rising and creative fatigue has not yet been confirmed — hook rate analysis is the first diagnostic step

## Inputs Required
- TikTok Ads Manager export (CSV or pasted data) with the following columns: Ad Name, Impressions, 2-Second Video Views, 6-Second Video Views, Video Views (25%), Video Views (50%), Video Views (75%), Video Views (100%), Clicks, CTR, Spend, CPA or Conversions
- Campaign objective (Traffic, Conversion, App Install, Lead Gen)
- Target hook rate benchmark (default: 25% for awareness, 30%+ for conversion campaigns)
- Date range (minimum 7 days recommended)
- Optional: creative format labels (UGC, branded, Spark, non-Spark, talking head, text-overlay, POV)

## What This Skill Does
This skill calculates the thumbstop rate for each creative (2-second video views / impressions × 100), benchmarks it against the account's historical average and TikTok platform norms, and classifies every creative into one of four buckets: Hook Winner, Hook Underperformer, Hook Dead, or Insufficient Data. It then cross-references hook rate against hold rate and conversion rate to determine whether the hook problem is isolated or compounding downstream. The skill produces a prioritized action list for each creative.

## Analysis Workflow
1. Ingest raw data. Parse the creative-level export and validate that all required columns are present. Flag any rows with fewer than 500 impressions as "insufficient data" and exclude from primary analysis.
2. Calculate thumbstop rate for each creative: (2-Second Video Views / Impressions) × 100. Record alongside 6-second view rate for depth comparison.
3. Rank all creatives by thumbstop rate descending. Identify the top quartile (Hook Winners) and bottom quartile (Hook Dead).
4. Cross-reference hook rate vs. CTR. Flag any creative where hook rate is above 30% but CTR is below 1% — this indicates the hook stops the scroll but fails to build desire or urgency.
5. Cross-reference hook rate vs. CPA or CVR. A high hook rate with poor CPA signals a messaging or landing page problem, not a hook problem. Document this finding separately.
6. Identify hook patterns across winners: question-based open loops, bold visual statements, controversy openers, transformation previews, POV formats, pattern interrupts. Tag the dominant hook mechanic in each winner.
7. Identify failure patterns in underperformers: slow burns, brand logo intros, generic lifestyle B-roll, talking head with no tension in frame 1. Document the failure mechanic.
8. Flag any creative that was previously a Hook Winner (based on historical data if provided) and is now sliding — this signals hook fatigue rather than creative misfire.
9. Produce ranked creative action table: Winner (scale), Test New Hook (iterate), Replace Hook (rework first 3 seconds), Kill (pause immediately).

## Output Requirements
- Creative-level hook rate table with thumbstop rate, 6s view rate, CTR, CPA, spend, and classification bucket
- Top 3 hook patterns working in the account (labeled by mechanic type)
- Top 3 failure patterns dragging performance
- Prioritized action list per creative: scale / iterate / rework / kill
- Iteration brief for each "Rework" creative: what the current hook is, why it fails, and a 1–2 sentence replacement hook direction
- Summary benchmark: account average hook rate vs. TikTok norm (25–35% conversion campaigns)

## Platform-Specific Best Practices
- TikTok's algorithm front-loads delivery to users most likely to engage with the first 2 seconds. A sub-20% thumbstop rate actively signals the algorithm to deprioritize that creative.
- Spark Ads using strong organic hooks tend to outperform non-Spark on thumbstop because the native feel reduces the viewer's instinct to skip.
- Sound-on behavior on TikTok is the default (unlike Meta). Hook copy and audio must align — a visual hook that contradicts the audio tone kills retention at second 1.
- The "first frame test": if the first frame of the creative were a static image, would it create curiosity or question? If not, the hook will likely underperform.
- Avoid branded intros in the first 3 seconds on TikTok. Unlike YouTube, TikTok users will swipe before a brand reveal has any equity-building value.
- Creator-style hooks (handheld, imperfect framing, direct address to camera) consistently outperform polished brand-style cold opens on TikTok for conversion campaigns.

## Guardrails
- Do not rework a creative's hook based on fewer than 500 impressions. Wait for statistical signal.
- Do not pause a creative for low hook rate alone if it has a CPA below target — exceptions exist where the creative self-selects a small, highly qualified audience.
- Do not confuse low hook rate with low view rate from audience exhaustion — cross-check frequency and reach overlap before calling it a hook problem.
- Never recommend hook iterations without first identifying the winning hook mechanic pattern in the account. Generic advice wastes creative budget.

## Example Requests
1. "Here's my TikTok ad export for the last 14 days. Analyze the hook rate on all creatives, identify which ones are underperforming, and tell me exactly what to fix or kill."
2. "My best creative's hook rate dropped from 34% to 18% over the past week. It's a Spark Ad on a talking head format. What's happening and what should my next hook test look like?"
3. "I'm launching 6 new creatives next week. Give me the hook rate benchmarks I need to hit by day 3 before I decide whether to kill or scale each one."
