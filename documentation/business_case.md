# Business Case: Route Intelligence System

## 1. Current Operational Challenges

As a logistics operation with a vast network of routes, vehicles, and drivers, we faces a number of operational inefficiencies that directly impact delivery performance, cost control, and sustainability goals. Based on our available data tables (`Cleaned_Fact`, `Dim_Weather`, `Cleaned_Dim_Drivers`, `Dim_Vehicles`, `Cleaned_Dim_Routes`), the following key challenges have been identified:

### 1.1 Delivery Delays due to Weather Disruptions
Analysis of `Dim_Weather` reveals high-risk wind zones and heavy rainfall days concentrated in certain regions. However, these risk factors are not currently integrated into route planning. This often leads to late deliveries, especially when average wind speeds or heavy rainfall exceed safety thresholds. Columns such as `windrisk category`, `avg wind speed`, and `heavy rain days` show significant spikes in some delivery regions, correlating with longer delivery durations in the `Cleaned_Fact` table.

### 1.2 Lack of Centralized Driver Performance Monitoring
The `Cleaned_Dim_Drivers` table shows variations in metrics like `avg deliveries`, `experience category`, and `driver per region`. However, there is no consolidated dashboard to track individual or regional driver KPIs in real-time. This makes it difficult to identify high-performing vs. underperforming drivers or allocate them optimally across regions.

### 1.3 Fuel Inefficiency and Emission Oversights
Fuel and emission metrics exist in the `Dim_Vehicles` table (`fuel efficiency`, `avg fuel`, `emission factor`), but there's no unified view combining these with delivery and distance data from `Cleaned_Fact`. This results in missed opportunities for identifying low-efficiency vehicles, high emitters, or routes with disproportionate fuel consumption (`avg fuel efficiency`, `distance km`, `vehicle id`).

### 1.4 Inconsistent Route Optimization
The `Cleaned_Dim_Routes` table indicates high variance between `min route dist` and `max route distance`, and many routes have `no start location` assigned. Without clear visibility on `avg distance`, `total routes`, or `route id` performance, planning is often reactive instead of data-driven. This inconsistency results in avoidable travel time and excessive fuel usage.

### 1.5 Limited Delivery SLA Monitoring
While `Cleaned_Fact` includes `delivery > 2hrs`, `avg delivery duration`, and `delivery date`, these aren’t being proactively tracked against SLA targets. Without dynamic alerts or visual thresholds, it becomes hard to intervene before SLA violations occur.

### 1.6 Siloed Operational Data
Each dataset — whether it's driver, weather, vehicle, or route — is analyzed in isolation. This siloed structure limits cross-domain insights, such as understanding how weather affects certain vehicles differently, or how driver experience impacts delivery time under adverse conditions.

> **Summary**: The logistics operations are hindered by fragmented data usage, lack of integrated monitoring tools, and insufficient automation in identifying risks and inefficiencies. This creates bottlenecks in performance, fuel economy, and service reliability — all of which can be significantly improved through centralized BI and dashboarding.

## 2. Proposed Solution

The proposed solution is a unified Power BI dashboard designed to centralize and visualize key logistics metrics across drivers, vehicles, routes, weather conditions, and deliveries. By integrating data from multiple sources, the dashboard enables operational leaders to quickly identify performance bottlenecks, delivery risks, and optimization opportunities.

The dashboard draws from the following datasets:

- **`Cleaned_Fact`**: Core delivery data including `delivery duration`, `distance km`, `vehicle id`, `driver ID`, and `delivery date`, providing insights into historical performance and delivery timelines.
- **`Cleaned_Dim_Drivers`**: Driver-related metrics like `avg deliveries`, `experience category`, and `driver per region`, enabling monitoring of workload distribution and skill allocation.
- **`Cleaned_Dim_Routes`**: Route-specific information such as `avg distance`, `start/end location`, and `total routes`, supporting route comparison and distance-based efficiency analysis.
- **`Dim_Vehicles`**: Vehicle-level efficiency data including `fuel efficiency`, `avg fuel`, and `emission factor`, useful for identifying high- and low-performing trucks.
- **`Dim_Weather`**: Environmental risk data like `avg rainfall`, `windrisk category`, and `heavy rain days`, allowing correlation of weather events with delivery disruptions.

The dashboard currently uses **descriptive KPIs** — such as average delivery duration, fuel efficiency per route, high-risk weather zones, and emissions per vehicle — to drive operational decisions. While no predictive analytics models are yet deployed, the current data structure and relationships have been designed to support future enhancements like **ETA prediction**, **delivery delay risk modeling**, and **driver performance forecasting**.

Compared to traditional systems based on spreadsheets and fragmented reports, this Power BI dashboard offers real-time, cross-functional visibility through dynamic visuals, filters, and drill-through capabilities.

> By connecting drivers, routes, vehicles, and weather into a cohesive analytical framework, this solution replaces guesswork with clear, data-backed operational visibility and prepares the ground for intelligent forecasting.

## 3. Strategic Benefits

Implementing this Power BI dashboard will deliver measurable improvements across operational efficiency, environmental sustainability, and service reliability. By integrating delivery performance, vehicle telemetry, driver data, and weather conditions into a single analytical platform, the business stands to benefit in the following key areas:

### 3.1 Improved Delivery Timeliness
With visibility into delivery bottlenecks (`delivery > 2hrs`, `avg delivery duration`) and weather-related delays (`windrisk category`, `heavy rain days`), logistics coordinators can proactively reassign drivers or reroute vehicles. This is expected to improve on-time deliveries by an estimated **12–15%**.

