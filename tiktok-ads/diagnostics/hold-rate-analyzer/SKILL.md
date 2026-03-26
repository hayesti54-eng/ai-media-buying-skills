# Hold Rate & Watch Time Analyzer

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Evaluate the hold rate and watch time distribution across active TikTok ad creatives to diagnose where viewers drop off after the hook, identify pacing failures in the body of the ad, and determine whether a creative has the structural retention needed to drive conversion-intent signals. This skill bridges the gap between a strong hook (thumbstop) and actual conversion — the part most operators overlook.

## When to Use
- Hook rate is healthy (25%+) but CTR or CVR is underperforming relative to spend
- A creative has strong 2-second views but poor 25%, 50%, or 75% video completion rates
- You are evaluating the pacing and storytelling quality of new creative before deciding to scale
- CPA is inconsistent across creatives with similar hook rates — watch time depth may explain the divergence
- Running video ads longer than 15 seconds and need to validate that the extended length is working

## Inputs Required
- TikTok Ads Manager export with: Ad Name, Video Views (2s), Video Views (6s), Video Views (25%), Video Views (50%), Video Views (75%), Video Views (100%), Average Watch Time, Impressions, Spend, Clicks, CTR, Conversions or CPA
- Creative duration in seconds for each ad (label each creative with its length: 9s, 15s, 21s, 30s, 45s, 60s)
- Creative format classification: UGC, Spark, talking head, product demo, voiceover B-roll, text-overlay, carousel (video)
- Campaign objective: Conversion, Traffic, App Install, Video Views
- Minimum 7-day window with at least 1,000 impressions per creative

## What This Skill Does
This skill builds a retention curve for each creative using the 25/50/75/100% video view milestones, calculates hold rate at each checkpoint (views at milestone / 2-second views × 100), benchmarks against TikTok norms by creative length, and identifies the specific drop-off window where viewer attention collapses. It then diagnoses whether the drop-off is a pacing issue (body of video), a relevance issue (wrong audience), or a structural issue (CTA placement). Output includes a per-creative retention scorecard and iteration direction.

## Analysis Workflow
1. Ingest data and normalize. For each creative, calculate hold rate at each checkpoint: (Video Views at X% / 2-Second Video Views) × 100. Label each as Hold-25, Hold-50, Hold-75, Hold-100.
2. Build retention curve per creative. Flag the specific checkpoint where drop-off exceeds 30% of remaining viewers — this is the "cliff." Classify: Early Cliff (between 2s and 25%), Mid Cliff (25–50%), Late Cliff (50–75%), End Drop (75–100%).
3. Apply creative length normalization. A 9-second ad with 60% hold-100 is not the same as a 45-second ad with the same metric. Adjust benchmarks: 9–15s ads should target 45%+ hold-100; 30–45s ads should target 25%+ hold-75.
4. Cross-reference average watch time against creative length. Calculate watch time ratio: (Average Watch Time / Creative Duration) × 100. Flag any creative below 30% watch time ratio as critically underperforming.
5. Identify Mid Cliff creatives — these are the highest-leverage iteration candidates. The hook worked, but the body lost the viewer. Pinpoint the likely cause: weak transition from hook to offer, loss of pacing, visual monotony, no secondary hook or curiosity loop at 6–8 seconds.
6. Flag Late Cliff creatives separately. These signal that the offer or CTA section is weak, not the creative storytelling. Recommend CTA repositioning or offer clarity improvements.
7. Cross-reference retention depth with CTR. A creative with deep watch time (Hold-75 above 50%) but low CTR suggests the CTA is not compelling even if the content is engaging — a classic "content but no conversion" problem.
8. Rank creatives by watch time ratio × CTR composite score. Identify top 20% for scaling and bottom 20% for pausing or iteration.
9. Output retention drop-off diagnosis for each underperformer with specific structural fix recommendations.

## Output Requirements
- Retention curve table per creative: Hold-25, Hold-50, Hold-75, Hold-100, Average Watch Time, Watch Time Ratio
- Drop-off cliff classification per creative (Early / Mid / Late / End)
- Composite retention-to-CTR score ranked table
- Creative iteration brief for each "Mid Cliff" and "Late Cliff" creative: what is collapsing and why, plus a specific structural fix (pacing, secondary hook, CTA timing, offer reveal)
- Watch time ratio distribution chart (text table format) for the full creative set
- Scale / Iterate / Rework / Kill classification for every creative

## Platform-Specific Best Practices
- TikTok's algorithm uses watch time as a direct quality signal. Creatives with higher average watch time receive better auction priority over time, compounding performance advantages.
- On TikTok, the 6-second mark is the second critical threshold — it marks whether a viewer has accepted the premise of your ad. If Hold-6 falls below 50% of Hold-2, the transition from hook to body is broken.
- For Spark Ads, native creator-style pacing (quick cuts, direct speech, informal transitions) retains better than scripted corporate pacing. Match the energy of the FYP context, not a TV commercial.
- Secondary hooks at the 7–10 second mark dramatically improve Mid Cliff performance. Pattern-interrupt visuals, surprising statements, or "but here's the thing..." narrative pivots reset viewer commitment.
- Subtitles improve watch time by 15–25% on TikTok due to sound-optional environments in certain use cases (work, public). Always include caption-style text overlays on every creative.
- CTA placement for conversion creatives: test CTAs at 70–80% of video duration for ads under 20 seconds, and at 60% for ads 30 seconds and above.

## Guardrails
- Do not judge hold rate on creatives with fewer than 500 2-second video views — the retention curve will be statistically unreliable.
- Do not equate low hold-100 on a 45-second video with failure — viewers who reach the 50% mark on a 45-second TikTok ad are highly engaged relative to platform norms.
- Do not recommend lengthening a creative as a fix for low hold rate. More often the ad needs tightening, not extending.
- Avoid comparing hold rates across fundamentally different creative formats without applying format-specific benchmarks.

## Example Requests
1. "My ads have solid hook rates but my CPA is garbage. Here's my video view data — analyze where viewers are dropping off and tell me what's broken in the body of each creative."
2. "I have three creatives with the same hook rate but very different CPAs. Walk me through the hold rate and watch time on each to explain why they're performing differently."
3. "I'm testing a 45-second UGC ad against a 15-second cut-down. Compare the retention curves and tell me which format is actually working and which to kill."
