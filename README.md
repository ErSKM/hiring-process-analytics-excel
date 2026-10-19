# Hiring Process Analytics — Excel (Advanced)

**Tool:** Microsoft Excel 2021 (Power Query, PivotTables, statistical functions, charts, dashboard)  
**Dataset:** Hiring Process Statistics — 7,168 applicant records from a multinational company (2014)  
**Domain:** HR Analytics / Talent Acquisition  
**Status:** Completed

---

## Project Overview

This project analyzes hiring-process data to examine gender distribution among applicants and hires, salary patterns, departmental activity, and position-tier composition. It presents five analysis tasks using Excel and summarizes descriptive findings for the provided dataset.

---

## Dataset Description

| Column | Description |
|---|---|
| `application_id` | Identifier for each application record |
| `Interview Date` | Date and time of the interview |
| `Status` | Outcome — Hired or Rejected |
| `Gender` | Applicant gender (Male / Female / Not Disclosed) |
| `Department` | One of 9 company departments |
| `Position Code` | Coded job position (e.g., c5, i7, b9) |
| `Position Tier` | Derived tier from position code (Clerical / Intermediate / Business / Management / Non-Technical) |
| `Salary` | Offered salary in INR |
| `Salary Band` | Derived salary range bucket |

**Raw records:** 7,168  
**Records after cleaning:** 7,162  
**Records removed:** 6 — 3 salaries below ₹1,000 were excluded as implausibly low, and 3 salaries above the IQR upper fence of ₹1,47,763.25 were excluded.

---

## Excel Techniques Used

- **Power Query** — Data preparation and loading
- **Formula-based derived columns** — Position Tier (IF + LEFT) and Salary Band (nested IF)
- **PivotTables** — Cross-tabulations for the five analysis tasks
- **Statistical functions** — AVERAGE, MEDIAN, STDEV, QUARTILE, COUNTIFS, AVERAGEIFS
- **IQR review** — Q1, Q3, and IQR calculated; the upper fence was used to flag three high-salary records. Three sub-₹1,000 salaries were separately excluded as implausibly low.
- **Charts and dashboard** — Pie, bar, column/histogram, and donut charts arranged in a dashboard

---

## Analysis Tasks and Key Findings

### A. Gender Distribution of Hires

- **Total hired:** 4,692 of 7,162 cleaned records (65.5%)
- **Male applicants hired:** 2,561 of 4,083 (62.7%)
- **Female applicants hired:** 1,853 of 2,672 (69.3%)
- **Not disclosed applicants hired:** 278 of 407 (68.3%)
- These are descriptive rates for this dataset. They do not establish why the rates differ or support a conclusion about hiring bias.

### B. Average Salary

- **Mean salary:** ₹49,887
- **Median salary:** ₹49,625
- **Standard deviation:** ₹28,342
- General Management has the highest average salary (₹55,295); Marketing has the lowest (₹48,490).

### C. Salary Distribution

- The ₹40k–60k band is the largest, representing about **21.4%** of cleaned records.
- Counts are broadly similar across the five displayed salary bands; the workbook does not include a formal normality test.
- The “Very High (>₹100k)” band has no records after cleaning; the maximum salary is ₹99,967.

### D. Departmental Analysis

- **Operations** has the most applicants: 2,771 (38.7%).
- **Service** is second: 2,052 (28.6%).
- Together, Operations and Service account for 67.3% of cleaned records.
- **Human Resources** has the lowest applicant volume: 97 (1.4%).

### E. Position Tier Analysis

- **Clerical:** 4,091 records (57.1%)
- **Intermediate:** 2,603 records (36.4%)
- Clerical and Intermediate together account for 93.5% of cleaned records.
- Management and Non-Technical each have 3 records, so those groups are too small for broad conclusions.

---

## Statistical Summary

| Metric | Value |
|---|---:|
| Total Records | 7,168 |
| Records after cleaning | 7,162 |
| Records removed | 6 |
| Hire Rate | 65.5% |
| Rejection Rate | 34.5% |
| Mean Salary | ₹49,887 |
| Median Salary | ₹49,625 |
| Standard Deviation | ₹28,342 |
| Q1 | ₹25,473.25 |
| Q3 | ₹74,389.25 |
| IQR | ₹48,916 |
| Upper Outlier Fence (Q3 + 1.5 × IQR) | ₹147,763.25 |
| Minimum Salary (after cleaning) | ₹1,007 |
| Maximum Salary (after cleaning) | ₹99,967 |

---

## Workbook Structure

| Sheet | Contents |
|---|---|
| `Raw Data` | Cleaned dataset (7,162 records) with derived columns |
| `Analysis` | PivotTables and analysis for Tasks A–E |
| `Summary Stats` | Statistical summary |
| `Dashboard` | KPI cards and five charts |

---

## Files

| File | Description |
|---|---|
| `Hiring_Process_Analytics_Excel.xlsx` | Excel workbook with the analysis |
| `README.md` | Project overview and findings |
| `dashboard.png` | Dashboard screenshot |

---

## How to Use

1. Open `Hiring_Process_Analytics_Excel.xlsx` in Microsoft Excel 2021 or a compatible recent version.
2. Start on the `Dashboard` sheet for the summary view.
3. Open `Analysis` to review the five analysis tasks.
4. Review the cleaned records and derived columns in `Raw Data`.
5. Refer to `Summary Stats` for the statistical summary.

---

## Author

**Salahuddin K M** — Data Analyst  
Portfolio: [erskm.github.io](https://erskm.github.io) | GitHub: [github.com/ErSKM](https://github.com/ErSKM)
