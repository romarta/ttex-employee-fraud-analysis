# FLEETGUARD
## Fleet Fraud Detection & Analytics

## Live Interactive Dashboard

[**Open FLEETGUARD in Power BI**](https://app.powerbi.com/view?r=eyJrIjoiY2ZkMTBhMjctYWExYy00MzQ5LTljZGEtZDdjMDM4ZjI2YjdlIiwidCI6IjJmYWI1MTA4LTBiM2UtNDYwMy05Yjc3LTM2Y2QyYzk0ZmEzZSJ9&pageName=1873d2e93ba65ee9c949)

Explore the interactive fleet analytics dashboard,
including fuel anomaly detection, employee risk scoring,
fleet utilization, and financial exposure analysis.

**Dataset:** Synthetic data for demonstration purposes.

### Project Overview

FLEETGUARD is an interactive Power BI solution designed to
identify unusual fuel consumption patterns, analyze employee
driving behavior, monitor fleet utilization, and estimate
potential financial exposure.

The project uses a synthetic dataset containing 64 Excel files.

The objective is to demonstrate how business intelligence,
statistical benchmarking, and risk scoring can support
fleet auditing and investigation prioritization.

### Business Objectives

- Detect unusual fuel consumption using peer benchmarks.
- Identify employees requiring additional audit review.
- Analyze mileage consistency across comparable routes.
- Monitor travel behavior and vehicle utilization.
- Estimate potential financial exposure using fuel price scenarios.
- Assess data quality and benchmark coverage.

### Dataset Overview

| Metric | Value |
|--------|-------|
| Recorded Trips | 4,432 |
| Total Distance | 666,300 KM |
| Recorded Fuel | 77,104.16 L |
| Active Drivers | 14 |
| Vehicles Used | 8 |
| Source Files | 64 Excel files |

All data is synthetic and used for demonstration purposes.

### Key Analytical Findings

**Fuel Anomaly Detection**

- 3,980 trips were assessed using peer benchmarks.
- 648 trips exceeded their benchmarks by at least 50%.
- Fuel assessment coverage reached 89.8%.
- The anomaly rate among assessed trips was 16.3%.

**Mileage Consistency**

- 4,336 trips were assessed.
- Mileage assessment coverage reached 97.8%.
- Observed distance deviations ranged from -4.8% to +4.9%.

**Financial Exposure**

- Estimated excess fuel: 12,143.67 L.
- Financial exposure is calculated using an adjustable
  fuel price scenario.
- All financial results are model-based estimates.

### Power BI Features

- Interactive dashboards and cross-filtering
- Star schema data modeling
- Power Query data transformation
- Advanced DAX calculations
- Statistical peer benchmarking
- Employee risk scoring
- Drill-through investigation pages
- Bookmarks and page navigation
- What-if parameters
- Custom report page tooltips
- Data quality monitoring

### Report Pages

1. Executive Overview
2. Employee Risk Ranking
3. Fuel Consumption Audit
4. Route & Mileage Audit
5. Travel Behavior Analysis
6. Fleet Utilization
7. Financial Exposure Analysis
8. Data Quality & Methodology

The report also includes a dedicated Employee Investigation
drill-through page.

### Methodology

Fuel anomalies are identified by comparing trip-level
fuel consumption against the median consumption of other
drivers using the same vehicle and route pair.

A valid fuel benchmark requires at least 20 comparable
trips performed by at least two other drivers.

Employee risk scores combine anomaly frequency,
severity, and persistence.

Mileage consistency is assessed using route-specific
peer benchmarks.

### Limitations

- The dataset is synthetic.
- Data is available for 2023 and 2026, with no records
  for 2024–2025.
- Some trip dates extend beyond the analysis date.
- Exact GPS routes are unavailable.
- Historical department assignments are unavailable.
- Fuel quantities have not been verified against purchases.
- Peer benchmarks are calculated using the full dataset.

Detected anomalies indicate areas for further investigation.
They do not constitute confirmed fraud.

Estimated financial exposure does not represent
confirmed financial loss.
