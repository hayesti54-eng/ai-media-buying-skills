# LSA Ranking Factor Analyzer

**Platform:** Google LSA
**Category:** diagnostics
**Tier:** agency

## Purpose
Perform a comprehensive multi-factor ranking diagnosis across all signals Google uses to determine LSA ad position: proximity, review volume and rating, responsiveness, profile completeness, years in business, license verification status, and budget availability. This skill is agency-grade because it requires cross-client benchmarking, competitive context, and the ability to prioritize ranking levers by ROI impact — not just flag deficiencies. It answers the operational question: which ranking factor, if fixed, moves the needle the most for this specific business in this specific market?

## When to Use
- When a profile consistently ranks below position 3 despite adequate budget
- When a competitor with fewer reviews outranks on relevant search intents
- After Google updates LSA ranking logic (typically rolled out silently — identified by sudden rank shifts)
- During a competitive market entry where a new LSA profile needs rank acceleration
- Quarterly, as a full profile health review for agency-managed accounts
- When a profile is flagged, suspended, or re-verified and ranking has not recovered post-reinstatement

## Inputs Required
- Current LSA profile data: review count, average rating, years in business, license/insurance verification status
- Responsiveness score (current) from LSA dashboard
- Profile completeness checklist: all service types active, business description populated, photos uploaded, hours set
- Service area configuration: zip codes, cities, or radius currently active
- Budget cap setting and average weekly spend vs. cap utilization
- Competitive landscape: top 2–3 competitor profiles visible in the same search results (review count, rating, badge status)
- Any Google Guarantee badge status issues or verification flags
- Historical rank position data (if available — can be approximated from impression/lead volume trends)

## What This Skill Does
Scores the profile across every known LSA ranking factor, weights each factor by its estimated impact on rank in the given vertical and market, identifies the performance gap between the current profile and the top-ranked competitor, and outputs a prioritized ranking improvement roadmap. Distinguishes between quick-fix factors (profile completeness, hours, budget cap) and long-cycle factors (review volume, years in business) so improvement effort can be sequenced rationally.

## Analysis Workflow
1. Confirm Google Guarantee or Google Screened badge status — any verification issue overrides all other ranking factors until resolved.
2. Score profile completeness: job types populated, photos present, business description written, hours accurate, service area boundaries defined. Flag any missing element.
3. Pull responsiveness score and call answer rate — score against the 90%+ threshold for top-tier ranking.
4. Count active Google reviews and compute average star rating — compare to top 2 competitors in the same service area.
5. Calculate the review gap: how many additional reviews are needed to match the leading competitor.
6. Assess proximity configuration: is the service area set too wide (diluting proximity signals) or too narrow (missing high-intent geography)?
7. Check budget cap utilization — a profile spending at 100% of its cap daily is being throttled; this is not a ranking failure but a budget failure, and they look identical in lead volume.
8. Evaluate years-in-business signal: this is fixed but informs expectations for new profiles competing against incumbents.
9. Check license and insurance verification status — expired or flagged credentials suppress rank silently.
10. Build a weighted ranking factor scorecard: each factor scored 1–5, weighted by vertical-specific importance.
11. Identify the top 3 factors where the gap between current performance and top competitor is largest.
12. Sequence improvement actions by impact-to-effort ratio — surface the 1–2 actions with the fastest rank lift potential.

## Output Requirements
- Ranking factor scorecard: each factor scored, weighted, and compared to competitive benchmark
- Competitive gap analysis: current profile vs. top-ranked competitor across each factor
- Top 3 ranking deficiencies with estimated rank impact and fix difficulty
- Prioritized improvement roadmap: actions sequenced by impact-to-effort, with owner and timeline
- Budget assessment: is rank suppression caused by budget cap throttling vs. genuine profile weakness?
- Red flag log: any verification issues, completeness gaps, or responsiveness failures requiring immediate attention

## Platform-Specific Best Practices
- Proximity is a non-negotiable factor — a service area that covers 40 zip codes will almost always rank lower for a specific zip than a competitor whose service area is tightly focused on that zip.
- Review velocity matters as much as total review count — a profile accumulating 5 reviews per month will outpace a stagnant 80-review profile within a year.
- The Google Guarantee badge is a trust accelerator — any lapse in background check or license verification should be treated as a P1 issue.
- Budget cap suppression is frequently misidentified as ranking weakness — always rule out budget exhaustion before diagnosing profile deficits.
- LSA does not use keyword relevance — job type selection is the only topical alignment mechanism.
- New profiles (under 6 months) are algorithmically disadvantaged in competitive markets regardless of other signals — set realistic rank expectations.

## Guardrails
- Do not promise specific rank positions — LSA ranking is dynamic and query-dependent.
- Do not recommend service area expansion as a ranking fix — wider areas dilute proximity signals and reduce lead quality simultaneously.
- Competitor profile data is observable but not fully verifiable — treat competitive benchmarks as directional, not absolute.
- Never advise a client to misrepresent business age, license status, or service capabilities to improve ranking signals.

## Example Requests
1. "We're a roofing company in Dallas with 94 reviews and a 4.8 rating but we're consistently in position 4–5. Run a full ranking factor analysis and tell me what's holding us back."
2. "A new competitor entered our market 3 months ago and is already outranking us. How is that possible? Break down their ranking signals vs. ours."
3. "Our LSA profile was suspended for a license verification issue and just got reinstated. Rank hasn't recovered in two weeks — what's the recovery sequence?"
