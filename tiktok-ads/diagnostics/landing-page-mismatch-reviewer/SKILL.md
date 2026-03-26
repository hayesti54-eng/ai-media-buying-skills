# Landing Page–Ad Mismatch Reviewer

**Platform:** TikTok Ads
**Category:** diagnostics
**Tier:** pro

## Purpose
Audit the alignment between TikTok ad creatives and their destination landing pages, identify messaging, tone, visual, and offer discontinuities that are causing post-click drop-off, and produce a detailed fix list that restores message match and conversion continuity from the FYP scroll to the conversion event.

## When to Use
- Click-through rate is healthy but conversion rate (visit-to-lead or visit-to-purchase) is underperforming
- CPA is high relative to industry benchmarks despite strong creative-level metrics (hook rate, CTR, watch time)
- Landing page bounce rate is above 70% from TikTok traffic specifically
- Launching a new creative campaign against an existing landing page and want to pre-validate message alignment before spending
- Creative and landing page were built by separate teams with no intentional message handoff

## Inputs Required
- Ad creative description or script (paste full script or describe the hook, body, CTA, and offer presented in the ad)
- Landing page URL or full landing page content (headline, subheadline, hero section, offer details, CTA button copy, social proof, form fields if applicable)
- Campaign objective and conversion event type (Purchase, Lead, App Install, Sign-Up)
- Target audience and awareness stage (cold traffic, warm retargeting, existing customer)
- Any known post-click metrics: landing page bounce rate (from GA4 or TikTok Pixel), average time on page, scroll depth, conversion rate

## What This Skill Does
This skill performs a six-dimension message match audit between the TikTok ad and the landing page: (1) Offer Continuity, (2) Tone and Energy Match, (3) Visual Language Alignment, (4) CTA Continuity, (5) Audience Expectation Match, (6) Speed and Friction Assessment. It scores each dimension, identifies the highest-impact mismatches, and produces a prioritized fix brief with specific copy, layout, and CTA recommendations for both the ad and the landing page.

## Analysis Workflow
1. Extract the ad's core promise. Identify the exact offer stated in the ad: what the viewer is told they will get, how, and for what cost or commitment. This is the "ad contract."
2. Audit Dimension 1 — Offer Continuity: Does the landing page headline immediately restate or reinforce the offer made in the ad? If the ad promises "free trial" and the landing page headline leads with brand story, that is a critical mismatch. Score: Pass / Partial / Fail.
3. Audit Dimension 2 — Tone and Energy Match: TikTok ad creatives are typically fast-paced, informal, creator-style. If the landing page is corporate, formal, or static, there is a jarring tone discontinuity. Native-feel TikTok ads need landing pages with similar energy: short paragraphs, casual language, bold statements. Score each.
4. Audit Dimension 3 — Visual Language Alignment: Does the landing page hero image or video match the aesthetic of the TikTok ad? Color scheme, spokesperson appearance, lifestyle imagery — mismatches here create subconscious distrust. Score.
5. Audit Dimension 4 — CTA Continuity: What action did the ad tell the viewer to take? What does the landing page CTA button say? If the ad says "Shop now for 30% off" but the landing page CTA says "Learn More," there is a commitment level mismatch. Score.
6. Audit Dimension 5 — Audience Expectation Match: TikTok cold traffic audiences arrive with minimal brand awareness. Does the landing page assume prior knowledge, brand familiarity, or trust that cold traffic does not have? Flag any copy that relies on established brand equity.
7. Audit Dimension 6 — Speed and Friction: Landing page load speed on mobile is critical for TikTok traffic (mobile-first by default). Flag any page with more than 3 form fields for cold traffic lead gen, intrusive pop-ups that fire before 5 seconds, or redirect chains.
8. Score all six dimensions. Identify the top 2–3 mismatches by impact on conversion rate.
9. Produce fix brief: for each critical mismatch, write specific recommended copy edits, layout changes, and CTA updates for both the ad and the landing page.

## Output Requirements
- Six-dimension message match scorecard with Pass / Partial / Fail per dimension
- Impact-ranked list of mismatches (highest conversion impact first)
- Specific copy rewrites for landing page headline, subheadline, and CTA button where mismatches are identified
- Ad-side fixes if the creative is making promises the landing page cannot fulfill
- Landing page structure recommendations for TikTok cold traffic: fold structure, trust element placement, form field reduction guidance
- Before/after comparison table: current ad promise vs. current landing page response vs. recommended alignment

## Platform-Specific Best Practices
- TikTok traffic is almost entirely mobile. Landing pages must load under 3 seconds on mobile — every second of delay reduces conversion rate by approximately 7% for e-commerce and lead gen.
- The TikTok FYP context creates a high-stimulus entry state. Landing pages that open with slow, text-heavy content immediately contrast with the energy the viewer just left. Use bold hero headlines, short punchy copy, and a single clear CTA above the fold.
- For Spark Ads that use creator-style video, the landing page should ideally feature the same creator, voice, or visual language to maintain the personal relationship established in the ad.
- Advertorial-style landing pages (written in the voice of a story or recommendation, rather than a traditional ad) significantly improve TikTok-to-conversion rates for cold traffic because they match the content consumption behavior of the FYP.
- For lead gen campaigns, native TikTok Instant Forms (TikTok Lead Gen objective) almost always outperform external landing pages for cold audiences because they eliminate the transition entirely.

## Guardrails
- Do not recommend landing page overhauls without identifying the single highest-impact fix first — implement and measure one major change at a time.
- Do not assume a landing page that converts well from Google or Meta traffic will work for TikTok — the audience entry state and device context are fundamentally different.
- Do not make ad-side changes to fix a landing page problem — address each side independently.
- Never recommend adding more content or longer copy to a TikTok landing page as a fix — the direction is almost always toward simplification and faster value delivery.

## Example Requests
1. "My TikTok CTR is 2.1% but my landing page conversion rate is only 1.8%. Here's my ad script and landing page content — tell me exactly where the message breaks down."
2. "I built a TikTok UGC ad with a creator talking about our skincare product in a casual, personal way. But our landing page is full corporate. Audit the mismatch and tell me how to fix it."
3. "I'm about to launch a new campaign with a cold traffic hook about a limited-time offer. The landing page is our standard homepage. Should I build a new page, and what should it say?"
