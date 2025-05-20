# HR Analytics Dashboard Project

![Power BI](https://img.shields.io/badge/tool-Power%20BI-yellow?style=for-the-badge&logo=powerbi)
![MySQL](https://img.shields.io/badge/tool-MySQL-blue?style=for-the-badge&logo=mysql)
![Excel](https://img.shields.io/badge/tool-Excel-green?style=for-the-badge&logo=microsoft-excel)

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Tools Used](#tools-used)
- [Dataset Information](#dataset-information)
- [Data Preparation](#data-preparation)
- [SQL Analysis](#sql-analysis)
- [Power BI Dashboard](#power-bi-dashboard)
- [Retention Risk Model](#retention-risk-model)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Screenshots](#screenshots)
- [Limitations](#limitations)
- [Conclusion](#conclusion)
- [Author](#author)

---

## Project Overview

This project explores patterns and drivers of employee attrition using historical HR data. It combines SQL for querying, Excel for initial wrangling, Power BI for visualization, and DAX for KPI modeling. The final deliverable is a dynamic, interactive dashboard that HR teams can use to monitor retention, identify high-risk groups, and make proactive decisions.

---

## Objectives

- Analyze key factors influencing employee attrition.
- Build dynamic KPIs and interactive visuals using Power BI.
- Develop a custom Retention Risk Score using business rules.
- Provide actionable recommendations to improve retention.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| **MySQL** | Data extraction, filtering, grouping |
| **Microsoft Excel** | Initial data cleaning and exploration |
| **Power BI** | Dashboard design and data visualization |
| **DAX** | Creation of dynamic KPIs and risk scoring |
| **Python (optional)** | For potential automation or scripting |

---

## Dataset Information

- **Source**: [IBM HR Analytics Employee Attrition Dataset](https://www.ibm.com/communities/analytics/watson-analytics-blog/hr-employee-attrition/)
- **Rows**: 1,470
- **Columns**: 35
- **Target Column**: `Attrition` (Yes/No)

Key features include Age, Gender, Department, Job Role, Monthly Income, Overtime, Job Satisfaction, and Years at Company.

---

## Data Preparation

Steps performed:
- Removed irrelevant columns (`EmployeeNumber`, `Over18`, `StandardHours`)
- Formatted categorical and numeric fields
- Created new calculated fields:
  - `YearsSinceLastPromotion`
  - `Risk Score` input fields (income, satisfaction, overtime)
- Exported cleaned data as CSV for Power BI

---

## SQL Analysis

Performed using MySQL Workbench:
- Total Attrition and Attrition Rate
- Department and Job Role-based attrition counts
- Influence of Overtime, Monthly Income, and Promotions
- Filtered high-risk groups based on multiple dimensions

---

## Power BI Dashboard

Dashboard Sections:
- **KPI Cards**: Attrition Rate, Total Employees, Avg Age, Avg Income
- **Charts**:
  - Attrition by Department, Job Role, Gender, Age, Overtime
  - Risk Level Classification
  - Satisfaction Scores vs Attrition
- **Slicers** for Department, Gender, Education Field

All visuals are dynamic and reflect selected filters in real time.

---

## Retention Risk Model

Custom DAX score was built using:
- High Overtime = +25
- Low Job Satisfaction = +25
- Delayed Promotion (4+ years) = +15
- Low Monthly Income (< $3000) = +20
- Poor Environment Satisfaction = +15

### Risk Levels:
- **Low Risk**: Score < 30
- **Medium Risk**: 30 ≤ Score < 60
- **High Risk**: Score ≥ 60

This model helps HR prioritize interventions for individuals or departments.

---

## Key Insights

- Over 16% of employees have left the company.
- Sales department and overtime workers show high attrition rates.
- Employees with low satisfaction and delayed promotions are most likely to leave.
- Majority of high-risk employees earn less than $3,000 monthly.

---

## Recommendations

- Monitor and support high-risk employees identified in the dashboard.
- Reduce overtime and promote a balanced workload.
- Review promotion policies for employees with 4+ stagnant years.
- Adjust compensation for low-income roles where feasible.

---

## Screenshots


![Attrition Dashboard](screenshots/attrition-dashboard.png)
![Retention Risk Analysis](screenshots/risk-score.png)
![KPI Section](screenshots/kpi-section.png)
