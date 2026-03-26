# Bid Strategy Selector — Cost Cap vs Bid Cap vs Lowest Cost

**Platform:** Meta Ads
**Category:** launch
**Tier:** pro

## Purpose

Select the correct Meta Ads bid strategy for a given campaign stage, objective, and business constraint. Choosing the wrong bid strategy is a structural error that causes either delivery failure (Cost Cap or Bid Cap set too aggressively), cost inefficiency (Lowest Cost running without controls when cost efficiency is required), or learning phase instability. This skill maps campaign conditions to the correct bid strategy with specific configuration guidance.

## When to Use

- When launching a new campaign and selecting a bid strategy for the first time
- When a campaign is delivering but costs are too high and you need to add a cost control
- When a campaign has a Cost Cap or Bid Cap that is preventing delivery
- When transitioning a campaign from the learning phase to scaled delivery
- When a campaign's cost controls need to be recalibrated after a significant performance shift
- When an account has a strict CPA or ROAS target that must be met for the campaign to be viable
- When evaluating whether to switch from Lowest Cost to a cost control strategy after accumulating sufficient data

## Inputs Required

- Campaign objective: conversions (purchase, lead), traffic, awareness, app installs
- Historical account data: average CPA or ROAS over the last 30 days for the same or similar campaign type
- Budget: daily or lifetime, with absolute ceiling
- Conversion volume: estimated or historical weekly optimization events per adset
- Business constraint: hard CPA ceiling, target ROAS floor, or no constraint (maximize volume)
- Campaign stage: new (no history) vs. active (stable delivery) vs. scaling (budget increase)
- Audience type: cold prospecting vs. warm retargeting

## What This Skill Does

This skill applies Meta's bid strategy decision framework to the specific campaign conditions, recommends the correct strategy with configuration parameters, explains the delivery behavior and risk profile of the recommended strategy, and identifies the conditions under which the strategy should be changed. It prevents the two most common bid strategy errors: launching new campaigns with aggressive cost controls (which causes delivery failure) and running mature campaigns without cost controls (which causes cost drift).

## Analysis Workflow

1. Assess campaign history: does the account have at least 30 days of conversion data for a similar campaign type? If no: Lowest Cost is the required starting strategy. Cost Cap and Bid Cap require historical conversion data to calibrate — without it, they prevent delivery.
2. Assess conversion volume: does the target adset generate at least 50 optimization events per week? If below 50/week: Lowest Cost with no controls. Insufficient volume for cost controls to function reliably.
3. Assess the business constraint: is there a hard CPA ceiling the campaign cannot exceed, or is the goal to maximize volume within a budget? Hard CPA ceiling → Cost Cap. Maximize volume → Lowest Cost. If the goal is to win specific auction slots at a maximum bid price (not average cost) → Bid Cap.
4. Define Lowest Cost: Meta automatically bids to get the most results at the lowest cost within the budget. No cost control is applied. Delivery is uncapped. CPA will fluctuate as the algorithm explores the audience. Best for: new campaigns, learning phase, audiences where true cost efficiency is unknown, campaigns without hard CPA targets.
5. Define Cost Cap: you set the average cost per result you are willing to pay. Meta optimizes to achieve the average cost at or below your cap across the campaign. Individual results may cost above or below the cap; the average is controlled. Best for: campaigns with known CPA targets and sufficient conversion history (50+ results/week). Configuration rule: set the Cost Cap at 10-20% above your actual target CPA to allow delivery room. Setting it at the exact target CPA will cause delivery throttling.
6. Define Bid Cap: you set the maximum bid Meta can place in any single auction. This is not a cost per result control — it is a per-auction bid ceiling. Meta will not bid above this amount in any single impression auction. Best for: advertisers who deeply understand Meta's auction mechanics, want precise bid control over specific inventory, or are managing brand safety through bid-level access control. Not recommended for most direct response advertisers because it causes severe delivery restriction.
7. Define Highest Value (ROAS target): for e-commerce campaigns optimizing for purchase value, ROAS target bids to achieve a minimum return on ad spend. Best for: accounts with widely varying order values where optimizing for revenue yield, not just conversion count, is the goal.
8. Map the campaign conditions to the decision matrix: New campaign → Lowest Cost. Known CPA target, 50+ conversions/week → Cost Cap. Auction-level bid control required → Bid Cap. Maximize order value with ROAS target → Highest Value.
9. Configure the selected strategy: for Cost Cap, calculate the recommended cap based on historical CPA + 15% buffer. For Bid Cap, assess average CPMs and conversion rates to determine the economically viable maximum bid. For ROAS target, set the target at 10% below the minimum acceptable ROAS to allow algorithmic room.
10. Specify the conditions for switching to the next strategy: what performance thresholds or data accumulation milestones trigger a strategy upgrade.

## Output Requirements

- Recommended bid strategy with rationale tied to campaign conditions
- Configuration parameters: specific cap or target value to use, with calculation shown
- Delivery behavior explanation: what the algorithm will do with this strategy and what normal delivery looks like vs. a delivery problem
- Risk profile: what can go wrong with this strategy and how to detect it early
- Strategy transition roadmap: when to switch from Lowest Cost → Cost Cap → potentially Bid Cap, with specific trigger conditions

## Platform-Specific Best Practices

- Cost Cap campaigns require significantly more budget than Lowest Cost campaigns to maintain delivery. A Cost Cap set at $30 with a $30/day budget means Meta can only make one conversion per day before exhausting the cap headroom. Ensure budget is at least 5-10x the Cost Cap per day.
- Lowering a Cost Cap mid-campaign resets learning. Raise it first (if delivery is constrained), let the campaign stabilize, then lower it gradually.
- Bid Cap is almost never the right strategy for conversion-objective campaigns. It is primarily used by large advertisers managing brand safety budgets or reach/CPM-sensitive media buyers.
- In CBO campaigns, the bid strategy applies at the campaign level and affects all adsets. If individual adsets need different bid strategies, they must be in separate campaigns.
- Lowest Cost without any controls will always seek the cheapest conversions available — which may be low-value users. For accounts with customer value differences (high LTV vs. low LTV customers), Highest Value (ROAS target) aligns bidding with revenue outcomes.

## Guardrails

- Do not set a Cost Cap below the account's 30-day average CPA on a new campaign. The algorithm has no signal to find conversions below a floor it has never achieved.
- Do not switch bid strategies during the learning phase. Strategy changes reset learning.
- Do not use Bid Cap for conversion campaigns without a deep understanding of your conversion rate and average auction dynamics. Incorrect Bid Cap settings cause near-zero delivery.

## Example Requests

1. "I'm launching a new purchase campaign with no prior data in the account. What bid strategy should I use and how do I configure it?"
2. "My Lowest Cost campaign has been running for 6 weeks and my CPA has drifted from $22 to $41. Should I switch to Cost Cap and how do I configure it without killing delivery?"
3. "My client has a hard CPA ceiling of $35 for leads. They've been running for 3 months and average $29 CPA. Which bid strategy should I use and what should I set the cap at?"
