# Missed Call & Missed Opportunity Reviewer

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** pro

## Purpose
Quantify the revenue impact of every unanswered LSA lead and convert the missed opportunity analysis into a business case for operational change. On LSA, a missed call is doubly punishing: the business is still charged for the lead, and the responsiveness signal degrades, compressing future ad delivery. This skill translates missed call data into lost revenue estimates, identifies the operational patterns causing the misses, and produces a prioritized recovery plan.

## When to Use
- When missed calls appear in the LSA leads tab and no callback was logged
- When the client questions why spend is high but booked jobs are low
- After a staffing gap event (employee quit, vacation coverage failure, system outage)
- When you need to justify investment in after-hours coverage or an answering service
- Monthly, as part of the lead waste portion of the performance review
- When call answer rate drops more than 5 percentage points week-over-week

## Inputs Required
- Missed call log from LSA Leads tab: date, time, lead charge amount
- CRM callback log: any outbound calls made to LSA missed call numbers, outcomes
- Job type distribution of missed leads (when inferable from profile active job types)
- Average ticket value by job type or blended average ticket
- Typical close rate when a return call successfully reaches the prospect
- Business operating hours and staffing schedule for the review period
- Any known coverage gaps during the review period (sick days, system issues, holidays)

## What This Skill Does
Converts raw missed call data into a revenue opportunity loss calculation. Maps each missed call to the probability of recovery based on callback timing, identifies the time-of-day and day-of-week concentration of missed calls, calculates the compound cost of each miss (lead charge + lost revenue potential + responsiveness penalty), and segments misses by recoverability — immediate callback opportunity, likely gone, or already recovered. Delivers a total missed revenue estimate and an operational fix prescription.

## Analysis Workflow
1. Extract all missed calls from the LSA leads tab for the review period — record timestamp, lead charge, and whether a callback was attempted.
2. For each missed call, check the CRM or call log for a return call attempt — note time gap between miss and callback.
3. Categorize each missed call by recovery status: Recovered (callback made within 1 hour), Late Recovery (callback made after 1 hour), No Callback Attempted, Not Reachable.
4. Calculate callback-to-book rate for recovered leads — compare to answered-call booking rate to quantify the conversion penalty of calling back late.
5. Map missed calls by day of week and hour of day — identify the 2–3 time windows with the highest miss concentration.
6. Cross-reference miss timestamps against declared business hours — flag every miss that occurred during hours when the business claimed to be open.
7. Calculate total missed call spend: (number of missed calls × average lead charge).
8. Calculate lost revenue potential: (missed calls × estimated recovery rate × average ticket value × close rate).
9. Calculate the compound cost: missed call spend + lost revenue potential = total opportunity cost.
10. Identify the single biggest operational gap causing misses (e.g., lunch hour coverage, Monday morning surge, no after-hours routing).
11. Model the ROI of an answering service: estimated monthly cost vs. estimated recovered revenue from improved answer rate.
12. Build a prioritized coverage fix plan targeting the highest-concentration miss windows first.

## Output Requirements
- Missed opportunity summary: total missed calls, total wasted lead spend, recovery attempts made
- Revenue loss estimate: missed calls × estimated booking probability × average ticket value
- Compound cost table: lead charge cost + revenue opportunity cost per missed call category
- Time pattern breakdown: missed calls by day and hour — highlight top 3 concentration windows
- Recovery rate analysis: callbacks made, time-to-callback, booked vs. not booked outcomes
- Operational gap diagnosis: root cause of miss concentration (staffing, routing, hours, coverage)
- Fix recommendations: specific coverage changes with estimated ROI, including answering service analysis if applicable

## Platform-Specific Best Practices
- LSA missed calls are charged at the same rate as answered calls in most verticals — there is no partial credit for not answering.
- Google tracks callback attempts but does not use them to reverse the responsiveness penalty — the penalty accrues at call time, not callback time.
- A business that misses 20% of its LSA calls is losing both the lead cost and a measurable fraction of its ad delivery reach.
- Prospect return rate on LSA missed calls drops significantly after 15 minutes — by 2 hours, the prospect has typically booked a competitor.
- After-hours calls represent the highest percentage of missed calls in home services — coverage from 6–9 PM is frequently the highest ROI coverage investment.
- Setting LSA hours to match real staffing coverage reduces miss rate without adding staff by simply not receiving calls during unstaffed windows.

## Guardrails
- Revenue loss estimates are probabilistic — present them as ranges, not guarantees.
- Do not recommend extending hours without confirming that staffing or answering service coverage will actually be in place.
- Missed call disputes are typically not eligible unless the lead itself was invalid — a missed call from a real prospect is a chargeable lead regardless of outcome.
- Do not assume every missed call equals a lost booking — some callers were window-shopping or price-checking.

## Example Requests
1. "We had 23 missed calls last month on LSA. Calculate what that cost us in lead spend and lost revenue, and tell me what time slots are killing us."
2. "Our call answer rate dropped to 68% this week. Show me the missed call pattern and build the business case for hiring an after-hours answering service."
3. "Client says they answered every call but LSA is showing 14 missed calls. Help me reconcile the data and figure out where the disconnect is."
