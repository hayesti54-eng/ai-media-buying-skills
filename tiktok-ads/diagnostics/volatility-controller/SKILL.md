# Campaign Volatility Controller

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Identify and stabilize TikTok campaigns exhibiting high metric volatility — defined as erratic swings in CPA, ROAS, spend delivery, or conversion volume across consecutive days — by diagnosing the structural cause of instability, distinguishing normal algorithm learning behavior from genuine campaign misalignment, and producing a stabilization playbook.

## When to Use
- CPA swings more than 40% day-over-day across 3 or more consecutive days on the same campaign
- Spend delivery oscillates between near-zero and over-budget on the same campaign with a fixed budget
- Conversion volume is highly inconsistent (e.g., 0 conversions one day, 12 the next) with no corresponding spend or creative changes
- A campaign exited the learning phase but continues to behave erratically
- You are managing a Cost Cap or Bid Cap campaign and experiencing chronic instability that makes performance unreadable

## Inputs Required
- 14–21 days of daily campaign and ad set level data: Impressions, Spend, Conversions, CPA, ROAS (if applicable), CTR, CPM
- Budget type (daily vs. lifetime) and current budget amount
- Bid strategy: Lowest Cost, Cost Cap, Bid Cap, or Value-Based
- Learning phase status: In Learning, Learning Limited, Active
- Number of ad sets per campaign and number of active creatives per ad set
- Conversion window settings: 1-day click, 7-day click, 1-day view
- Audience targeting configuration: interest stack, behavioral, Lookalike, Broad, or custom audience

## What This Skill Does
This skill measures volatility coefficient (standard deviation / mean) for CPA and spend delivery across the analysis window, classifies volatility type by root cause (Learning Instability, Bid Strategy Conflict, Audience Depletion, Creative Inconsistency, or Budget Constraint), and produces a structured stabilization protocol with specific settings adjustments and a monitoring cadence.

## Analysis Workflow
1. Calculate daily CPA standard deviation and mean over the analysis window. Compute volatility coefficient (CV = σ / μ). A CV above 0.40 on CPA is high volatility; above 0.60 is critical instability.
2. Calculate daily spend delivery rate (actual spend / daily budget × 100). Flag days with sub-70% delivery or over-120% delivery (budget exhausted before day ends).
3. Map volatility pattern type:
   - Periodic volatility (every 2–3 days): suggests algorithm learning cycle oscillation — common in the first 7–10 days of a new campaign or post-edit learning reset.
   - Random volatility (no pattern): suggests audience insufficiency, bid-auction mismatch, or competing ad sets cannibalizing budget.
   - Degrading volatility (stable then unstable): suggests creative fatigue or audience exhaustion beginning mid-flight.
   - Delivery volatility without CPA volatility: budget pacing issue, not a performance issue.
4. Run learning phase audit. If the campaign has been active more than 14 days and conversion volume has not hit 50 total conversions, the campaign is structurally learning-limited. Document this as a primary volatility driver.
5. Evaluate bid strategy fit:
   - Cost Cap: check if the stated cap is within 20–30% of actual achievable CPA based on historical performance. Caps set too low cause underdelivery and volatility cycles.
   - Bid Cap: rarely suitable for TikTok conversion campaigns in early stages — creates severe delivery instability.
   - Lowest Cost with daily budget: most stable for campaigns in learning, but susceptible to auction volatility at smaller budgets.
6. Assess ad set consolidation. Multiple ad sets targeting overlapping audiences within the same campaign creates internal auction competition that amplifies spend volatility. Flag overlap candidates.
7. Check conversion window alignment with sales cycle. A 1-day click window on a product with a 3–5 day consideration cycle will produce erratic day-over-day conversion reporting even if true performance is stable.
8. Produce volatility CV score and root cause classification (1–3 primary causes, ranked by contribution to instability).
9. Generate stabilization actions with expected stabilization timeline (days to stable delivery post-fix).

## Output Requirements
- Volatility scorecard: CPA CV, Spend Delivery CV, pattern type classification, learning phase status
- Root cause ranking: top 3 causes of instability with confidence level (High / Medium / Low)
- Stabilization playbook: specific bid, budget, audience, and campaign structure changes in implementation order
- Bid strategy recommendation with the specific number to use (e.g., "Set Cost Cap at $X, which is 25% above your 7-day average CPA of $Y")
- Monitoring metrics and decision thresholds post-stabilization: what to watch and when to intervene
- Learning phase reset risk assessment: will any of the recommended changes trigger a learning phase reset? Flag each action with Yes / No / Possible.

## Platform-Specific Best Practices
- TikTok's algorithm requires a minimum of 50 optimization events per ad set per week to fully exit the learning phase and stabilize. Below this threshold, any campaign will exhibit natural volatility — this is expected, not a failure state.
- Cost Cap campaigns on TikTok will voluntarily underspend on days when the algorithm cannot find sufficient conversions at the cap. This is by design, not a bug — raising the cap by 10–15% often restores delivery without sacrificing efficiency.
- Campaign Budget Optimization (CBO) distributes budget across ad sets and reduces ad set level volatility but can mask individual ad set problems. Use CBO for stabilization only when individual ad set performance is known.
- Editing a live campaign (bid, budget, audience, or creative changes) resets learning on TikTok. Operators must weigh stabilization benefits of an edit against the 3–7 day learning disruption cost.
- Broad Targeting (no interest or behavior constraints) is TikTok's most stable long-term delivery configuration for conversion campaigns — the algorithm self-optimizes and experiences less auction volatility than tightly constrained interest stacks.

## Guardrails
- Do not make more than one structural campaign change per 3-day window — stacking changes prevents attribution of which fix caused stabilization.
- Do not interpret learning phase CPA swings (days 1–10) as true volatility requiring intervention — premature optimization resets learning and compounds instability.
- Do not conflate day-of-week CPA variation (Saturday vs. Wednesday) with true volatility — weight-adjust for known weekday performance patterns before calculating CV.
- Never recommend pausing and restarting a campaign as a volatility fix without understanding that this fully resets all algorithm learning accumulated to date.

## Example Requests
1. "My TikTok conversion campaign has been wildly inconsistent — $22 CPA one day, $89 the next, $0 conversions the day after. Here's 3 weeks of daily data. Tell me what's causing this and how to fix it."
2. "I'm running a Cost Cap campaign at $45 but it's only spending 30% of my daily budget most days. Walk me through why and what cap or structure change will fix it."
3. "I have 4 ad sets in the same campaign targeting slightly different audiences. My CPA is all over the place. Is this volatility coming from audience overlap and should I consolidate?"
