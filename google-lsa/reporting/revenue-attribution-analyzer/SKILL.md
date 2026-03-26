# Revenue Attribution Analyzer — Beyond Raw Lead Count

**Platform:** Google LSA
**Category:** reporting
**Tier:** agency

## Purpose
Build a rigorous revenue attribution model for Google LSA spend that moves beyond raw lead counts to demonstrate actual business impact: revenue generated, cost per dollar earned, and LSA's contribution relative to other lead sources. LSA reporting within Google's own dashboard shows only charges and lead types — it does not show revenue. This skill bridges the gap between LSA's cost data and the business's revenue data to produce a true ROI picture. It is agency-grade because it requires cross-system data integration, multi-source attribution analysis, and the judgment to handle attribution ambiguity.

## When to Use
- When a client questions whether LSA is "worth it" based on lead cost alone
- During a budget planning cycle where LSA investment is being evaluated against other channels
- When a client runs LSA alongside Google Search Ads, Facebook Ads, or organic SEO and needs source attribution
- Quarterly, as part of a full channel ROI review
- When a client wants to understand the lifetime value of LSA-sourced customers, not just the first-job revenue
- When CRM data is available and reliable enough to support revenue-level analysis

## Inputs Required
- LSA spend data for the attribution period (from LSA dashboard)
- CRM data: all jobs booked and closed in the period with source attribution field populated
- Revenue data by job: revenue per closed job, job type, and source attribution
- Customer lifetime data: repeat job count and revenue for LSA-sourced customers (if available)
- Other paid channel spend for the same period (for cross-channel comparison)
- Attribution methodology used in CRM (first touch, last touch, multi-touch)
- Any known attribution gaps: LSA leads that entered the CRM without LSA source tag

## What This Skill Does
Constructs a revenue attribution model that connects LSA spend to closed revenue through the CRM. Calculates LSA ROAS, cost-per-booked-job, revenue-per-lead, and — when lifetime data is available — customer acquisition cost relative to customer lifetime value. Identifies attribution confidence level and adjusts conclusions accordingly. Compares LSA revenue efficiency against other active channels. Surfaces the LSA revenue story in terms the client's business operations and finance stakeholders can engage with — not just marketing metrics.

## Analysis Workflow
1. Confirm CRM source attribution integrity: what percentage of closed jobs in the period have a valid source attribution? Flag the gap if attribution coverage is below 80%.
2. Isolate all jobs with LSA source attribution for the period — record revenue, job type, and close date for each.
3. Calculate LSA ROAS: (Total Revenue from LSA-Attributed Jobs / Total LSA Spend) × 100.
4. Calculate cost-per-booked-job: (Total LSA Spend / Total LSA-Attributed Booked Jobs).
5. Calculate revenue-per-lead: (Total LSA Revenue / Total Charged LSA Leads).
6. Calculate revenue-per-booked-lead: (Total LSA Revenue / Total LSA-Attributed Booked Jobs).
7. Segment revenue by job type — identify which job types are generating the highest revenue per LSA lead.
8. If repeat customer data is available: identify LSA-sourced customers who have returned for additional jobs — calculate extended customer value.
9. Compare LSA ROAS against other active paid channels for the same period.
10. Assess attribution confidence: identify any known LSA leads that entered the CRM without a source tag and estimate their contribution using the known attribution rate.
11. Build an adjusted revenue estimate that accounts for likely attribution undercount.
12. Produce the revenue attribution narrative: what did LSA cost, what did it generate, and how does that compare to alternatives?

## Output Requirements
- Revenue attribution summary: total LSA spend, total attributed revenue, LSA ROAS, with confidence rating
- Job-level metrics: cost-per-booked-job, revenue-per-lead, revenue-per-booked-lead
- Job type revenue breakdown: revenue and ROAS by job type — highest and lowest performers
- Customer lifetime value extension: repeat customer revenue from LSA-sourced customers (if data available)
- Cross-channel comparison: LSA ROAS vs. other paid channels in the same period
- Attribution confidence assessment: coverage rate, gap estimate, adjusted revenue calculation
- Executive ROI summary: the LSA investment story in 3–5 sentences suitable for a business owner or finance stakeholder

## Platform-Specific Best Practices
- LSA attribution must run through CRM — there is no conversion tracking pixel or UTM parameter available in LSA. Businesses that do not tag LSA leads in their CRM cannot produce revenue attribution without manual reconciliation.
- LSA ROAS in home services typically runs 3:1 to 8:1 depending on vertical and average ticket — an HVAC system replacement profile will show dramatically different ROAS than a drain cleaning profile even with similar booked lead rates.
- Customer lifetime value is especially important for home services with recurring needs (HVAC maintenance, pest control, cleaning) — first-job ROAS understates the true LSA investment value.
- Attribution gaps are the norm, not the exception — build the model to acknowledge and correct for the gap, not to pretend it does not exist.
- Cross-channel ROAS comparisons must account for funnel stage — LSA is bottom-of-funnel lead generation; comparing it to a brand awareness display channel ROAS is not an apples-to-apples analysis.
- Revenue per job type is the most actionable output — it tells the client exactly which job types are producing ROI and which are consuming budget without return.

## Guardrails
- Do not present LSA ROAS as a precise number when attribution coverage is below 80% — report it as a range with a confidence note.
- Do not make cross-channel ROI comparisons without equalizing the attribution methodology — first-touch vs. last-touch attribution will produce incomparable ROAS numbers.
- Customer lifetime value projections must be clearly labeled as projections, not historical fact.
- Never attribute revenue to LSA that has not been traced through CRM source data — overclaiming LSA attribution destroys credibility when the attribution is later audited.

## Example Requests
1. "We spent $3,200 on LSA in Q1 and booked 41 jobs. Build the full revenue attribution analysis — I need to know ROAS, cost-per-job, and which job types are actually driving the return."
2. "Our client runs LSA, Google Search, and Facebook simultaneously. Attribution is a mess. Help me build a revenue model that gives each channel credit based on CRM source data."
3. "The client wants to know if LSA is better than Google Search for their roofing business. Run a channel ROAS comparison using Q1 data from both platforms."
