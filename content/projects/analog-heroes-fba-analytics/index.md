---
title: "Should This Amazon Seller Adopt FBA? A Data-Driven Answer"
date: 2026-07-20
summary: "End-to-end analytics for a fictional Amazon seller weighing Fulfillment by Amazon: a seeded synthetic data generator, a DuckDB star schema with a PII-stripping staging layer, and an interactive Power BI dashboard with a what-if scenario slider."
tags:
  - Power BI
  - SQL
  - Data Analytics
  - Ecommerce
  - Synthetic Data
tech_stack:
  - Power BI
  - DuckDB
  - SQL
  - Python
  - pytest
links:
  - type: github
    url: https://github.com/krauseannelize/analog-heroes-analytics
    label: Code
featured: true
status: "Personal Project"
role: "Solo Project"
---

Analog Heroes is a fictional US-based Amazon seller of bullet journal supplies. The business is healthy and growing, but every order ships merchant-fulfilled, and shipping now consumes a third of revenue: 31.7% in 2024, 34.0% in 2025. The question the owners want answered: **do any SKUs justify the fees of Fulfillment by Amazon, and if so, which ones?**

The dashboard below answers it with a ranked shortlist. Sales velocity and projected annual savings are computed per SKU against a simplified FBA fee model (size tiers, fulfillment fees, seasonal storage rates). Eight SKUs clear both thresholds at baseline. The Prime Uplift slider on the FBA Opportunity page adds the speculative part: assume the Prime badge lifts conversion by up to 30%, and watch the shortlist grow from 8 candidates to 15.

Explore it live (best viewed on a desktop screen):

<div style="position: relative; width: 100%; padding-bottom: 62%; height: 0; overflow: hidden;">
  <iframe title="Analog Heroes FBA Analytics Dashboard" src="https://app.powerbi.com/view?r=eyJrIjoiNGNhMWUxZTYtMTNkMy00ZmNlLThmYWQtNjc5ZWZmNjhmNjYzIiwidCI6IjUxMjBkMjM4LTdkNjAtNGIwZi05YTQ1LTJlY2I4YzljNDI0MiJ9" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" allowfullscreen></iframe>
</div>

Every number in the report is synthetic by design. A seeded Python generator produces two years of order lines in the layout of Amazon's real seller reports, calibrated to realistic patterns: a hero product line carrying 77% of revenue, a Q4 gifting spike at 3 to 4 times baseline, and a second demand cycle in January when new year resolutions sell journals and dated planner inserts. Because the data is generated, the repository can be fully public, and the pipeline demonstrates privacy-by-design anyway: the raw format includes the buyer PII columns that real Amazon reports contain (with fake values), and the SQL staging layer strips them so nothing personal ever reaches the analytical model.

The pipeline runs on DuckDB with all transformations in plain SQL: staging, a star schema with conformed dimensions, and an FBA economics mart that feeds the dashboard. A pytest suite of 39 tests guards the build, from seeded reproducibility down to revenue reconciling to the cent between staging and the fact table. The full build process, from design document to phased implementation plan to review gates, is documented in the repository.
