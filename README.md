# Power BI Capstone Project – Route Intelligence System
**Group 6** | DSA 2040A – Semester Project

## Group Members
- Student 1 – Melanie Mweru
- Student 2 – [Insert Name]
- Student 3 – [Insert Name]

## Project Summary
This project focuses on building a Route Intelligence System dashboard for a logistics company. The goal is to enhance route optimization, monitor driver and vehicle performance, analyze delivery efficiency, and evaluate weather impacts. The dashboard supports strategic decisions by integrating KPIs, predictive metrics, and environmental factors.

## Key Deliverables
- **Business KPIs**: On-time delivery %, fuel efficiency per route, driver performance scores, carbon emissions
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



