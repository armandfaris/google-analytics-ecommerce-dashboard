# Google Analytics E-Commerce Executive Performance Dashboard

Project Overview
An end-to-end data engineering and business intelligence project that transforms raw, digital analytics logs from the global Google Merchandise Store into a production-ready executive dashboard. This pipeline models and analyzes over **$1.03M in total revenue** across **5M web visitors** to deliver high-value business insights on marketing channel ROI, device behavior, and normalized purchasing trends.

---

## Tech Stack & Architecture
* **Data Warehouse:** Google BigQuery (Cloud SQL)
* **BI Platform:** Power BI Desktop
* **Data Modeling:** Star Schema (1-to-Many Relationships)
* **Languages:** GoogleSQL & DAX (Data Analysis Expressions)

---

## Core Engineering Achievements

### 1. Robust Cloud Data Modeling & Pipeline Resilience
* Modeled a full year of granular e-commerce session logs directly inside Google BigQuery. 
* Implemented an **upstream-first ELT architecture**. By centralizing heavy data-cleaning logic within cloud SQL views rather than front-end BI tools, the entire data model proved highly resilient and could be fully reconstructed from scratch in minutes.

### 2. Overcoming Complex Data Fan-Out Anomalies
* Resolved a critical database fan-out duplication bug caused by multi-layered array unnesting (`UNNEST(hits)` and `UNNEST(product)`) inside the public Google Analytics schema.
* Engineered optimized DAX measures to safely bypass row-multiplication errors, accurately grounding an inflated trillion-unit count back to a precise, realistic **100K total transactions**.

### 3. Advanced Semantic Calculations & Bias Removal
* Developed custom DAX metrics to track high-level e-commerce health, including *Average Order Value (AOV)* and an accurate *1.24% Conversion Rate*.
* Programmed a dynamic, chronological calendar dimension (`Day Type`) utilizing seasonal iterators (`SUMX` and `AVERAGEX`) to evaluate weekday versus weekend performance, successfully eliminating calendar day-count biases.

---

## Strategic Business Insights Delivered

* **Marketing ROI:** Quantified channel execution, proving that while `Direct` traffic represents the strongest brand equity and core revenue pipeline, paid visual display advertisements (`dfa/Display Ads`) act as the critical top-of-funnel fuel driving brand awareness.
* **Product Strategy:** Discovered that although standard consumer items command high volume, premium branded merchandise commands the highest *Average Order Value*, highlighting a clear cross-selling opportunity.
* **Hardware Evaluation:** Exposed a severe purchasing power gap between hardware categories, revealing that Desktop traffic dominates over 70% of total sales—indicating a high-priority need to optimize mobile web conversion funnels.

Project Live View:
* https://app.powerbi.com/groups/me/reports/ac54c20f-dc6b-46cd-9899-603811daf134/71db6b6137ed3cc39244?experience=power-bi
