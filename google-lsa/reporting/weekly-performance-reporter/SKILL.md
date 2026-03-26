# LSA Weekly Performance Reporter

**Platform:** Google LSA
**Category:** reporting
**Tier:** pro

## Purpose
Produce a structured, operator-grade weekly performance report for a Google LSA account that covers lead volume, lead quality, spend efficiency, responsiveness health, and dispute activity. The weekly report is the operational pulse check — it catches emerging problems before they compound, surfaces dispute opportunities before the 60-day window closes, and maintains accountability on the key performance metrics that determine whether LSA spend is producing business outcomes.

## When to Use
- Every week, as a standing operational cadence for active LSA accounts
- When presenting performance updates to clients on a weekly basis
- When a specific performance event (rank drop, volume spike, lead quality dip) requires a structured summary
- As a hand-off document when account management changes within a team

## Inputs Required
- LSA dashboard data for the 7-day period: total leads, total spend, lead types (call/message/booking)
- Call answer rate for the period
- Responsiveness score (current and prior week)
- Booked lead count from CRM (LSA-sourced jobs booked in the week)
- Any disputes filed this week and any dispute resolutions received
- Budget cap setting and total spend vs. cap utilization
- Any profile changes made during the week
- Prior week baseline metrics for WoW comparison

## What This Skill Does
Compiles all available LSA performance data for the week into a standardized report format that surfaces the most operationally relevant insights at the top and provides full metric detail below. Calculates week-over-week changes for every core metric, flags any metric outside acceptable threshold, identifies whether dispute opportunities are aging, and provides a concise next-week action list. Designed to be readable in under 3 minutes and actionable without needing to open the LSA dashboard.

## Analysis Workflow
1. Pull total leads for the week: call leads, message leads, booking request leads — record each count.
2. Pull total spend for the week and calculate average cost-per-lead.
3. Calculate call answer rate for the period.
4. Pull booked lead count from CRM (or client-reported) — calculate booked lead rate for the week.
5. Calculate cost-per-booked-lead for the week.
6. Check responsiveness score — note current score, prior week score, and direction of change.
7. Calculate budget cap utilization: (Weekly Spend / Budget Cap) × 100.
8. Review disputes: list any disputes filed this week, any resolutions received (approved or denied), and estimate any credit recovered.
9. Identify any leads in the current rolling 30-day window that may be dispute-eligible and have not yet been reviewed.
10. Calculate week-over-week changes for: total leads, spend, cost-per-lead, answer rate, booked rate, cost-per-booked-lead.
11. Flag any metric that is outside threshold: answer rate below 80%, booked rate below 35%, utilization above 95% or below 60%, responsiveness decline of 1+ points.
12. Write the next-week action list: 3–5 specific operational tasks based on the week's data.

## Output Requirements
- Executive summary: 3–5 sentences covering the week's performance headline, the most important positive, and the most important concern
- Core metrics table: leads, spend, CPL, answer rate, booked leads, booked rate, cost-per-booked-lead — current week, prior week, WoW change
- Responsiveness health: current score, trend, and status (Healthy / Watch / Action Required)
- Budget utilization: spend vs. cap, utilization rate, and delivery status assessment
- Dispute activity log: disputes filed, resolutions received, credit recovered, leads still eligible for review
- Flags and alerts: any metric outside acceptable threshold with severity rating
- Next-week action list: 3–5 specific tasks with responsible party assigned

## Platform-Specific Best Practices
- The weekly report must include booked lead rate — reporting only raw lead volume without conversion context is operationally useless for LSA.
- Dispute activity should be tracked as a separate line item every week — credit recovery is real money and is frequently left unclaimed.
- Responsiveness score changes of even 1 point should be flagged — they often precede delivery changes within the following week.
- Budget utilization below 60% is as much of a concern as above 95% — under-delivery may indicate throttling that needs diagnosis.
- Week-over-week comparisons are more meaningful than month-over-month for LSA weekly reports — the platform responds quickly to operational changes.
- The report should be sent no later than Monday of the following week — Friday delivery is ideal so the client has the weekend to review before Monday decisions.

## Guardrails
- Do not report raw lead counts without booked lead rate — it gives an incomplete picture and can make a poor-performing week look acceptable.
- Do not omit WoW comparisons — context is what makes metrics actionable; absolute numbers without trend are not sufficient.
- Flag data gaps explicitly — if CRM booking data is unavailable for the week, note the limitation rather than omitting the booked rate section.
- Do not editorialize in the executive summary — describe what happened and what it means operationally; avoid speculative commentary.

## Example Requests
1. "Pull together this week's LSA report for our plumbing client — I have the dashboard data and CRM booking numbers. Format it for the client review call Tuesday."
2. "Generate a weekly report template for our 6 LSA accounts so I can run the same format every Monday. Include all the standard metrics and flag thresholds."
3. "This week was unusual — lead volume spiked and booking rate dropped. Write the weekly report and include a diagnosis of what happened in the executive summary."
