# Call Handling Diagnostician

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** pro

## Purpose
Diagnose what happens after an LSA call is answered — specifically how call handling quality, booking script execution, and front-desk conversion behavior are translating (or failing to translate) charged leads into booked jobs. LSA generates leads, not revenue. The gap between answered call rate and booked lead rate is almost always a call handling problem, not a lead quality problem. This skill identifies exactly where the conversion breakdown occurs on answered calls and prescribes corrections.

## When to Use
- When call answer rate is strong (above 85%) but booked lead rate remains below 45%
- When average lead cost is within target but cost-per-booked-job is unacceptable
- After a new receptionist or call center takes over LSA call handling
- When client feedback indicates "we get lots of calls but not many bookings"
- Quarterly, as part of a full funnel review for high-volume LSA accounts
- When you have access to call recordings and want to identify script failures

## Inputs Required
- Call answer rate and booked lead rate from LSA dashboard (current period)
- Call recordings or call notes from CRM (if available)
- Current booking script or intake process used by the front desk or call handler
- Average call duration for answered calls (from call log or phone system)
- Job type distribution of incoming leads
- Common objections or drop-off reasons reported by staff (price quotes, availability, geographic pushback)
- Any pricing or availability constraints that staff frequently cite on calls

## What This Skill Does
Builds a call conversion funnel from lead received through booking confirmed. Analyzes call duration distributions to identify where calls are ending prematurely, cross-references call outcomes against job type to find categories with consistently low booking rates, and audits the booking script for conversion gaps. Identifies whether the conversion problem is at the first-contact moment (caller not being offered an appointment), the objection-handling stage (price quotes derailing the call), or the scheduling stage (availability friction losing the booking). Produces a call handling scorecard and a script improvement brief.

## Analysis Workflow
1. Establish the baseline conversion funnel: total charged leads → answered calls → booking-attempted calls → confirmed bookings.
2. Calculate the answer-to-book rate: (Booked Leads / Answered Calls) × 100. This is the core diagnostic metric.
3. If call recordings are available: sample 10–20 answered calls that did not result in a booking — listen for the moment and reason the call ended without a booking.
4. If recordings are not available: use average call duration as a proxy — calls under 90 seconds on answered lines typically indicate a premature call end before booking attempt.
5. Categorize non-booked answered calls by failure type: Caller opted out (price/availability), Staff failed to attempt booking, Wrong service requested, Caller not ready to schedule.
6. Cross-reference non-booking rate by job type — identify which job types have the worst answer-to-book conversion.
7. Review the current booking script (if provided): assess whether it includes a direct booking ask, handles price objection with a range response, and captures contact information before the call ends.
8. Identify the average call duration for booked vs. non-booked answered calls — the gap reveals how much conversation time is needed to convert.
9. Check whether staff are offering specific appointment times (higher conversion) vs. asking the caller to call back (lower conversion).
10. Flag any scripting that prematurely provides pricing without first establishing value and scheduling intent.
11. Assess whether after-call follow-up is being attempted for calls that ended without a booking.
12. Produce a call conversion scorecard: each stage rated, with the highest-impact failure point identified.

## Output Requirements
- Call conversion funnel: total leads → answered → booking attempted → booked, with conversion rate at each stage
- Answer-to-book rate and benchmark comparison (target: 50%+ for most home service verticals)
- Top 3 call handling failure points with evidence (recording insight, duration data, or script gap)
- Job type conversion breakdown: which job types are converting calls to bookings, which are not
- Script gap analysis: specific script moments where the conversion fails most frequently
- Call handling scorecard: front-desk performance rated across answer, pitch, objection handling, and close
- Improvement brief: specific script changes, training priorities, and follow-up process recommendations

## Platform-Specific Best Practices
- LSA callers are high-intent — they have already seen pricing ranges and reviews before calling. A non-booking on an answered LSA call is almost always a handling failure, not a caller quality failure.
- The single highest-impact call handling fix in home services is training staff to offer a specific appointment time rather than "we'll call you back to schedule."
- Price objections on LSA calls are common because callers arrive with a price expectation from the ad — handling these requires a range-anchoring response, not a quote.
- Call duration under 2 minutes for a home service lead typically means the booking attempt was never made.
- Job types with complex scoping (HVAC system replacement, full electrical panel) will naturally have lower immediate booking rates than simple service calls — benchmark appropriately.
- A dedicated LSA call handler outperforms a shared receptionist handling multiple call types — context switching degrades conversion.

## Guardrails
- Do not attribute low booking rates solely to call handling if lead quality is also poor — diagnose both in parallel.
- Call recording analysis requires consent compliance — confirm legal recording consent is in place before accessing recordings.
- Script recommendations must be adapted to the specific vertical and client brand tone — generic scripts perform poorly.
- Do not assume a long call is a good call — lengthy calls without a booking may indicate indecision or objection handling failure rather than quality engagement.

## Example Requests
1. "We're answering 89% of our LSA calls but only booking 38% of them. Show me where the conversion is breaking down on the answered calls."
2. "I have 30 call recordings from last month's LSA leads. Run a call handling analysis — find the top failure points and write me a corrected booking script."
3. "Our plumbing job type has a terrible answer-to-book rate but our HVAC job type books fine. Why is there a difference and what do we do about it?"
