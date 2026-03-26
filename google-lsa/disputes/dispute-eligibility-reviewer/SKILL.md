# Dispute Eligibility Reviewer

**Platform:** Google LSA
**Category:** disputes
**Tier:** pro

## Purpose
Systematically evaluate every charged LSA lead against Google's current dispute eligibility criteria to identify which leads qualify for a dispute submission and which do not. Dispute review is one of the highest-ROI activities in LSA account management — eligible disputes that are never filed represent direct, recoverable money left on the table. This skill applies Google's dispute rules precisely, prevents invalid dispute submissions that could flag the account, and produces a clean, prioritized dispute queue ready for submission.

## When to Use
- Weekly, as part of the standard lead review cadence
- Immediately after any week with elevated junk lead volume
- When a new job type or service area was recently added and lead quality is unknown
- When the client reports receiving calls for services they do not offer
- Before the 45-day review checkpoint (disputes must be filed within 60 days of lead charge)
- After a budget increase that drove an unexpected volume spike with mixed quality

## Inputs Required
- Full lead log for the review period: date, time, lead type, charge amount, and lead status
- Call recordings or call duration data for all call leads in the review period
- CRM notes or disposition data mapped to LSA lead timestamps
- Active job types on the profile at the time of each lead
- Service area boundaries active at the time of each lead
- Prior dispute submissions and their resolution outcomes (to calibrate what Google approves)

## What This Skill Does
Applies Google's published and operationally observed dispute eligibility criteria to each lead in the review batch. Scores each lead as: Clearly Eligible, Likely Eligible, Borderline, or Not Eligible. Documents the specific eligibility rationale for each Clearly and Likely Eligible lead. Flags leads that are borderline with a confidence rating and the evidence that would strengthen or weaken the case. Outputs a ranked dispute queue sorted by eligibility confidence and estimated credit value.

## Analysis Workflow
1. Review Google's current dispute criteria: wrong service type requested, spam or robocall, call duration under 30 seconds with no meaningful exchange, geographic mismatch outside declared service area, duplicate contact within the billing period, solicitation or wrong business called.
2. For each call lead: retrieve call duration — flag all calls under 30 seconds as initial dispute candidates.
3. For calls over 30 seconds: review call notes or recording to determine whether the caller requested a service the business offers. If the service requested is outside active job types, flag as service mismatch dispute candidate.
4. Check caller phone number for duplicates within the current 30-day billing period — flag any number that appears more than once as a duplicate charge candidate.
5. Review message leads: assess content for spam patterns, solicitation language, or service requests outside active job types.
6. For any lead where the caller's area code or stated location is outside the declared service area, flag as geographic mismatch dispute candidate.
7. Review for robocall patterns: sequential dialing, silence on answer, automated speech, or common spam number databases.
8. Rate each flagged lead: Clearly Eligible (strong evidence, low denial risk), Likely Eligible (solid evidence, moderate approval probability), Borderline (weak or ambiguous evidence, file only if credit value justifies).
9. For each Clearly and Likely Eligible lead: write the dispute reason in Google's accepted language — precise, factual, no editorializing.
10. Calculate total estimated credit value for the eligible dispute queue.
11. Sort the dispute queue by eligibility confidence descending.
12. Flag any leads approaching the 60-day dispute window — prioritize these for immediate submission.

## Output Requirements
- Dispute eligibility summary: total leads reviewed, Clearly Eligible count, Likely Eligible count, Borderline count, Not Eligible count
- Total estimated credit value for Clearly + Likely Eligible disputes
- Dispute queue: each eligible lead with date, charge amount, eligibility category, eligibility rationale, and suggested dispute language
- Borderline leads with evidence assessment: what would make the case stronger, whether to file or hold
- 60-day expiration alert: any leads within 15 days of dispute window closing
- Prior dispute outcome reference: approval and denial patterns from prior submissions to calibrate current batch

## Platform-Specific Best Practices
- Google's dispute review is performed by a human team — write dispute reasons in clear, factual English, not jargon.
- Call duration under 30 seconds is the most consistently approved dispute criterion — do not overlook these in the review.
- Disputing valid leads (ones where a real customer asked about a real service) is flagged by Google and can reduce future dispute approval rates — precision matters.
- The "wrong service" dispute requires that the service requested is genuinely outside the business's active job types — if it is in the job types, it is not eligible.
- Duplicate charge disputes are the most commonly missed — always scan for repeat numbers.
- Filing 5 clean disputes is more valuable than filing 15 disputes with 8 valid ones — dispute precision protects the account's dispute track record.

## Guardrails
- Never dispute a lead where the caller clearly asked about a service the business provides, regardless of whether a booking resulted.
- Do not file a geographic mismatch dispute without confirming the caller location was outside the service area at the time of the call — area codes are not reliable geographic identifiers.
- Do not dispute leads from prior billing periods beyond 60 days — they will be automatically denied and waste dispute quota.
- Borderline disputes should only be filed when the credit value is high enough to justify the denial risk — use judgment on low-value borderline leads.

## Example Requests
1. "Review all 34 leads from March for dispute eligibility. I have call durations and CRM notes. Build me the dispute queue sorted by confidence."
2. "We have 12 leads that were flagged as short calls — assess all of them against dispute criteria and write the submission language for each eligible one."
3. "Our dispute approval rate has been dropping. Review our last 20 dispute submissions and tell me if we're filing borderline cases that are dragging down our approval rate."
