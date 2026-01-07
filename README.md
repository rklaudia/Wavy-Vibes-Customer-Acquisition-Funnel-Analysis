# Wavy Vibes: Customer Acquisition Funnel Analysis (E-Commerce)

## Overview

This project analyses the marketing funnel of Wavy Vibes, an Australian surf e-commerce store, to understand why strong traffic volume does not translate into sales. Using GA4 event data, the project focuses on acquisition quality, funnel drop-offs, and audience behaviour, with the goal of identifying the highest-impact optimisation opportunities.

The outcome is a session-level data model in BigQuery and a multi-page Looker Studio dashboard designed for marketing decision-making.

## Business Problem

Wavy Vibes attracts a large number of visitors, but revenue growth does not scale with traffic. The key questions addressed in this project are:

- Where are users dropping off in the marketing funnel?

- Which channels drive volume vs. value?

- Which audiences are most valuable?

- Where should optimisation efforts be prioritised?

## Data

- Source: GA4 Obfuscated Sample E-commerce dataset

- Granularity: Event-level data transformed to session-level

- Timeframe: November 2020 – January 2021

The dataset includes user events, traffic source information, device data, and e-commerce revenue. Campaign-level data is limited due to incomplete tagging in the public GA4 sample.

## Methodology

1. Session-level modelling
GA4 events were stitched into sessions using a deterministic session key (user_pseudo_id + ga_session_id), enabling accurate funnel and conversion analysis.

2. Data quality fixes
Sessions spanning multiple dates were deduplicated to prevent inflated session counts and misleading conversion rates.

3. KPI definition
All metrics were calculated as ratios of summed counts (not averages of averages) to ensure correctness across filters and time ranges.

4. Analytical views
Purpose-built KPI views were created for:
- time-based trends,
- acquisition analysis,
- funnel diagnostics,
- device and audience analysis.

5. Visual analysis
Looker Studio was used to build a 5-page dashboard focused on diagnosis and prioritisation rather than surface-level reporting.

## Dashboard Structure

1. Executive Overview
Traffic, revenue, conversion trends, and overall funnel performance.

2. Acquisition Performance
Channel and source quality comparison using sessions, revenue per session, and funnel step rates.

3. Funnel Diagnostics (Leak Finder)
Identification of the weakest funnel step by channel and prioritisation based on impact.

4. Campaign Deep Dive
Conceptual campaign analysis highlighting tagging limitations and efficiency differences.

5. Devices & Audience
Performance comparison by device category and new vs. returning users.

## Key Insights

- Conversion efficiency, not traffic volume, is the main growth lever.
- The largest funnel drop happens early (View → Cart), not at checkout.
- Returning users generate significantly higher value than new users.

## Recommendations

- Optimise product discovery and early-funnel engagement.
- Shift acquisition toward higher-intent traffic sources.
- Invest in retention and remarketing strategies.

## Tools & Tech

- BigQuery – data preparation, session modelling, KPI views
- Looker Studio – dashboarding and visual analysis
- SQL - data transformation and metric logic

## Limitations

- Campaign-level insights are constrained by incomplete tagging in the GA4 sample dataset.
- Cost data is not available, so efficiency is evaluated using revenue per session rather than ROAS or CAC.

## Next Steps

- Introduce A/B testing to validate funnel optimisation hypotheses.
- Improve campaign tagging to enable true campaign-level optimisation.
- Extend analysis with cohort and retention views.

## Repository Contents

- /sql – BigQuery models and KPI views
- /docs – data preparation notes and assumptions
- /dashboard – Looker Studio dashboard link

This project demonstrates an end-to-end marketing analytics workflow: from raw GA4 data to actionable insights and clear optimisation priorities.
