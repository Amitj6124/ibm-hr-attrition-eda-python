📊 IBM HR Attrition Analysis — Full Stack Project
> **SQL + Python EDA + Power BI Dashboard** — End-to-end employee attrition analysis using IBM HR dataset
![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-MySQL%2FSQLite-orange?logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-EDA-green?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
---
📁 Project Structure
```
IBM-HR-Attrition/
│
├── 📓 ibm_hr_eda.ipynb          # Python EDA Notebook (SQL → Pandas translation)
├── 📊 Attrition_project.pbix    # Power BI Dashboard
├── 🗃️ SQL Queries/              # Raw SQL analysis scripts (if separate)
├── 📂 data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv
└── 📄 README.md
```
---
🎯 Project Overview
This is a complete, multi-tool HR analytics project that analyzes employee attrition at IBM using three complementary approaches:
Tool	Purpose
SQL	Core business queries — aggregations, CTEs, subqueries
Python (Pandas + Seaborn)	EDA notebook mirroring SQL logic with charts
Power BI	Interactive executive dashboard for stakeholders
The dataset contains 1,470 employee records with 35 features including demographics, job role, salary, satisfaction scores, and attrition status.
---
🗃️ Dataset
Source: IBM HR Analytics Employee Attrition & Performance — Kaggle
File: `WA_Fn-UseC_-HR-Employee-Attrition.csv`
Rows: 1,470 employees
Columns: 35 features
Target Variable: `Attrition` (Yes / No)
---
📓 EDA Notebook — Query Breakdown
The notebook (`ibm_hr_eda.ipynb`) is structured as a SQL-to-Python translation, where every Pandas operation maps directly to a SQL query. This makes the logic readable for both data analysts and SQL users.
Queries Covered
#	Query	Chart
Q1	Total Employee Count	—
Q2	Attrition Count (Yes / No)	—
Q3	Department × Attrition Breakdown	—
Q4	Attrition Rate by Department (%)	✅ Bar Chart
Q5	Average Salary by Attrition Status	✅ Bar Chart
Q6	Overtime vs Attrition Rate	✅ Bar Chart
Q7	Income Stats — Min / Max / Avg	—
Q8	Attrition by Salary Band	✅ Bar Chart
Q9	CTE — High Risk Employees	—
Q10	Tenure Analysis (Years at Company)	✅ Line Chart
Q11	Subquery — Departments Above Average Attrition	—
SQL → Pandas Mapping (Examples)
```sql
-- SQL
SELECT Department, COUNT(*) AS total,
    ROUND(SUM(CASE WHEN Attrition='Yes' THEN 1 ELSE 0 END)*100.0/COUNT(*), 1) AS attrition_rate
FROM employee_attrition
GROUP BY Department ORDER BY attrition_rate DESC;
```
```python
# Python (Pandas equivalent)
dept_rate = df.groupby("Department").agg(
    Total_Employees=("Attrition", "count"),
    Left_Company=("Attrition_Flag", "sum")
).reset_index()
dept_rate["Attrition_Rate_%"] = (dept_rate["Left_Company"] / dept_rate["Total_Employees"] * 100).round(1)
dept_rate.sort_values("Attrition_Rate_%", ascending=False)
```
---
📊 Power BI Dashboard
The `.pbix` file (`Attrition_project.pbix`) provides an interactive executive dashboard built on the same dataset.
Dashboard Highlights
📌 Overall attrition KPI card
📊 Attrition by Department, Gender, Job Role
💰 Salary band vs attrition heatmap
⏰ Overtime impact visual
📅 Tenure / Years at Company trend
🔍 Slicer filters: Department, Gender, Age Group
> **To view:** Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download)
---
💡 Key Business Insights
```
══════════════════════════════════════════════════════
  KEY BUSINESS INSIGHTS
══════════════════════════════════════════════════════
  1. Overall Attrition Rate    : ~16.1%
  2. OT Employees Attrition    : ~30.5%   ← HIGH RISK
  3. Low Salary Band Attrition : ~29.4%   ← COMPENSATION ISSUE
  4. Highest Attrition Dept    : Sales
  5. High-Risk Employees       : OT + Low Satisfaction + Low Pay
  6. Danger Zone Tenure        : Year 0–2 employees leave the most
══════════════════════════════════════════════════════
```
Recommendations
🔴 Revisit Overtime Policy — OT employees are ~2x more likely to leave
💵 Revise Compensation for Low salary band employees
🏢 Focus HR programs on Sales department (highest attrition rate)
🎯 Strengthen Onboarding — Year 0–2 is the critical danger zone
---
🛠️ Tech Stack
```
Language    : Python 3.10+
Libraries   : Pandas, Matplotlib, Seaborn
BI Tool     : Microsoft Power BI Desktop
Database    : SQL (MySQL / SQLite compatible queries)
Notebook    : Jupyter / Google Colab
Dataset     : IBM HR Attrition (Kaggle)
```
---
🚀 How to Run
Option 1 — Run Notebook (Google Colab)
Upload `WA_Fn-UseC_-HR-Employee-Attrition.csv` to `/content/`
Open `ibm_hr_eda.ipynb` in Google Colab
Run all cells (`Runtime → Run all`)
Option 2 — Run Locally
```bash
git clone https://github.com/YOUR_USERNAME/IBM-HR-Attrition.git
cd IBM-HR-Attrition
pip install pandas matplotlib seaborn
jupyter notebook ibm_hr_eda.ipynb
```
Option 3 — Power BI Dashboard
Download and install Power BI Desktop
Open `Attrition_project.pbix`
Interact with slicers and visuals
---
📸 Screenshots
> *(Add screenshots of your Power BI dashboard and notebook charts here)*
Notebook EDA	Power BI Dashboard
![EDA](screenshots/eda_charts.png)	![Dashboard](screenshots/powerbi_dashboard.png)
To add screenshots:
```
screenshots/
├── eda_charts.png           # Notebook chart outputs
├── powerbi_dashboard.png    # Main dashboard page
└── powerbi_filters.png      # Slicer/filter panel
```
---
🗂️ File Details
File	Description
`ibm_hr_eda.ipynb`	Python EDA notebook with 11 SQL-mapped queries + 5 charts
`Attrition_project.pbix`	Power BI dashboard — fully interactive
`data/WA_Fn-UseC_-HR-Employee-Attrition.csv`	Raw IBM HR dataset
---
👤 Author
Amit
GitHub: https://github.com/Amitj6124/
LinkedIn: your-linkedin
---
⭐ If you found this useful, give the repo a star!
