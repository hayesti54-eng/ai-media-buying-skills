# Incrementality & Lift Study Interpreter

**Platform:** Meta Ads
**Category:** reporting
**Tier:** agency

## Purpose

Interpret and operationalize the results of Meta's Conversion Lift and Brand Lift studies to determine the true incremental value of Meta advertising — meaning the conversions or brand outcomes that would not have occurred without the ads. Platform-reported ROAS and conversion attribution overstate true incremental impact because they include conversions that would have happened organically. This skill translates lift study outputs into actionable decisions about budget allocation, campaign continuation, and true cost per incremental result.

## When to Use

- After a Conversion Lift or Brand Lift study has completed and results are available in Test and Learn
- When a client questions whether Meta ads are actually driving sales or just claiming credit for organic conversions
- When cross-channel attribution is contested and Meta's self-reported ROAS needs validation
- When considering a significant budget increase and needing to justify the decision with incrementality data
- When evaluating whether to continue a campaign type that shows strong attributed ROAS but uncertain incremental value
- For mature, high-spend accounts (>$50,000/month) where the difference between attributed and incremental results is financially significant
- When preparing a media mix modeling or multi-touch attribution analysis

## Inputs Required

- Lift study type: Conversion Lift or Brand Lift
- Study results from Test and Learn: treatment group size, control group size, test period, confidence level, lift percentage, absolute lift (incremental results), cost per incremental result
- Attributed results from Ads Manager for the same campaign and time period: reported conversions, reported ROAS, reported cost per result
- Confidence interval on the lift estimate
- Statistical significance level: Meta requires a minimum confidence level (typically 80%+) before reporting lift
- Total spend during the study period
- Baseline conversion rate of the control group

## What This Skill Does

This skill interprets lift study outputs to calculate the true incremental cost per result, compares incremental cost per result against platform-attributed cost per result to quantify attribution inflation, assesses the statistical reliability of the lift findings, identifies what the results mean for budget continuation and optimization decisions, and flags limitations and caveats of the study design that affect how actionable the findings are.

## Analysis Workflow

1. Retrieve the core lift study outputs: incremental conversions (absolute lift × treatment group), percentage lift, confidence level, and cost per incremental result (CPIR). The CPIR is the primary operational metric — it is total spend divided by incremental conversions, not attributed conversions.
2. Compare CPIR to attributed cost per result. Calculate the attribution inflation ratio: CPIR ÷ attributed cost per result. An inflation ratio of 2.0 means the campaign is claiming credit for 2x more conversions than it actually caused. An inflation ratio of 1.2-1.5 is typical and acceptable. Ratios above 3.0 indicate significant over-attribution.
3. Assess statistical significance. A confidence level below 80% means the lift estimate is not reliable enough to make budget decisions. Flag studies with low confidence and recommend extending the study or increasing reach to improve statistical power.
4. Evaluate the control group construction. Meta's Conversion Lift uses a ghost bidding methodology — the control group sees the same auction but the ad is withheld. The control and treatment groups must be comparable in composition. Note any study period anomalies (major sales events, creative changes mid-study) that may have contaminated the results.
5. Calculate the incremental ROAS (iROAS): incremental revenue attributed to lift ÷ total spend during study period. Compare this to the platform-attributed ROAS. If iROAS is above 1.0 and above the industry threshold for the business type, the campaign is generating incremental value.
6. Assess the conversion baseline (control group conversion rate). A high baseline conversion rate means the audience has significant organic purchase intent — the incremental lift from advertising is therefore a smaller proportion of total conversions. This does not mean the campaign is not valuable; it means it is working in a high-intent environment.
7. Identify which campaign types or audience segments were included in the study. Lift studies run at the campaign level and may not capture the full account's impact. Extrapolate findings only to campaigns with similar structure, audience, and objective.
8. For Brand Lift studies: interpret ad recall lift, brand awareness lift, and purchase intent lift as leading indicators. Connect to downstream conversion outcomes only if longitudinal data is available.
9. Produce a clear verdict: Is the campaign incrementally valuable at its current cost? Should budget be increased, maintained, or reduced based on incremental efficiency?
10. Identify the minimum efficient spend level: the budget level below which incremental reach drops below the break-even CPIR threshold.

## Output Requirements

- Lift study summary: test type, period, confidence level, lift %, incremental results, CPIR
- Attribution inflation ratio: CPIR ÷ attributed cost per result
- Incremental ROAS (iROAS) vs. attributed ROAS
- Statistical reliability assessment: confidence level evaluation, study limitations
- Business verdict: continue at current budget / increase budget / reduce budget / pause and retest, with supporting rationale
- Recommended next test: what should be tested in the follow-up lift study to answer the next strategic question

## Platform-Specific Best Practices

- Meta's Conversion Lift requires a minimum audience size and spend level to produce statistically significant results. For most SMB accounts under $20K/month, lift studies will not reach statistical significance — this is an agency-tier tool for appropriately scaled campaigns.
- Lift studies should be run on evergreen campaigns, not promotional or sale campaigns, for the most accurate baseline. A sale event inflates both the test and control group conversion rates and distorts the incremental measurement.
- The study period should be at least 2 weeks to capture delayed conversions in the attribution window. Shorter studies undercount conversions that occurred after the last ad impression.
- Meta's lift studies measure incremental conversions within their own platform — they do not measure offline, call, or cross-device conversions that were influenced by Meta ads but converted outside Meta's measurement environment.
- iROAS above 2.0 for DTC brands and above 3.0 for e-commerce brands generally supports budget continuation. Below 1.0 iROAS means the campaign is consuming more than it returns incrementally.

## Guardrails

- Do not make budget scaling decisions based on a single lift study. Run at least two studies (different seasons or campaign types) before drawing structural conclusions about incremental value.
- Do not present lift study CPIR to clients without explaining that it will always be higher than attributed cost per result and why.
- Do not run a lift study during a major promotional period. The study contamination will make results unreliable.

## Example Requests

1. "My Conversion Lift study shows 23% lift at 85% confidence, incremental CPIR of $62, but my attributed cost per purchase in Ads Manager is $28. Walk me through interpreting this gap."
2. "My client is questioning whether their $40K/month Meta spend is actually driving new customers or just claiming credit for people who would have bought anyway. How do I use lift study data to answer that?"
3. "My Brand Lift study shows 18% ad recall lift and 9% purchase intent lift. How do I connect these brand metrics to downstream conversion outcomes to justify continued investment?"
