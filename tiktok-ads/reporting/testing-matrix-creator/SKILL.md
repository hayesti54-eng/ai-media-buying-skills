# Creative Testing Matrix Creator

**Platform:** TikTok Ads
**Category:** reporting
**Tier:** agency

## Purpose
Design a structured, hypothesis-driven creative testing matrix for TikTok Ads that systematically isolates and validates one creative variable at a time across a defined test cycle — enabling operators and agencies to build a durable creative intelligence library rather than running ad hoc tests that produce ambiguous results. This skill turns creative testing from intuition-based iteration into a repeatable performance science.

## When to Use
- Launching a new TikTok Ads account and need to rapidly identify the winning hook mechanic, format, and offer angle
- Managing a multi-creative agency pipeline and need a structured framework for assigning test priorities and interpreting results
- Current account has been iterating creatives without a documented hypothesis — tests are running but no clear learnings are accumulating
- Scaling into a new product category, audience segment, or creative format and need to establish new performance baselines
- Building a quarterly creative intelligence document for a client or internal growth team

## Inputs Required
- Current known creative variables: which hook mechanics have been tested, which formats, which offer angles, which creator types, which CTAs
- Creative variables to test (choose from: Hook Mechanic, Creative Format, Offer Framing, Creator Style, CTA Type, Video Length, Caption Style, Music/Audio, Opening Visual, Social Proof Element)
- Testing budget per week: how much can be allocated to pure creative testing (separate from scaling budget)
- Production capacity: how many new creatives can be produced and launched per week?
- Current account CPA and ROAS benchmarks (to define what "winning" looks like in this matrix)
- Campaign objective and primary conversion event
- Audience targeting configuration: will tests run in the same ad set or different ad sets?

## What This Skill Does
This skill builds a structured creative testing matrix that organizes test variables into priority tiers, assigns hypotheses to each test, specifies isolation requirements (one variable change per test), defines success criteria and evaluation windows, and produces a testing calendar. The output is an actionable document that any media buyer or creative strategist can execute against.

## Analysis Workflow
1. Audit existing creative intelligence. List every variable that has already been tested and classify each as: Proven (confirmed working), Disproven (confirmed not working), Inconclusive (insufficient data), or Untested. This prevents redundant testing.
2. Identify the highest-priority unknown variables. Rank untested variables by potential impact on primary success metric:
   - Tier 1 (Highest Impact): Hook Mechanic, Creative Format, Offer Framing — these drive the most performance variance
   - Tier 2 (Medium Impact): Creator Style, CTA Type, Video Length, Social Proof Placement
   - Tier 3 (Optimization Layer): Caption Style, Music/Audio, Opening Visual, Text Overlay Timing
3. Build the testing matrix structure:
   - Column 1: Variable being tested
   - Column 2: Control (current best-performing version of that variable)
   - Column 3: Test Variant A
   - Column 4: Test Variant B (optional)
   - Column 5: Hypothesis statement ("We believe [Test Variant A] will outperform Control because [reason]")
   - Column 6: Success Metric and Threshold
   - Column 7: Required impressions/spend for statistical confidence
   - Column 8: Decision rule (what result at what threshold triggers a creative direction change)
4. Apply isolation enforcement. For each test, verify that only one variable is changing between the Control and Test Variant. Flag any planned test where multiple variables differ as a multi-variable test requiring separation.
5. Sequence the testing roadmap. Tier 1 variables are tested first in parallel (multiple Tier 1 tests can run simultaneously if budget allows). Tier 2 tests begin only after at least one Tier 1 variable is confirmed. Tier 3 tests optimize around confirmed Tier 1 and Tier 2 winners.
6. Define the evaluation window per test: at minimum 3 days and 1,000 impressions per variant; ideally 5 days and 2,000+ impressions for conversion-objective tests. Set calendar dates.
7. Write decision rules for each variable test:
   - Winner declared when: Test Variant CPA is 15% or more below Control AND has a minimum of 5 conversions
   - Inconclusive when: difference is less than 15% in either direction with insufficient volume
   - Loser declared when: Test Variant CPA is 20% or more above Control with sufficient volume
8. Build the creative intelligence summary that will be updated as each test concludes: a running record of every tested variable, outcome, and implication for future creative direction.
9. Calculate testing cadence metrics: tests per week, creative slots required per test, budget per test, projected time to complete full Tier 1 test matrix.

## Output Requirements
- Audit of existing creative intelligence: Proven / Disproven / Inconclusive / Untested per variable
- Prioritized variable testing list (Tier 1, 2, 3)
- Complete testing matrix table with all columns populated for each planned test
- Isolation verification checklist per test
- Testing calendar: which tests launch when, evaluation dates, decision dates
- Decision rules document: winner/loser/inconclusive thresholds per test
- Budget allocation plan: how much spend per test and how many tests can run simultaneously within budget
- Creative intelligence tracker template: running document format for capturing learnings as tests conclude

## Platform-Specific Best Practices
- TikTok creative testing benefits from running tests within the same ad set (same audience, same bid, same placement) to isolate creative variables from distribution variables. Use the Creative Optimization feature with creative-level data breakdown.
- Hook mechanic is the highest-leverage test variable on TikTok and should always be the first Tier 1 test priority for new accounts. Once the winning hook mechanic is identified, every subsequent test benefits from that anchor.
- TikTok's algorithm will self-optimize toward the winning creative within an ad set that runs multiple creatives — this is useful for scaling but fatal for controlled testing. For true isolation testing, run each creative in a separate ad set.
- Iteration cadence matters more than test perfection. A structured testing program that produces 3 learnings per week for 8 weeks builds more creative intelligence than a perfectly designed test that runs for 6 weeks and produces one finding.
- Always document disproven hypotheses. Knowing what does not work on TikTok for a specific audience is as valuable as knowing what does — it shapes brief direction and prevents repeated investment in dead-end angles.

## Guardrails
- Do not design tests that require more production capacity than the account can reliably execute — an unrun test is worse than no test.
- Do not run more Tier 1 variable tests than you have budget to evaluate properly — underfunded tests produce inconclusive results that waste production investment.
- Do not declare a winner from a single test cycle without a minimum conversion threshold — statistical noise on low-conversion-volume tests produces false winners.
- Never skip the hypothesis step in the testing matrix — testing without a hypothesis produces data but no learning.

## Example Requests
1. "I'm managing a TikTok account with a $4,000/month creative testing budget. I've been running UGC talking head ads but haven't tested hook mechanics systematically. Build me a complete creative testing matrix for the next 4 weeks."
2. "I have 5 creative variables I want to test for a new TikTok campaign launch: hook mechanic, video length, CTA type, creator gender, and offer framing. Build me a sequenced test matrix that isolates each variable properly."
3. "I'm running a TikTok ads program for 3 clients in the same vertical. Design a shared testing matrix I can use across accounts to build a cross-account creative intelligence library."
