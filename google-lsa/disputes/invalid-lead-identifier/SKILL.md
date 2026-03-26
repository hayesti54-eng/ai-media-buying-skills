# Invalid Lead Identifier

**Platform:** Google LSA
**Category:** disputes
**Tier:** pro

## Purpose
Rapidly identify invalid leads within a charged LSA lead set using a structured triage protocol — sorting every lead into Valid, Invalid (Disputable), or Invalid (Non-Disputable) before a full dispute documentation process begins. This skill is designed for speed: it applies a fast-pass filter that separates the clearly invalid from the clearly valid so dispute resources are focused only where recovery is possible, and valid leads are not mistakenly disputed.

## When to Use
- As the first step in any dispute workflow — runs before the Dispute Eligibility Reviewer in high-volume weeks
- When reviewing a large lead batch (20+ leads) and needing to triage efficiently
- When a new team member is learning dispute protocols and needs a clear decision framework
- When lead quality is generally poor and a broad initial scan is needed before deep review
- After any job type or service area change that is suspected of generating invalid volume

## Inputs Required
- Full lead list for the review period: lead ID, date, lead type (call/message), call duration (seconds for call leads), charge amount
- CRM disposition for each lead: was it a real conversation, wrong number, spam, out-of-area, or no record?
- Active job types at the time each lead was received
- Service area at the time each lead was received
- Any spam pattern indicators: known solicitation numbers, automated call characteristics noted by staff

## What This Skill Does
Applies a five-question invalid lead triage to every lead in the batch: (1) Was the call under 30 seconds? (2) Did the caller request a service the business does not offer? (3) Was the caller outside the declared service area? (4) Was this phone number already charged in the current billing period? (5) Does the call or message exhibit spam/solicitation characteristics? Any "yes" answer triggers an invalid flag. Each flagged lead is then classified as Disputable (Google will accept this dispute) or Non-Disputable Invalid (the lead is bad but does not meet Google's dispute criteria — e.g., a valid service request that the business chose not to pursue).

## Analysis Workflow
1. Load the lead batch — create a working list with Lead ID, date, lead type, call duration, and CRM status for each entry.
2. Apply Question 1 — Call Duration Filter: flag every call lead with a duration under 30 seconds. Mark as: Invalid - Duration.
3. Apply Question 2 — Service Mismatch Filter: for every lead with a CRM note or call recording reference, check whether the service requested is in the active job types. Flag mismatches as: Invalid - Service Mismatch.
4. Apply Question 3 — Geographic Filter: for leads where the caller's location is stated or their area code suggests out-of-area, check against service area boundaries. Flag geographic outliers as: Invalid - Geographic Mismatch.
5. Apply Question 4 — Duplicate Filter: scan all call leads for repeat phone numbers within the 30-day billing window. Flag duplicates as: Invalid - Duplicate Charge.
6. Apply Question 5 — Spam Filter: review CRM notes for any staff indication of automated voice, solicitation, wrong business, silence on answer. Flag as: Invalid - Spam/Robocall.
7. For all flagged leads: apply Google's dispute eligibility mapping — determine which invalid categories are Disputable under Google's criteria and which are invalid but non-disputable.
8. For Non-Disputable Invalid leads: categorize the root cause — these leads are valid charges under Google's rules but represent waste that should be addressed through profile configuration (job type removal, service area tightening).
9. Compile the sorted lead list: Valid, Invalid-Disputable, Invalid-Non-Disputable.
10. Calculate: total leads, valid count, disputable count (with estimated credit), non-disputable invalid count (with cost and root cause).
11. Output the triage report with the disputable leads ready to move into the documentation stage.
12. Flag the non-disputable invalid leads for profile fix recommendations.

## Output Requirements
- Triage summary: total leads by category — Valid, Invalid-Disputable, Invalid-Non-Disputable
- Invalid-Disputable lead list: each flagged lead with Lead ID, date, charge, invalid type, and evidence basis
- Estimated credit recovery from disputable leads
- Invalid-Non-Disputable analysis: root cause breakdown and associated lead cost — what these leads reveal about profile configuration problems
- Profile fix triggers: specific job type or service area changes recommended based on non-disputable invalid patterns
- Triage decision log: the triage answer (Yes/No) for each of the five questions applied to each flagged lead

## Platform-Specific Best Practices
- The five-question triage is designed to run in under 3 minutes per lead with available data — do not over-analyze at the triage stage; the documentation stage handles depth.
- Non-Disputable Invalid leads are often the most diagnostically valuable — they reveal structural profile problems that will recur if not fixed.
- Call duration is the highest-precision triage signal — it is objective and verifiable. Service mismatch requires more interpretation and should be applied with more care.
- In home services, the most common invalid lead type is the under-30-second hang-up — followed by wrong-service calls caused by misconfigured job types.
- Triage should happen weekly, not monthly — leads that are not triaged within 45 days are at risk of missing the 60-day dispute window.

## Guardrails
- A "yes" to any triage question does not automatically mean the lead is disputable — it flags it for review. Apply the disputable/non-disputable classification carefully.
- Do not apply the geographic filter based solely on area code — callers from a different area code may be located within the service area. Use stated location or CRM notes.
- Do not triage calls with 30–60 second durations as automatically invalid — assess call content before flagging.
- The triage output is a preliminary sort, not a final dispute decision — all Invalid-Disputable leads should pass through the Dispute Eligibility Reviewer before submission.

## Example Requests
1. "I have 28 leads from this week. Run the invalid lead triage — I want a quick sort before I spend time on documentation."
2. "Our cost-per-lead is high and booking rate is low. Run the invalid lead triage on last month's full lead set and show me the breakdown of what's actually invalid."
3. "What percentage of our leads are typically invalid but non-disputable? Run the triage and show me the profile changes that would eliminate those."
