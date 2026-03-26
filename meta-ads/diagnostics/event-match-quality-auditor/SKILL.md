# Event Match Quality Auditor

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Evaluate and improve Event Match Quality (EMQ) scores across all pixel and CAPI events to maximize Meta's ability to match conversion events to real user profiles in the Meta identity graph. Higher EMQ directly improves conversion attribution accuracy, bidding signal quality, learning phase stability, and cost efficiency — especially in post-iOS 14.5 environments where browser-based identity signals are degraded.

## When to Use

- When CPL or CPA is rising without a clear creative or audience explanation
- When EMQ scores in Events Manager drop below 7.0 for any key optimization event
- Before launching a new campaign to confirm signal quality meets Meta's optimization threshold
- After a site migration, CRM swap, checkout redesign, or pixel reinstall
- When the learning phase is resetting frequently on adsets with sufficient budget
- When Meta's delivery system is indicating "Learning Limited" and budget is not the issue
- When auditing a new client account for signal infrastructure quality

## Inputs Required

- Events Manager access with at least 7 days of data
- Current EMQ score per event (visible in Events Manager under each event's diagnostics)
- Current parameter list being sent: email (em), phone (ph), first name (fn), last name (ln), city (ct), state (st), zip (zp), country (country), date of birth (db), gender (ge), external ID (external_id), click ID (fbc), browser cookie (fbp), client IP, client user agent
- Whether data is coming from browser pixel, CAPI, or both
- Integration method: direct code, tag manager, partner platform, or CDP
- Business type: ecommerce, lead gen, app, or offline

## What This Skill Does

This skill audits each event's EMQ score, identifies the specific customer information parameters that are absent or improperly formatted, calculates the potential EMQ lift from each parameter addition, and produces a prioritized remediation plan. It accounts for business-type constraints (B2B lead gen vs. ecommerce) and integration method to recommend technically feasible improvements with the highest impact on match rate.

## Analysis Workflow

1. Navigate to Events Manager → select the dataset → click on a specific event → open the "Parameters" tab. Record the current EMQ score and the parameter contribution breakdown (shown as green, yellow, or red indicators per parameter).
2. Identify which parameters are completely absent. Separate parameters into three buckets: identity-grade (email, phone, external_id), location-grade (city, state, zip, country), and session-grade (fbp, fbc, client_user_agent, client_ip_address).
3. For each absent identity-grade parameter, assess feasibility: Is the user logged in at time of event? Is the parameter available in the CRM? Is the checkout flow collecting it?
4. Verify hashing format: email and phone must be SHA-256 hashed, lowercase, trimmed of whitespace. Phone must be in E.164 format before hashing (+1XXXXXXXXXX). Name fields must be lowercase, no punctuation before hashing.
5. Check that `fbp` (Meta pixel first-party cookie, format: `fb.1.{timestamp}.{random}`) is being read from the browser and passed to the server on every CAPI event. This is the highest single-parameter EMQ lever for server-side events.
6. Check that `fbc` (click ID cookie, derived from fbclid URL parameter) is being captured from the landing page URL and persisted through checkout. Loss of fbc breaks click-level attribution for paid traffic.
7. For ecommerce: confirm that `external_id` (your internal customer/order ID) is being passed consistently across all events for the same user session. This enables cross-event stitching even when PII is unavailable.
8. For lead gen: confirm that the Lead event is firing post-form-submit with at minimum email, phone (if collected), first name, and last name from the form fields in real time — not batch-processed later.
9. Estimate the EMQ improvement for each parameter addition. Email typically contributes 2-3 EMQ points; phone 1-2 points; fbp 1-2 points; name/location fields 0.3-0.7 points each.
10. Produce a ranked fix list by estimated EMQ lift per parameter, grouped by implementation complexity (low/medium/high).

## Output Requirements

- EMQ score table per event: current score, target score, gap
- Parameter presence matrix: which parameters are present, absent, or malformed per event
- Ranked fix list: parameter name, estimated EMQ lift, implementation complexity, and specific technical action required
- Estimated attribution improvement from full implementation
- Summary status per event: Excellent (8+), Good (6-7.9), Needs Improvement (4-5.9), Critical (<4)

## Platform-Specific Best Practices

- EMQ scores of 7.0 and above are the operating target for campaigns optimizing toward purchase, lead, or any downstream event.
- The combination of hashed email + fbp cookie typically yields the largest single EMQ improvement for server-side events.
- Do not normalize or modify email/phone values after SHA-256 hashing. The hash must match exactly what Meta expects from its own user profile matching.
- For Shopify stores: the Shopify CAPI integration does not pass all available parameters by default. Supplement with a custom CAPI implementation or a trusted partner app that passes `fbp`, `fbc`, and complete customer PII.
- If your business collects phone at checkout, that alone can improve EMQ by 1.5-2 points. Make phone collection a growth lever, not just a UX decision.
- Multiple matching signals compound: an event with email + phone + fbp + fbc will always outperform one with only email.

## Guardrails

- Never pass un-hashed PII to Meta's CAPI endpoint, regardless of HTTPS encryption in transit.
- Do not attempt to improve EMQ by fabricating or inferring parameters that were not explicitly provided by the user (e.g., guessing email from a username).
- EMQ improvements do not retroactively fix past attribution gaps. Changes take effect on new events going forward.
- High EMQ does not guarantee accurate attribution in all cases — it improves probability of match, not certainty.

## Example Requests

1. "My Purchase event EMQ is 5.8. I'm sending email and city/state/zip but nothing else. What's my fastest path to getting above 7.0?"
2. "I'm a B2B lead gen advertiser and most of my form fills don't include phone. How do I improve EMQ when I only have email, first name, and last name?"
3. "We just migrated our checkout from Shopify to a custom platform. Walk me through auditing our new CAPI implementation to make sure EMQ isn't degrading."
