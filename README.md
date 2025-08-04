# Power BI Capstone Project – Route Intelligence System
**Group 6** | DSA 3050A – Semester Project

## Group Members
- 1 – Melanie Mweru
- 2 – Weldesenbet Aregay
- 3 – Phiona 
- 4 – Cedric

## Project Summary
This project focuses on building a Route Intelligence System dashboard for a logistics company. The goal is to enhance route optimization, monitor driver and vehicle performance, analyze delivery efficiency, and evaluate weather impacts. The dashboard supports strategic decisions by integrating KPIs, predictive metrics, and environmental factors.

We have simulated a real-world package delivery operation in Nairobi, Kenya, where a logistics company needs to optimize delivery routes, improve driver performance, and reduce its environmental footprint. The company uses GPS telemetry, weather data, and vehicle tracking to monitor and analyze delivery operations in real time.

**Objectives:**  
- Design a robust data model (star schema) for route-based delivery analytics

- Track and evaluate driver performance using key delivery metrics

- Analyze the impact of weather on delivery efficiency and fuel usage

- Estimate and report on the carbon emissions of the delivery fleet

- Provide actionable insights through interactive dashboards and KPIs

**Business Case:**   
In urban delivery logistics, inefficiencies in routing, delays due to weather, and poor fuel optimization lead to increased costs and environmental impact. This project aims to provide a data-driven route intelligence solution that enables:

- 📈 Improved operational decision-making through real-time performance monitoring

- ⏱ Better delivery time predictions using weather and distance analytics

- ♻️ Sustainable logistics with estimated carbon emission reporting

- 🧠 Insightful dashboards for stakeholders to identify optimization opportunities

By integrating dynamic data sources and analytics into a unified reporting system, this solution empowers logistics managers to make smarter, faster, and greener decisions.

## Key Deliverables
- **Business KPIs**: #### **1.1) Defining KPIs and success metrics:**
- **Average Delivery Time:**  Mean duration between StartTime and EndTime  
- **On-Time Delivery Rate:**  % of deliveries completed within expected time (if SLA is known)  
- **Carbon Emission per Delivery:**	 Based on vehicle emission factor × distance  
- **Driver Efficiency Score:**  Could combine # of deliveries, timeliness, and route complexity  
- **Fuel Consumption:**  Estimated from distance and vehicle fuel efficiency
#### **1.2) Designing star schema data model:**
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/dae1c3d6-6177-4eba-b957-6efe8e1b514b" />


- **Top 3 insights**:
  1. Rainfall and wind levels significantly impact delivery delays in coastal regions.
  2. Drivers with higher experience and fewer incidents consistently outperform in delivery timing.
  3. Certain vehicle types have lower emissions but also lower efficiency on hilly routes.
- **ROI Estimate Summary**: Projected 15–20% reduction in fuel costs and improved delivery SLA compliance after implementation of insights.

## Technical Features
- Star schema data model with `Cleaned_Fact` as central fact table
- Role-Level Security (RLS) enabled for regional managers
- 30+ DAX measures including time intelligence, carbon impact, and scoring models
- Mobile layout for field managers and executives
- Parameter tables: `RouteNamePar`, `DriverNamePar`, `RouteWeatherSummary`, `EndDatePar`
- Drill-through reports, bookmarks, and summary cards

## Published Dashboard
[Click to View Live Report](PASTE_PUBLISH_TO_WEB_LINK_HERE)

## Presentation Materials
See [`documentation/`](documentation/) folder for the full project report including:
- `presentation.pdf` – Executive presentation deck  
- `business_case.md` – Problem background, stakeholders, and strategic value  
- `data_model_diagram.png` – Entity relationships and schema design  
- `performance_tuning.md` – Performance enhancements implemented  
- `ROI_calculations.xlsx` – Spreadsheet with impact modeling  



