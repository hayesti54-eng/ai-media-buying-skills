# CRM Sourcing & Lead Dispositioning Analyzer

**Platform:** Google LSA
**Category:** funnel
**Tier:** pro

## Purpose
Ensure that every Google LSA lead is accurately sourced, tracked, and dispositioned in the CRM so that revenue attribution, booked lead rate reporting, and dispute review workflows are based on reliable data rather than estimation. LSA generates leads but has no native CRM integration or UTM tracking — every downstream data connection must be built manually. This skill audits the current CRM sourcing setup, identifies attribution gaps, corrects dispositioning inconsistencies, and establishes a clean data pipeline that makes all LSA performance reporting trustworthy.

## When to Use
- During initial LSA account setup or agency onboarding — before reporting baselines are established
- When booked lead rate calculations appear inconsistent with what the business reports closing
- When revenue attribution analysis shows unexpectedly low LSA ROAS due to suspected under-attribution
- When the CRM is being changed, upgraded, or migrated
- Quarterly, as part of a data hygiene review for active LSA accounts
- When multiple lead sources are active and source attribution is muddled in the CRM

## Inputs Required
- CRM system in use (HubSpot, Jobber, ServiceTitan, Housecall Pro, GoHighLevel, or other)
- Current source attribution fields and values used in the CRM (e.g., what is the "LSA" source tag, and is it being used consistently?)
- Sample of 20–30 recent LSA leads — pulled from the LSA dashboard lead log with timestamps — compared against corresponding CRM entries
- Disposition stage definitions currently in use: what stages exist in the pipeline, and what do they mean?
- Current process for entering LSA leads into the CRM (manual entry by staff, automated, or not being entered)
- Any integrations currently connecting LSA to the CRM (phone system integration, webhook, Zapier)

## What This Skill Does
Audits the accuracy and completeness of LSA lead data in the CRM through a sample match analysis. Compares LSA lead timestamps against CRM entry timestamps to measure entry lag and entry rate. Assesses source attribution consistency — are all LSA leads being tagged as LSA, or are they entering under "phone," "unknown," or no source at all? Reviews disposition stage usage — are stages being updated as leads progress, or do leads stagnate in "New" without ever being moved? Identifies the specific breakdown points in the CRM data flow and prescribes fixes with priority ranking.

## Analysis Workflow
1. Pull a 30-day sample of LSA leads from the LSA dashboard: lead ID, date, time, and lead type.
2. Match each LSA lead to a CRM entry using call timestamp, phone number, or manual cross-reference.
3. Calculate the CRM entry rate: (LSA leads with a matching CRM entry / Total LSA leads) × 100. Flag if below 90%.
4. For matched entries: check the source attribution field — is it tagged as LSA, Google LSA, or an equivalent value? Calculate the LSA source tagging rate.
5. For entries with missing or incorrect source tags: identify the pattern — are they tagged as a different source, untagged, or missing entirely?
6. Measure average time between LSA lead received and CRM entry created — flag any average lag over 24 hours.
7. Review disposition stage distribution: count leads in each stage. Flag any disproportionate concentration in early stages (New, Uncontacted) that suggests leads are not being worked or updated.
8. Identify the disposition stage where the most leads are being lost without a recorded outcome — this is the funnel leak point.
9. Check whether "Booked" or equivalent is defined as a stage and whether jobs are being marked booked in the CRM at the moment of booking (vs. retroactively).
10. Assess whether the CRM data would support an accurate booked lead rate calculation — if not, document the specific gap preventing it.
11. Determine the root cause of each data gap: process failure (staff not entering), system gap (no integration), definition failure (stages not clearly defined), or training failure.
12. Produce the CRM data quality scorecard with fix prescriptions.

## Output Requirements
- CRM data quality scorecard: entry rate, source tagging rate, average entry lag, disposition stage distribution
- Attribution gap analysis: percentage of LSA leads unattributed or misattributed in the CRM, with estimated revenue undercount
- Disposition funnel analysis: lead counts by stage, stage-to-stage conversion rates, drop-off point identification
- Root cause classification for each data gap: process / system / definition / training
- Fix prescription by gap: specific change to make, system or process involved, and implementation complexity
- Recommended CRM workflow: a step-by-step data entry process for LSA leads that produces clean attribution and disposition tracking
- Minimum viable data setup: if a full CRM integration is not feasible, what is the simplest reliable manual system?

## Platform-Specific Best Practices
- LSA does not provide webhook triggers or native CRM integrations — every lead must be entered manually or via a phone system integration that captures call timestamps.
- Phone system integrations (e.g., CallRail, RingCentral with CRM sync) are the most reliable way to auto-populate LSA call leads into a CRM — evaluate if the client has the infrastructure.
- ServiceTitan and Housecall Pro both have phone integration options that can reduce manual entry lag for trades businesses — use native tools before building custom workflows.
- The most common attribution error is assigning LSA leads to "Phone" as a generic source, which merges them with non-LSA phone leads and breaks revenue attribution permanently.
- Disposition hygiene matters for dispute review: if a lead's CRM note shows a service mismatch, that note is evidence for a dispute — it must be entered accurately and promptly.
- A booked lead rate calculation that relies on incomplete CRM data will always undercount performance — fix the data before benchmarking.

## Guardrails
- Do not recommend CRM workflows that require more than 3 manual steps per lead for a small business — complexity will be ignored.
- Source attribution corrections should be applied prospectively, not retroactively retroactively without auditing the backfill — retroactive retagging can corrupt historical reporting.
- Do not assume the CRM's "source" field is being used consistently across team members — verify with a sample, not an assumption.
- Revenue figures derived from incomplete CRM data should always be presented with a confidence range, not as precise numbers.

## Example Requests
1. "Our LSA revenue attribution looks way too low — we booked 38 jobs but only 19 are tagged as LSA in the CRM. Audit our sourcing setup and tell me where the attribution is breaking."
2. "We just switched from Jobber to ServiceTitan. Help me rebuild the LSA lead sourcing and dispositioning workflow in the new CRM before we go live."
3. "Our client has no CRM at all — they track jobs in a spreadsheet. Design the minimum viable LSA lead tracking system they need to support performance reporting and disputes."
