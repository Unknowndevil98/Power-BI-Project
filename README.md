# 📊 HR Analytics Dashboard — Power BI

An interactive Power BI dashboard analyzing employee workforce data across **3,000+ records**, covering attrition, demographics, satisfaction, and organizational distribution — built with a strong focus on **data validation** before visualization.

---

## 🔍 Overview

This project started as a typical HR analytics dashboard, but evolved into a data-quality case study. During validation, I discovered that a significant portion of employees marked as **"Active"** in the source data actually had an **Exit Date** and a valid **Termination Type** on record — a direct logical contradiction.

Left uncorrected, this inconsistency would have **understated the true attrition rate by nearly 3x** (18% vs. the corrected 51.1%). The dashboard reflects the corrected, validated employee status logic.

---

## 🖼️ Dashboard Preview

**Page 1 — Overview**
> KPIs, Attrition Breakdown, Yearly Hiring Trend, Gender Split, Key Insights

**Page 2 — Workforce Demographics**
> Marital Status, Employment Type, Department, and Business Unit distribution

*(Add your dashboard screenshots here — e.g. `/assets/page1.png`, `/assets/page2.png`)*

---

## 📁 Dataset

| File | Description | Rows |
|---|---|---|
| `employee_data.csv` | Core employee records — status, department, business unit, demographics, exit info | 3,000 |
| `employee_survey_data.csv` | Employee engagement, satisfaction, and work-life balance survey scores | 3,000 |

---

## ⚠️ Data Quality Issue & Fix

**Problem:** ~991 employees had `EmployeeStatus = "Active"` while simultaneously having a populated `ExitDate` and a non-"Unknown" `TerminationType`.

**Fix:** Introduced a corrected status classification so that any employee with a valid exit record is reclassified as terminated, regardless of the original status label.


**Impact of the fix:**

| Metric | Before Fix | After Fix |
|---|---|---|
| Active Employees | 2,458 | 1,467 |
| Left Employees | 542 | 1,533 |
| Attrition Rate | 18.07% | **51.10%** |

---

## 📊 Key Metrics & Visuals

- **KPI Cards:** Total Employees, Total Active Employees, Left Employees, Attrition Rate, AVG Active Employee Rating, AVG Work Life Balance Score, AVG Satisfaction Score
- **Employee Status & Exit Type** — Pie chart of Active vs. Involuntary / Voluntary / Resignation / Retirement
- **Active Employees Joined By Year** — Hiring trend (2018–2023)
- **Total Active Employees by Gender**
- **Total Active Employees by Marital Status, Employment Type, Department, and Business Unit**
- **Interactive slicers:** Employment Type, Gender, Joining Date, Department

---

## 🧠 Key Insights

- Corrected attrition rate stands at **51.10%**, significantly higher than initially reported.
- **Female employees (817)** outnumber male employees (650) in the active workforce.
- **Production** department has the highest active workforce.
- Exit reasons are evenly split across Involuntary, Voluntary, Resignation, and Retirement (~12–13% each).
- Average Satisfaction and Work-Life Balance scores are both **3.03/5**, indicating moderate employee sentiment.

---

## 🛠️ Tools & Skills Used

- **Power BI Desktop** — Data modeling & report design
- **DAX** — Measures and calculated columns
- **Power Query** — Data cleaning and transformation
- **Data Validation** — Cross-checking source data integrity before building KPIs

---

## 🚀 How to Use

1. Clone this repository
2. Open `HR_Dashboard_On_Power_BI.pbix` in Power BI Desktop
3. Load `employee_data.csv` and `employee_survey_data.csv` when prompted (update file paths in Power Query if needed)
4. Refresh the data model to apply the corrected status logic

---

## 📬 Connect

If you found this project useful or have suggestions, feel free to connect or open an issue!
