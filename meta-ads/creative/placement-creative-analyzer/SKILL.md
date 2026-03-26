# Placement-Creative Fit Analyzer

**Platform:** Meta Ads
**Category:** creative
**Tier:** pro

## Purpose

Evaluate whether ad creatives are properly formatted, dimensioned, and behaviorally optimized for each Meta placement where they are being served. Creative-placement mismatch — running a landscape video in Stories, serving a text-heavy static in Reels, or using a 1:1 image in a right-column placement — degrades performance through lower Thumbstop, lower click-through rates, and wasted impressions. This skill audits creative fit across all active placements and identifies where mismatched creative is costing performance.

## When to Use

- When using Advantage+ Placements and want to confirm creative assets are meeting all placement format requirements
- When a campaign is running on automatic placements but only one or two placements were designed for
- When Stories or Reels placements have significantly lower CTR or higher CPM than Feed placements
- When reviewing a new creative asset before launch to validate format across all target placements
- When a client provides creative assets built for a different platform (TV, YouTube, billboard) and assets need to be adapted for Meta
- When diagnosing why a creative that performs well on one placement underperforms on another

## Inputs Required

- Creative asset specifications: dimensions (width × height in pixels), aspect ratio, file type, file size, video length (if applicable), text overlay percentage
- List of placements being targeted: Facebook Feed, Instagram Feed, Facebook Stories, Instagram Stories, Facebook Reels, Instagram Reels, Audience Network, Messenger, Facebook Right Column, Facebook Marketplace
- Primary text character count
- Headline and description character count
- Whether creative has audio (and whether critical information depends on audio being on)
- Whether creative contains logos, CTAs, or critical text overlaid on the visual

## What This Skill Does

This skill maps each creative asset against Meta's current technical and behavioral requirements per placement, identifies format violations (wrong aspect ratio, video too long for placement) and behavioral mismatches (landscape video in vertical placement, audio-dependent creative where 85% of users watch muted), and produces a placement-specific asset optimization plan. It separates hard violations (creative will not serve) from soft violations (creative will serve but underperforms).

## Analysis Workflow

1. Map each creative asset to Meta's required specifications per placement. Key specifications: Facebook/Instagram Feed (1:1 or 4:5 recommended, 1.91:1 landscape supported; video max 240 minutes but 15-30 seconds optimal); Stories (9:16 required, 1080×1920 recommended, max 15 seconds for image and 60 seconds for video with first 5 seconds critical); Reels (9:16 required, max 60 seconds, first 3 seconds must hook); Right Column (1:1, minimum 1080×1080); Audience Network Interstitial (9:16 or 16:9, 30 seconds max).
2. Identify aspect ratio mismatches. A 16:9 (landscape) video served in Stories will be pillarboxed with black bars and occupy approximately 50% of the screen — effectively a half-size ad at full-size auction price.
3. Evaluate video length against placement best practices: Feed video over 60 seconds is unlikely to be watched to completion; Stories video over 15 seconds will be cut off. Identify any videos that are technically allowed but behaviorally mismatched.
4. Audit text overlay: Meta's previous 20% text rule was retired, but text-heavy creatives still receive reduced delivery scores. Check whether critical information (price, CTA, offer) is overlaid on the visual and whether it fits within the safe zones for each placement (e.g., Stories safe zones avoid the top 14% and bottom 20% of the screen to prevent overlap with UI elements).
5. Assess audio dependency: if the video's message is only comprehensible with audio on, the creative is behaviorally mismatched with Meta's feed environment where 85%+ of video is watched muted. Check whether captions or on-screen text carry the full message independently of audio.
6. Evaluate hook timing for Reels specifically: the first 3 seconds must deliver the visual hook before the user swipes. Creatives that open on a logo, a black screen, or a slow pan are structurally mismatched with Reels consumption behavior.
7. Check safe zone compliance for logos and CTAs: on Stories and Reels, logos or CTAs placed in the bottom 20% of the frame will be covered by the platform's UI (like button, share button, CTA overlay). On Facebook Feed, the right edge of the image may be partially obscured on some devices.
8. For carousel ads: check that each card image has a consistent visual style, that card-level headlines are under 40 characters, and that the last card (which serves as an organic-looking card by default) matches the campaign's CTA intention.
9. Evaluate the creative against Advantage+ Creative's automatic enhancement features: if Advantage+ Creative is enabled, Meta may add music, change aspect ratios, apply image enhancements, or add text overlays. Assess whether the original creative would be degraded or improved by these automatic enhancements.
10. Produce a placement-creative fit matrix with severity of each misfit and recommended asset modifications.

## Output Requirements

- Placement-creative fit matrix: each creative × each placement, fit status (Optimal / Acceptable / Suboptimal / Violation), specific issue if not optimal
- Hard violations: placements where the creative will not serve or will be severely degraded
- Soft violations: placements where the creative serves but underperforms against native format standards
- Asset modification list: specific changes required per creative per placement (resize, trim, add captions, reformat)
- Priority recommendation: which placement-creative pairs to fix first based on spend allocation and estimated performance lift

## Platform-Specific Best Practices

- The 9:16 vertical format is the native format for Stories and Reels. Any budget allocated to these placements with non-vertical creative is effectively discounted.
- Captions on video ads increase view time by 12% on average on Meta placements. They are not optional for muted-environment performance.
- For Reels specifically: native-feeling creative (shot on phone, no heavy production value, authentic tone) consistently outperforms polished broadcast-style creative in the Reels environment.
- Advantage+ Placements will automatically resize and reformat creatives when technically possible. Automatic reformatting often results in center-cropping images in ways that cut off important visual elements. Always preview how Meta will crop your creative before enabling Advantage+ Placements.
- Right Column ads have a much lower CTR than Feed ads but cost less per impression. They work best for retargeting with simple, high-contrast visual and clear offer.

## Guardrails

- Do not disable specific placements without analyzing their CPM relative to Feed. Right Column and Audience Network often have cheaper CPMs that can support profitable retargeting.
- Do not assume that a creative that performs well on Instagram Feed will perform equally on Facebook Feed. Audience behavior and creative expectations differ between platforms.
- Do not over-optimize for a single placement at the expense of format flexibility. Building assets in 9:16, 1:1, and 4:5 from the start provides full coverage.

## Example Requests

1. "I have a 16:9 YouTube video that I want to repurpose for a Meta campaign targeting Feed, Stories, and Reels. What do I need to change for each placement?"
2. "My Stories placement is spending 30% of my budget but generating 5x worse CPA than Feed. My creative is a landscape image. Is format the problem?"
3. "I'm using Advantage+ Placements and I only built one 1:1 static image ad. Walk me through what Meta is doing with my creative across all placements and what I'm probably missing."
