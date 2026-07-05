# **Talent Management & Workforce Dynamics Dashboard**
An interactive human resources dashboard designed to analyze workforce demographics, evaluate employee performance and track attrition trends to improve retention strategies at Liew Wai San Trading Co.

---

## 1. Project Overview & Business Problem

* **Objective:** Developed an interactive human resources dashboard to analyze workforce demographics, evaluate employee performance, and track attrition trends to improve retention strategies at Liew Wai San Trading Co. The solution identifies the operational root causes behind employee attrition to stabilize workforce dynamics and reduce talent replacement costs.
* **Target Audience:** HR Directors, C-Suite Executives, and Department Managers.

---

## 2. Technical Stack & Data Specifications

* **Tools Used:** Power BI Desktop, Power Query (M), DAX, and Power BI Service.
* **Data Source & Extraction:** Raw internal HR datasets loaded via distinct tabular files, including *Education*, *Attrition Rates*, *Employee Data*, *Job Involvement*, *Performance Rating*, *Satisfaction*, and *WorkLifeBalance*.
* **Data Modeling & Cleaning:** 
  * **Data Cleaning:** Pruned empty rows and rows containing null values. Standardized the `Attrition_rate` column to a percentage data type and the `Date` column to a DateTime layout. Eliminated redundant empty columns (Columns 30–40) in the primary employee data table.
  * **Schema Layout:** Built a standard Star Schema linking 5 peripheral dimension tables (*Education*, *Job Involvement*, *Performance Rating*, *Satisfaction*, *Work Life Balance*) to a centralized fact table (*Employee Data*) using One-to-Many ($1:*$) relationships.
  * **Hierarchies:** Configured an organizational drill-down path (`Department` $\rightarrow$ `Job Role`) inside the fact table.

---


## 3. Key Performance Indicators (KPIs) & Logic

* **Metrics & Formulas:** 
  * **Total Employees = DISTINCTCOUNT('Employee Data'[EmployeeID])
  * **Active Employees = CALCULATE([Total Employees], FILTER('Employee Data', 'Employee Data'[Attrition]="No"))
  * **Inactive Employees = CALCULATE([Total Employees], FILTER('Employee Data', 'Employee Data'[Attrition]="Yes"))
  * **% Attrition = DIVIDE([Inactive Employees], [Total Employees])* **
* **Visuals & Context:* ** 
  * **KPI Cards: Arranged summary cards at the top for immediate visibility into Total, Active, Inactive headcount, and Attrition Rate.
  * **Stacked Bar Chart: Selected to contrast attrition impact against structural salary bands.
  * **Treemap: Leveraged to visualize employee volume concentrations across department and job role hierarchies simultaneously
  * **Gauges: Employed to track average performance ratings and work-life balance levels against clear target thresholds.
  * **Dual-Axis Combination Chart: Implemented to compare employee headcount bars alongside average monthly income line trends by job role.

---

## 4. Key Insights & Business Recommendations

* **Insights:** 
  * **Compensation Trigger: Workers earning below $50k experience a massive 31.2% turnover rate, whereas individuals earning above $100k maintain a highly stable attrition profile of only ~10.5%.
  * **Work-Life Burnout: Staff required to complete Overtime assignments exhibit a ~30% turnover rate, significantly higher than non-overtime staff. Frequent business travel also accelerates voluntary departures.
  * **Tenure Risks: Attrition spikes aggressively within the initial 0–2 years of tenure, stabilizes mid-career, and spikes again at ultra-long tenure phases.
   
* **Recommendations:** 
  * **Adjust Entry-Level Compensation: Benchmark and increase entry-level compensation packaging for roles earning below $50k to mitigate the 31.2% churn rate.* **
  * **Manage Overtime & Travel Fatigue: Re-evaluate overtime necessity, audit business travel frequency, or implement compensatory resting cycles to mitigate burnout.* **
  * **Target Early Tenure Retention: Deploy specialized onboarding mentorship and explicit milestone career-mapping frameworks tailored to shield employees in their first two years.* **

---

## 5. Links & Access
Live Link: 
https://app.powerbi.com/groups/me/reports/c9bad196-4c97-485d-8ed9-d689371b84f2/3da49a5f76b4b386e416?experience=power-bi

---

## 6. Dashboard Visualizations Reference
Overview Page
<img width="1280" height="720" alt="overview" src="https://github.com/user-attachments/assets/4cfd8cb0-8c4e-4fac-8a34-fb52c2f93fe1" />

Demographic Page 
<img width="1280" height="720" alt="Demographic" src="https://github.com/user-attachments/assets/8aed9408-0b3c-4235-babf-b0ff8ebc38ab" />

Performance Tracker Page 
<img width="1280" height="720" alt="Performance Tracker" src="https://github.com/user-attachments/assets/0b282737-2c80-404d-827f-85f14faac71e" />

Attrition Rate Page 
<img width="1280" height="720" alt="Attrition Rate" src="https://github.com/user-attachments/assets/18a279f3-9666-4ef8-b9f1-2b6ab4af7b3f" />



