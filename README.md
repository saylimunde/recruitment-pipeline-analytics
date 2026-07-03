# Recruitment & Pipeline Analytics Dashboard

## Project Overview
An executive-ready Power BI dashboard designed to track, analyze, and optimize an end-to-end IT recruitment funnel. This interactive tool transforms raw tracking data into actionable human resources intelligence, focusing on capacity mapping, stage drop-offs, and operational bottlenecks.

## Dashboard Preview
![Dashboard Layout](dashboard_preview.png)

## Core Analytical Insights
* **Pipeline Conversion:** Out of 113 total student enrollments, the vetting funnel yields a 33.6% screening rate (38 candidates) and a 2.6% overall placement yield (3 successful hires).
* **Operational Velocity:** Candidate application profiles are linked and processed with high responsiveness, averaging a crisp **1.37 days** to register across pipeline stages.
* **Geographic Concentration:** Vacancy demand is heavily clustered within the **Mumbai region**, indicating where targeted upskilling and operational efforts should align.

## Technical Architecture & DAX Implementation
* **Interactive Filtering:** Implemented a space-saving regional dropdown slicer to allow dynamic, real-time KPI recalculations for specific cities.
* **Custom Time-to-Process Modeling:** Developed a custom calculated column utilizing cross-table relationships to calculate exact pipeline tracking gaps:
  ```DAX
  Days To Process = DATEDIFF(RELATED('Skill Test - Database - Job Openings'[Created Time]), 'Skill Test - Database - Applications'[Created Time], DAY)
