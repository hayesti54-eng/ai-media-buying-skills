# Audience Expansion Planner

**Platform:** TikTok Ads
**Category:** funnel
**Tier:** pro

## Purpose
Design a structured audience expansion strategy for TikTok Ads — moving beyond a saturating or exhausted initial audience configuration toward broader, scaled targeting that maintains or improves CPA efficiency. This skill diagnoses when and how to expand audiences, builds the expansion sequencing logic, and produces a targeting architecture that prevents the common mistake of expanding too broadly too fast or staying too narrow for too long.

## When to Use
- Current audience frequency is above 2.5 and performance is declining despite creative refreshes
- Scaling spend is causing CPMs to rise significantly, suggesting audience saturation
- CPA is efficient but conversion volume is capped and cannot be increased within the current audience
- Launching a scaled budget phase after validating performance in a small initial audience
- Current interest-stack targeting has been exhausted and Lookalike or Broad targeting needs to be structured

## Inputs Required
- Current audience targeting configuration: interest clusters, behaviors, Lookalike sources, or Broad (describe exactly)
- Estimated audience size for each current ad set (from TikTok audience size estimator)
- Current frequency and reach metrics (14–21 day window)
- Current CPA and ROAS performance vs. target
- Available first-party data for Lookalike seed audiences: customer email list (size and recency), website visitors, TikTok video engagers, TikTok lead form submitters
- Current daily spend and target daily spend (expansion budget target)
- Geographic targeting: current vs. potential expansion regions
- Campaign objective and conversion event

## What This Skill Does
This skill analyzes the current audience configuration for saturation signals, designs a sequenced audience expansion framework from narrow to broad, specifies each new audience tier with configuration details, and produces a budget allocation and testing plan across audience tiers. Expansion is architected to minimize CPA risk during scale.

## Analysis Workflow
1. Run the Audience Saturation Diagnostic:
   - Calculate current Frequency: Impressions / Reach. Flag if above 2.5 in any 14-day window.
   - Calculate Reach Efficiency Ratio: week-over-week new reach growth / total impressions. If new reach growth is decelerating while impressions hold, audience pool is exhausting.
   - Cross-reference CPM trend: rising CPMs with stable targeting = the algorithm is competing harder within a shrinking available pool.
2. Map the current audience tier. Classify the existing configuration:
   - Tier 1 (Narrowest): specific interest stacks (3+ interests layered), narrow behavioral targeting, small Lookalike (1% LAL)
   - Tier 2 (Moderate): broader interest stack (1–2 interests), larger Lookalike (2–5% LAL), interest + demographic combination
   - Tier 3 (Broad): single interest category, Lookalike 5–10%, or Broad (no interest targeting)
3. Design the expansion sequence. Do not jump from Tier 1 directly to Broad — expand one tier at a time and validate CPA before moving further:
   - Step 1: If currently at interest-stack Tier 1, expand to Tier 2 by widening or reducing the interest layers
   - Step 2: Introduce a Lookalike audience parallel test using the best available seed (customer list > website visitors > video engagers)
   - Step 3: Introduce a Broad Targeting (no interest constraints) test at 15–20% of total campaign budget
   - Step 4: If Broad Targeting validates CPA efficiency, scale Broad as primary, move interest stack to secondary or phase out
4. Specify Lookalike audience configuration:
   - Customer email list: minimum 1,000 records for reliable LAL generation, 5,000+ for strong signal
   - Website Custom Audience: minimum 1,000 unique visitors in the past 30–60 days
   - Engagement Custom Audience: TikTok video engagers (watched 75%+ of an ad or organic video) is the highest-intent LAL seed
   - LAL percentage recommendation: start at 1–2% for highest similarity, expand to 5% if 1–2% saturates
5. Design the parallel testing architecture: run current audience (control) alongside 1–2 new expansion audience tests simultaneously. Use separate ad sets with equal budgets. Run for 7 days minimum before evaluating expansion audience CPA.
6. Define the expansion budget allocation: current audience (control) 60%, Expansion Test A 20%, Expansion Test B 20%. Rebalance after data.
7. Write the scaling trigger criteria: when an expansion audience achieves CPA within 20% of the control for 5 consecutive days, it is ready to receive scaling budget.
8. Document the Broad Targeting strategy for TikTok specifically: on TikTok, Broad Targeting (no interest or behavior constraints) often outperforms interest stacks for conversion objectives because TikTok's algorithm has significantly more behavioral data to work with than operator-defined interest clusters.

## Output Requirements
- Audience saturation diagnostic: frequency, reach efficiency, CPM trend assessment
- Current audience tier classification
- Expansion sequence roadmap: Step 1 → Step 2 → Step 3 → Step 4 with trigger criteria for each step
- New audience configuration specifications: interests, behaviors, Lookalike parameters, or Broad
- Lookalike seed audience recommendations ranked by quality
- Testing architecture: which audiences run in parallel, what budgets, what evaluation window
- Scaling trigger criteria table: what performance threshold unlocks budget reallocation to each new audience
- TikTok Broad Targeting case for conversion campaigns: when to use it and why

## Platform-Specific Best Practices
- TikTok Broad Targeting (no interest, behavior, or demographic constraints beyond age/gender/geography) is significantly more powerful than on Meta due to TikTok's richer behavioral signal from in-app content consumption. For DTC e-commerce and lead gen, Broad Targeting at sufficient budget ($100+/day) often achieves the best CPA efficiency of any targeting configuration.
- TikTok Lookalike audiences are most powerful when seeded with high-intent actions: purchasers, not just website visitors. A Lookalike built from 1,000 purchasers outperforms one built from 50,000 website visitors.
- Interest-based targeting on TikTok is less precise than on Meta because TikTok's interest categories are inferred from FYP behavior, not self-declared. Treat interest stacks as starting points, not precision tools.
- Expanding to Broad on TikTok requires creative quality to carry the targeting weight. Broad Targeting amplifies creative performance — strong creatives scale efficiently, weak creatives fail expensively.
- Custom Audience exclusions are as important as inclusions: always exclude recent purchasers from acquisition campaigns and segment retargeting audiences (website visitors, video engagers) into separate campaigns with different creative messaging.

## Guardrails
- Do not expand to Broad Targeting before validating at least 50 conversions in the current audience configuration — the algorithm needs a sufficient conversion signal to perform at Broad.
- Do not run Broad Targeting and narrow interest targeting in the same ad set — the Broad setting will cause the algorithm to explore far outside the interest constraint and produce unreliable data.
- Do not expand audience and change creative simultaneously — isolate audience variable from creative variable for clean test reads.
- Never build a Lookalike audience from fewer than 1,000 seed users — small seeds produce noisy, low-quality Lookalikes that often underperform basic interest targeting.

## Example Requests
1. "My TikTok ad set is fatiguing — frequency is 3.2 and CPA is climbing even after fresh creatives. Walk me through a sequenced audience expansion plan with specific audience configurations to test next."
2. "I want to scale my TikTok campaign from $200/day to $1,000/day without destroying my CPA. Design an audience expansion roadmap with budget allocation and scaling trigger criteria."
3. "I've been running interest targeting on TikTok for 60 days. Should I move to Broad Targeting? Build me a plan to test Broad alongside my current audiences and tell me how to evaluate the results."
