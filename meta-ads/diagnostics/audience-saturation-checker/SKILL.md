# Audience Saturation Checker

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** pro

## Purpose

Diagnose whether an adset's declining performance is caused by audience saturation — the condition where a defined audience has been exposed to the advertiser's creative at a frequency high enough to exhaust the pool of responsive users. Saturation is distinct from creative fatigue (which is creative-specific) and auction competition (which is market-wide). This skill measures saturation depth, forecasts remaining audience capacity, and prescribes audience expansion or rotation strategies.

## When to Use

- When frequency for a cold audience exceeds 2.5 in a 7-day window
- When frequency for a warm/retargeting audience exceeds 5.0 in a 7-day window
- When CPM is rising but the market is not in a known competitive period
- When reach is plateauing while impressions continue to increase (frequency climbing)
- When the first-time impression ratio is declining week-over-week
- When performance was strong at launch but has decayed linearly over 3-6 weeks without creative changes
- After running the same audience for more than 30-45 days continuously

## Inputs Required

- Adset-level frequency data: 7-day, 14-day, and lifetime
- Reach vs. impressions over time (weekly breakdown)
- First-time impression ratio (available in custom column breakdown)
- Estimated audience size from adset definition
- Daily budget and average CPM (to calculate daily reach)
- Days the adset has been running
- Performance trend: CPM, CTR (all), Outbound CTR, cost per result over the same period
- Audience type: Lookalike, interest-based, custom audience, broad

## What This Skill Does

This skill calculates audience penetration depth, estimates the percentage of the defined audience that has already been reached, projects how many days remain before the audience is effectively exhausted at the current burn rate, and compares current metrics against known saturation benchmarks. It distinguishes between temporary saturation (audience will reset as user behavior changes) and structural saturation (audience is too small for the budget level), and recommends targeted interventions for each.

## Analysis Workflow

1. Calculate audience penetration: divide total unique reach (lifetime or over campaign period) by the estimated audience size. Penetration above 40% in a small audience (<500K) is a saturation warning. Penetration above 60% is saturation confirmed.
2. Calculate daily reach burn rate: (daily budget ÷ CPM) × 1000. This is the approximate number of unique users reached per day, assuming frequency = 1. Divide remaining uncontacted audience by daily reach to estimate days until full saturation.
3. Pull the first-time impression ratio for the affected adset over a 14-day period. A ratio below 20% means 80% of your daily impressions are going to users who have already seen your ads. This is a high-confidence saturation indicator.
4. Plot frequency trend week-over-week. If 7-day frequency is increasing by more than 0.5 per week while reach growth is flat, the audience pool is exhausting faster than Meta can find new users within it.
5. Check CPM trend concurrent with frequency rise. In a saturating audience, CPM rises as Meta has to bid more aggressively to reach remaining unexposed users who are increasingly less likely to be responsive — they are the lowest-responsive segment of the audience.
6. Compare CTR (all) and Outbound CTR trends to frequency trend. If CTR is declining in direct proportion to frequency increase, the problem is saturation (lower-quality users being reached). If CTR holds steady while frequency rises, the problem is post-click, not saturation.
7. Assess the audience type's saturation ceiling: custom audiences (website visitors, customer lists) have a fixed ceiling and cannot grow. Lookalike audiences and interest audiences are dynamic and can be refreshed by Meta over time. Custom audiences require retargeting pool refreshes (new visitors, new customers) to avoid saturation.
8. Calculate the maximum sustainable daily budget for the current audience size: (audience size × target frequency of 2.0 per week) ÷ 7 days = daily reach needed × CPM ÷ 1000 = maximum efficient daily budget. If actual daily budget exceeds this, structural saturation is occurring.
9. Identify expansion options: Lookalike percentage expansion (1% → 3%), interest audience broadening, geo expansion, age/gender broadening, or switching to Advantage+ Audience.
10. Produce a saturation scorecard and expansion plan.

## Output Requirements

- Saturation scorecard: penetration %, first-time impression ratio, frequency trend, saturation severity (early / moderate / severe)
- Days remaining at current burn rate
- Maximum efficient daily budget for current audience
- Root cause: temporary saturation vs. structural saturation vs. creative fatigue (differentiated)
- Expansion options ranked by estimated audience size increase and implementation risk
- Recommended frequency cap or budget reduction if immediate action is needed

## Platform-Specific Best Practices

- Meta does not expose first-time impression ratio as a default column. Add it via the "Customize Columns" menu under the "Engagement" category.
- For retargeting audiences, acceptable frequency is higher than cold audiences — but diminishing returns for most industries begin above 7 impressions per 30 days.
- Advantage+ Audience automatically expands beyond your defined audience when Meta determines it can find more efficient conversions outside your stated targeting. If saturation is detected, enabling Advantage+ Audience expansion can extend runway without a full structural change.
- Audience saturation and creative fatigue often occur simultaneously. Always run the Creative Fatigue Detector alongside this skill when both frequency and declining CTR are present.
- For B2B advertisers with inherently small audiences (e.g., targeting job titles in a specific industry), saturation is a structural constraint. The correct response is frequency capping via campaign-level frequency controls, not audience expansion.

## Guardrails

- Do not expand audience purely to escape saturation if the expanded audience has materially different conversion characteristics. Lookalike percentage expansion degrades audience quality.
- Do not reduce budget below the minimum required for the learning phase if the campaign is still in learning.
- Retargeting audience saturation is expected and healthy in some contexts — users who have visited your site multiple times and seen your ads are demonstrating purchase intent even if they have not converted yet.

## Example Requests

1. "My retargeting adset targeting 30-day website visitors is showing a 7-day frequency of 6.8 and my CPA has doubled. Is this saturation and what do I do?"
2. "I'm targeting a 1% Lookalike audience of 1.2 million users with a $500/day budget. How long before this audience saturates and what should I do before it does?"
3. "My first-time impression ratio dropped from 45% to 12% over 3 weeks. What does that tell me and how do I fix it?"
