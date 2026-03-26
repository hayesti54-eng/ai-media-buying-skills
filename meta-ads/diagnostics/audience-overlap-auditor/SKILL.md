# Audience Overlap Auditor

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Identify and quantify audience overlap between adsets, campaigns, and custom audiences within a Meta Ads account. Auction Overlap causes adsets to compete against each other in the same auction, fragmenting delivery, inflating costs, preventing learning phase exit, and producing misleading performance comparisons between adsets. This skill diagnoses overlap severity, identifies the specific adset pairs causing it, and produces a restructuring recommendation.

## When to Use

- When multiple adsets targeting similar audiences show inconsistent or volatile delivery
- When CPMs are higher than expected for the audience type and market
- When adsets appear to cannibalize each other's delivery (one scales, others flatten)
- Before launching a new campaign to audit for structural overlap with existing live campaigns
- After adding new audiences (Lookalikes, interest stacks) to an existing account structure
- When reviewing a new client's account and auditing for structural inefficiencies
- When consolidating from a high-volume adset structure down to a more efficient architecture

## Inputs Required

- Full list of active adsets and their targeting definitions: custom audiences, Lookalike audiences, interest/behavior targeting, geo targeting, age/gender targeting
- Audience Overlap tool access in Ads Manager (Audiences section)
- Number of active campaigns targeting the same conversion objective
- Budget allocation across adsets
- Whether Campaign Budget Optimization (CBO) is in use
- Retargeting audience definitions: website visitors, video viewers, customer lists

## What This Skill Does

This skill maps all audience definitions across active adsets and campaigns, uses Meta's Audience Overlap tool to quantify overlap percentages between specific audience pairs, identifies the highest-severity overlap pairs, and determines whether the overlap is causing auction competition. It distinguishes between benign overlap (different placements, time-sequenced retargeting) and damaging overlap (same auction, same placement, competing bids) and produces a prioritized fix plan.

## Analysis Workflow

1. Export all active adsets with their targeting settings. Create a targeting matrix listing: campaign name, adset name, audience type (cold/warm/hot), geo, age, gender, custom audience or Lookalike name, interest/behavior stack.
2. Navigate to Ads Manager → Audiences → select the first audience → click "Show Audience Overlap" → select comparison audiences one at a time. Record overlap percentage for each pair.
3. Flag pairs with overlap above 20% as a concern. Flag pairs with overlap above 40% as high-severity. Overlap above 60% between two active adsets competing in the same auction is a structural failure.
4. Identify whether overlapping adsets share the same optimization objective and campaign. Two adsets in the same CBO campaign with high overlap are less damaging than two adsets in separate campaigns with separate budgets, because CBO's internal delivery system manages some of the competition. Two separate campaigns targeting the same audience have no such protection.
5. Check for Lookalike overlap: a 1% Lookalike (LAL) is a subset of a 2% LAL, which is a subset of a 5% LAL. Running all three simultaneously in separate adsets creates 100% overlap of the smaller audience within the larger. The correct structure is either exclusion or sequential testing, not simultaneous targeting.
6. Audit retargeting audience stacking: if a 180-day website visitor audience and a 90-day website visitor audience are both active in separate adsets, the 90-day audience is 100% overlapping with the 180-day audience. Users in the 90-day window will be targeted by both adsets simultaneously.
7. Check for customer list overlap: if multiple custom audiences derived from CRM uploads contain the same email addresses (e.g., "all customers" vs. "30-day purchasers"), adsets targeting these will have significant overlap for the same users.
8. Assess whether exclusions are in place: cold prospecting adsets should exclude all website visitors (30+ days), all customer lists, and all warm audiences to prevent overlap with retargeting campaigns.
9. For each high-severity overlap pair, evaluate the correct fix: audience consolidation, exclusion layers, Lookalike stacking replacement with a single broader LAL, or campaign structure redesign.
10. Produce an overlap severity map and ranked fix list.

## Output Requirements

- Overlap matrix: adset pairs with overlap percentage and severity rating (low/medium/high/critical)
- Auction competition assessment: which overlapping pairs are competing in the same auction
- Specific exclusion recommendations per adset
- Lookalike stacking restructure plan if applicable
- Retargeting audience hierarchy redesign if time-window stacking is present
- Net estimated impact on CPM and delivery stability from fixing each overlap issue

## Platform-Specific Best Practices

- Meta's Audience Overlap tool shows the overlap between two defined audiences, not between live adsets. Use it as a proxy, not a definitive auction-level measure.
- Advantage+ Audiences and Broad targeting (no defined audience) inherently overlap with everything. If running Advantage+ audience adsets alongside defined-audience adsets targeting the same users, the Advantage+ adset will typically win the auction due to higher algorithmic confidence.
- CBO does not eliminate overlap-driven cost inflation. It only prevents self-competition within a single campaign's adsets. Cross-campaign overlap is not managed by CBO.
- When using interest-based targeting, broad interest categories (e.g., "fitness") overlap heavily across adsets. If you must use interest stacking, use exclusion lists to create mutually exclusive adsets.
- Lookalike audiences from different seed audiences (email list vs. pixel visitors) can still have significant overlap if the seed audiences themselves overlap.

## Guardrails

- Do not eliminate all segmentation in the name of overlap reduction. Some overlap is acceptable and serves legitimate strategic purposes (e.g., retargeting users who are also in a Lookalike).
- Do not use the Audience Overlap tool output as the sole basis for campaign restructuring. Confirm with delivery data — high overlap with no delivery competition may not require action.
- Audience exclusions add complexity. Apply exclusions only where overlap is causing measurable delivery or performance problems.

## Example Requests

1. "I'm running a 1%, 2%, and 5% Lookalike audience in three separate adsets in the same campaign. My 2% and 5% adsets have almost no delivery. Is overlap the reason and how do I fix it?"
2. "I have cold prospecting and retargeting campaigns both running to US audiences. How do I audit whether my retargeting audiences are bleeding into my cold prospecting adsets?"
3. "My client has 8 active campaigns all targeting women 25-45 interested in wellness products in the US. Walk me through auditing for auction overlap before I rebuild their account structure."
