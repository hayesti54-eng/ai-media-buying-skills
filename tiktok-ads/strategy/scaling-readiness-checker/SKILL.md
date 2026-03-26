# TikTok Campaign Scaling Readiness Checker

**Platform:** TikTok Ads
**Category:** strategy
**Tier:** pro

## Purpose
Evaluate whether a TikTok Ads campaign is structurally and performance-ready to scale spend — and by how much, at what pace, and through which scaling method — without triggering learning phase resets, CPA degradation, or creative fatigue collapse. Scaling TikTok campaigns prematurely or incorrectly is one of the most common sources of performance loss; this skill prevents it.

## When to Use
- Current campaign is hitting CPA target and you want to increase budget but are not sure when or how
- You have identified a winning creative and want to scale it aggressively without breaking its performance
- A campaign exited the learning phase and is performing consistently for 5+ consecutive days — is it ready to scale?
- You have been asked by a client or stakeholder to double or triple spend and need to determine whether the account can absorb that increase
- Planning a scale push around a seasonal event, product launch, or promotional period

## Inputs Required
- Current daily budget and actual daily spend over the past 7–14 days
- CPA or ROAS performance over the past 7–14 days (daily, not blended average)
- Campaign learning phase status: Active, Learning, Learning Limited
- Number of conversions per week over the past 2 weeks (total, not averaged)
- Number of active creatives and their individual performance status (Winner / Contributing / Fatiguing / New Test)
- Current audience size estimate and frequency level
- Bid strategy in use: Lowest Cost, Cost Cap, Bid Cap, or Value-Based
- Target scale level: percentage or absolute budget increase desired (e.g., 2× from $500 to $1,000/day)

## What This Skill Does
This skill runs a five-category scaling readiness assessment, assigns a Scaling Readiness Score (0–100), recommends a specific scaling method and pace (vertical budget increase, horizontal ad set expansion, or creative-led scaling), and produces a step-by-step scaling execution plan with monitoring checkpoints.

## Analysis Workflow
1. Category 1 — Learning Phase Stability Assessment (25 points):
   - Is the campaign currently in "Active" status (out of learning)? If yes, +15 points.
   - Has the campaign produced 50+ conversions in the past 7 days? If yes, +10 points.
   - Any score below 15 on this category = scaling is high-risk and may force a learning reset. Recommend waiting.
2. Category 2 — CPA Consistency Check (25 points):
   - Calculate CPA standard deviation over the past 7–14 days. If coefficient of variation (σ/μ) is below 0.25 = high consistency (+20 points). Between 0.25–0.40 = moderate (+10). Above 0.40 = volatile (+0).
   - Is CPA below target? If yes, add 5 points. If above target, subtract 5 points.
3. Category 3 — Creative Runway Assessment (20 points):
   - Does the account have at least 2 creatives performing at or below CPA target? (+10 points)
   - Is there a creative in the testing pipeline ready to replace fatiguing ads within 7 days? (+10 points)
   - A creative pipeline gap is a scaling blocker — scaling without creative replacement capacity leads to performance collapse within 2–3 weeks.
4. Category 4 — Audience Capacity Check (20 points):
   - Current estimated audience size sufficient to absorb 2× spend without frequency spiking to 3+ within 14 days? (+15 points)
   - Is current frequency below 2.0 in the past 14 days? (+5 points)
   - Audience saturation risk makes scaling inefficient even when creative and CPA are healthy.
5. Category 5 — Bid Strategy Compatibility (10 points):
   - Lowest Cost: fully compatible with vertical budget scaling up to 20% per day without learning reset risk. (+10)
   - Cost Cap: scaling requires verifying cap headroom. If current CPA is 20%+ below the cap, scaling is viable. (+7)
   - Bid Cap: scaling is structurally risky — underspend increases as budget grows beyond bid constraint. (+3)
