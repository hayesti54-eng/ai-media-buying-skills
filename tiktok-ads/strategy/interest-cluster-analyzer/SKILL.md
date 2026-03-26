# Interest Cluster Analyzer

**Platform:** TikTok Ads
**Category:** strategy
**Tier:** agency

## Purpose
Analyze and structure the interest targeting clusters available within TikTok Ads Manager for a specific product or audience, evaluate the performance and saturation risk of existing interest configurations, and produce a structured targeting architecture that maximizes audience quality, reach efficiency, and learning signal — while avoiding the common errors of over-layered interest stacks, under-diversified clusters, and interest selection based on intuition rather than audience behavior data.

## When to Use
- Setting up targeting for a new TikTok Ads account and need to build the initial interest cluster architecture
- Current interest targeting is producing high CPMs or saturating quickly, suggesting poor cluster selection
- Testing multiple interest clusters in parallel and need a structured framework for evaluation and consolidation
- Managing multiple client accounts in the same vertical and need a repeatable interest research methodology
- Transitioning from interest targeting to Broad and need to understand which clusters produced the best learnings to inform that decision

## Inputs Required
- Product or service and the target audience profile: demographics, psychographics, content consumption habits, lifestyle indicators
- TikTok industry category or business type
- Existing interest clusters being targeted (list all current interest categories and sub-categories in use)
- Existing performance data by audience segment if available: CPM, CTR, CPA per interest cluster
- Campaign objective and conversion event
- Geographic market
- Current audience size estimates per cluster (from TikTok audience estimator)
- Budget available for interest cluster testing

## What This Skill Does
This skill builds a structured interest cluster research methodology specific to TikTok's interest taxonomy, evaluates existing clusters for performance and saturation risk, identifies high-potential untested clusters based on audience behavior analysis, and produces a tiered targeting architecture with a parallel test plan for cluster validation.

## Analysis Workflow
1. Map the target audience psychographic profile. Before selecting interest categories, define the audience through behavioral lens:
   - What content do they consume on TikTok's FYP? (e.g., fitness tutorials, before/after transformations, product reviews, lifestyle vlogs)
   - What are their purchase motivators? (pain avoidance, aspiration, social proof, novelty)
   - What other categories do they over-index in beyond the obvious product category? (e.g., a fitness supplement buyer also over-indexes in productivity content, self-improvement, and meal prep)
2. Research the TikTok interest taxonomy. Navigate TikTok Ads Manager's interest categories and map each relevant category against the audience profile. TikTok's interest taxonomy is organized into primary categories with sub-category depth — identify relevant options at both levels.
3. Classify interests into three cluster types:
   - Core Clusters: direct product category interests (e.g., "Fitness & Health" for a supplement brand) — high relevance, high competition, typically higher CPMs
   - Adjacent Clusters: lifestyle and behavioral interests that the target audience shares (e.g., "Food & Beverage" and "Personal Development" for the same supplement buyer) — lower competition, often lower CPMs
   - Lookalike-Adjacent Clusters: interest categories that define the audience's identity beyond the product category — require hypothesis-based testing but can unlock underpriced inventory
4. Evaluate existing cluster performance. For each active interest cluster, score:
   - Audience size: is the estimated reach above 500,000? Below this, saturation risk is high.
   - CPM efficiency: which clusters are delivering impressions at lower cost? This reveals algorithm competition levels.
   - CTR performance: which clusters produce higher click intent? This reveals relevance quality.
   - CPA efficiency: if conversion data is split by audience, which clusters are converting most efficiently?
5. Flag over-layered clusters: interest stacks with 4+ categories layered with AND logic dramatically reduce audience size and create expensive, narrow delivery. Recommend separation into individual test clusters.
6. Build the cluster architecture:
   - Tier 1 — Core Clusters (test separately, 1 interest category per ad set)
   - Tier 2 — Adjacent Clusters (test separately or in small 2-category stacks)
   - Tier 3 — Exploratory Clusters (hypothesis-based, smaller budget allocation)
7. Design the parallel cluster test plan:
   - Run each primary cluster as an independent ad set with equal budget
   - Use identical creative across all cluster tests (only variable = audience)
   - Run for 7 days minimum with at least $50/day per cluster before evaluating
8. Produce consolidation recommendation: after testing, which clusters should be consolidated (combined budgets), which should be scaled, and which should be killed?

## Output Requirements
- Psychographic audience map: behavioral and content consumption profile used as the interest research foundation
- Interest cluster inventory: all relevant TikTok interest categories mapped to Core, Adjacent, and Exploratory tiers
- Existing cluster evaluation table: audience size, CPM, CTR, CPA (if available), and Saturation Risk score per current cluster
- Over-layering flag: identify any current clusters that are too tightly stacked
- New cluster recommendations: 5–10 untested clusters with rationale for each
- Tiered targeting architecture: Tier 1, 2, and 3 cluster assignments
- Parallel test plan: ad set configuration, budget per cluster, test duration, evaluation criteria
- Consolidation decision framework: what performance thresholds qualify a cluster for scale, maintenance, or kill

## Platform-Specific Best Practices
- TikTok interest categories reflect FYP consumption behavior, not search intent. A user interested in "fitness" on TikTok has been algorithmically identified by watching fitness-related content — this is a more nuanced and less self-declared signal than interest targeting on Facebook or Google.
- Single-interest ad sets almost always outperform tightly stacked multi-interest ad sets on TikTok. The algorithm needs room to find the highest-quality users within a category — stacking interests creates a smaller, more expensive audience without proportionate quality improvement.
- Adjacent interest clusters frequently deliver lower CPMs and comparable CPAs to Core clusters because they access less competitively bid inventory. Budget allocated to Adjacent clusters often produces better cost-efficiency than the same budget in Core clusters.
- Audience size sweet spot for TikTok interest targeting: 1–10 million per ad set for conversion campaigns. Above 10 million, algorithm will find quality users efficiently. Below 500,000, saturation risk within 2–3 weeks is high.
- TikTok's interest targeting performs better in broad geographic markets (US national, not city-level) because audience density is sufficient for the algorithm to find conversion-intent users efficiently within large pools.

## Guardrails
- Do not layer more than 2 interest categories in a single ad set on TikTok — single-interest ad sets produce cleaner data and better delivery in most cases.
- Do not select interest categories solely based on product category relevance — always research adjacent and behavioral interests that over-index for the specific audience.
- Do not allocate scaling budget to an interest cluster that has not been individually validated at a test budget level.
- Never evaluate interest cluster performance without controlling for creative quality — a bad creative will underperform in every interest cluster, making targeting data unreadable.

## Example Requests
1. "I'm launching TikTok ads for a productivity app targeting professionals 25–45. Build me a complete interest cluster architecture with Core, Adjacent, and Exploratory tiers, and a test plan to validate each cluster."
2. "I'm currently running TikTok ads against 6 interest categories stacked together in one ad set. My CPMs are high and my reach is narrow. Restructure my interest targeting and tell me which clusters to separate and test independently."
3. "I manage 4 TikTok accounts in the home improvement vertical. Build me a repeatable interest cluster research methodology and a tiered architecture I can apply across all accounts with minor customization."
