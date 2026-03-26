# Meta Campaign Launch Verifier

**Platform:** Meta Ads
**Category:** launch
**Tier:** pro

## Purpose

Conduct a pre-launch audit of a Meta Ads campaign to confirm that all technical, structural, and strategic components are correctly configured before spending begins. A missed pixel event, incorrect optimization selection, wrong attribution window, or misaligned bid strategy discovered after $2,000 of spend is more costly than the 20 minutes required to run this checklist. This skill catches errors before they become expensive.

## When to Use

- Before activating any new campaign, adset, or ad
- After making significant structural changes to an existing campaign (new audience, new bid strategy, new optimization event)
- When a team member other than the primary account manager built the campaign
- When launching a campaign for a new client whose account setup may have legacy issues
- When duplicating a campaign from another account and adapting it for a new context
- Before scaling a campaign (increasing budget significantly) to ensure the foundation is solid

## Inputs Required

- Access to the campaign in Ads Manager (draft or review mode)
- Access to Events Manager to verify pixel and CAPI configuration
- Campaign objective and the corresponding business goal
- Bid strategy and target cost (if Cost Cap or Bid Cap)
- Attribution window setting
- Pixel events being used for optimization
- Landing page URL
- Target audience definition
- Budget (daily or lifetime) and campaign dates
- Creative assets and their approval status

## What This Skill Does

This skill runs a 10-point pre-launch verification protocol covering pixel integrity, campaign objective alignment, bid strategy configuration, audience setup, creative compliance, attribution window correctness, ad scheduling, tracking parameters, and landing page accessibility. Each checkpoint is a binary pass/fail with a specific corrective action for each failure.

## Analysis Workflow

1. Pixel and event verification: confirm the pixel is installed on the landing page and firing the correct optimization event. Navigate to Events Manager → Test Events → enter the landing page URL → complete the conversion action → confirm the event fires with correct parameters. A pixel that fires on the wrong page or wrong event is the most common launch error.
2. Campaign objective alignment: confirm the campaign objective matches the business goal. Purchase campaigns require the Purchase event in Events Manager; Lead Generation campaigns should use either Lead Ads or the Lead event from a website form. Using Traffic objective when the goal is conversions wastes spend on unoptimized clicks.
3. Bid strategy verification: confirm the bid strategy is appropriate for the campaign's stage and conversion volume. New campaigns with no historical data should launch on Lowest Cost, not Cost Cap or Bid Cap. If Cost Cap is selected, confirm the cap is set at no lower than 10% above the actual target CPA to allow delivery room.
4. Optimization event check: confirm the selected optimization event matches the stage of the funnel the campaign is designed for, and that the event fires more than 50 times per week at the account level. If not, flag the event as under-volume and recommend a higher-funnel event.
5. Attribution window confirmation: verify the attribution window is set intentionally, not left at default. The default 7-day click + 1-day view window attributes more conversions than a 1-day click window. Confirm the window aligns with the product's typical purchase consideration period.
6. Audience setup review: confirm the defined audience (custom audience, Lookalike, or interest stack) is correctly constructed, has no unintended geo restrictions, and the size estimate is within operational range (>500K for prospecting). Confirm exclusion audiences are applied (exclude past purchasers from prospecting, exclude cold audiences from retargeting).
7. Creative compliance check: confirm all ads are in "Approved" or "Active" status, not "In Review" or "Rejected." For ads still in review at launch time, confirm there are backup approved ads in the adset to maintain delivery. Check text overlay compliance and that no copy violates Meta's advertising policies.
8. UTM and tracking parameter verification: confirm all destination URLs contain UTM parameters (utm_source, utm_medium, utm_campaign, utm_content) or that Meta Value Ruler or GA4 tracking is configured. Without UTM parameters, campaign attribution in Google Analytics and downstream reporting tools will be broken.
9. Landing page accessibility test: open the destination URL on mobile (not desktop) and confirm: page loads in under 3 seconds, the page is accessible without an app or account, the page is not behind a geo-block that would prevent the target audience from seeing it, and the conversion action is functional (form submits, add to cart works, checkout is accessible).
10. Budget and schedule confirmation: confirm daily budget or lifetime budget is set correctly. If lifetime budget is used, confirm the campaign end date is set and the delivery schedule matches the business's operational hours (no point spending on a lead gen campaign at 2 AM if the sales team only operates 8 AM-6 PM).

## Output Requirements

- Pre-launch verification checklist: each checkpoint with pass/fail status and specific issue description on failure
- Critical blockers: items that must be resolved before launch (pixel error, rejected ads, wrong optimization event)
- Non-critical warnings: items that are suboptimal but won't prevent delivery (missing UTMs, default attribution window not reviewed)
- Estimated time to resolve all issues
- Launch go/no-go recommendation

## Platform-Specific Best Practices

- Always test the pixel using Meta's Pixel Helper Chrome extension or Test Events in Events Manager before launch, not after the campaign starts spending.
- AEM domain verification must be complete before launching web conversion campaigns targeting iOS audiences. Verify domain status in Events Manager before launch.
- Set up custom conversion columns in Ads Manager before launch so your performance dashboard is ready when data starts coming in. Post-launch column setup means you miss early data patterns.
- If using a new pixel with no conversion history, expect 1-5 days of higher CPA during the algorithm's initial learning. This is expected; do not make bid or budget changes within the first 72 hours of a new pixel campaign.
- Check that the Facebook Page and Instagram Account associated with the campaign are the correct brand accounts, not default or placeholder accounts. Incorrect Page associations affect ad delivery and brand trust scoring.

## Guardrails

- Do not launch a campaign if the optimization event pixel is not verified and firing correctly. The campaign will spend without meaningful optimization signal.
- Do not launch with a Cost Cap set below the account's 30-day average CPA if no historical data exists for that specific campaign. The cap will prevent delivery.
- Do not proceed past a rejected ad without understanding the rejection reason. Launching a campaign with rejected ads in the adset means delivery is reduced to only the approved ads, which may not be your intended test setup.

## Example Requests

1. "I've built a new lead gen campaign for a home services client. Walk me through a complete pre-launch check before I activate it."
2. "My team duplicated a campaign from another client account and adapted it. What do I need to verify to make sure nothing carried over incorrectly?"
3. "I'm about to launch my first Meta Ads campaign ever. Walk me through everything I need to check before hitting the publish button."
