# Lead Throttling Analyzer

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** pro

## Purpose
Identify and diagnose lead throttling — the condition where Google LSA restricts ad delivery and reduces lead volume below the business's budget capacity and market demand level. Throttling on LSA is not always transparent; it can appear as an unexplained plateau in lead volume, a rank suppression, or erratic delivery patterns. This skill distinguishes between the four core throttling causes — budget cap constraints, responsiveness-triggered suppression, profile compliance issues, and competitive market dynamics — and produces the correct unlock strategy for each.

## When to Use
- When weekly lead volume plateaus or drops despite budget availability and no declared profile changes
- When daily spend consistently falls below the weekly budget cap divided by 7
- When lead volume drops suddenly after a responsiveness decline
- When a profile shows "Active" status but impressions or contacts have decreased without explanation
- When a budget increase does not produce a proportional lead volume increase
- When a competitor's new profile enters the market and your lead volume drops simultaneously

## Inputs Required
- Weekly lead volume trend (last 8–12 weeks)
- Weekly spend vs. budget cap (utilization rate per week)
- Responsiveness score trend over the same period
- Profile status (Active, Paused, Under Review, Suspended)
- Any recent profile changes: job types added/removed, service area changes, hours updates
- Review count and rating trend over the period
- Budget cap setting history (any changes made in the review period)
- Competitor activity in the service area (new entrants, significant review gains)

## What This Skill Does
Runs a structured throttling diagnosis that separates budget-side throttling (budget is the ceiling, not demand) from algorithm-side throttling (Google is restricting delivery based on profile signals). Maps lead volume patterns against responsiveness score changes, budget utilization rates, and profile modification history to pinpoint the throttling trigger. Calculates the estimated lead volume ceiling under current constraints and models what unlock actions would recover volume. Outputs a ranked throttling cause list with specific resolution steps for each.

## Analysis Workflow
1. Plot weekly lead volume against weekly spend — if spend is consistently below budget cap, the constraint is delivery-side, not budget-side.
2. Calculate average budget utilization rate: (Weekly Spend / Weekly Budget Cap) × 100. Consistent utilization above 95% signals budget throttling; below 70% signals delivery throttling.
3. Overlay responsiveness score trend on the lead volume trend — a correlated decline confirms responsiveness-triggered suppression.
4. Check the profile modification log — job type removals, service area contractions, or hours reductions in the prior 30 days often cause temporary or permanent delivery reductions.
5. Review profile compliance status — check for any background check expiration, license verification flag, or Google Guarantee status issue.
6. Assess review velocity: a sudden stop in new reviews can correlate with rank and delivery decline as the profile loses freshness signal.
7. Check for budget cap changes — a budget cap that was recently raised may not produce immediate volume increases due to algorithm recalibration lag (typically 5–10 days).
8. Identify the date of the first volume decline — map it against the timeline of responsiveness changes, profile changes, and competitor entries.
9. Classify the throttling type: Budget Cap Throttling, Responsiveness Suppression, Compliance Hold, Competitive Displacement, or Algorithm Recalibration.
10. For each identified throttle type, define the resolution action and estimated recovery timeline.
11. Model the expected lead volume under resolved conditions using historical pre-throttle averages.
12. Prioritize resolution actions by recovery speed and effort required.

## Output Requirements
- Throttling diagnosis summary: classified throttle type(s) and confidence level
- Lead volume trend chart description: volume trajectory, inflection point, and correlation events
- Budget utilization analysis: spend vs. cap by week, utilization rate, and throttling verdict
- Responsiveness correlation: score trend vs. volume trend with causation assessment
- Profile change impact log: which changes preceded volume decline and their estimated delivery impact
- Resolution action plan: ranked by recovery speed — immediate actions, 1-week actions, 30-day actions
- Volume recovery model: estimated lead volume under fully resolved profile conditions

## Platform-Specific Best Practices
- LSA budget pacing is weekly, not daily — do not diagnose daily spend variance as throttling without examining the weekly pattern.
- Google LSA does not provide an impression share metric — throttling must be inferred from spend utilization, volume trends, and signal correlation.
- Responsiveness suppression is the most common and most fixable throttling cause in LSA — it responds to operational changes within 1–2 weeks.
- Raising the budget cap on a responsiveness-suppressed profile will not increase lead volume — the throttle is not on the budget side.
- New profiles are algorithmically ramped over 4–8 weeks — early throttling in the first month is expected and not a diagnostic signal.
- Service area expansion will not unlock throttled volume if the throttle is responsiveness- or compliance-based.

## Guardrails
- Do not increase the budget cap as a default throttling fix without first ruling out responsiveness suppression — it will not work and wastes client budget.
- Do not diagnose competitive displacement without evidence of a specific competitor gaining position — correlation without causal evidence leads to wrong recommendations.
- Algorithm recalibration after profile changes is temporary (5–10 days) and should not be treated as a sustained performance problem.
- Never recommend profile pausing as a throttling fix — pausing resets delivery history and typically makes re-entry performance worse.

## Example Requests
1. "We raised our LSA budget from $150 to $300 per week three weeks ago and lead volume hasn't moved. What's actually throttling us?"
2. "Lead volume dropped from 18 leads per week to 9 leads per week starting six weeks ago — nothing changed on our end. Run a throttling analysis."
3. "Our responsiveness score went from 9/10 to 6/10 after we changed our call routing system. How much is that suppressing our delivery and what do we do to recover?"
