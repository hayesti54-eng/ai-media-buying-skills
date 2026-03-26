# Creative Fatigue Detector

**Platform:** Meta Ads
**Category:** creative
**Tier:** pro

## Purpose

Identify which specific ads within an adset or campaign are experiencing creative fatigue — the condition where repeated exposure to the same creative causes declining engagement, rising CPMs, and worsening conversion metrics. Creative fatigue is distinct from audience saturation (which is audience-pool-driven) and must be diagnosed at the individual ad level. This skill surfaces fatigued creatives before they drag down adset-level performance, and prescribes a rotation or replacement strategy.

## When to Use

- When CTR (all) or Outbound CTR is declining for an adset that has not had creative changes in 14+ days
- When frequency for the adset exceeds 2.5 in a 7-day window for cold audiences
- When individual ads within an adset show diverging performance (one ad's CTR is fine, another's has collapsed)
- During weekly creative audits to proactively identify which ads are approaching fatigue thresholds
- When CPM is rising without an obvious audience or auction explanation
- When Thumbstop rate (3-second video views ÷ impressions) is declining on video ads
- When hook rate (percentage of users who watch past the first 3 seconds) is declining week-over-week

## Inputs Required

- Ad-level performance data: impressions, reach, frequency, CTR (all), Outbound CTR, CPM, cost per result, ROAS — broken down per individual ad
- Video-specific metrics (if applicable): 3-second video views, video average play time, ThruPlays, Thumbstop rate, hook rate
- Date the ad was launched (to calculate exposure days)
- Adset-level frequency and reach data
- Breakdown by placement (Feed vs. Stories vs. Reels) if available
- Creative type per ad: static image, video, carousel, collection

## What This Skill Does

This skill analyzes individual ad performance trends over time, applies fatigue thresholds by creative type, identifies fatigued ads vs. underperforming ads that were never strong (a critical distinction), and produces a creative refresh priority list. It uses Thumbstop, hook rate, and CTR trend trajectory to separate creative-specific fatigue from audience or structural causes, and recommends whether a creative should be paused, replaced, or remixed.

## Analysis Workflow

1. Pull ad-level performance data for the past 28 days with a weekly breakdown. For each ad, calculate the week-over-week change in CTR (all), Outbound CTR, and cost per result.
2. Identify ads where CTR (all) has declined by more than 20% over a 7-day period AND impressions have increased or held steady. This combination — rising impressions, falling CTR — is the core fatigue signal.
3. Calculate Thumbstop rate for each video ad: (3-second video views ÷ impressions) × 100. A Thumbstop rate below 25% for Feed video indicates the hook is not capturing attention. A week-over-week decline in Thumbstop rate indicates fatigue with the hook specifically.
4. Calculate hook rate: (percentage of video viewers who watched past 3 seconds). If hook rate is strong (>30%) but Outbound CTR is weak, the creative captures attention but lacks a compelling call to action or offer in the body copy.
5. Check frequency per ad. In adsets without ad-rotation controls, Meta will allocate most impressions to the "winning" ad. The winning ad gets high frequency while other ads get minimal impressions. Identify which ad in each adset is holding the majority of impressions and what its frequency is.
6. Cross-reference fatigue indicators with ad launch date. An ad showing CTR decline after 7 days of strong performance is fatigued. An ad showing low CTR from day one was never a strong creative — these need different responses (pause the poor performer vs. rotate the fatigued winner).
7. For carousel ads: check link click distribution across cards. If the first card is receiving 80%+ of clicks, the other cards are not driving engagement and may be contributing to lower overall CTR as frequency on those cards rises.
8. Evaluate placement-level fatigue: break down CTR by placement (Facebook Feed, Instagram Feed, Stories, Reels). An ad may be fatigued on Feed but still performing in Stories due to different frequency and format dynamics.
9. Apply fatigue thresholds by audience type: cold (prospecting) audiences fatigue faster — watch for CTR decline signals at 7-10 days of strong delivery. Warm audiences tolerate higher frequency — use a 14-21 day threshold.
10. Produce a creative health scorecard per ad with a status designation and recommended action.

## Output Requirements

- Creative health scorecard: ad name, impressions, frequency, CTR trend, Outbound CTR trend, Thumbstop rate (video), status (Healthy / Fatiguing / Fatigued / Never Performed)
- Fatigue severity ranking: which ads need immediate replacement vs. monitoring
- Creative refresh priority list: ads to pause now, ads to test replacements for, ads to remix (reformat, new hook, new CTA)
- Estimated performance recovery from creative refresh based on historical account data
- Recommended testing cadence: how often to introduce new creative for this adset based on audience size and budget level

## Platform-Specific Best Practices

- For cold audiences at $200+/day budget, plan creative refreshes every 2-3 weeks proactively, not reactively.
- A Thumbstop rate above 30% and hook rate above 35% are target thresholds for video creatives on Feed placements.
- Meta's Dynamic Creative feature can mask individual creative fatigue — aggregated dynamic creative results can look stable while one creative variant has collapsed. Always check variant-level performance when using Dynamic Creative.
- Introducing a new creative does not automatically reset learning for an adset. It adds an ad to the existing adset, which Meta will test against existing ads. A new adset with fresh creative has a different optimization trajectory.
- Remixing a fatigued creative (new hook, same offer) typically underperforms a genuinely new creative after an audience has seen the original version 3+ times. Fresh hooks matter more than new overlays on the same footage.

## Guardrails

- Do not pause all ads in an adset simultaneously to fight fatigue. Always keep at least 2 ads running to maintain delivery continuity.
- Do not interpret low CTR on a brand-new ad as fatigue. Allow minimum 3 days and 1,000+ impressions before evaluating creative performance.
- Do not confuse creative fatigue with audience saturation. If all ads in an adset are declining simultaneously at the same rate, saturation is more likely. If one ad declines while others hold, fatigue is more likely.

## Example Requests

1. "My top video ad has been running for 18 days and its Outbound CTR dropped from 1.8% to 0.7% this week while impressions doubled. Is this fatigue and what do I do?"
2. "I have 5 ads in an adset. One ad has 85% of the impressions and its CTR is collapsing. The other 4 ads have almost no data. How do I fix this distribution problem?"
3. "Walk me through a weekly creative audit process that flags fatiguing creatives before they hurt my CPA."
