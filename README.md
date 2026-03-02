# A/B Test: AI-Generated Blog Post Summarization
### FinTech Content Platform — Experiment Design, Results & Ship Decision

---

## Overview

This repository contains the full experiment design, results, and decision rationale for a 5-week A/B test evaluating an AI-generated summarization feature on long-form FinTech blog content.

The feature presented users with a summary CTA at the top of qualifying articles. Clicking it triggered a modal overlay with the AI-generated summary alongside an embedded targeted product ad — combining content value with a product conversion opportunity in a single interaction.

Results were inconclusive — the variant showed directional lift in product page CTR but did not reach statistical significance due to insufficient sample size. The feature was shipped anyway. This document explains why that was the right call.

📄 **[Read the full experiment write-up →](./ab-test-ai-summarization.md)**

---

## What This Demonstrates

**Honest results documentation** — Most portfolio case studies cherry-pick wins. This test returned flat, statistically insignificant results across all metrics — and the document doesn't hide that. It surfaces the root cause (insufficient traffic to power the test), quantifies the limitation, and explains what a better-powered retest would require.

**Data-informed ship decisions under ambiguity** — Inconclusive results don't always mean "don't ship." This document walks through the full ship rationale: directional signal, no negative effects, low risk profile, targeted rollout scope, and strategic context (enterprise AI adoption mandate). It shows how product judgment fills the gap when data can't give a definitive answer.

**Metric design and guardrail thinking** — The experiment defines primary, secondary, and guardrail metrics with explicit rationale for each. The guardrail metric — summary CTA read rate — was designed to detect feature adoption post-launch and became the key input for follow-on iteration planning.

**Post-launch learning loop** — The 0.92% post-launch read rate (205 of 22,233 sessions) is treated as a meaningful finding, not a footnote. It reframes the next question: not "did the feature work?" but "is the CTA compelling enough to measure whether the feature works?" That reframing drives the follow-on opportunities section.

**Structural limitations, not just results** — The document calls out that editorial content pages have limited testability at current organic traffic baselines — a structural constraint that affects future experiment planning across the entire content hub, not just this feature.

---

## Document Metadata

| | |
|---|---|
| **Product** | FinTech Content Platform — Blog Summarization Feature |
| **Document Type** | A/B Test Design & Results |
| **Status** | Completed — Feature Shipped |
| **Test Window** | May 23 – June 26, 2023 (5 weeks) |
| **Outcome** | Inconclusive — shipped under strategic context |

---

## Related Artifacts

| Artifact | Description |
|---|---|
| [PRD: FinTech Consumer Content Hub](https://github.com/thedmons/prd-content-hub) | Platform PRD for the content hub this feature was built on |
