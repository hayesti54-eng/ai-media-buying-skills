# CAPI Diagnostics — Conversion Signal Integrity Auditor

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Diagnose the health, completeness, and deduplication accuracy of Conversions API (CAPI) implementation. Ensure that server-side event signals are reaching Meta with sufficient match quality, proper deduplication against browser pixel events, and no signal loss that would degrade campaign optimization, bidding accuracy, or attribution reporting.

## When to Use

- After initial CAPI implementation to confirm signal parity with pixel
- When ROAS or conversion volume drops without a corresponding drop in actual business results
- When Events Manager shows a high percentage of browser-only events or server-only events
- When deduplication warnings appear in Events Manager
- Before launching or scaling campaigns that rely on purchase, lead, or add-to-cart optimization
- During post-iOS 14.5 audits to ensure AEM-compatible signal coverage
- When cost per result rises unexpectedly and learning phase keeps resetting

## Inputs Required

- Access to Events Manager for the relevant pixel/dataset
- CAPI integration method (direct API, partner integration, GTM server-side, or CDP)
- Event volume comparison: browser pixel vs. server CAPI for each standard event
- Deduplication key being used: `event_id` match rate confirmation
- Customer information parameters being passed: email, phone, first name, last name, city, state, zip, country, external ID, client IP, client user agent, click ID (fbclid), browser ID (fbp), cookie ID (fbc)
- Time window for analysis: minimum 7 days, 14 days preferred
- List of all standard events being fired (PageView, ViewContent, AddToCart, InitiateCheckout, Purchase, Lead, CompleteRegistration)

## What This Skill Does

This skill audits the end-to-end conversion signal pipeline from browser pixel through CAPI, evaluating deduplication fidelity, customer information parameter completeness, event timing accuracy, and Event Match Quality (EMQ) scores per event type. It identifies gaps that cause Meta's algorithm to under-optimize, surfaces deduplication failure modes that inflate reported conversions, and produces a prioritized fix list ranked by impact on bidding signal quality.

## Analysis Workflow

1. Open Events Manager → select the dataset → navigate to the Overview tab. Record the 7-day and 30-day event counts per event type broken down by source (browser, server, partner).
2. Check the deduplication rate for each event. Navigate to Events Manager → Event Deduplication. Flag any event with a deduplication rate below 95% or above 105% (over-deduplication is also a problem).
3. Pull the Event Match Quality (EMQ) score for each server event. Flag any event scoring below 6.0 as a priority fix. Note which customer information parameters are contributing to the score.
4. Identify which customer information parameters are present vs. absent in server calls. Rank parameters by EMQ contribution: email (hashed) and phone (hashed) have the highest weight. Confirm that `fbp`, `fbc`, and `client_user_agent` are being passed on every server event.
5. Audit event timing: compare the timestamp on server events vs. browser events for the same user session. Server events arriving more than 15 minutes after the browser event indicate pipeline latency that can disrupt deduplication.
6. Check the `event_id` format for consistency. The same `event_id` must be passed in both the browser Pixel and the CAPI call for deduplication to work. Inconsistent formats (UUID vs. timestamp strings) cause deduplication failures.
7. Verify that the fbclid (click ID from Meta ads click) is being captured and passed through to server events. Loss of fbclid degrades attribution accuracy and reduces EMQ for click-based events.
8. Review for signal redundancy: confirm that non-deduplicated duplicate events from partner integrations (e.g., Shopify + direct CAPI) are not inflating reported conversion volume.
9. Document findings in a signal integrity scorecard: event name, source split %, deduplication rate, EMQ score, missing parameters, estimated impact on bidding signal.

## Output Requirements

- Signal integrity scorecard table: one row per event type
- Deduplication status per event: pass / warning / fail with threshold explanation
- EMQ score per event with specific missing parameters called out
- Prioritized fix list: ranked by estimated impact on optimization quality
- Estimated percentage of conversions being lost due to signal gaps
- Summary verdict: CAPI implementation health (Healthy / Degraded / Critical)

## Platform-Specific Best Practices

- Always hash PII (email, phone, name) using SHA-256 before sending to CAPI. Passing plain text will cause event rejection.
- Pass `fbp` (Meta browser pixel cookie) from the browser to your server on every event. This is the single highest-impact parameter for server-side EMQ improvement.
- Use a consistent UUID v4 format for `event_id` across both browser and server. Generate it client-side and pass it to the server.
- CAPI events should fire within 1 second to 5 minutes of the corresponding browser pixel event for reliable deduplication.
- If using a partner integration (Shopify, WooCommerce, Segment), audit whether the partner is passing all available customer parameters or only the minimum required.
- For lead gen businesses, fire a Lead event server-side upon CRM confirmation, not just on form submit, to improve signal quality tied to actual qualified leads.

## Guardrails

- Do not disable the browser pixel while CAPI is being tested. Signal redundancy with deduplication is the correct operating model.
- Never pass raw (unhashed) PII to CAPI, regardless of claimed encryption at transport layer.
- Do not over-fire events: sending the same event 3+ times for a single user action inflates conversion reporting and distorts bidding.
- CAPI does not replace AEM domain verification. Both are required post-iOS 14.5 for web conversion campaigns targeting iOS users.

## Example Requests

1. "My Events Manager shows Purchase events are 60% browser and 40% server but deduplication is only 78%. Walk me through diagnosing where deduplication is breaking down."
2. "My CAPI is live but my EMQ scores for Lead events are showing 4.2. What parameters am I likely missing and how do I fix them?"
3. "I switched from Shopify's built-in CAPI integration to a direct API implementation. How do I verify there's no signal loss or double-counting in the transition?"
