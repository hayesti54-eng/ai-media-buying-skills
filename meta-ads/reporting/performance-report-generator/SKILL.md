# Meta Ads Performance Report Generator

**Platform:** Meta Ads
**Category:** reporting
**Tier:** pro

## Purpose

Generate structured, insight-driven performance reports for Meta Ads campaigns that go beyond raw metric recaps to deliver diagnosed findings, trend analysis, and prioritized recommendations. A report built by this skill tells the reader what is happening, why it is happening, and what to do next — not just what the numbers are.

## When to Use

- For weekly campaign performance reviews
- For monthly client reports requiring professional narrative alongside data
- After a major campaign test, creative launch, or bid strategy change
- For end-of-quarter performance summaries with strategic recommendations
- When a client or internal stakeholder needs a non-technical performance overview
- When preparing for a strategy session and needing a clear picture of account health before making decisions
- For new client onboarding audits where historical account performance must be synthesized

## Inputs Required

- Campaign performance data from Ads Manager: impressions, reach, frequency, CPM, CPC (all), Outbound CPC, CTR (all), Outbound CTR, landing page views, cost per result, ROAS, total spend, results — per campaign, adset, and ad
- Reporting time window: specific date range
- Business KPIs: target CPA or ROAS, monthly budget, revenue goal
- Comparison period: prior week, prior month, or prior year equivalent
- Attribution window in use: 7-day click + 1-day view is Meta's default
- Breakdown preferences: by campaign, adset, ad, age/gender, placement, device
- Context: any external factors during the reporting period (sale events, seasonality, creative changes, audience changes)

## What This Skill Does

This skill structures raw campaign data into a layered performance narrative: executive summary (3-sentence verdict), campaign-level highlights (what moved and why), adset-level diagnosis (which audiences are efficient and which are draining budget), ad-level creative performance (which creatives are carrying the account and which are fatigued), and a forward-looking recommendations section with specific next steps ranked by priority.

## Analysis Workflow

1. Calculate the top-line account performance for the period: total spend, total results, blended cost per result, blended ROAS. Compare against prior period and against targets. Express variance as both absolute numbers and percentage change.
2. Identify the top 3 performing campaigns by cost per result efficiency (vs. goal). Identify the bottom 3 performing campaigns by the same metric. Note the spend allocation between the top and bottom performers — budget concentration in underperformers is a common inefficiency.
3. For each campaign, pull delivery status. Flag any campaign with "Learning Limited" status or fewer than 50 optimization events in the last 7 days as structurally constrained, not just underperforming.
4. At the adset level, segment by audience type (cold / warm / hot) and calculate cost per result per segment. Identify whether retargeting is delivering a materially lower cost per result than prospecting (expected) or whether the gap is closing (indicates retargeting audience exhaustion).
5. Calculate frequency per adset for the reporting period. Flag any cold audience adset above 3.0 and any warm audience adset above 7.0 as saturation risk.
6. At the ad level, rank all active ads by Outbound CTR and cost per result. Identify the top creative (highest Outbound CTR or lowest CPA) and the bottom creative. If the bottom creative is receiving significant spend, flag it as a budget drag.
7. Analyze the CTR (all) vs. Outbound CTR spread per campaign. A large gap (CTR all 3%, Outbound CTR 0.8%) indicates post-click friction or landing page issues. A tight gap indicates strong creative-to-page alignment.
8. Pull CPM trend over the reporting period by week. Increasing CPM trend indicates auction competition increase, audience saturation, or targeting narrowing. Decreasing CPM indicates auction relief or learning improvement.
9. Assess the first-time impression ratio where available. Declining ratio is a leading saturation indicator that should be noted even if current performance is acceptable.
10. Compile recommendations: structure them as "Action → Expected Outcome → Priority (High/Medium/Low)" with a maximum of 5 recommendations to prevent decision paralysis.

## Output Requirements

- Executive Summary: 3-sentence performance verdict (hit/miss vs. targets, biggest win, biggest risk)
- Campaign Performance Table: spend, results, cost per result, ROAS, vs. prior period, vs. goal — per campaign
- Adset Efficiency Analysis: top and bottom performing adsets with specific diagnosis
- Creative Performance Ranking: top 3 and bottom 3 ads by Outbound CTR and cost per result
- Frequency and Saturation Flags: any adsets above threshold
- Forward-Looking Recommendations: maximum 5 actions, ranked by priority
- Glossary note for non-technical stakeholders (optional, if audience is non-technical)

## Platform-Specific Best Practices

- Always report cost per result using the same attribution window consistently across periods. Changing attribution windows mid-comparison invalidates trend analysis.
- ROAS from Ads Manager is based on Meta's attributed revenue and may differ from actual backend revenue due to multi-touch attribution, view-through conversions, and AEM modeling. Note this discrepancy in reports when presenting to data-literate stakeholders.
- For lead gen accounts, report down-funnel metrics (cost per qualified lead, cost per booked call, cost per closed deal) in addition to Meta's platform-reported cost per lead, if CRM data is available.
- Frequency should always be reported in the context of the time window. Lifetime frequency for a 90-day campaign is meaningless — always use 7-day frequency for operational decisions.
- When performance improves, diagnose why it improved with the same rigor as when it declines. Understanding the cause of wins is how you replicate them.

## Guardrails

- Do not present modeled conversion data (from AEM) as measured conversion data. Always label modeled figures.
- Do not make recommendations without supporting data evidence. Every recommendation must be tied to a specific metric or trend in the report.
- Do not report vanity metrics (likes, post shares, profile visits) as primary performance indicators for direct response campaigns.

## Example Requests

1. "Generate a weekly performance report for my e-commerce Meta campaign. Spend: $4,200. Purchases: 87. CPA goal: $45. Last week CPA was $38. Walk me through what changed and what to do."
2. "Create a monthly client report for a lead gen campaign. We spent $8,000, got 240 leads at $33/lead against a $30 target. Client needs to understand what's working and what needs attention."
3. "I need a performance report that compares this quarter's Meta campaigns against last quarter. Focus on creative performance and audience efficiency trends."
