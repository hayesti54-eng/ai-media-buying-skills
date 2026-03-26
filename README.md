# AI Media Buying Skills for Claude Code

> A modular, operator-grade paid media Skills library for Claude Code Capabilities — covering Meta Ads, Google Local Services Ads, and TikTok Ads.

---

## Overview

This repository is a production-ready paid media operating system built as Claude Code Skills. Each Skill is a standalone module that activates Claude to perform a specific diagnostic, planning, reporting, auditing, or optimization task — without requiring API access, platform integrations, or MCP connections.

Skills operate entirely from user-provided inputs: exported reports, pasted campaign data, screenshots, CRM notes, call logs, booking data, funnel metrics, ad copy, creative descriptions, and review trends. The result is a portable, privacy-safe intelligence layer that any media buyer, growth marketer, or performance team can install and use immediately.

---

## What This Repository Includes

**63 Skills total across 3 platforms:**

| Platform | Skills |
|---|---|
| Meta Ads | 21 |
| Google LSA | 21 |
| TikTok Ads | 21 |

Skills are organized by platform and operating function (diagnostics, creative, reporting, launch, funnel, strategy — and for LSA: operations and disputes).

---

## Who This Is For

- **Paid media specialists** managing accounts across Meta, Google LSA, and TikTok
- **Growth marketers** who need structured diagnostic and planning support
- **Freelance media buyers** building systematic operating procedures
- **Agencies** managing multi-client workflows and needing repeatable analysis frameworks
- **In-house demand generation teams** requiring clear reporting and optimization logic
- **Performance marketing operators** who run their own media buying OS

---

## How to Use These Skills

1. **Copy a Skill folder** into your Claude Code Capabilities directory (e.g., `~/.claude/capabilities/`)
2. **Activate the Skill** by making a natural-language request that matches the Skill's trigger conditions (see `## When to Use` in each file)
3. **Provide the required inputs** as described in `## Inputs Required` — paste data directly, attach exports, or describe your situation
4. **Use the output** for diagnosis, planning, reporting, optimization, or client deliverables

Each Skill is self-contained. You do not need to install all Skills at once. Start with the ones most relevant to your current operating needs.

---

## Input Types These Skills Work Best With

- **Platform exports** — CSV/XLSX campaign reports from Meta Ads Manager, Google LSA dashboard, TikTok Ads Manager
- **Screenshots** — dashboards, charts, ad previews, creative performance tables
- **CRM notes** — lead disposition records, pipeline status, follow-up logs
- **Booking and job data** — confirmed bookings, job type, service value, close rate by source
- **Lead logs** — call logs, lead timestamps, response time records
- **Call notes** — transcripts, CSR notes, missed call records
- **Creative metrics** — thumbstop rate, hook rate, hold rate, CTR, spend-per-creative
- **Funnel stage reports** — impression → click → landing → lead → booked → closed
- **Landing page links** — for mismatch, copy audit, and CRO review
- **Copy drafts** — headlines, primary text, scripts, descriptions
- **Review trends** — rating history, review velocity, sentiment patterns
- **Operator context** — budget, goals, account history, audience notes, any background the operator can provide

---

## Repository Structure

```
/ai-media-buying-skills/
  README.md
  /meta-ads/
    /diagnostics/
      /capi-diagnostics/
      /event-match-quality-auditor/
      /learning-phase-diagnostician/
      /audience-overlap-auditor/
      /anomaly-detector/
      /audience-saturation-checker/
      /aem-compliance-reviewer/
    /creative/
      /creative-fatigue-detector/
      /ad-copy-generator/
      /offer-message-auditor/
      /placement-creative-analyzer/
    /reporting/
      /performance-report-generator/
      /breakdown-analysis-reporter/
      /incrementality-interpreter/
    /launch/
      /launch-verifier/
      /bid-strategy-selector/
      /campaign-structure-reviewer/
    /funnel/
      /funnel-dropoff-diagnostician/
      /retargeting-structure-reviewer/
    /strategy/
      /advantage-plus-evaluator/
      /scaling-readiness-checker/
  /google-lsa/
    /diagnostics/
      /lead-quality-auditor/
      /response-time-diagnostician/
      /ranking-factor-analyzer/
      /missed-opportunity-reviewer/
      /call-handling-diagnostician/
      /lead-throttling-analyzer/
    /operations/
      /booking-rate-analyzer/
      /service-area-optimizer/
      /lead-handling-sop-auditor/
      /profile-completeness-checker/
    /reporting/
      /weekly-performance-reporter/
      /monthly-performance-reporter/
      /revenue-attribution-analyzer/
    /disputes/
      /dispute-eligibility-reviewer/
      /dispute-documentation-builder/
      /invalid-lead-identifier/
      /refund-readiness-planner/
    /funnel/
      /crm-sourcing-analyzer/
      /funnel-dropoff-diagnostician/
    /strategy/
      /local-market-performance-reviewer/
      /review-velocity-strategist/
  /tiktok-ads/
    /diagnostics/
      /hook-rate-analyzer/
      /hold-rate-analyzer/
      /creative-fatigue-detector/
      /anomaly-detector/
      /landing-page-mismatch-reviewer/
      /volatility-controller/
    /creative/
      /ugc-sourcing-workflow/
      /creative-brief-generator/
      /ad-script-generator/
      /native-style-ad-reviewer/
      /offer-message-fit-auditor/
    /reporting/
      /performance-report-generator/
      /creative-iteration-planner/
      /testing-matrix-creator/
    /launch/
      /launch-verifier/
      /spark-ads-strategist/
      /non-spark-dark-post-strategist/
    /funnel/
      /funnel-dropoff-diagnostician/
      /audience-expansion-planner/
    /strategy/
      /interest-cluster-analyzer/
      /scaling-readiness-checker/
```

