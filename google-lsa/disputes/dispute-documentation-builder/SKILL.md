# Dispute Documentation Builder

**Platform:** Google LSA
**Category:** disputes
**Tier:** pro

## Purpose
Build complete, submission-ready dispute documentation for every eligible LSA lead identified for dispute. The difference between an approved dispute and a denied dispute is often the quality and specificity of the written dispute reason. This skill translates raw evidence — call duration, call notes, job type configuration, service area settings — into precise, factual dispute language that matches Google's review framework and maximizes approval probability.

## When to Use
- After a dispute eligibility review has identified confirmed or likely eligible leads
- When preparing a batch dispute submission for a high-volume week
- When a dispute was previously denied and needs to be reframed with better documentation
- When a staff member without dispute experience needs to file disputes on behalf of the account
- When preparing a dispute pack for a client to self-submit

## Inputs Required
- Dispute-eligible lead list from the eligibility review: lead ID, date, charge amount, eligibility category, evidence summary
- Specific evidence for each lead: call duration (seconds), call recording notes or transcript excerpt, service requested (if available from notes), caller location (if determinable)
- Active job types at the time of the lead
- Service area configuration at the time of the lead
- Prior approved dispute language (if available — use as calibration reference)
- Google's current dispute reason category options (Wrong Service, Spam/Robocall, Short/Incomplete Call, Duplicate, Geographic Mismatch, etc.)

## What This Skill Does
Writes individualized, evidence-backed dispute reason statements for each eligible lead. Matches each lead to the correct Google dispute reason category. Formats the dispute reason in plain, specific language that a Google reviewer can verify against call records — avoiding vague language, emotional framing, or claims that cannot be corroborated. Packages all documentation into a submission-ready format with lead ID, reason category, and reason text for each dispute. Also produces a batch submission summary so the account manager can file efficiently.

## Analysis Workflow
1. For each eligible lead, confirm the dispute reason category: Short/Incomplete Call, Wrong Service, Spam or Robocall, Duplicate, Geographic Mismatch, or Other.
2. For Short/Incomplete Call disputes: record the call duration in seconds, note that no service request was established, and confirm the charge amount. Write: "[Duration]-second call. No service information exchanged and no appointment or quote requested. Call ended before any meaningful exchange."
3. For Wrong Service disputes: identify the service requested by the caller, confirm it is not in the active job types, note the job types that are active. Write: "Caller requested [specific service]. Our active job types are [list]. This service is not offered and was not listed on our profile at the time of this lead."
4. For Spam/Robocall disputes: note any evidence — automated voice, silence on answer, sequential dialing, known spam number. Write: "Call exhibited [specific spam indicator]. No human interaction occurred. This appears to be an automated or solicitation call, not a genuine service request."
5. For Duplicate disputes: identify the prior lead from the same number with its date and lead ID. Write: "This number ([last 4 digits or full number if permissible]) was already charged as Lead ID [prior ID] on [date]. This is a duplicate charge within the same billing period."
6. For Geographic Mismatch disputes: state the caller's location evidence and compare to the declared service area. Write: "Caller identified their location as [city/region], which is outside our declared service area of [service area description]. We do not service this geography."
7. Review each written dispute reason for: specificity (concrete facts, not opinions), verifiability (can Google check this against call records?), category match (is the reason aligned to the selected category?).
8. Remove any language that is argumentative, subjective, or unsupported by evidence.
9. Organize the dispute batch: lead ID, charge date, charge amount, dispute reason category, written reason — one row or block per lead.
10. Calculate the total credit amount at stake in the batch.
11. Flag any disputes requiring supplementary documentation (screenshots, call log exports) and note what to attach.
12. Produce the final submission-ready batch document.

## Output Requirements
- Submission-ready dispute batch: each lead formatted with Lead ID, Date, Charge Amount, Dispute Reason Category, Written Dispute Reason
- Total estimated credit value for the batch
- Evidence attachment checklist: for each lead, note what supporting documentation should be uploaded with the dispute
- Submission sequence recommendation: file Clearly Eligible leads first; batch borderline leads separately
- Denial risk flag: any dispute in the batch where language or evidence is weaker than ideal
- Resubmission notes for previously denied disputes: what changed in the framing and why it improves the case

## Platform-Specific Best Practices
- Dispute reason text should be 2–4 sentences — concise, factual, and matched to observable evidence. Google reviewers read many disputes; clear language gets faster and more favorable decisions.
- Never use language like "I don't think this was a real lead" — Google needs verifiable evidence, not opinion.
- For Short Call disputes, the call duration in seconds is the single most important piece of evidence — include it explicitly.
- For Wrong Service disputes, naming the specific service requested (even an approximation from call notes) dramatically improves approval rates over generic "wrong service" claims.
- Filing disputes in batches (rather than one by one) is operationally efficient but does not affect individual approval probability — each dispute is reviewed independently.
- A denied dispute can be refiled once with additional evidence — the second submission should include any new information not in the original.

## Guardrails
- Do not fabricate or embellish evidence — if the only evidence is call duration, write a call-duration dispute. Do not infer what the caller said without documentation.
- Do not submit dispute language that contradicts what is in the CRM notes — inconsistency is a denial trigger.
- Dispute documentation must be written for the specific platform's review process — do not repurpose language from Yelp, Angi, or other dispute processes.
- Dispute reason text should not include the caller's full phone number in public-facing documentation — use last 4 digits or reference only.

## Example Requests
1. "I have 11 eligible leads from March ready to dispute. Build the full submission documentation for each one — I have call durations and CRM notes for all of them."
2. "Three disputes got denied last week. Here's what I submitted — rewrite the dispute reasons with stronger framing and tell me what evidence to add on resubmission."
3. "Our front desk manager needs to file disputes every week but she's never done it. Build a dispute documentation template she can fill in for each eligible lead."
