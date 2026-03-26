# TikTok Campaign Launch Verifier

**Platform:** TikTok Ads
**Category:** launch
**Tier:** pro

## Purpose
Execute a systematic pre-launch verification protocol for new TikTok Ads campaigns, ad sets, and creatives — ensuring that every structural, technical, tracking, and creative element is correctly configured before budget is committed. This skill prevents the most common and costly TikTok launch errors: broken pixel tracking, misconfigured bid strategies, unverified Spark authorizations, non-compliant creative, and misaligned conversion windows.

## When to Use
- Launching a new TikTok Ads campaign from scratch
- Launching a new creative batch into an existing campaign or ad set
- Setting up a new ad account for a client or new brand
- Reactivating a paused campaign after a significant gap (30+ days off)
- After making structural changes to an existing campaign (new audience, bid strategy change, creative swap)

## Inputs Required
- Campaign objective selected in TikTok Ads Manager
- Bid strategy type and bid/budget amounts
- Ad set targeting configuration: audience type (interest, behavior, Lookalike, Broad, Custom), geographic targeting, age/gender settings
- Creative assets loaded: video file specs, ad copy, display name, CTA button, destination URL
- Whether creatives are Spark Ads (requires authorization code) or non-Spark
- TikTok Pixel status: installed on landing page, target conversion event configured, test event fired successfully
- Conversion window selection: 1-day click, 7-day click, 1-day view, or combination
- UTM parameters and tracking URLs

## What This Skill Does
This skill runs a 10-category pre-launch checklist across campaign structure, targeting, bidding, creative, tracking, and compliance — producing a pass/fail verification report with specific fix instructions for any failed item before the campaign goes live.

## Analysis Workflow
1. Category 1 — Campaign Objective Alignment: Verify that the selected campaign objective matches the intended conversion action. TikTok's bidding and delivery algorithms are optimized entirely around the objective selected at campaign level. Mismatch (e.g., selecting Traffic objective for a conversion campaign) will deliver clicks without conversion optimization.
2. Category 2 — Bid Strategy Sanity Check: Verify that the bid strategy is appropriate for the account's conversion data maturity:
   - New accounts with no conversion history: Lowest Cost (no bid cap) is the only appropriate strategy
   - Accounts with 50+ conversions in the past 30 days: Cost Cap is viable
   - Bid Cap: rarely appropriate at launch, flag if selected
   - Verify that any stated Cost Cap is no more than 30% below historical average CPA
3. Category 3 — Budget Configuration: Verify daily budget is set above TikTok's recommended minimum (typically $20/day per ad set for conversion campaigns). Verify that lifetime budgets have a correct end date. Flag any budget below $50/day for conversion objective as high-risk for learning phase failure.
4. Category 4 — Audience Configuration: Verify targeting is not so narrow that audience size estimate falls below 500,000 (risk of fast audience exhaustion). Verify Lookalike source audience has minimum 100 seed users. Verify no inadvertent audience exclusions that block the primary target segment. Check for audience overlap with other running ad sets if relevant.
5. Category 5 — Creative Asset Verification: Verify video specs meet TikTok requirements: 9:16 aspect ratio (1080×1920 minimum), file size within limit (500MB max), duration within campaign format limits. Verify ad copy character counts are within limits. Verify display name is set correctly. Verify CTA button selection matches the campaign action.
6. Category 6 — Spark Ad Authorization: If running Spark Ads, verify that the authorization code from the creator has been entered, is not expired (Spark Auth codes expire after 30 days from generation), and the post is publicly accessible. A Spark Ad running on an expired auth code will be rejected or lose its social proof.
7. Category 7 — Destination URL and UTM Verification: Verify the destination URL loads correctly on mobile. Verify UTM parameters are correctly formatted and appended. Test the URL from a mobile device. Verify the URL does not redirect to a page that breaks tracking.
8. Category 8 — TikTok Pixel Verification: Verify Pixel base code fires on the landing page (check with TikTok Pixel Helper Chrome extension). Verify the target conversion event (Purchase, Lead, etc.) fires on the correct page (thank you page, confirmation page). Verify no duplicate pixel events that would inflate conversion reporting. Confirm conversion window settings match the sales cycle.
9. Category 9 — Ad Policy Pre-Screening: Review ad copy and creative description for common TikTok policy triggers: income claims, health claims without substantiation, before/after weight loss imagery, financial product claims, prohibited product categories. Flag any potential policy issues before submission.
10. Category 10 — Naming Convention and Tracking Hygiene: Verify campaign, ad set, and ad naming convention follows account SOP (client/account, objective, date, audience, creative type). Confirm all tracking parameters are documented in the account's tracking log.

## Output Requirements
- 10-category verification checklist with Pass / Fail / Warning per item
- Specific fix instructions for every Fail or Warning item
- Launch-ready classification: All Clear (launch now), Fix Required (specific items must be resolved first), or Hold (critical tracking or structural failure requiring full rebuild)
- Estimated time to fix all failures before resubmitting
- Post-launch monitoring checklist: what to check at 1 hour, 6 hours, and 24 hours after launch

## Platform-Specific Best Practices
- TikTok's Pixel event verification should always be performed on a mobile device, not desktop — TikTok traffic is 95%+ mobile and mobile-specific tracking issues are common.
- Spark Ad authorization codes must be requested from creators through TikTok Creator Marketplace or direct Spark authorization flow and are valid for 30 days. Always generate fresh codes within 7 days of planned launch.
- The conversion window selection on TikTok significantly affects which conversion events the algorithm optimizes for. For products with 1–3 day consideration cycles, 7-day click + 1-day view is the most stable setting.
- TikTok's ad review process can take 24–48 hours. Never plan a time-sensitive campaign launch without submitting creatives for review at least 48 hours before the intended start date.
- Budget below $50/day per ad set for a conversion objective will almost always result in a learning phase that never exits — the algorithm cannot gather enough conversion signals to optimize.

## Guardrails
- Do not launch a campaign with a Fail on the Pixel Verification item — running budget without conversion tracking produces unattributed spend that cannot be optimized or reported accurately.
- Do not launch a campaign without verifying the destination URL loads on mobile — broken landing pages are the single highest-cost launch error in TikTok Ads.
- Do not bypass the creative policy pre-screen — TikTok's automated review will flag policy issues but often after spend has begun, creating partial campaign delivery and wasted budget.
- Never launch a new account's first campaign with Cost Cap or Bid Cap — always start with Lowest Cost to allow the algorithm to build conversion signal before applying bid constraints.

## Example Requests
1. "I'm about to launch a new TikTok conversion campaign for a DTC skincare brand. Walk me through the full pre-launch verification checklist and tell me what to check in each category."
2. "I set up a new TikTok ad set with Spark Ads from two creators. Give me a complete launch verification checklist specifically for Spark Ad campaigns — what can go wrong and how do I verify everything is correct before going live?"
3. "My campaign launched but spend isn't being delivered. I think I may have made a setup error. Give me a systematic diagnosis checklist starting with the most common launch configuration errors."
