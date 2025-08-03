# Performance Tuning Guide

This document outlines the strategies implemented to optimize the performance of the **Route Intelligence System** dashboard.

---

## 1. 📊 Data Model Optimization

- **Star Schema Architecture**:
  - Central Fact Table: `Cleaned_Fact`
  - Dimensions:
    - `Cleaned_Dim_Drivers`
    - `Cleaned_Dim_Routes`
    - `Dim_Vehicles`
    - `Dim_Weather`
    - `DateTable`

- **Optimizations Applied**:
  - Removed unused columns from both fact and dimension tables to reduce memory consumption.
  - Enforced single-directional relationships where bi-directional filters were not necessary to reduce model complexity and improve engine performance.
  - Verified cardinality to maintain optimal join paths.
  - Ensured that keys used in relationships are unique and non-null to avoid relationship ambiguity.

---

## 2. ⚙️ DAX Optimization

- **Measure-First Approach**:
  - Replaced calculated columns with DAX measures where calculations were only needed at query-time.

- **DAX Best Practices**:
  - Utilized `VAR` statements to store intermediate results and reduce redundant calculations.
  - Avoided `EARLIER()` and expensive row context operations in visual-level calculations.
  - Replaced inefficient iterators (`SUMX`, `FILTER`, etc.) with pre-aggregated summaries using `SUMMARIZE` or base-level measures.
  - Created reusable base measures to minimize DAX duplication across visuals.

---

## 3. 🧩 Visual-Level Optimization

- **Simplified Visuals**:
  - Removed high-cardinality tables from key report pages.
  - Moved detailed breakdowns to drill-through pages to reduce rendering time.

- **Efficient Slicers**:
  - Used drop-down slicers instead of list slicers to improve page load times.
  - Avoided unnecessary slicers on shared pages.

- **Performance Features**:
  - Applied bookmarks for toggling views instead of loading new pages.
  - Optimized tooltips by limiting the number of context fields.

---

## 4. 🔄 Refresh & Query Performance

- **Data Reduction Techniques**:
  - Applied filters on `DateTable` to limit data scope (e.g., last 12 months).
  - Removed historical records from inactive routes unless used in trend analysis.

- **Incremental Refresh**:
  - Implemented on `Cleaned_Fact` to reduce refresh time for large datasets.
  - Partitioned data by `DeliveryDate` column.

- **Data Types**:
  - Ensured columns use efficient data types (e.g., `Whole Number` for IDs, `Decimal` for distance, fuel).

---

## 5. ☁️ Power BI Service Deployment

- **Deployment Workflow**:
  - Reduced dataset size using Power Query filters before publish.
  - Published to Power BI Service with Gateway configured for scheduled refresh.

- **Performance Monitoring**:
  - Used **Performance Analyzer** in Power BI Desktop to monitor load times of visuals.
  - Monitored dataset refresh history in Power BI Service for bottlenecks.

---

## 6. 🛠️ Tools Used

| Tool              | Purpose                                             |
|-------------------|-----------------------------------------------------|
| DAX Studio         | Query performance analysis, storage engine metrics |
| Power Query Diagnostics | Evaluate transformation steps load times     |
| Performance Analyzer (Power BI Desktop) | Visual load time monitoring |
| Power BI Service Gateway | Enables secure refresh from on-prem sources  |

---

> 🔁 Continuous improvement: Performance tuning is reviewed monthly based on user feedback and backend telemetry logs.

