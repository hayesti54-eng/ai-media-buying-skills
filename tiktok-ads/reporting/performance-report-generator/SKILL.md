# TikTok Ads Performance Report Generator

**Platform:** TikTok Ads
**Category:** reporting
**Tier:** pro

## Purpose
Transform raw TikTok Ads Manager data exports into a structured, decision-grade performance report that communicates account health, creative performance, funnel efficiency, and prioritized action items — formatted for media buyers, growth operators, and client-facing presentations. Reports are built around actionable insight, not vanity metrics.

## When to Use
- Compiling a weekly or monthly TikTok Ads account performance review for internal or client presentation
- Conducting an end-of-sprint creative performance analysis after a batch test cycle
- Presenting campaign results to a client, founder, or marketing leadership team
- Building a performance baseline document at the start of a new engagement
- Responding to a performance question from a stakeholder who needs data context, not raw numbers

## Inputs Required
- TikTok Ads Manager export (CSV) covering the reporting period: Impressions, Reach, CPM, Clicks, CTR, Spend, Conversions, CPA, ROAS or Revenue (if applicable), 2-Second Video Views, Average Watch Time, Video Views (25/50/75/100%), Frequency
- Reporting period: date range and comparison period (previous 7 days, previous month, etc.)
- Campaign objective(s) active during the period
- Account-level targets: CPA target, ROAS target, monthly budget, creative testing goals
- Audience of the report: internal media buyer (technical), client (executive summary), agency team (operational)
- Creative labels: which ads are UGC, Spark, branded, new test, scaling, or being phased out

## What This Skill Does
This skill structures a full performance report across four sections: Account-Level Health Summary, Creative Performance Breakdown, Funnel Efficiency Analysis, and Action Plan. It calculates period-over-period deltas, highlights wins and problems, classifies creative performance, and produces a prioritized next-step action list — all calibrated to the report audience's decision-making needs.

## Analysis Workflow
1. Set the reporting framework. Define the primary success metric (CPA, ROAS, or CPL) based on campaign objective. All other metrics are supporting or diagnostic.
2. Calculate Account-Level Health metrics: total spend vs. budget, blended CPA vs. target, total conversions, revenue (if tracked), ROAS, CPM trend (rising = market pressure, falling = algorithm efficiency improving), CTR trend, total reach and frequency.
3. Compute period-over-period deltas for all key metrics. Flag any metric with a delta greater than ±20% as a material change requiring explanation.
4. Run Creative Performance Breakdown: for each active creative, pull hook rate, hold rate (25%/50%/75%), CTR, CPA, spend, and conversion volume. Rank creatives by CPA efficiency (lowest CPA with highest conversion volume = highest priority for scale). Classify each creative: Top Performer, Steady Contributor, Underperformer, or New Test (insufficient data).
5. Calculate creative mix analysis: what percentage of total spend and conversions is concentrated in the top creative? Over-reliance on a single creative (more than 60% of conversions from one ad) is a concentration risk — flag it.
6. Build Funnel Efficiency Section:
   - Impression-to-Click Rate (CTR): top of funnel engagement
   - Click-to-Conversion Rate (Landing Page CVR): mid funnel
   - Cost-per-Click vs. Cost-per-Conversion ratio: efficiency gap analysis
   - If video objective: completion rate funnel (25/50/75/100%)
7. Identify and document the top 3 wins for the period (with data to support each).
8. Identify and document the top 3 problems for the period (with root cause hypothesis for each).
9. Produce the Action Plan: specific recommended changes for the next 7 days, ranked by expected impact on the primary success metric. Each action must include: what to do, why, and the expected outcome.

## Output Requirements
- Executive Summary: 3–5 bullet points summarizing the period in plain language (non-technical)
- Account Health Dashboard: spend, CPA vs. target, ROAS, blended CTR, CPM, conversions — with period delta for each
- Creative Performance Table: all active creatives with hook rate, CTR, CPA, spend, conversion volume, and classification
- Top Performer Spotlight: 1–2 sentence explanation of why the top creative is working
- Funnel Efficiency Section: CTR, CVR, CPC-to-CPA ratio, completion rate funnel
- Top 3 Wins with supporting data
- Top 3 Problems with root cause hypothesis
- 7-Day Action Plan: prioritized list with expected impact and responsible action owner
- Optional: client-facing narrative paragraph framing the period in business context

## Platform-Specific Best Practices
- TikTok reports should always lead with creative performance, not account-level aggregates. On TikTok, creative is the primary performance lever — the report structure should reflect that hierarchy.
- CPM context is critical for TikTok reports. Rising CPMs are often a platform auction signal (high-competition period, holiday, campaign scaling) rather than an account problem — always provide CPM trend context rather than presenting the number in isolation.
- Video-specific metrics (hook rate, hold rate, average watch time) should be included in every TikTok performance report regardless of campaign objective. They are leading indicators of future conversion performance.
- Frequency should always be reported alongside reach for TikTok campaigns. An audience with high frequency and declining CTR is approaching saturation — this context prevents misdiagnosis of metric drops.
- For client-facing reports, always frame creative fatigue as a planned, expected phase rather than a failure — and always pair the fatigue diagnosis with a replacement pipeline status update.

## Guardrails
- Do not build a TikTok report that leads with brand awareness metrics (impressions, reach) for a conversion campaign — this misrepresents the account's performance priority.
- Do not present period-over-period deltas without accounting for significant differences in spend levels between periods.
- Do not include data without interpretation — every metric in the report should be accompanied by a "so what" statement.
- Never produce a report that ends without a clear action plan — data without direction is not a performance document, it is a data dump.

## Example Requests
1. "Here's my TikTok Ads Manager export for the last 30 days across 3 campaigns. Build me a complete performance report with account health summary, creative performance breakdown, and a prioritized 7-day action plan."
2. "I need a client-facing performance report for my TikTok account. CPA is above target, one creative is crushing it, and two others are dragging the average up. Write the report in a way that explains what's happening and what we're doing about it."
3. "Build me a weekly performance review template for TikTok that I can fill in every Friday, covering creative ranking, funnel metrics, and next-week priorities. Make it operator-grade and concise."
