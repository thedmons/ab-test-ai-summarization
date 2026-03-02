# A/B Test Design: AI-Generated Blog Post Summarization
**Author:** Thomas Edmons, Platform and Digital Product Manager
**Status:** Completed — Feature Shipped
**Test Duration:** 5 weeks (May 23 – June 26, 2023)
**Last Updated:** February 2026

---

## Table of Contents
1. [Overview](#overview)
2. [Background & Motivation](#background--motivation)
3. [Hypothesis](#hypothesis)
4. [Test Design](#test-design)
5. [Audience & Segmentation](#audience--segmentation)
6. [Metrics](#metrics)
7. [Results](#results)
8. [Decision & Rationale](#decision--rationale)
9. [Learnings & Limitations](#learnings--limitations)
10. [Follow-On Opportunities](#follow-on-opportunities)
11. [Appendix](#appendix)

---

## Overview

This document outlines the design, execution, and outcome of an A/B test evaluating an AI-generated summarization feature on long-form blog content for a FinTech platform. The feature presented users with a summary CTA module at the top of qualifying blog posts. Clicking the CTA triggered a modal overlay displaying the AI-generated article summary alongside an embedded targeted product ad — combining content value with a product conversion opportunity in a single interaction.

The test sought to determine whether the summarization feature improved user engagement and drove higher clickthrough to product pages. Results showed a directional lift in clickthrough rate (CTR) on the variant but did not reach statistical significance due to insufficient sample size — a limitation that surfaced important insights about the testability of this page type.

The feature was ultimately shipped as an enterprise AI adoption initiative, applied to all blog posts with a read time of 7 minutes or longer.

---

## Background & Motivation

The FinTech platform's content team publishes long-form blog posts as a key channel for organic acquisition and customer education. Longer articles — while high in informational value — present a reader commitment barrier: users arriving from search or social may bounce before engaging with the full content or the embedded product ad unit.

Separately, AI adoption had been identified as an enterprise strategic priority. Product teams were encouraged to find meaningful, user-facing applications of AI capabilities that aligned to measurable business outcomes rather than shipping AI for its own sake.

The AI blog summarization feature sat at the intersection of both goals: a user experience improvement with a plausible engagement uplift thesis, and a concrete AI use case with a defined success metric.

---

## Hypothesis

**If** long-form blog posts include an AI-generated summary CTA module at the top of the page, **then** users will have higher engagement with the article content and be more likely to click through to the product page via the ad embedded within the summary modal, **because** the CTA lowers the perceived reading barrier by offering an on-demand summary — and users who engage with the modal are presented with a targeted product ad in a high-attention context, increasing the likelihood of product conversion.

---

## Test Design

### Control (A)
The highest-engaged article on the platform in its existing state — full long-form blog post with no summarization feature. The right-column embedded product ad unit was present as standard.

### Variant (B)
The same article with the AI-generated summarization feature added. A summary CTA module appeared at the top of the post. Clicking the CTA triggered a modal overlay containing the AI-generated article summary and an embedded targeted product ad — presenting the product conversion opportunity within a high-attention, user-initiated interaction. The right-column product ad unit remained present and unchanged.

### What Changed
| Element | Control (A) | Variant (B) |
|---|---|---|
| Summary CTA module | ❌ Not present | ✅ Present at top of article |
| AI-generated summary modal | ❌ Not present | ✅ Triggered on CTA click |
| Product ad in modal | ❌ Not present | ✅ Embedded within summary modal |
| Right-column product ad | ✅ Present | ✅ Present (unchanged) |
| Full article body | ✅ Present | ✅ Present (unchanged) |

### Test Type
A/B test (two variants) — run across 5 articles selected to maximize available sample size within the test window. Articles were chosen based on engagement and read time qualification.

### Traffic Split
50% Control / 50% Variant

### Test Window
May 23 – June 26, 2023 (5 weeks)

---

## Audience & Segmentation

| Attribute | Detail |
|---|---|
| Test population | All organic and direct traffic to 5 qualifying articles during the test window |
| Traffic split | 50/50 |
| Targeting criteria | No segmentation applied — full traffic exposure |
| Exclusions | None applied |

**Notes on audience:** The test was run across 5 qualifying articles to aggregate sample size across the test window. No audience segmentation was applied — all users landing on these pages during the test window were eligible for either variant. In retrospect, aligning the test window with an active marketing campaign would have significantly increased traffic volume and improved the viability of reaching statistical significance.

---

## Metrics

### Primary Metrics
**Product page views (CTR to product page)** — the number and percentage of users who navigated to the product page via the embedded ad, used as the primary measure of product conversion intent.

*Rationale:* Product page views are the most direct signal of commercial intent generated by the blog content. This metric connects the content experience to a downstream business outcome and is the clearest measure of whether the summarization feature influenced user behavior beyond passive reading.

**Recirculation rate** — the percentage of users who engaged with other articles on the site following their visit to the test article.

*Rationale:* Recirculation measures the degree to which the summarization feature kept users engaged within the content ecosystem. A higher recirculation rate would indicate the feature increased content affinity and encouraged users to explore further — a meaningful engagement signal beyond a single article visit.

### Secondary Metrics
**Exit rate** — the percentage of users who left the site from the test article without visiting any other page.

*Rationale:* Exit rate serves as a direct measure of whether the summary CTA reduced abandonment. If the feature successfully lowered the reader commitment barrier, we would expect a corresponding decrease in exit rate on the variant.

**Average scroll depth** — how far down the article page users scrolled on average.

*Rationale:* Scroll depth validates whether users with access to the summary still engaged with the full article body, or treated the summary as a substitute for reading. A maintained or improved scroll depth on the variant would indicate the feature complemented rather than replaced article engagement.

### Guardrail Metric
- **Summary CTA read rate** — monitored post-launch to establish a baseline for feature adoption and identify future CTA optimization opportunities

---

## Results

| Metric | Control (A) | Variant (B) | Delta | Significant? |
|---|---|---|---|---|
| Sessions | 14,117 | 14,289 | +172 | ❌ Not significant |
| CTR to product page (product page views) | 581 (4.1%) | 608 (4.2%) | +27 (+0.1pp) | ❌ Not significant |
| Exit rate | 92.1% | 92.3% | +0.2pp | ❌ Not significant |
| Recirculation rate | 3.68% | 3.48% | -0.2pp | ❌ Not significant |
| Avg scroll depth | 27.6% | 27.6% | Flat | ❌ Not significant |
| Summary CTA read rate (post-launch) | N/A | 0.92% (205 of 22,233 sessions) | N/A | — |

### Summary
The variant showed a marginal directional lift in product page views (581 → 608, +0.1pp CTR) but all metrics were effectively flat between control and variant. Exit rate, recirculation, and scroll depth showed no meaningful difference. Results did not reach statistical significance at the 95% confidence threshold across any metric.

Post-launch, the summarization feature was adopted by 0.92% of sessions (205 out of 22,233 visitors) — a low but measurable initial read rate that informed future CTA optimization opportunities.

### Statistical Context
- **Confidence level target:** 95%
- **Result:** Below significance threshold across all metrics
- **Sessions per variant:** ~14,000 over 5 weeks across 5 articles
- **Root cause:** Aggregate traffic across 5 articles over 5 weeks was insufficient to power the experiment; the organic baseline for editorial content was too low to detect the effect size with confidence

---

## Decision & Rationale

**Decision: Ship the feature**

Despite inconclusive statistical results, the feature was approved for production release and applied to all blog posts with a read time of 7 minutes or longer.

**Rationale:**

**Enterprise AI adoption priority:** The feature was initiated in the context of an organizational mandate to identify meaningful AI use cases. Inconclusive but directionally positive results, combined with a low-risk user experience change, supported a ship decision under this strategic context.

**Directional signal:** While the results did not reach significance, the variant showed higher CTR than the control. No negative signals were observed — the feature did not depress engagement, increase bounce, or harm time on site.

**Low risk profile:** The summarization feature is additive — it does not remove or replace existing content and does not alter the product ad placement. The downside risk to the user experience was judged to be minimal.

**Targeted rollout:** Rather than a full site rollout, the feature was scoped to posts with a 7-minute or longer read time — the content segment where the reader commitment barrier is highest and the perceived value of a summary is greatest. This constraint reduces surface area while targeting the use case with the strongest underlying rationale.

---

## Learnings & Limitations

### What This Test Revealed

**1. Metrics were flat — not directionally positive.**
Exit rate, recirculation, scroll depth, and product page CTR were all effectively unchanged between control and variant. The test did not surface a clear signal in either direction, which is itself a meaningful finding — it suggests the summary CTA in its current form did not materially alter user behavior on these articles.

**2. Summary read rate was low at 0.92% post-launch.**
After shipping the feature as the default experience, only 205 of 22,233 sessions (0.92%) engaged with the summary. This low adoption rate points to a CTA visibility or value proposition gap — users may not have understood what the feature offered or found the prompt compelling enough to act on.

**3. This page type has limited testability at current traffic levels.**
~14,000 sessions per variant over 5 weeks across 5 articles was insufficient to reach statistical significance. This is a structural constraint of editorial content pages — future experiments need either higher traffic amplification via campaigns or longer run times to be adequately powered.

**4. The CTA treatment is a candidate for iteration.**
With a 0.92% read rate as a baseline, even modest improvements to CTA design, copy, or placement could meaningfully increase feature adoption.

**5. Directional data still informs decisions in a strategic context.**
While metrics were flat, no negative signals were observed. Combined with the enterprise AI adoption mandate, the low-risk profile of the feature, and its targeted rollout to 7-minute+ articles, the ship decision was defensible — and the post-launch data now provides a real baseline for future iteration.

### Limitations
- ~14,000 sessions per variant over 5 weeks was insufficient to reach statistical significance
- Test was run against organic baseline traffic with no campaign amplification
- 5-article scope limits generalizability across the full blog content catalog
- Post-launch summary read rate of 0.92% suggests the CTA itself may need optimization before the feature's true impact on engagement can be measured
- No qualitative user research was conducted alongside the quantitative test to understand why users did or did not engage with the summary CTA

---

## Follow-On Opportunities

| Opportunity | Description | Priority |
|---|---|---|
| Campaign-aligned retest | Rerun the experiment during a marketing campaign to increase traffic volume and test power | High |
| CTA interaction tracking | Instrument detailed tracking on summary CTA clicks, modal open rate, time spent in modal, and modal ad CTR as a funnel within the feature | High |
| Scroll depth analysis | Analyze whether users who read the summary scroll further into the article body than those without | Medium |
| Broader article rollout retest | Extend the test beyond the initial 5 articles to the full catalog of 7min+ posts to aggregate greater sample size | Medium |
| Personalization integration | Test whether serving summaries only to first-time visitors (vs. returning readers) produces stronger CTR lift | Low |

---

## Appendix

### Glossary
- **A/B test:** A controlled experiment that exposes two groups of users to different experiences (control and variant) to measure the causal impact of a change
- **CTR (Clickthrough Rate):** The percentage of users who click a specific element — in this case, the embedded product ad — out of total users exposed to it
- **Statistical significance:** A threshold (typically 95% confidence) above which observed results are unlikely to be due to chance
- **Confidence level:** The probability that the observed result reflects a true difference between control and variant, rather than random variation
- **Sample size:** The number of users included in each variant of the test; insufficient sample size reduces the test's ability to detect true effects (statistical power)
- **Guardrail metric:** A metric monitored during a test to ensure the variant does not cause unintended harm to the user experience or business, even if the primary metric improves
- **Recirculation rate:** The percentage of users who engaged with other articles on the site following their visit to the test article; used here as a measure of content ecosystem engagement
- **Read time:** An estimated time to read an article calculated from word count, used here as the threshold criterion (7 minutes or longer) for feature eligibility

### Related Documents
- [Blog Content Engagement Dashboard](../analytics/blog-engagement)
- [AI Summarization Feature Spec](../specs/ai-summarization)
- [Enterprise AI Adoption Roadmap](../strategy/ai-roadmap)