---

## Platform Coverage

### Meta Ads

Covers the full Meta performance advertising stack: pixel and CAPI signal integrity, creative lifecycle management, audience architecture, campaign structure, bid strategy selection, funnel diagnosis, retargeting design, Advantage+ evaluation, scaling decision logic, and executive-grade performance reporting. Skills apply to conversion campaigns, lead generation, and retargeting programs.

### Google LSA

Covers the operational and economic mechanics of Google Local Services Ads — specifically as a pay-per-lead platform, not a keyword bidding system. Skills address lead quality review, dispute filing, call handling, booking rate analysis, service area configuration, CRM pipeline analysis, review velocity, and both weekly and monthly performance reporting. Designed for home services, legal, health, and other LSA-eligible verticals.

### TikTok Ads

Covers TikTok's creative-first, short-form native ad environment. Skills address hook rate and hold rate analysis, creative fatigue detection, UGC sourcing, script and brief generation, Spark vs. non-Spark strategy, landing page alignment, audience expansion, interest cluster analysis, scaling readiness, and testing matrix construction. Built for operators who understand that TikTok performance is primarily a creative problem.

---

## Skill Categories

| Category | Description |
|---|---|
| **diagnostics** | Root-cause analysis of performance drops, signal integrity issues, audience problems, or platform anomalies |
| **creative** | Creative strategy, fatigue detection, copy generation, brief writing, and placement-level review |
| **reporting** | Structured performance reports for internal use or client delivery |
| **launch** | Pre-launch verification, campaign structure review, bid strategy selection, and go-live readiness |
| **funnel** | Drop-off analysis, retargeting architecture, lead pipeline review, and stage-by-stage conversion diagnosis |
| **strategy** | High-level planning, scaling frameworks, market analysis, and multi-account strategic reviews |
| **operations** *(LSA only)* | Booking rate, service area, profile management, and lead handling procedures |
| **disputes** *(LSA only)* | Invalid lead identification, dispute eligibility, documentation building, and refund planning |

---

## Recommended First Installs

These 10 Skills deliver the highest immediate value across the three platforms:

| # | Skill | Path | Why |
|---|---|---|---|
| 1 | **CAPI Diagnostics** | `meta-ads/diagnostics/capi-diagnostics` | Signal integrity issues silently destroy optimization — diagnose before spending another dollar |
| 2 | **Learning Phase Diagnostician** | `meta-ads/diagnostics/learning-phase-diagnostician` | Learning Limited is the #1 silent campaign killer on Meta and almost always has a fixable root cause |
| 3 | **Meta Campaign Scaling Readiness Checker** | `meta-ads/strategy/scaling-readiness-checker` | Prevents premature scaling that resets learning and inflates CPA |
| 4 | **LSA Lead Quality Auditor** | `google-lsa/diagnostics/lead-quality-auditor` | Most LSA accounts waste 20–40% of budget on unchargeable or misaligned leads |
| 5 | **Dispute Eligibility Reviewer** | `google-lsa/disputes/dispute-eligibility-reviewer` | Recovers real budget from invalid charges — one of the highest-ROI activities in LSA management |
| 6 | **LSA Booking Rate Analyzer** | `google-lsa/operations/booking-rate-analyzer` | Raw lead count is a vanity metric; booked lead rate determines actual LSA economics |
| 7 | **Hook Rate Analyzer** | `tiktok-ads/diagnostics/hook-rate-analyzer` | Hook rate is TikTok's most controllable performance lever — low hook rate invalidates all other analysis |
| 8 | **TikTok Ad Script Generator** | `tiktok-ads/creative/ad-script-generator` | TikTok performance lives or dies on creative; structured scripts ship faster and iterate smarter |
| 9 | **TikTok Creative Fatigue Detector** | `tiktok-ads/diagnostics/creative-fatigue-detector` | TikTok creative burns faster than any other platform — catching fatigue early saves CPAs |
| 10 | **Meta Funnel Drop-off Diagnostician** | `meta-ads/funnel/funnel-dropoff-diagnostician` | Translates platform data into a full click-to-purchase attribution diagnosis with stage-level fixes |

---

## Operating Philosophy

**Diagnostics before decisions.**
Every optimization decision should be grounded in a specific, identified root cause. These Skills are built to surface root causes — not generate generic recommendations.

**Structure over guesswork.**
Each Skill follows a repeatable, structured workflow. The same problem analyzed twice should produce the same diagnostic logic, even if inputs differ.

**Platform-native reasoning.**
Meta, Google LSA, and TikTok operate by fundamentally different mechanics. These Skills treat each platform on its own terms — LSA is not Google Search, TikTok is not Meta, and Meta post-iOS14 is not what it was in 2019.

**Human-in-the-loop judgment.**
These Skills produce analysis and recommendations, not autonomous actions. Every output is designed to support operator judgment, not replace it. Guardrails are built into every Skill.

**Practical outputs over generic advice.**
Every Skill produces outputs that are immediately usable: audit tables, root cause summaries, prioritized fix lists, structured reports, testing matrices, and implementation plans. Nothing here is just "improve your targeting."

---

## Notes

- These Skills **do not require API access** to any ad platform
- No MCP server, no live account connection, no third-party integration needed
- All analysis is performed on **user-provided inputs** — exports, pastes, descriptions, and screenshots
- Skills are designed to be used **conversationally** — paste your data, describe your situation, and activate the Skill
- Tier designations (`free`, `pro`, `agency`) indicate operational complexity, not feature gating — all Skills in this repository are fully open

---

*Built for operators. Designed for results.*
