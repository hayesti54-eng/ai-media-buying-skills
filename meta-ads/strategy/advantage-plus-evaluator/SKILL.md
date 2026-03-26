# Advantage+ Campaign Evaluator

**Platform:** Meta Ads
**Category:** strategy
**Tier:** agency

## Purpose

Evaluate whether an advertiser's campaigns are appropriate candidates for Meta's Advantage+ automated campaign formats — specifically Advantage+ Shopping Campaigns (ASC) and Advantage+ Audience — and assess the performance and structural implications of adopting, expanding, or reverting from Advantage+ automation. Advantage+ is not universally superior to manual campaign structures; its value depends on account scale, data maturity, creative volume, and business type.

## When to Use

- When Meta recommends switching to Advantage+ Shopping Campaigns and the team needs to evaluate whether to accept
- When an existing Advantage+ campaign is underperforming vs. a manual structure
- When an account has sufficient scale to justify Advantage+ automation but has not yet adopted it
- When a client wants to reduce campaign management overhead without sacrificing performance control
- When transitioning from detailed audience targeting to Advantage+ Audience expansion
- When comparing Advantage+ Shopping Campaign performance against a standard conversion campaign running simultaneously
- When assessing how Advantage+ Creative automation is affecting creative performance data visibility

## Inputs Required

- Account monthly spend and monthly conversion volume
- Current campaign types in use: standard conversion campaigns, catalog campaigns, or existing Advantage+ campaigns
- Product catalog status: does the account have a Meta product catalog with all active products?
- Creative inventory: number of active creative assets available (ASC performs best with 10+ creative variations)
- Business type: DTC e-commerce, B2B, lead gen, app, or service-based
- Historical ROAS and CPA benchmarks: what has the manual structure been achieving?
- Customer segmentation needs: does the business require strict separation between new customer acquisition and retargeting?
- Reporting requirements: does the client require granular adset or audience-level performance breakdowns?

## What This Skill Does

This skill evaluates the account against Advantage+ adoption criteria, benchmarks current Advantage+ performance against manual structures, identifies Advantage+ capabilities that would benefit the account vs. limitations that would constrain it, and produces a clear recommendation on whether to adopt, expand, limit, or revert Advantage+ automation — with a specific implementation plan for the recommended path.

## Analysis Workflow

1. Assess account eligibility for Advantage+ Shopping Campaigns (ASC): ASC is available to e-commerce advertisers with an active product catalog. Confirm the catalog is connected, products are approved, and product feeds are up to date. ASC without a complete product catalog will default to landing page ads and lose catalog-level optimization.
2. Evaluate creative inventory: ASC's performance compounds with creative volume. The system tests combinations of images, videos, text, and catalog cards. With fewer than 10 creative assets, ASC's optimization advantage is limited. Assess whether the team can produce the creative volume ASC requires.
3. Evaluate the new customer acquisition constraint: ASC bundles prospecting and retargeting into a single campaign. Meta allocates budget between new and existing customers automatically. If the business needs strict control over new customer acquisition budget (e.g., tracking CAC separately from retention spend), ASC's bundled approach is a structural limitation.
4. Benchmark existing Advantage+ campaign performance: if ASC is already running, compare its ROAS and CPA against the manual conversion campaign for the same period and product set. A true comparison requires both campaigns running simultaneously on the same products, or historical period comparison with controlled variables.
5. Assess Advantage+ Audience adoption: Advantage+ Audience allows Meta to expand beyond the defined targeting parameters when it identifies conversion opportunities outside the defined audience. Evaluate the tradeoff: broader algorithmic reach vs. loss of audience-level performance segmentation data. For accounts that require demographic or interest-level performance visibility, Advantage+ Audience hides this data in the algorithm's black box.
6. Evaluate Advantage+ Creative: when enabled, Meta can automatically enhance creative assets with image crops, brightness adjustments, music addition, and text repositioning. Assess whether this automation aligns with brand standards and whether the creative enhancements Meta applies are acceptable.
7. For ASC specifically: assess the new customer budget cap setting. ASC allows advertisers to set a minimum percentage of budget for new customer acquisition. Default is no cap. Without setting a new customer budget minimum, ASC may over-index on retargeting (which is easier to convert) at the expense of prospecting.
8. Assess reporting depth requirements: ASC does not provide adset-level performance breakdowns or audience-level segmentation in the same way manual campaigns do. If a client requires granular performance data for strategic decisions, ASC's reporting limitations are a real constraint.
9. Evaluate the account's data maturity: ASC performs best in accounts with strong conversion signal history (1,000+ purchases in the last 30 days at the account level). In early-stage accounts with thin conversion data, the manual structure's ability to concentrate signal in fewer adsets may outperform ASC's broader optimization approach.
10. Produce a recommendation: adopt ASC fully, adopt ASC in parallel with manual structure (split test), adopt Advantage+ Audience only, or maintain manual structure with Advantage+ Creative enhancements only.

## Output Requirements

- Advantage+ readiness assessment: eligibility status, creative inventory gap, data maturity score
- ASC vs. manual performance comparison (if both are running or historical data is available)
- Capability matrix: Advantage+ features that would benefit this account vs. features that would constrain it
- New customer budget cap recommendation for ASC (if adopting)
- Reporting limitation assessment: what the team or client loses in data visibility by adopting Advantage+
- Recommendation: adopt / partial adopt / defer, with specific implementation plan

## Platform-Specific Best Practices

- ASC allocates budget between prospecting and retargeting automatically. The new customer budget minimum setting (found in ASC campaign settings) should be set to the percentage of budget needed for new acquisition goals. Default (uncapped) typically results in over-investment in retargeting.
- Meta's internal tests show ASC outperforms manual campaigns in accounts with high conversion volume and large creative libraries. For accounts with under 500 monthly conversions, the performance advantage is less consistent.
- Advantage+ Audience with a "suggested audience" still allows you to provide a seed audience as a starting signal. Setting a thoughtful seed audience (your best customer list) improves early algorithm efficiency vs. completely open targeting.
- Advantage+ Creative enhancements can be individually toggled on or off within the creative settings. You do not need to accept all enhancements or reject all of them — audit each enhancement type for brand alignment before enabling.
- Running ASC alongside a manual prospecting campaign targeting the same products creates auction overlap between your own campaigns. If testing ASC against manual, separate the product sets or use holdout groups to prevent self-competition.

## Guardrails

- Do not adopt ASC without setting a new customer acquisition budget minimum if new customer growth is a primary business objective.
- Do not turn off all manual campaigns immediately when adopting ASC. Run both for 4-6 weeks before making a full structural transition.
- Do not interpret ASC's lack of audience-level reporting as a campaign management simplification if the client requires demographic or interest-level performance accountability.
- Advantage+ does not eliminate the need for creative testing, EMQ optimization, or CAPI integrity. The automation layer optimizes delivery — the inputs (creative, signal) still require operator-level management.

## Example Requests

1. "Meta is recommending I switch my top-performing conversion campaign to Advantage+ Shopping. Should I do it, and what's the risk if I do?"
2. "I've been running ASC for 8 weeks and my ROAS is 2.1x vs. 3.4x on my manual campaign. Why is ASC underperforming and should I revert?"
3. "I want to adopt Advantage+ Audience but I'm worried about losing control over who sees my ads. Walk me through how to set it up in a way that gives me guardrails."
