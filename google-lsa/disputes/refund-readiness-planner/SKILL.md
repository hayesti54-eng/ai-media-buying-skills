# Refund Readiness Planner

**Platform:** Google LSA
**Category:** disputes
**Tier:** agency

## Purpose
Build a systematic, proactive refund readiness operation that ensures no eligible LSA lead dispute is missed, no dispute window expires without review, and every approved credit is tracked through to confirmed application on the account. Refund readiness is agency-grade because it requires building a durable operational process — not just reacting to individual disputes, but designing a system that consistently recovers eligible credits across multiple clients, accounts, and billing periods. At scale, consistent dispute execution is a measurable service differentiator.

## When to Use
- When onboarding a new LSA client who has never had a dispute process in place
- When taking over an existing LSA account where multiple months of disputes have been missed
- When managing 5+ LSA accounts and needing a standardized dispute cadence across the portfolio
- When a client questions why they are not recovering any credits despite apparently poor lead quality
- Quarterly, to audit the dispute process itself — not just individual disputes

## Inputs Required
- Lead history for the past 60 days: all charged leads across the account(s) in scope
- Prior dispute submission history: dates submitted, reason categories, approval/denial outcomes, credits received
- Current dispute review cadence (if any exists): how often leads are reviewed and who is responsible
- Account access status: confirmation that the account manager has dispute submission access in the LSA dashboard
- Any historical months where disputes were not filed at all — estimate the missed credit exposure
- Budget and spend data to contextualize dispute credit as a percentage of total spend

## What This Skill Does
Audits the current state of dispute recovery across the account or account portfolio, identifies any backlog of unreviewed leads (with urgency classification based on dispute window expiration), builds a forward-looking weekly dispute review calendar, establishes the criteria and documentation standard for each dispute reason type, and produces a credit recovery tracker that connects disputes filed to credits approved to credits confirmed on the account. For agencies managing multiple clients, it also produces a portfolio-level dispute dashboard.

## Analysis Workflow
1. Pull the full 60-day lead log — identify every lead that has not been reviewed for dispute eligibility.
2. Sort unreviewed leads by charge date, oldest first — flag any lead within 15 days of the 60-day dispute window closing as URGENT.
3. Apply the rapid invalid lead triage to all unreviewed leads — identify the disputable subset.
4. Estimate the total credit exposure in the unreviewed backlog: (disputable lead count × average charge per lead).
5. Audit prior dispute submissions: calculate the overall approval rate, identify the most and least successful dispute reason categories.
6. Identify any patterns in denied disputes — determine whether denials are due to insufficient evidence, wrong category selection, or legitimate ineligibility.
7. Build the weekly dispute review calendar: set a specific day and time each week for lead review, documentation, and submission. Assign a responsible party.
8. Define the minimum documentation standard for each dispute reason type: what evidence is required before a dispute is filed.
9. Build the credit recovery tracker: a rolling log of disputes filed, outcomes, credit amounts approved, and confirmation that credits have been applied to the account balance.
10. For multi-client agencies: build a portfolio-level dispute summary showing dispute activity, approval rates, and credit recovery across all accounts.
11. Establish an escalation protocol for denied disputes: when to resubmit, what additional evidence to gather, and when to accept the denial.
12. Produce the refund readiness plan: process documentation, calendar, tracker template, and backlog remediation schedule.

## Output Requirements
- Dispute backlog report: all unreviewed leads sorted by urgency, estimated credit exposure, and action deadline
- Prior dispute performance audit: approval rate, top approved categories, top denied categories, root cause of denials
- Weekly dispute review calendar: specific day/time, responsible party, expected time investment
- Documentation standard by dispute type: minimum evidence required for each reason category
- Credit recovery tracker template: rolling log of disputes filed → outcomes → credits confirmed
- Portfolio dispute dashboard (if multi-account): aggregate metrics across all client accounts
- Refund readiness score: overall assessment of the current dispute operation (0–10) with specific gaps identified

## Platform-Specific Best Practices
- The 60-day dispute window is absolute — Google will not process disputes filed after 60 days regardless of how valid they are. Build the process around 45-day maximum review age.
- Approved dispute credits are applied to the next billing cycle — they do not appear as immediate refunds. Track them in the credit tracker to confirm they are applied correctly.
- Dispute approval rates vary by account history — accounts with a high prior approval rate and low abuse pattern receive more favorable treatment on borderline cases.
- At scale (10+ client accounts), a weekly dispute review cadence across all accounts requires approximately 2–4 hours per week — factor this into service delivery time estimates.
- Denied disputes can typically be resubmitted once with additional evidence within 30 days of the denial — build this into the escalation protocol.
- Some verticals (legal, financial) have lower LSA dispute approval rates due to Google's higher scrutiny of lead legitimacy claims — calibrate expectations accordingly.

## Guardrails
- Refund readiness planning must not create a culture of disputing every lead — it creates a culture of disputing every eligible lead. Quality control is the standard.
- Do not guarantee specific credit amounts to clients — approval is at Google's discretion and past approval rates do not guarantee future results.
- Credit tracking must be verified against actual billing statements — approved credits do not always appear as expected and must be confirmed.
- Any agency offering dispute management as a service must disclose the process limitations: disputes may be denied, and Google's criteria can change without announcement.

## Example Requests
1. "We just took over an LSA account that hasn't filed a single dispute in 8 months. Run a refund readiness assessment — how much potential credit has been missed and what do we do first?"
2. "I manage 12 LSA accounts and dispute review is inconsistent across the portfolio. Build me a standardized refund readiness system I can apply to all of them."
3. "Our dispute approval rate dropped from 78% to 45% over the past three months. Audit our dispute process and tell me what changed."
