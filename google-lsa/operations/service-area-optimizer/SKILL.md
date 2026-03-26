# Service Area Optimizer

**Platform:** Google LSA
**Category:** operations
**Tier:** pro

## Purpose
Optimize the service area configuration in Google LSA to maximize lead quality, proximity ranking signals, and cost efficiency simultaneously. Service area is one of the most consequential and most frequently misconfigured settings in LSA. Too broad: proximity signals dilute, out-of-area leads increase, cost-per-booked-lead rises. Too narrow: high-value geographies are missed, lead volume is unnecessarily constrained. This skill finds the optimal balance for a specific business's operational capacity and market density.

## When to Use
- At account setup, before the profile goes live
- When out-of-area leads represent more than 15% of total leads
- When the business adds a new dispatch location or expands service capacity
- When lead volume is being artificially constrained by an overly narrow service area
- Quarterly, as market conditions and business capacity evolve
- When cost-per-booked-lead is high and lead quality analysis points to geographic mismatch

## Inputs Required
- Current service area configuration: zip codes, cities, or radius setting currently active
- Business primary address (dispatch location)
- Maximum drive time or mileage the business is willing to accept for a job
- Revenue contribution by zip code or neighborhood (from CRM or job history)
- Lead quality data segmented by geography (if available)
- Competitor service areas (observable from their LSA profiles — approximate)
- Population density and housing density for each geography in consideration
- Any neighborhoods, cities, or zip codes the business explicitly refuses to service

## What This Skill Does
Audits the current service area against three criteria: proximity ranking efficiency (tighter areas rank better for specific searches), lead quality correlation (which geographies generate leads that book), and revenue density (which geographies produce the highest-value jobs). Recommends a service area configuration that maximizes proximity signal in the highest-revenue geographies while removing geographies that generate chargeable leads the business cannot or will not convert. Produces a tiered service area map: core zones (highest priority), secondary zones (moderate priority), and excluded zones (remove).

## Analysis Workflow
1. Map the current service area configuration — list every zip code or city currently included.
2. Pull job history from CRM: for each zip code or city in the service area, record total jobs, total revenue, and average ticket.
3. Identify the zip codes or cities producing the most booked jobs and highest revenue — these are core zone candidates.
4. Identify zip codes or cities receiving leads but producing zero or very few booked jobs — these are exclusion candidates.
5. Calculate drive time or distance from the primary dispatch location to each geography — flag any that exceed the business's maximum acceptable drive time.
6. Check the current service area for geographic gaps: are there high-density residential areas within the business's drive time range that are not currently included?
7. Assess proximity signal efficiency: calculate the ratio of the service area's geographic extent to the business's actual dispatch radius — a ratio above 2x suggests over-extension.
8. Review any out-of-area leads received in the past 30 days — if geographies outside the declared service area are generating leads, the area may be configured incorrectly.
9. Classify each current geography into one of three tiers: Core (keep and protect), Secondary (keep but deprioritize), Remove (exclude).
10. Identify 2–3 high-value geographies currently excluded that should be added.
11. Model the lead quality and cost impact of the recommended service area change.
12. Build the recommended service area configuration with specific zip codes or city names for each tier.

## Output Requirements
- Current service area audit: geography list with revenue contribution, lead volume, and booking rate per zone
- Geographic revenue density map description: core zones vs. low-value zones clearly identified
- Proximity efficiency assessment: current area extent vs. optimal extent for ranking signal
- Out-of-area lead analysis: geographies generating leads outside service intent
- Recommended service area configuration: tiered zip code/city list — Core, Secondary, Excluded
- Addition recommendations: high-value geographies to add with supporting rationale
- Estimated impact of recommended changes: lead quality, cost-per-booked-lead, and proximity signal improvement

## Platform-Specific Best Practices
- Proximity is calculated from the business address to the searcher's location — a narrowly defined service area centered on the dispatch location produces the strongest proximity rank signal for nearby searches.
- Adding a second dispatch location to LSA (if the business operates one) can legitimately expand the proximity-optimal area — do not artificially widen a single-location service area to simulate this.
- Service area changes take 3–7 days to fully propagate in LSA delivery — do not assess results immediately after a change.
- Zip code-based service areas provide more precise proximity control than radius-based areas in urban and suburban markets.
- Removing a geography from the service area does not immediately eliminate leads from that area if Google's systems have not updated — allow one full billing cycle to assess the change.
- In rural markets, wider service areas are often necessary and proximity penalties are less severe — calibrate differently than urban markets.

## Guardrails
- Do not remove geographies that are currently producing high-value booked jobs based solely on drive time assumptions — verify actual job data first.
- Do not add geographies outside the business's genuine service capacity to chase lead volume — it produces unchargeable leads and responsiveness penalties from declined calls.
- Service area should reflect operational reality, not aspirational coverage — misrepresenting service area violates Google's LSA policies.
- Do not confuse service area with Google Business Profile coverage — the two systems are separate and must be managed independently.

## Example Requests
1. "We're getting a lot of leads from zip codes 45 minutes away from our shop and we're not booking them. Audit our service area and tell me what to cut."
2. "We just opened a second location. Help me reconfigure our LSA service area to maximize proximity signals from both dispatch points."
3. "Our service area covers 60 zip codes but 80% of our revenue comes from 12 of them. Optimize the service area to protect those 12 and cut the rest."
