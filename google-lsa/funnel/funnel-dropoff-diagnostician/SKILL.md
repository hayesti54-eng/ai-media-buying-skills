# LSA Funnel Drop-off Diagnostician

**Platform:** Google LSA
**Category:** funnel
**Tier:** pro

## Purpose
Identify the specific stage in the LSA lead-to-revenue funnel where the highest volume of leads is being lost and diagnose the operational cause of that drop-off. The LSA funnel has five distinct stages, each with a different failure mode: lead delivery, call answer, conversation-to-booking, booking confirmation, and job completion. Every business leaks at one or more of these stages — this skill finds the largest leak, quantifies its revenue cost, and prescribes the targeted fix.

## When to Use
- When cost-per-revenue-dollar from LSA is higher than expected but no single metric explains why
- When lead volume is healthy but revenue generated from LSA is disappointing
- After implementing an operational change to determine whether it improved funnel efficiency
- When a client asks "why aren't we converting our LSA leads into money?"
- As part of a quarterly funnel health review for high-investment LSA accounts
- When comparing funnel efficiency across multiple business locations on the same LSA program

## Inputs Required
- Total charged LSA leads for the review period (by lead type)
- Call answer rate for the period
- Total answered calls (calls answered / total call leads)
- Total booking attempts (calls where a booking was offered and the caller was interested)
- Total booked jobs from LSA (confirmed in CRM)
- Total completed jobs from LSA (jobs that were scheduled and actually executed)
- Revenue from completed LSA jobs
- Any known operational events during the period (staff changes, no-shows, cancellations)

## What This Skill Does
Maps all available lead-to-revenue data across five funnel stages, calculates the conversion rate at each stage, identifies the stage with the largest absolute lead count drop-off and the largest percentage conversion gap versus benchmark, and diagnoses the specific failure mechanism at that stage. Distinguishes between funnel leaks that are platform-side (Google not delivering high-quality leads), operations-side (answer rate, booking rate), and execution-side (no-shows, cancellations after booking). Outputs a funnel efficiency score, a primary leak diagnosis, and a stage-specific fix prescription.

## Analysis Workflow
1. Define the five funnel stages and populate each with available data:
   - Stage 1: Leads Charged (from LSA dashboard)
   - Stage 2: Calls Answered (answer rate applied to call leads)
   - Stage 3: Booking Attempts (calls where scheduling was offered)
   - Stage 4: Jobs Booked (CRM confirmed bookings)
   - Stage 5: Jobs Completed and Paid (CRM closed won revenue)
2. Calculate the conversion rate between each adjacent stage: Stage 1→2, Stage 2→3, Stage 3→4, Stage 4→5.
3. Calculate the cumulative funnel conversion: (Stage 5 count / Stage 1 count) × 100 — this is the end-to-end funnel efficiency rate.
4. Identify the stage with the lowest stage-to-stage conversion rate — this is the primary leak point.
5. Calculate the revenue impact of the primary leak: if Stage 2→3 conversion improved by 10 points, how many additional booked jobs would result, and at what average revenue?
6. Diagnose the failure mechanism at the primary leak point:
   - Stage 1→2 leak: platform delivery or answer rate problem
   - Stage 2→3 leak: call handling or pitch failure
   - Stage 3→4 leak: scheduling friction, availability problem, or objection handling failure
   - Stage 4→5 leak: no-show rate, cancellation rate, or job execution failure
7. Identify secondary leak points — any stage with a conversion rate more than 10 points below benchmark.
8. Calculate what the funnel efficiency rate would be if the primary leak were resolved to benchmark performance.
9. Assess whether the funnel drop-off pattern is consistent across job types or concentrated in specific categories.
10. Determine whether the leak is a one-time event (staffing gap week) or a structural pattern.
11. Write the funnel drop-off diagnosis: one primary cause, two secondary causes, and the evidence supporting each.
12. Produce the stage-specific fix prescription with estimated funnel efficiency improvement.

## Output Requirements
- Funnel stage table: lead count and conversion rate for each of the five stages
- Cumulative funnel efficiency rate: end-to-end conversion from charged lead to paid job
- Primary leak point identification: stage, conversion rate, gap to benchmark, revenue impact
- Secondary leak points: identified with conversion rates and brief evidence
- Failure mechanism diagnosis: what is causing the drop-off at the primary leak stage
- Revenue recovery model: projected revenue improvement if primary leak is resolved to benchmark
- Stage-specific fix prescription: targeted operational change for each identified leak point

## Platform-Specific Best Practices
- Most LSA funnels in home services leak hardest at Stage 2→3 (answered call to booking attempt) — this is the call handling gap and is the most fixable leak in the shortest time.
- Stage 4→5 leaks (booked to completed) are frequently underreported because businesses track bookings but not no-shows — always ask for no-show and cancellation rate.
- A Stage 1→2 leak (delivery to answer) that represents more than 20% loss is a responsiveness penalty in action — fix it before addressing downstream stages.
- Funnel efficiency benchmarks by vertical: home services broadly 15–30% cumulative efficiency (charged lead to completed job) — ranges vary widely by trade.
- Multi-location funnel comparisons reveal operational performance differences that single-location analysis cannot show — use them to identify the highest-performing operational model.
- The funnel model must account for lead type differences — message leads and call leads have different conversion profiles at every stage.

## Guardrails
- Do not draw stage-specific conclusions with fewer than 20 leads at that stage — small sample sizes produce misleading conversion rates.
- Stage 3 (booking attempts) data often requires direct staff input — do not estimate it without confirmation from call handlers.
- Funnel analysis is a diagnostic tool, not a performance guarantee — fixing the primary leak improves the funnel but does not guarantee specific revenue outcomes.
- Do not compare raw funnel efficiency rates across different verticals — a 20% end-to-end rate is excellent for a large-ticket renovation contractor and weak for a carpet cleaning company.

## Example Requests
1. "We're charging $3,200/month on LSA and generating $11,000 in revenue. That feels low. Map our funnel and show me where we're losing the most leads."
2. "Our booking rate looks fine but our completed job revenue is way below what the bookings should be generating. Run a funnel analysis — I think we have a no-show problem."
3. "We have three locations running LSA. Run the funnel analysis for all three and show me which location has the worst conversion efficiency and why."
