# TikTok Funnel Drop-off Diagnostician

**Platform:** TikTok Ads
**Category:** funnel
**Tier:** pro

## Purpose
Diagnose the specific funnel stage where TikTok ad performance is leaking — from first impression through conversion event — by analyzing metric ratios at each funnel transition point, identifying the highest-leverage drop-off bottleneck, and producing a prioritized fix protocol that targets the actual constraint rather than symptoms. Most TikTok performance problems are localized to one funnel stage; this skill finds it.

## When to Use
- CPA is above target but you cannot identify whether the problem is in the creative, the click, or the post-click experience
- Multiple metrics are simultaneously underperforming and the root cause is unclear
- A new campaign is underperforming relative to benchmarks and you need to triage whether to fix creative, audience, landing page, or offer
- Comparing funnel efficiency across multiple campaigns or ad sets to identify where each is losing performance
- Building a performance diagnostic framework for a new client account that has never been systematically analyzed

## Inputs Required
- TikTok Ads Manager data: Impressions, 2-Second Video Views (thumbstop), Clicks, CTR, Spend, Conversions (TikTok-attributed), CPA
- Landing page analytics: sessions from TikTok (GA4 or equivalent), bounce rate, average session duration, conversion rate (GA4 goal completions or e-commerce purchases)
- Conversion event type: Purchase, Lead, App Install, Sign-Up
- TikTok Pixel event data if available: ViewContent, AddToCart, InitiateCheckout, Purchase (for e-commerce funnel depth)
- Campaign objective and bid strategy
- Creative format and audience targeting type

## What This Skill Does
This skill maps the TikTok ad funnel into five discrete transition stages, calculates the conversion rate at each stage, benchmarks each against TikTok platform norms and account-specific targets, identifies the single biggest drop-off bottleneck, and produces a focused diagnostic and fix protocol for that stage. It treats every other stage as context, not cause — preventing the common error of fixing the wrong funnel layer.

## Analysis Workflow
1. Define the five funnel stages and their transition metrics:
   - Stage 1 — Impression to Thumbstop: (2-Second Video Views / Impressions) = Thumbstop Rate. Target: 25–35% for conversion campaigns.
   - Stage 2 — Thumbstop to Full Engagement: (Video Views 75% or Average Watch Time Ratio) = Retention Rate. Target: 25–45% (varies by creative length).
   - Stage 3 — Engagement to Click: (Clicks / 2-Second Video Views) = Engaged Click Rate. Or use standard CTR (Clicks / Impressions): target 1–3% for cold conversion campaigns.
   - Stage 4 — Click to Landing Page Conversion: (Conversions / Clicks) = Post-Click CVR. Target: 2–8% for cold traffic e-commerce; 10–25% for lead gen with optimized landing page.
   - Stage 5 — Pixel Event Depth (e-commerce only): (InitiateCheckout or Purchase / ViewContent or AddToCart) = Checkout Funnel Rate.
2. Calculate the actual rate at each transition for the target campaign/creative.
3. Benchmark each rate against established norms:
   - Below 15% thumbstop: critical creative hook failure
   - Below 15% retention (watch time ratio): creative body failure
   - Below 0.5% CTR: creative desire/relevance failure
   - Below 2% post-click CVR: landing page, offer, or audience mismatch
   - Below 10% checkout initiation: pricing, trust, or UX failure
4. Apply the Constraint Identification Rule: identify the single funnel stage with the largest absolute gap between actual rate and benchmark. This is the Primary Constraint. All other stages are secondary.
5. Diagnose the Primary Constraint. For each stage, run the specific diagnosis:
   - Stage 1 failure (Thumbstop): hook mechanics, visual opening, first-frame content — refer to Hook Rate Analyzer protocol
   - Stage 2 failure (Retention): creative pacing, body relevance, secondary hook absence — refer to Hold Rate Analyzer protocol
   - Stage 3 failure (Click): CTA delivery, desire building, offer clarity, urgency element
   - Stage 4 failure (Post-Click CVR): landing page message match, mobile load speed, offer friction, form fields
   - Stage 5 failure (Checkout): pricing display, checkout trust signals, cart abandonment triggers
6. Rule out compounding factors: if two stages are both below benchmark but close to each other, identify which stage feeds the other (fixing Stage 1 will automatically improve Stage 3 volume, but not Stage 3 rate).
7. Produce the Primary Constraint Fix Protocol: 3–5 specific, prioritized actions targeting the identified bottleneck stage.
8. Document secondary constraints for future optimization cycles after the primary is resolved.

## Output Requirements
- Five-stage funnel table: Stage Name, Transition Metric, Current Rate, Benchmark Rate, Gap, Status (Pass/Fail)
- Primary Constraint identification with supporting rate gap evidence
- Root cause diagnosis for Primary Constraint with 2–3 specific hypotheses
- Primary Constraint Fix Protocol: ordered action list with expected impact and implementation difficulty
- Secondary constraint documentation: which other stages will need attention after primary is resolved
- Funnel efficiency score: composite index of all five stage rates vs. benchmarks
- Before/after projection: if the Primary Constraint is fixed to benchmark rate, what is the projected CPA improvement?

## Platform-Specific Best Practices
- The most common TikTok funnel mistake is attributing a Stage 4 (post-click) problem to a Stage 1 (hook) problem. CTR can be low because the hook fails to drive click intent (Stage 3) or because the landing page is known to be poor (Stage 4 feedback affects Stage 3 behavior). Separate these diagnoses carefully.
- TikTok traffic lands on mobile pages with high impatience. A 3-second page load adds significant friction at Stage 4. Mobile landing page speed is a frequently overlooked Stage 4 lever.
- For e-commerce campaigns, the TikTok Pixel's AddToCart and InitiateCheckout events provide critical Stage 5 data that TikTok Ads Manager does not expose by default. Setting up these intermediate pixel events dramatically improves funnel diagnostic precision.
- Watch time funnel (Stage 2) is the leading indicator of Stage 3 performance. Improving average watch time by even 20% consistently improves CTR because deeper engagement drives higher purchase intent before the CTA appears.
- On TikTok, the CTA button click and the landing page visit count can diverge significantly due to mobile redirect friction, popup blockers, and network issues. Use GA4 sessions (not just TikTok-reported clicks) for Stage 4 diagnosis.

## Guardrails
- Do not attempt to fix multiple funnel stages simultaneously — always resolve the Primary Constraint first and re-measure before addressing secondary stages.
- Do not diagnose Stage 4 problems from TikTok Ads Manager data alone — always cross-reference with landing page analytics from GA4 or equivalent.
- Do not assume a low CTR is always a Stage 3 (CTA) problem — trace the CTR calculation back to thumbstop rate to determine whether volume entering Stage 3 was sufficient.
- Never prescribe a landing page rebuild without first verifying that Stage 1–3 rates are above benchmark — a perfect landing page cannot save a creative that fails to generate qualified click intent.

## Example Requests
1. "My TikTok campaign has a 2.1% CTR but only a 1.2% post-click conversion rate. My CPA is $95 against a $45 target. Map my full funnel, find the biggest drop-off, and tell me exactly where to focus first."
2. "I have two campaigns with similar spend and CTR but very different CPAs. Walk me through a funnel comparison to identify what stage is different between them and why."
3. "I'm running a lead gen campaign with a TikTok Instant Form. How do I map the funnel for an in-app form versus a landing page destination, and which stage is most likely to be causing my high CPL?"
