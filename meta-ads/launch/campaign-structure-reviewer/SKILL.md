# Campaign Structure Reviewer

**Platform:** Meta Ads
**Category:** launch
**Tier:** agency

## Purpose

Audit an entire Meta Ads account's campaign structure against operational best practices for scalability, learning efficiency, budget control, and attribution clarity. Poor campaign structure — over-segmentation, misaligned objectives, mixed funnel stages in the same campaign, and conflicting bid strategies — causes systemic underperformance that cannot be fixed by creative or audience changes alone. This skill produces a structural diagnosis and redesign blueprint.

## When to Use

- When onboarding a new client account and conducting an initial audit
- When account performance has plateaued and campaign-level changes aren't moving the needle
- When the account has accumulated more than 20 active adsets without a documented consolidation strategy
- Before a significant budget increase that would expose structural weaknesses
- When multiple team members have built campaigns in the same account without a unified architecture
- When preparing to pitch a new structure to a client who inherited an account from a previous agency
- When migrating from an ABO (Ad Set Budget Optimization) structure to CBO (Campaign Budget Optimization)

## Inputs Required

- Full account campaign list: campaign names, objectives, bid strategies, budget types, budget amounts, delivery status
- Adset list per campaign: audience type, targeting definition, optimization event, budget, delivery status
- Ad list per adset: creative type, approval status, performance summary
- Account conversion volume: total weekly conversions across all campaigns
- Attribution window in use per campaign
- Whether CBO or ABO is in use and per which campaigns
- Business funnel stages: awareness, consideration, conversion, retention

## What This Skill Does

This skill audits account structure across six dimensions: objective alignment, funnel stage separation, campaign budget management, adset segmentation efficiency, learning phase capacity, and cross-campaign audience conflict. It produces a structural health score, identifies the highest-impact structural problems, and delivers a redesign blueprint specifying exactly how campaigns, adsets, and budget should be reorganized for maximum efficiency and scalability.

## Analysis Workflow

1. Map all campaigns to business funnel stages (awareness / consideration / conversion / retention) and verify that each campaign uses the appropriate objective for its stage. Traffic-objective campaigns in the conversion stage are structural misalignments. Engagement campaigns used as conversion vehicles are a red flag.
2. Count total active adsets across the account. Divide this by the account's weekly conversion volume. The ratio of conversions per adset should be at least 7 (50 conversions/week ÷ 7 days minimum), ideally above 14. An account with 25 adsets and 100 weekly conversions is structurally over-segmented.
3. Audit budget management approach: identify all campaigns using CBO vs. ABO. CBO is the current Meta-recommended approach for most accounts. ABO should only be used for testing specific audiences against each other with equal budget, or for protecting specific high-performing adsets from algorithm underspending.
4. Evaluate campaign naming conventions for operational clarity. Campaigns without clear naming that identifies objective, funnel stage, audience type, and launch date create operational debt that accumulates over time. Flag accounts with inconsistent naming conventions.
5. Audit for cross-campaign audience conflict: identify campaigns with overlapping audience definitions that are not intentionally sequenced. Prospecting campaigns targeting the same audience as retargeting campaigns (without proper exclusions) are a structural deficiency.
6. Assess bid strategy consistency within campaigns. In a CBO campaign, all adsets inherit the campaign's bid strategy. Mixed bid strategy intent (some adsets needing Cost Cap, others needing Lowest Cost) cannot be achieved within a single campaign — this requires campaign separation.
7. Evaluate adset count per campaign relative to CBO's ability to optimize. CBO campaigns with more than 8-10 adsets often result in adset starvation — the algorithm concentrates budget in 2-3 adsets and systematically underspends the rest, creating a false impression of poor performance for under-budgeted adsets.
8. Review the always-on vs. test structure: distinguish campaigns that are part of the permanent account structure (always-on prospecting, always-on retargeting) from test campaigns. Test campaigns should be time-bounded with documented hypotheses. Accounts where tests are never turned off accumulate structural debt.
9. Identify the optimal consolidated structure: how many campaigns are needed, what objectives, what adset count per campaign, and what budget allocation between funnel stages. The optimal structure is the minimum number of campaigns needed to achieve the account's business goals without sacrificing funnel coverage.
10. Produce a current-state assessment and a recommended target-state structure with a migration plan.

## Output Requirements

- Campaign structure health score (0-100) across six dimensions
- Current-state account map: campaigns, adsets, budgets, objectives — visual or tabular
- Structural deficiency list: each issue, severity, and estimated performance impact
- Target-state blueprint: recommended campaign count, adset count, budget allocation, naming convention
- Migration plan: sequence of changes to move from current state to target state without triggering unnecessary learning resets
- Risk assessment: which structural changes require a full learning reset vs. which can be made incrementally

## Platform-Specific Best Practices

- The Simplified Account Structure approach Meta recommends uses broad audiences, fewer adsets, CBO, and Advantage+ Audience as the operating model for most accounts. This is the direction Meta's algorithm is optimized for.
- For most direct response accounts, a 3-campaign structure covers 80% of needs: (1) Advantage+ Shopping Campaign or broad prospecting CBO, (2) Warm audience retargeting CBO, (3) Customer retention/upsell.
- Always-on campaigns should be separated from test campaigns in naming and budget allocation. Test campaigns should have a fixed budget ceiling and a defined end date.
- When migrating from ABO to CBO, expect a 1-2 week learning adjustment period as the algorithm redistributes budget across adsets under the new budget control system.
- Account spending level affects optimal structure. At under $5,000/month, 2-3 campaigns with 2-4 adsets total is the right scale. At $50,000+/month, more segmentation is justified but each adset must still meet the 50 conversions/week threshold.

## Guardrails

- Do not restructure an account during a peak business period (Black Friday, holiday season, major product launch). Run the audit, build the plan, and implement during a lower-stakes period.
- Do not consolidate audiences that have materially different conversion profiles into the same adset just to reach conversion volume thresholds.
- Do not migrate from ABO to CBO for all campaigns simultaneously. Migrate one campaign at a time and monitor learning phase recovery before proceeding.

## Example Requests

1. "I just took over a client account with 47 active adsets across 12 campaigns, spending $18K/month and getting 180 purchases/week. Audit the structure and tell me what to consolidate."
2. "My account uses ABO for all campaigns. Meta keeps recommending I switch to CBO. Walk me through when to make the switch and how to do it without crashing performance."
3. "I'm building a Meta account from scratch for a DTC e-commerce brand at $8K/month. Design the optimal campaign structure from the ground up."
