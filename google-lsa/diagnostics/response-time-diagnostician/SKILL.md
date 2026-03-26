# Response Time & Responsiveness Diagnostician

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** pro

## Purpose
Diagnose responsiveness performance as a direct LSA ranking input. Google LSA uses responsiveness — a composite signal built from call answer rate, message reply speed, and booking confirmation rate — as one of the most heavily weighted local ranking factors. This skill identifies exactly where response failures are occurring, quantifies their ranking impact, and prescribes operational corrections with timeline targets.

## When to Use
- When LSA ad rank declines without a budget or review change
- When call answer rate in the LSA dashboard falls below 80%
- When message response time exceeds 24 hours on any active week
- When a competitor's profile begins outranking despite fewer reviews
- During onboarding of a new client to establish a responsiveness baseline
- After any staffing change (new receptionist, new call routing, after-hours coverage gap)

## Inputs Required
- LSA dashboard responsiveness score (current and 30-day trend)
- Call answer rate percentage from LSA Leads tab
- Message lead log with timestamps (received time vs. first reply time)
- Missed call log with timestamps and day-of-week breakdown
- Business operating hours as currently set in LSA profile
- After-hours call handling setup (voicemail, answering service, or nothing)
- Current ad rank position (approximate — top 3, position 4–6, or rarely appearing)

## What This Skill Does
Maps every responsiveness failure to its operational root cause. Differentiates between missed calls during business hours (a staffing or call routing failure), missed calls after hours (a coverage gap or hours misconfiguration), and slow message replies (an operational process failure). Calculates the call answer rate impact on responsiveness score, estimates the rank position delta caused by current responsiveness deficits, and produces a corrective action plan with specific time-bound targets for each failure type.

## Analysis Workflow
1. Pull the responsiveness score from the LSA dashboard — note the current score and the 30-day trend direction.
2. Extract total incoming calls vs. answered calls for the review period — compute call answer rate.
3. Break missed calls down by day of week and time of day to identify pattern concentrations (e.g., Monday mornings, lunchtime, after 5 PM).
4. Cross-reference missed call timestamps against declared business hours — categorize each as within-hours miss or outside-hours miss.
5. Pull all message leads — calculate average time-to-first-reply for each message and flag any replies exceeding 4 hours.
6. Identify the longest reply gaps — these are the most damaging to responsiveness score.
7. Check whether the LSA profile business hours match actual staffing coverage — mismatches between declared hours and actual coverage are a common rank killer.
8. Assess whether the business has an answering service or voicemail configured — an unanswered call without voicemail signals abandonment to Google.
9. Score the severity of each responsiveness gap: Critical (during declared hours), Moderate (edge of hours), Low (late night/weekend with no declared coverage).
10. Calculate the estimated responsiveness score impact of fixing the top 2 failure categories.
11. Benchmark current call answer rate against LSA's implicit threshold of 90%+ for top-3 ranking.
12. Produce a corrective action plan with staffing, routing, and hours configuration changes.

## Output Requirements
- Responsiveness diagnostic summary: current score, trend, primary failure category
- Call answer rate breakdown: total calls, answered, missed, answer rate %, gap to 90% threshold
- Missed call pattern matrix: day-of-week × time-of-day heatmap of miss concentrations
- Message response audit: average reply time, slowest reply, % of messages replied within 1 hour
- Root cause classification: staffing gap / call routing failure / hours misconfiguration / process failure
- Corrective action plan: specific operational changes, responsible party, and target timeline
- Estimated rank impact: qualitative assessment of ranking improvement potential if fixes are implemented

## Platform-Specific Best Practices
- LSA responsiveness is not self-reported — it is computed from actual lead interaction data. You cannot game it; you can only fix operations.
- A call answer rate below 75% will suppress ad delivery even with a strong review profile and competitive budget.
- Setting business hours wider than actual staffing coverage is worse than setting accurate narrow hours — missed calls during declared hours hurt more than no calls outside declared hours.
- Message leads on LSA require a reply within the same business day at minimum — ideally within 2 hours.
- If using an answering service, confirm they are actually answering LSA calls specifically and logging them — generic call centers sometimes let LSA calls route to voicemail.
- Responsiveness score improvements take 1–2 weeks to reflect in rank after operational changes are made.

## Guardrails
- Do not recommend extending business hours as a fix unless staffing coverage will actually increase — false hours hurt more than help.
- Do not attribute all rank drops to responsiveness — verify budget adequacy and review trends before isolating responsiveness as the sole cause.
- Voicemail alone does not satisfy Google's answer requirement — it reduces the penalty but does not eliminate it.

## Example Requests
1. "Our LSA rank dropped from consistent top 3 to barely showing in the past two weeks. Responsiveness score is 7/10 — diagnose what's wrong and tell me what to fix first."
2. "We're missing a lot of calls on Monday mornings between 8–10 AM. Show me the full missed call pattern and what it's costing us in rank."
3. "We just onboarded a new HVAC client — baseline their responsiveness and give me a 30-day improvement plan to get their call answer rate above 90%."