### 3.2 Fuel Cost Reduction
Cross-analyzing `fuel efficiency`, `avg fuel`, and `distance km` across routes and vehicle types helps identify inefficient patterns. By optimizing route allocation and favoring high-efficiency vehicles, fuel usage is projected to decrease by **8–10%**, translating to direct cost savings.

### 3.3 Emissions and Sustainability Tracking
The inclusion of `emission factor`, `avg emission`, and `total emissions` metrics enables ongoing tracking of the fleet's carbon footprint. This not only supports internal ESG goals but also prepares the business for compliance with future environmental regulations. Estimated reduction in CO₂ emissions is **5–8%** over 12 months.

### 3.4 Driver Performance Insights
Using `avg deliveries`, `exp category`, and `region` from `Cleaned_Dim_Drivers`, managers can match drivers with routes that suit their experience, improving productivity and reducing overwork or underutilization. This fosters better HR planning and driver satisfaction.

### 3.5 Faster Operational Decisions
The dashboard replaces manual reporting cycles and spreadsheet-based monitoring with live KPIs, enabling real-time decisions across departments. Cross-functional teams—from fleet managers to sustainability officers—gain shared visibility and faster time-to-action.

> **In summary**, the dashboard equips operations, planning, and sustainability teams with the tools to act on live insights, reduce cost drivers, and strengthen delivery performance across the board.


## 4. Key Stakeholders

The successful adoption and impact of this Power BI dashboard depend on the collaboration of multiple cross-functional teams. The following stakeholders are either decision-makers, end users, or key contributors to the development, deployment, and long-term utility of the solution:

- **Head of Logistics Operations**  
  Oversees regional and global delivery performance. Uses dashboard insights to monitor KPIs such as on-time deliveries, total delivery hours, and delays exceeding SLA thresholds.

- **Fleet Managers**  
  Responsible for vehicle performance and allocation. Rely on `fuel efficiency`, `emissions`, and `avg fuel` data to optimize fleet usage and identify high/low-performing vehicle types.

- **Regional Route Planners**  
  Use data from `Cleaned_Dim_Routes` and `Dim_Weather` to redesign or reroute based on weather risks (`windrisk category`, `heavy rain days`) and distance metrics (`avg distance`, `max route distance`).

- **Driver Managers / HR**  
  Leverage `Cleaned_Dim_Drivers` insights (e.g., `experience category`, `driver per region`, `avg deliveries`) to balance workloads, assign routes effectively, and manage training needs.

- **Sustainability & Compliance Officers**  
  Monitor `emission factor`, `total emissions`, and `high emitters count` to report on ESG goals and ensure environmental compliance.

- **Data & Reporting Analysts**  
  Maintain the data model, optimize queries, and enhance DAX performance. They support long-term scalability and can introduce predictive capabilities in future phases.

- **IT & Power BI Admin Team**  
  Provide data infrastructure, access control, and refresh schedules to ensure that dashboard deployment is secure, scalable, and reliable.

- **Project Sponsor**  
  Typically a senior executive (e.g., Director of Operations or Chief Data Officer) who champions the initiative, secures budget, and ensures alignment with organizational strategy.

> Each stakeholder group benefits from different views and levels of drill-down, ensuring the dashboard serves both strategic oversight and day-to-day operational needs.

## 5. Metrics for Success

To measure the effectiveness of the Route Intelligence dashboard, we define the following key performance metrics. These metrics will be tracked using data from the `Cleaned_Fact`, `Dim_Vehicles`, `Dim_Weather`, and `Cleaned_Dim_Drivers` tables.

| Metric                              | Baseline | Target | Frequency |
|-------------------------------------|----------|--------|-----------|
| % On-time Deliveries                | 78%      | 90%    | Weekly    |
| Avg. Fuel Consumption (L/km)        | 0.32     | 0.28   | Monthly   |
| Emissions per km (gCO₂)             | 270      | 230    | Monthly   |
| High-Emission Vehicle Ratio (%)     | 22%      | <15%   | Monthly   |
| Deliveries per Driver per Week      | 85       | 100    | Weekly    |
| Rain/Wind Delay Impacted Deliveries | 15%      | <7%    | Weekly    |

These metrics serve as the foundation for evaluating both short-term efficiency gains and long-term sustainability improvements. While some baseline values are currently estimates derived from initial analysis, they can be refined as more data is integrated and verified.


## 6. Risks & Mitigation

- **Risk:** Inaccurate or incomplete data in `Cleaned_Fact` or `Dim_Weather` tables  
  **Mitigation:** Implement automated data validation rules and regular audits

- **Risk:** Low adoption by drivers and fleet managers  
  **Mitigation:** Provide tablet-based training and ensure dashboards are mobile-friendly

- **Risk:** Integration issues with legacy systems or Excel-based tracking  
  **Mitigation:** Work closely with the tech team to create seamless ETL pipelines and ensure backward compatibility

- **Risk:** Resistance from operations staff used to manual logs  
  **Mitigation:** Run change management sessions and emphasize time-saving benefits

- **Risk:** Delayed or inconsistent data refresh cycles  
  **Mitigation:** Schedule automated data pipeline refreshes and monitor failures proactively

- **Risk:** Misinterpretation of KPIs due to lack of context  
  **Mitigation:** Add tooltip explanations and glossary within the dashboard UI
