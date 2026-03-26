# LSA Profile Completeness Checker

**Platform:** Google LSA
**Category:** operations
**Tier:** free

## Purpose
Perform a systematic completeness audit of a Google LSA business profile to ensure every available profile field is fully populated, every ranking signal is activated, and no configuration gap is silently suppressing ad delivery or conversion rate. Profile completeness is a direct LSA ranking input — incomplete profiles are algorithmically disadvantaged. This skill is free-tier because it requires no paid data access: every input is visible in the LSA profile settings and dashboard.

## When to Use
- At account setup, before the profile is submitted for Google's verification process
- After a verification-related profile edit (changes during verification can reset fields)
- When a profile is newly reinstated after a suspension
- During a standard quarterly profile health check
- When a client reports their ads "aren't showing" and more complex diagnostics have been ruled out
- When onboarding a client whose profile was previously self-managed

## Inputs Required
- Access to the Google LSA business profile (web or app)
- Business name, primary address, and all service locations
- Complete list of services the business offers (not just what is currently in LSA)
- Business description (if written — will draft if missing)
- All current photos in the LSA profile
- Verified license and insurance documentation status
- Current business hours including holiday and special hours settings
- Current review count visible on the profile

## What This Skill Does
Steps through every configurable profile element in LSA and checks for completeness, accuracy, and optimization quality. Goes beyond binary "filled/not filled" to assess whether each field is strategically populated: is the business description keyword-aware for service intent? Are job types configured to match the actual business offering without over-selection? Are photos present and appropriate for the vertical? Is the service area set with precision rather than maximum radius? Outputs a completeness scorecard with a priority-ranked fix list.

## Analysis Workflow
1. Verify Google Guarantee or Google Screened badge status — confirm the verification is active and not expired or flagged.
2. Check business name for accuracy — confirm it matches the legal business name used in the verification documents.
3. Confirm primary business address is correct and matches the address used in the Google Business Profile.
4. Audit job types: list every job type currently selected, compare against the business's actual service offerings, flag over-selections (job types selected that the business does not perform) and under-selections (services offered but not selected).
5. Check business description: confirm it is populated, reads naturally, references the primary service and service area, and is within the character limit without truncation.
6. Count photos in the profile — flag if fewer than 3 photos are present; flag if photos are low quality, irrelevant, or stock images.
7. Verify business hours: confirm all 7 days are set accurately, special hours for holidays are configured, and hours match actual staffing availability.
8. Confirm service area: assess whether the service area is set to zip codes/cities (preferred) or radius, and whether the coverage reflects actual operational reach.
9. Check license and insurance expiration dates if accessible — alert if any credentials are within 60 days of expiration.
10. Review the intro/tagline field if available — confirm it is populated with a value-differentiating statement.
11. Check whether the business has linked its Google Business Profile — this connection supports review display and profile cohesion.
12. Compile the completeness scorecard: each element rated Complete, Partial, or Missing with fix priority assigned.

## Output Requirements
- Profile completeness scorecard: each profile element with status (Complete / Partial / Missing) and fix priority (P1 / P2 / P3)
- Job type audit: current selections vs. recommended selections — additions and removals recommended
- Business description assessment: quality score and improvement recommendations or full rewrite if needed
- Photo audit: current count, quality assessment, recommended additions
- Hours verification: accuracy confirmation or correction recommendations
- Credential status alert: any licenses or insurance approaching expiration
- Prioritized fix list: top 5 completeness actions ranked by ranking impact

## Platform-Specific Best Practices
- Job type over-selection (adding job types the business cannot perform) generates low-quality leads and suppresses booked lead rate — it is actively harmful, not neutral.
- The business description is read by Google's systems as well as prospective customers — include the primary service category and city naturally.
- Profile photos in LSA are not just trust signals for customers; they are completeness signals for Google's ranking algorithm — blank photo sections are a ranking disadvantage.
- License and insurance expiration is the most common cause of unexpected profile deactivation — set a 60-day advance reminder for every credential on file.
- The service area should never be set to maximum radius as a default — it is an invitation for out-of-area leads and proximity signal dilution.
- A complete profile does not guarantee top rank — but an incomplete profile guarantees a ranking ceiling.

## Guardrails
- Do not add job types to improve completeness score if the business genuinely cannot perform them — this is a profile quality failure, not an improvement.
- Do not recommend a business description that is keyword-stuffed or sounds robotic — Google's review team reads these during verification.
- Photo recommendations must consider brand appropriateness — not all businesses should use the same photo style (a law firm and a plumber have different visual standards).
- Do not change the business name in the profile without confirming it matches verification documents — mismatches trigger re-verification.

## Example Requests
1. "Run a full profile completeness check on our new LSA account before we submit it for verification — tell me everything that's missing."
2. "Our client has been live on LSA for 6 months but their profile still looks like it was set up in 5 minutes. Audit it and give me a prioritized fix list."
3. "Check whether our job types are configured correctly — I think we have some selections that are hurting our lead quality."
