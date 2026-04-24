# 📊 IBM HR Attrition — Python EDA

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-EDA-green?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Charts-9cf)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plots-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> 🔗 **Same project — SQL + Power BI version:** [Click here](https://github.com/Amitj6124/ibm-hr-attrition-eda-python)

---

## 🎯 Overview

Exploratory Data Analysis on IBM's HR dataset of **1,470 employees** to find out who is leaving the company and why — using Python (Pandas, Matplotlib, Seaborn).

The analysis covers department-level breakdowns, salary impact, overtime effect, tenure patterns, and identification of high-risk employee segments.

---

## 🗃️ Dataset

| | |
|---|---|
| Source | [Kaggle — IBM HR Analytics](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) |
| File | `WA_Fn-UseC_-HR-Employee-Attrition.csv` |
| Rows | 1,470 employees |
| Columns | 35 features |
| Target | `Attrition` (Yes / No) |

---

## 📁 Project Structure

```
ibm-hr-attrition-eda-python/
├── ibm_hr_eda.ipynb
├── data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv
├── screenshots/
│   ├── attrition.png
│   ├── Attrition by dept.png
│   ├── Attrition by salary band.png
│   ├── Attrition overtime vs no time.png
│   ├── avg monthly income.png
│   └── random 1.png
└── README.md
```

---

## 📊 Analysis Breakdown

### 1 — Overall Attrition Split
Count and percentage of employees who left vs stayed across the entire organization.

![attrition](screenshots/attrition.png)

---

### 2 — Attrition by Department
Department-wise attrition rate to identify which teams are losing the most people.

![dept](screenshots/Attrition%20by%20dept.png)

> **Sales** department shows the highest attrition rate among all departments.

---

### 3 — Average Monthly Income by Attrition
Salary comparison between employees who left vs who stayed.

![income](screenshots/avg%20monthly%20income.png)

> Employees who left earned notably less on average — compensation is a clear driver of attrition.

---

### 4 — Overtime vs Attrition
How working overtime correlates with the decision to leave.

![overtime](screenshots/Attrition%20overtime%20vs%20no%20time.png)

> Overtime employees have an attrition rate of **~30.5%** vs **~10.4%** for non-overtime — nearly **3x higher**.

---

### 5 — Attrition by Salary Band
Employees segmented into Low / Mid / High salary bands compared against attrition rate.

![salary](screenshots/Attrition%20by%20salary%20band.png)

> **Low salary band (<$3k/month)** has the highest attrition at ~29.4% — compensation is the single biggest lever.

---

### 6 — Tenure Analysis (Years at Company)
Attrition rate plotted across each year of tenure to find the danger zone.

![tenure](screenshots/random%201.png)

> Employees in their **first 2 years** are most likely to quit. Attrition spikes sharply at Year 0–2 and stabilizes after Year 5.

---

## 💡 Key Business Insights

| # | Finding |
|---|---------|
| 1 | Overall attrition rate is **~16.1%** |
| 2 | **Sales** has the highest department-level attrition |
| 3 | Overtime employees leave at **~3x the rate** of non-overtime employees |
| 4 | **Low salary band** employees face the highest attrition (~29.4%) |
| 5 | **Year 0–2 tenure** is the critical danger zone for employee exits |
| 6 | High-risk segment identified: **Overtime + Low Pay + Low Job Satisfaction** |

---

## ✅ Recommendations

- **Revisit overtime policy** — excessive OT is the strongest predictor of attrition
- **Revise compensation** for low salary band employees
- **Focus HR programs** on the Sales department
- **Strengthen onboarding and mentorship** for Year 0–2 employees
- **Flag and monitor** the high-risk segment: OT + low pay + low satisfaction

---

## ▶️ How to Run

```bash
git clone https://github.com/Amitj6124/ibm-hr-attrition-eda-python.git
cd ibm-hr-attrition-eda-python
pip install pandas matplotlib seaborn
jupyter notebook ibm_hr_eda.ipynb
```

Or open in **Google Colab** — upload the CSV to `/content/` and run all cells.

---

## 🛠️ Tech Stack

`Python 3.10+` · `Pandas` · `Matplotlib` · `Seaborn` · `Jupyter Notebook / Google Colab`

---

⭐ *If this helped, drop a star on the repo!*
