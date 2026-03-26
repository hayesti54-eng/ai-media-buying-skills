# Aggregated Event Measurement (AEM) Compliance Reviewer

**Platform:** Meta Ads
**Category:** diagnostics
**Tier:** agency

## Purpose

Audit and remediate compliance with Meta's Aggregated Event Measurement (AEM) framework, which governs how web conversion events are measured and reported for users who have opted out of tracking on iOS devices. AEM limits each domain to 8 prioritized conversion events, applies modeled (estimated) reporting for opted-out users, and requires domain verification before events can be configured. Non-compliance with AEM results in broken attribution, campaign delivery restrictions, and inability to optimize for key conversion events.

## When to Use

- When setting up any new advertising domain for the first time post-iOS 14.5
- When an advertiser has not yet verified their domain in Events Manager
- When conversion campaigns show unexplained drops in reported iOS conversions
- When an event that was previously used for optimization is no longer available as a campaign objective
- When agency is managing multiple client domains and needs to audit AEM configurations across all of them
- When a client acquires a new website or rebrands with a new domain
- After Events Manager shows a warning about unverified domains or unconfigured conversion events
- When a pixel is associated with the wrong Business Manager and conversion data ownership is disputed

## Inputs Required

- Business Manager account access with domain admin permissions
- Full list of domains in use across all active campaigns
- Current AEM event priority configuration in Events Manager
- List of all standard and custom conversion events in use across campaigns
- DNS access or hosting provider access (for domain verification via DNS or HTML file method)
- List of active campaigns and their optimization events
- Whether the advertiser is using multiple pixels across different subdomains or TLDs

## What This Skill Does

This skill conducts a full AEM compliance audit across all advertiser domains, verifying domain verification status, reviewing the 8-event priority configuration for strategic correctness, identifying conflicts between event usage in active campaigns and AEM priority configuration, and assessing the impact of modeled conversion reporting on account decision-making. It produces an AEM configuration plan that maximizes attribution coverage within AEM's structural constraints.

## Analysis Workflow

1. Navigate to Events Manager → Aggregated Event Measurement → Manage Events. List all domains currently shown and their verification status: Verified, Pending, or Unverified.
2. For any unverified domain, identify the appropriate verification method: DNS TXT record (preferred for stability), HTML meta tag (second choice), or HTML file upload (third choice). Flag unverified domains associated with any active campaign conversion events as critical — these campaigns may have restricted delivery or broken attribution.
3. Review the 8-event priority list for each verified domain. Assess whether the current priority order reflects actual business value: higher-funnel events (ViewContent, AddToCart) should occupy lower priority slots; revenue-generating events (Purchase, Subscribe, Lead) should occupy the top 1-3 priority slots.
4. Identify whether any active campaign is optimizing for an event that is NOT in the domain's 8-event priority list. Events not on the priority list are not reportable or optimizable for iOS opted-out users. This creates an attribution gap for a significant portion of the audience.
5. Check for duplicate events: if the same conversion event is being reported by both a browser pixel and a CAPI implementation on the same domain, AEM counts them as one event slot, but deduplication must be verified to prevent inflated reporting.
6. Audit event slot utilization: if fewer than 8 slots are configured, identify whether there are business-valuable events that could fill the empty slots. Empty slots are wasted measurement capacity.
7. Assess the 3-day click and 1-day view attribution window impact: AEM applies a limited attribution window for iOS opted-out users. If campaigns are using 7-day click or 28-day click windows, the AEM window will show materially lower conversions for iOS traffic. This must be communicated clearly in reporting.
8. For advertisers with multiple domains (e.g., main site + landing page domain + checkout domain), verify that each domain with pixel/CAPI events is independently verified and has its own AEM configuration. Subdomain events must roll up to the verified parent domain.
9. Check Business Manager domain ownership. A pixel must be owned by a Business Manager that has verified the domain. If a client's pixel is in an agency Business Manager and the domain is verified under the client's Business Manager, there can be AEM configuration conflicts.
10. Produce a full AEM compliance report with remediation steps.

## Output Requirements

- Domain verification status table: domain, verification method used, status, campaigns affected
- 8-event priority configuration review: current configuration vs. recommended configuration
- Event slot gaps: events being used in campaigns that are not in the priority list
- Attribution window impact assessment: estimated percentage of iOS conversions affected by AEM's 3-day click window
- Conflict log: any domain ownership, pixel ownership, or Business Manager conflicts
- Remediation plan: ordered list of actions to achieve full AEM compliance

## Platform-Specific Best Practices

- Domain verification must be completed at the root domain level (e.g., `yourdomain.com`), not the subdomain. Events on `shop.yourdomain.com` are covered under the root domain verification.
- AEM event priority can be changed at any time, but changes affect reporting retroactively for some data and can temporarily disrupt optimization for active campaigns.
- Meta applies modeled (estimated) reporting for iOS opted-out users. Actual conversion counts include both measured conversions (users who consented) and modeled conversions (statistical estimates). Modeled conversions are labeled in breakdowns.
- If two equally important events compete for the same priority slot (e.g., Lead and Subscribe both being used), model your iOS traffic mix to determine which event generates more value per conversion and prioritize accordingly.
- AEM compliance does not guarantee perfect iOS attribution. It maximizes the attribution that is technically possible within Apple's ATT framework constraints.

## Guardrails

- Do not remove an event from the AEM priority list while an active campaign is optimizing for that event. This will break iOS attribution for that campaign immediately.
- DNS TXT record verification is the most stable method. HTML file upload verification can break if the site is redeployed without preserving the verification file.
- AEM configurations are Business Manager-specific. Verify you are configuring AEM in the correct Business Manager, especially in agency accounts managing multiple clients.
- Modeled conversion data should never be presented as precise measurement. Always annotate AEM-modeled figures in client reports.

## Example Requests

1. "My client's domain is unverified and we're running Purchase optimization campaigns. What's the exact process to get domain verified and fix AEM, and what's the priority order for their 8 events?"
2. "I'm managing 6 client domains in one Business Manager. Walk me through auditing all of them for AEM compliance at once."
3. "My client has a main site on one domain and a Shopify checkout on a different domain. How do I set up AEM correctly across both domains?"
