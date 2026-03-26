# LSA Lead Quality Auditor

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** pro

## Purpose
Systematically evaluate the quality of every lead charged through Google Local Services Ads to separate legitimate, dispute-eligible, and genuinely chargeable leads. LSA charges per lead regardless of outcome — this skill exists to surface the cost of low-quality volume, drive dispute submissions where eligible, and reveal structural issues in job type targeting and service area configuration that are generating noise rather than revenue.

## When to Use
- After any week where booked lead rate drops below 40%
- When average cost-per-lead exceeds your target cost-per-acquisition threshold
- When a new service area or job type is added and lead quality is unknown
- Monthly, as part of a standard lead charge review cycle
- When a client reports receiving leads for services they do not offer
- After a budget increase that drove unexpected lead volume spikes

## Inputs Required
- Lead log export from LSA dashboard (date range, lead type, lead status, charge amount)
- CRM disposition data mapped to LSA lead IDs or phone timestamps
- Job type configuration currently active on the LSA profile
- Service area boundaries (zip codes or city/radius currently set)
- Average ticket value and close rate by job type
- Any dispute submissions filed in the prior 30 days and their resolution status

## What This Skill Does
Performs a structured quality score on each lead bucket — answered calls, missed calls, messages — against job type alignment, geographic validity, and conversion outcome. Flags leads that are dispute-eligible based on Google's current dispute criteria: wrong service, spam/robo calls, calls under 30 seconds with no meaningful exchange, geographic mismatch outside the declared service area, and duplicate contacts. Outputs a lead quality breakdown by category, a dispute shortlist, and a structural diagnosis of what in the profile configuration is generating low-quality volume.

## Analysis Workflow
1. Pull the full lead log for the target date range — include all lead types (call, message, booking).
2. Segment leads into four buckets: Booked, Not Booked - Valid, Not Booked - Disputed, Not Booked - Unclear.
3. For each "Not Booked" lead, cross-reference CRM call notes or recording timestamps to identify call duration and content.
4. Flag leads under 30 seconds with no booked outcome as dispute candidates — log call timestamp, duration, and lead ID.
5. Identify leads where the caller requested a service not listed in the active job types — these are job type misalignment leads and may be disputable.
6. Cross-reference caller zip code or area code (when available) against service area boundaries — flag geographic outliers.
7. Check for duplicate caller numbers within the billing period — multiple charges from the same number within 30 days may qualify for dispute.
8. Calculate booked lead rate: (Booked Leads / Total Charged Leads) × 100.
9. Calculate effective cost-per-booked-lead: Total Lead Spend / Booked Leads.
10. Score each active job type by its individual booked lead rate — surface the lowest performers.
11. Compile dispute submission shortlist with evidence requirements for each flagged lead.
12. Identify the top 2–3 structural causes of quality degradation (job type, geography, time-of-day).

## Output Requirements
- Lead quality scorecard: total leads, booked count, booked lead rate %, dispute-eligible count
- Cost analysis: total spend, cost-per-lead, cost-per-booked-lead, estimated recoverable spend via disputes
- Dispute shortlist: lead ID, date, call duration, disqualification reason, recommended dispute category
- Job type quality breakdown: booked rate per job type, recommended job types to pause or refine
- Service area assessment: flagged zip codes or regions generating out-of-scope leads
- Actionable recommendations: profile changes, job type removals, service area tightening, call handling fixes

## Platform-Specific Best Practices
- Google LSA disputes must be filed within 60 days of the lead charge — never let a dispute backlog age past 45 days.
- Do not dispute leads that lasted over 2 minutes even if no booking occurred — Google will deny these.
- Job type alignment is the single highest-leverage fix for lead quality: removing irrelevant job types reduces junk volume immediately.
- LSA does not allow keyword-level exclusions — quality control happens entirely at the job type and service area level.
- Message leads have a different dispute threshold than call leads — evaluate them separately.
- A booked lead rate below 30% is a structural profile problem, not a market problem.

## Guardrails
- Do not dispute leads where the conversation was substantive but the customer chose a competitor — these are valid leads.
- Do not remove job types without confirming the business actually cannot service that category.
- Never inflate dispute claims — Google tracks dispute abuse and can reduce profile trust signals.
- Geographic flags are indicators, not automatic dispute qualifications — verify before submitting.

## Example Requests
1. "Audit our LSA leads for March — we spent $1,800 and only booked 6 jobs. Show me what's disputable and what's a profile problem."
2. "We added water heater installation as a job type last month and lead quality tanked. Run a quality breakdown and tell me if we should remove it."
3. "Pull a dispute shortlist from last week's leads — I want every call under 30 seconds and every out-of-area contact flagged with evidence notes."
