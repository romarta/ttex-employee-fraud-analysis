# TTex Employee Fraud Analysis | Python & Power BI

End-to-end analysis of company vehicle usage and employee travel records to identify potential irregularities in trip distances and reported fuel consumption. The project combines Python-based data cleaning and exploratory analysis with Power BI reporting to support investigation of suspicious records and improve oversight of fleet-related expenses.

## Project Overview

TTex needs to assess the reliability of its company vehicle records and identify unusual patterns in employee trips and fuel usage. The analysis focuses on data quality, consistency of travel records, and anomalies that may indicate inaccurate reporting or warrant further investigation.

The source data consists of **64 Excel files** covering five related entities:

- departments,
- job positions,
- employees,
- company vehicles,
- trips.

After validation, cleaning, and integration, the final analytical dataset contains **4,432 trip records** and **24 columns**. The reference tables include **5 departments, 36 positions, 36 employees, and 20 vehicles**.

## Business Questions

The analysis addresses four questions:

1. Are trip distances consistent for journeys between the same locations?
2. Are there trips with unusually high reported fuel consumption relative to comparable journeys made with the same vehicle?
3. Were trips recorded within the relevant employees' employment periods and vehicles' activity periods?
4. Which records, employees, and vehicles should be prioritized for further investigation?

## What I Did

### 1. Data validation and cleaning

- consolidated data from 64 Excel files into five entity-level tables,
- checked and removed duplicate records introduced by combining files,
- inspected data types and missing values,
- resolved missing vehicle activity-status values using available activity dates,
- standardized inconsistent location names and spelling variants,
- checked trip-date consistency and employee/vehicle activity periods.

### 2. Data preparation and integration

- joined trip, vehicle, employee, position, and department data,
- built a trip-level analytical dataset with 4,432 rows and 24 columns,
- created standardized route identifiers so journeys could be compared regardless of travel direction,
- calculated route-level distance benchmarks and vehicle-level fuel-consumption measures.

### 3. Trip distance analysis

- examined the distribution of trip distances and descriptive statistics by route,
- calculated the median distance for each route,
- flagged trips exceeding the relevant route median by **more than 10%**,
- summarized the flagged trips by route, distance, and employee.

### 4. Fuel consumption analysis

- calculated reported fuel consumption per **100 km** for each trip,
- compared fuel-consumption distributions across vehicle groups,
- calculated median consumption for each vehicle group,
- flagged trips with fuel consumption **more than 50% above** the corresponding vehicle-group median,
- summarized flagged trips and average consumption deviations by employee.

### 5. Power BI reporting

The Power BI component presents the vehicle-usage and fuel-consumption analysis in an interactive reporting format, complementing the Python investigation. It focuses on trip-distance patterns, vehicle-level fuel consumption, flagged trips, and employee-level irregularities to help users explore the results.

## Tools and Technologies

- **Python** — data analysis and anomaly detection
- **pandas** — data cleaning, integration, grouping, and calculations
- **NumPy** — numerical operations and conditional calculations
- **Matplotlib / Seaborn** — exploratory data visualizations
- **Jupyter Notebook** — reproducible analytical workflow
- **Quarto** — report generation
- **Power BI** — interactive analysis and reporting
- **Excel** — source data format

## Key Findings

- **4,432 trip records** were integrated into the analytical dataset. Recorded trip distances ranged from **3 km to 576 km**, with an average of approximately **150.34 km**.
- **Trip timing checks found no conflicts** with the recorded employee employment dates or vehicle activity periods. Trip start and end dates were also consistent.
- **30 trips** exceeded their route's median distance by more than **10%**. Many concerned trips to broadly defined locations, such as a shop or office, where distance differences do not necessarily indicate misconduct.
- **670 trips** were flagged for reported fuel consumption more than **50% above** the vehicle-group median.
- The fuel-consumption flags were concentrated among **two Transport Department employees**, associated with trips made using a **Fiat Ducato** and a **Ford Transit**. Their records warrant closer examination rather than an assumption of proven fraud.

**Important:** Flagged records are indicators of potentially inaccurate reporting, not proof of intentional fraud.

## Business Recommendations

- review flagged distance records, particularly where destination labels are too broad to establish a reliable route benchmark,
- verify unusually high reported fuel consumption against fuel receipts, mileage logs, and other supporting documentation,
- prioritize investigation of recurring fuel-consumption anomalies linked to particular employees or vehicles,
- standardize location entries and strengthen validation rules at data entry,
- use Power BI reporting to support regular reviews of fleet utilization and exceptions.

## Repository Contents

```text
ttex-employee-fraud-analysis/
|
|-- README.md
|
|-- analysis/
|   `-- fraud_analysis.ipynb
|
|-- dashboard/
|   `-- fraud_analysis.pbix
|
|-- report/
|   |-- fraud_analysis.pdf
|   `-- fraud_analysis.qmd
|
`-- data/
    `-- TTex_*.xlsx
```

### File descriptions

- **`analysis/fraud_analysis.ipynb`** — Python notebook containing source-data integration, cleaning, validation, exploratory analysis, and anomaly identification.
- **`dashboard/fraud_analysis.pbix`** — Power BI report for exploring vehicle usage, trip-distance anomalies, and unusual fuel-consumption patterns.
- **`report/fraud_analysis.pdf`** — written report summarizing the business problem, methodology, findings, and recommendations.
- **`report/fraud_analysis.qmd`** — Quarto source file used to generate the written analysis report.
- **`data/TTex_*.xlsx`** — weekly source Excel files containing department, position, employee, vehicle, and trip records.

## Limitations

- Distance comparisons are based on route labels; locations such as “shop” or “office” may represent different actual destinations.
- Fuel-consumption thresholds are **screening rules**, not validated fraud-detection models. They do not independently account for driving conditions, cargo weight, traffic, or reporting conventions.
- The analysis identifies deviations from observed medians rather than establishing actual fuel misuse or financial loss.
- Flagged cases require verification against independent operational records before drawing conclusions about employee conduct.

## Summary

This project demonstrates a practical fraud-risk screening workflow: consolidating fragmented Excel data, validating records, integrating related tables, applying explainable anomaly thresholds, and translating findings into investigation priorities. Python provides the analytical foundation, while Power BI supports interactive exploration and reporting of potential irregularities in company vehicle usage and fuel consumption.
