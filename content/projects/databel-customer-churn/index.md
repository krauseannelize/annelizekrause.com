---
title: "Why Are a Quarter of Databel's Customers Leaving? An Excel Answer"
date: 2025-05-23
summary: "An interactive Excel dashboard analyzing customer churn for a fictional US telecom: churn drivers, demographics, tenure, and a state-level map, built with dynamic array formulas (LET, SWITCH, FILTER, PIVOTBY)."
tags:
  - Excel
  - Data Analytics
  - Dashboard
  - Customer Churn
tech_stack:
  - Excel
links:
  - type: github
    url: https://github.com/krauseannelize/project-excel-databel-customer-churn
    label: Code
featured: true
status: "Personal Project"
role: "Solo Project"
---

Databel is a fictional US telecom from DataCamp's case study "Analyzing Customer Churn in Excel." The case ships with a suggested solution; I built the dashboard I would actually want on my desk if 26.86% of my customers were walking out the door.

The numbers tell a specific story. Of 6,687 customers, 1,796 churned. Nearly half of them (44.82%) left for a competitor, with customer-service attitude a distant second at 15.98%. Churn climbs past 40% for customers aged 79 to 88, concentrates in short-tenure accounts, and spikes geographically: California churns at 63.24%, wildly out of line with every other state. Each of those findings is one click deep in the dashboard, with dynamic filtering and an interactive state map doing the work a static report can't.

Under the hood it runs on modern Excel: dynamic array formulas (LET, SWITCH, FILTER, PIVOTBY) instead of hidden helper columns, so the whole pipeline from raw data to dashboard stays inspectable in one workbook. The full transformation from raw export to final dashboard is documented step by step in the repository's changelog.

Watch the walkthrough:

<div style="display: flex; justify-content: center;">
  <video controls preload="metadata" style="width: 100%; max-width: 360px; aspect-ratio: 9 / 16; border-radius: 10px;">
    <source src="walkthrough.mp4" type="video/mp4">
    Your browser does not support the video tag. <a href="walkthrough.mp4">Download the walkthrough</a> instead.
  </video>
</div>
