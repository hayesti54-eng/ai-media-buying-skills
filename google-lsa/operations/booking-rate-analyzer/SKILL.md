# LSA Booking Rate Analyzer

**Platform:** Google LSA
**Category:** operations
**Tier:** pro

## Purpose
Measure, benchmark, and improve the booked lead rate — the single most important conversion metric in LSA performance management. Booked lead rate (booked jobs / total charged leads) determines the true cost of customer acquisition, exposes waste in the lead pipeline, and serves as the primary signal for whether LSA spend is producing business outcomes. This skill builds a complete booking rate analysis across job type, time period, lead type, and operational variable to isolate what is driving the rate and what is suppressing it.

## When to Use
- As a standard component of every monthly LSA performance review
- When cost-per-booked-job exceeds the client's acceptable acquisition cost
- When total lead volume increases but revenue does not increase proportionally
- When comparing performance across multiple LSA profiles (multi-location clients)
- After operational changes (new staff, new script, new hours) to measure their booking rate impact
- When setting performance targets for a new LSA account in a competitive vertical

## Inputs Required
- LSA lead log: total leads by type (call, message, booking request) for the review period
- CRM or job management data: booked jobs sourced to LSA for the same period
- Lead charge data: total spend and per-lead cost for the period
- Booked job revenue data: total revenue from LSA-sourced booked jobs
- Job type breakdown of incoming leads (if available)
- Call answer rate for the period
- Any operational changes made during the period that could affect booking rate

## What This Skill Does
Calculates booked lead rate at the aggregate level and by every available segmentation: job type, lead type (call vs. message), day of week, and time of day if data permits. Computes cost-per-booked-lead, revenue-per-lead, and return-on-ad-spend from the booked lead perspective. Benchmarks results against vertical norms. Identifies the highest-leverage variables correlated with higher booking rates and flags the variables correlated with rate suppression. Outputs a full booking rate diagnostic with improvement levers ranked by potential impact.

## Analysis Workflow
1. Establish the gross booking rate: (Total Booked Jobs from LSA / Total Charged LSA Leads) × 100.
2. Segment booking rate by lead type: calculate separate rates for call leads vs. message leads vs. booking request leads — these have fundamentally different conversion dynamics.
3. Segment booking rate by job type (to the extent job type is inferable from CRM notes or LSA data).
4. Calculate cost-per-booked-lead: (Total LSA Spend / Total Booked Jobs from LSA).
5. Calculate revenue-per-lead: (Total Revenue from LSA-Booked Jobs / Total Charged LSA Leads).
6. Calculate LSA ROAS: (Total Revenue from LSA-Booked Jobs / Total LSA Spend).
7. Break booking rate by week within the period — identify trend direction and any inflection events.
8. Cross-reference booking rate against call answer rate — determine whether booking rate variance is driven by answer rate or by post-answer conversion.
9. Identify the job types or lead categories with the highest and lowest booking rates.
10. Benchmark aggregate booking rate against vertical norms (home services baseline: 35–55% depending on trade).
11. Model the booking rate impact of the top 2 improvement levers: (a) increasing call answer rate to 90%, (b) improving answer-to-book conversion by 10 points.
12. Produce a booking rate improvement priority list with estimated impact.

## Output Requirements
- Booking rate dashboard: gross rate, segmented by lead type, job type, and time period
- Cost metrics: cost-per-lead, cost-per-booked-lead, revenue-per-lead, LSA ROAS
- Benchmark comparison: current rate vs. vertical benchmark range
- Segment analysis: highest and lowest performing lead type, job type, and time period
- Trend analysis: booking rate direction over the period with inflection events flagged
- Improvement model: projected booking rate and cost-per-booked-lead under top 2 improvement scenarios
- Prioritized action list: specific changes ranked by booking rate impact potential

## Platform-Specific Best Practices
- Booked lead rate is not reported natively in the LSA dashboard — it requires cross-referencing with CRM data. Set up this data connection as a baseline operational requirement.
- Message leads typically book at a lower rate than call leads — do not blend them without segmenting first, as blending masks call performance.
- Booking request leads (when the customer requests a booking directly through LSA) have the highest inherent booking probability — treat them as priority follow-ups.
- A booking rate below 30% in a home service vertical is almost always multi-causal: answer rate, call handling, and job type alignment are all contributing.
- Seasonal demand variation affects booking rate — benchmark against the same period in the prior year, not against arbitrary static targets.
- Revenue-per-lead is a more complete performance metric than cost-per-lead because it accounts for job size variation by lead type.

## Guardrails
- Do not use booking rate as a quality score for individual job types without a sufficient sample size — minimum 20 leads per job type before drawing conclusions.
- Booking rate comparisons across markets or verticals require context — a 40% rate in HVAC is strong; a 40% rate in cleaning services may be weak.
- Do not conflate "not booked" with "bad lead" — some answered calls are valid leads that did not convert due to timing or pricing, not lead quality.
- Revenue attribution requires reliable CRM source tagging — if LSA leads are not being tagged at the CRM level, revenue data will undercount and ROAS will appear artificially low.

## Example Requests
1. "Calculate our LSA booking rate for Q1 and break it down by job type. I want to see which job types are performing and which are costing us money per lead."
2. "Our cost-per-lead is $42 and we're running at a 33% booking rate. What does that make our cost-per-booked-job, and what's the fastest way to bring that number down?"
3. "We manage 4 LSA profiles for the same roofing client in different cities. Run booking rate comparisons across all four locations and identify which operation has the biggest improvement gap."
