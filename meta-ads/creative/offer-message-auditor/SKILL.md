# Offer-Message Alignment Auditor

**Platform:** Meta Ads
**Category:** creative
**Tier:** pro

## Purpose

Audit the alignment between the offer stated in an ad's creative and copy, and the experience delivered on the landing page. Message mismatch — where the ad promises something different from what the landing page delivers — is one of the most common causes of high CTR paired with low conversion rate. This skill diagnoses misalignment across offer, tone, visual continuity, CTA specificity, and social proof, and produces a fix list that closes the gap between ad promise and page delivery.

## When to Use

- When Outbound CTR is strong (above 1.5%) but conversion rate is weak (below expected benchmark)
- When landing page bounce rate is high relative to ad traffic quality
- When cost per landing page view is low but cost per result is disproportionately high
- When a new campaign is being launched and the landing page was not built specifically for the ad
- When running multiple ad angles pointing to the same landing page
- When a client or team member created the ad and landing page independently without coordination
- After a landing page redesign that may have changed the offer presentation

## Inputs Required

- Ad creative: image/video description or asset, primary text, headline, description
- Landing page URL and full page content: headline, subheadline, body copy, offer details, CTA, social proof elements, form or checkout fields
- Campaign objective: leads, purchases, app installs, or bookings
- Target audience and their likely prior knowledge of the brand
- Conversion goal: what specific action defines a successful visit

## What This Skill Does

This skill performs a systematic offer-message alignment audit across seven dimensions: offer clarity, offer specificity, headline continuity, visual tone continuity, CTA alignment, social proof positioning, and friction level. It identifies each dimension where the ad and landing page diverge, scores the severity of each misalignment, and produces a prioritized list of corrections with specific recommended copy or structural changes.

## Analysis Workflow

1. Read the ad creative and copy from the perspective of a first-time viewer. Identify the specific offer being made: what is promised, at what price or value, with what CTA. Write this as a single sentence: "The ad promises [offer] for [audience] with [CTA]."
2. Read the landing page from the same first-time viewer perspective. Identify what the page immediately communicates above the fold: headline, subheadline, primary image, and visible CTA. Write this as a single sentence: "The landing page delivers [offer] for [audience] with [CTA]."
3. Compare the two sentences. Identify any divergence in: offer description, price or value claim, audience targeting signal, and action being asked of the user. Score divergence as: No Gap, Minor Gap (nuance difference), Moderate Gap (different emphasis), Severe Gap (different offer or different product).
4. Audit headline continuity: the landing page headline should either directly mirror or logically continue the ad headline. If the ad headline says "Get Your Free HVAC Inspection" and the landing page headline says "Houston's Trusted HVAC Company Since 2001," that is a severe gap — the offer-specific language is lost.
5. Audit visual tone continuity: the visual style, color palette, and person/scenario shown in the ad should be reflected or consistent with the landing page imagery. A dark, premium-feeling ad driving to a low-quality, text-heavy page with stock photos creates cognitive dissonance that reduces conversion.
6. Audit CTA alignment: the specific CTA verb and outcome in the ad ("Book Your Free Inspection") must match the landing page form or button CTA exactly. Discrepancies in CTA specificity ("Contact Us") reduce conversion intent clarity.
7. Audit social proof positioning: if the ad references a testimonial, review count, or trust signal, the landing page should reinforce that same social proof above the fold. Users look for confirmation of the claims made in the ad.
8. Audit friction level: the ad's promise implies a level of commitment (free inspection = low commitment; schedule a call = medium commitment; purchase now = high commitment). If the landing page asks for more commitment than the ad implied, conversion rate will suffer.
9. Audit offer specificity: if the ad advertises a specific price, discount, or bonus, the landing page must make that exact offer visible within 5 seconds of landing — before any scroll. Hidden offers cause users to doubt whether the offer is real and bounce.
10. Produce a misalignment severity report and prioritized fix list.

## Output Requirements

- Alignment audit scorecard: seven dimensions, score per dimension (Aligned / Minor Gap / Moderate Gap / Severe Gap), specific evidence for each rating
- Overall alignment health score (0-100 scale)
- Prioritized fix list: ranked by estimated conversion rate impact, specific copy or structural recommendation for each
- Quick wins: fixes that can be implemented in under 30 minutes
- Structural changes: fixes that require landing page redesign or ad creative revision

## Platform-Specific Best Practices

- Message match is more important for cold traffic than warm traffic. Cold audiences have no brand familiarity — the landing page must immediately confirm they arrived at the right place for the right offer.
- For lead gen forms: Meta Lead Ads (on-platform forms) eliminate the landing page step entirely. When message match is a persistent problem, Meta Lead Ads can be a tactical fix — but they sacrifice landing page conversion optimization.
- For retargeting campaigns: the offer on the landing page should be differentiated from what the user already saw when they didn't convert. Showing the same page to a non-converter twice rarely improves conversion.
- For Advantage+ Creative: Meta may modify ad copy, headlines, and descriptions dynamically. Audit the most common served variant, not just your input defaults.
- Scarcity and urgency claims in ad copy ("Limited spots," "Sale ends Sunday") must be visibly enforced on the landing page. Fake urgency on the ad with no confirmation on the page destroys trust.

## Guardrails

- Do not recommend changes to the landing page that would reduce offer clarity in service of design aesthetics.
- Do not audit message match in isolation from conversion data. A high-alignment ad-page combination may still underperform due to offer-market fit issues unrelated to message match.
- Do not recommend identical copy between ad and landing page. Mirror principle means logical continuation, not verbatim repetition.

## Example Requests

1. "My ad CTR is 2.1% but my landing page conversion rate is 0.4%. The ad promises a free quote in 2 minutes but the landing page has a 9-field form. Is this a message match problem?"
2. "I'm running 4 different ad angles (price, speed, guarantee, reviews) all pointing to the same landing page. Audit whether one landing page can serve all four angles or if I need dedicated pages."
3. "My Facebook ad shows a smiling customer with a testimonial and a 'Start Free Trial' CTA but the landing page leads with product features and has a 'Get Started' button. Walk me through fixing this."