6. Calculate total Scaling Readiness Score (0–100). Classify:
   - 80–100: Scale-Ready — proceed with confidence
   - 60–79: Conditionally Ready — address identified gaps before full scale
   - 40–59: Not Ready — resolve learning, CPA consistency, or creative issues first
   - Below 40: Do Not Scale — current issues will compound under higher spend
7. Prescribe the scaling method based on the score and constraints:
   - Method A — Vertical Scaling: increase budget on the existing campaign by 20% per day. Safe for Lowest Cost campaigns with high readiness scores.
   - Method B — Horizontal Scaling: duplicate the ad set with a new audience or launch a parallel campaign. Preserves original learning while expanding reach.
   - Method C — Creative-Led Scaling: maintain budget, increase creative velocity. Resolve creative runway gaps before touching budget.
   - Method D — New Campaign Architecture: for very large budget increases (3×+), build a separate campaign to absorb scale budget rather than disrupting the proven structure.
8. Produce the scaling execution timeline: day-by-day budget increase schedule, checkpoint dates for CPA evaluation, creative refresh deadlines, and scale-back trigger thresholds (if CPA rises above 125% of target for 3 consecutive days, roll back to previous budget level).

## Output Requirements
- Five-category scoring breakdown with points earned and rationale per category
- Total Scaling Readiness Score (0–100) and classification (Scale-Ready / Conditionally Ready / Not Ready / Do Not Scale)
- Recommended scaling method (A / B / C / D) with rationale
- Step-by-step scaling execution plan: day-by-day budget increase schedule and checkpoints
- Creative runway gap analysis: how many new creatives are needed to support the scaling timeline?
- Scale-back trigger criteria: the specific performance thresholds that should trigger a budget reduction
- Risk factors log: any identified risks that could cause CPA degradation at higher spend

## Platform-Specific Best Practices
- TikTok's learning phase is highly sensitive to budget edits. Increasing budget by more than 50% in a single edit on a conversion campaign restarts the learning phase. The safest approach is daily increases of 20% or less until the target budget is reached.
- CBO (Campaign Budget Optimization) enables smoother budget scaling than ad-set level budgets because TikTok distributes the increased budget across ad sets based on real-time performance signals — this self-regulates CPA degradation during scale.
- Creative velocity is the non-negotiable requirement for scaling. Every week that budget doubles, creative fatigue risk also doubles. High-scale TikTok accounts that maintain CPA during aggressive scaling are always paired with high creative output — typically 5–7 new creatives per week at $1,000+/day spend levels.
- Horizontal scaling (duplicating ad sets with new audiences) is the lowest-risk scaling method on TikTok because it does not disturb existing campaign learning while opening new delivery pools.
- For seasonal scaling events (holiday sale periods, flash promotions), begin budget increases 72 hours before the event — TikTok's algorithm needs time to recalibrate delivery pacing before peak spend windows.

## Guardrails
- Do not scale a campaign that is in learning phase — budget increases during learning phase extend and destabilize the learning period.
- Do not scale a campaign with only one working creative — single-creative concentration is a catastrophic risk during scale because any creative issue immediately collapses the entire scaling spend.
- Do not increase budget more than 50% in a single day — this triggers a learning phase reset on most TikTok conversion campaigns.
- Never scale without defining in advance the CPA threshold that will trigger a scale-back. Scaling without a stop condition turns a temporary CPA spike into a budget hemorrhage.

## Example Requests
1. "My TikTok campaign has been hitting $32 CPA for the past 10 days against a $40 target. I want to go from $300/day to $1,000/day. Run the scaling readiness check and give me the step-by-step plan."
2. "I have a client who wants to triple their TikTok spend for a Black Friday push in 3 weeks. Score the account's scaling readiness and tell me what I need to do in the next 3 weeks to make that increase viable without destroying CPA."
3. "My Cost Cap campaign is at $500/day and I want to scale to $2,000/day. What's my readiness score, which scaling method should I use, and what are the daily budget milestones to get there safely?"
