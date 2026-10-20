# Hiring Process Analytics — Excel (Advanced)

**Tool:** Microsoft Excel 2021 (Power Query, PivotTables, statistical functions, charts, dashboard)  
**Dataset:** Hiring Process Statistics — 7,168 applicant records from 2014  
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

**Source records:** 7,168  
**Records in the cleaned worksheet:** 7,162  
**Difference:** 6 records

### Cleaning and reconciliation

The workbook's Summary Stats sheet reports Q1 of ₹25,473.25, Q3 of ₹74,389.25, an IQR of ₹48,916, and an upper IQR fence of ₹147,763.25. Comparing the supplied source statistics workbook with the cleaned worksheet by application ID and salary shows:

- Three omitted records had salaries above the upper fence: ₹200,000, ₹300,000, and ₹400,000.
- Two omitted records had salaries below ₹1,000: ₹100 and ₹800.
- One other omitted record had a salary of ₹85,914 and Position Code `Unassigned`. This salary is below the upper fence, and the supplied files do not document why this row was omitted.
- A source row with a ₹0 salary appears in the cleaned worksheet with a salary of ₹49,625, the reported median. This appears to be median imputation, but the workbook does not document the transformation rule.

The workbook's summary describes six records as removed through outlier cleaning. The row-level comparison confirms the six-record difference but shows that the six omissions do not all fit that explanation. The treatment of the `Unassigned` row and the ₹0-to-median change should therefore be considered undocumented in the supplied workbook.

---

## Excel Techniques Used

- **Power Query** — Data preparation and loading
- **Formula-based derived columns** — Position Tier (IF + LEFT) and Salary Band (nested IF)
- **PivotTables** — Cross-tabulations for the five analysis tasks
- **Statistical functions** — AVERAGE, MEDIAN, STDEV, QUARTILE, COUNTIFS, AVERAGEIFS
- **IQR review** — Calculated Q1, Q3, IQR, and the upper fence; three omitted high-salary records exceed that fence. The row-level comparison also identified two omitted salaries below ₹1,000 and one omitted `Unassigned` row below the upper fence.
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

The counts below are transcribed from the workbook's **Analysis** sheet Salary Distribution PivotTable:

| Salary band | Applications | Share of 7,162 |
|---|---:|---:|
| Very Low (₹0–20k) | 1,408 | 19.7% |
| Low (₹20k–40k) | 1,420 | 19.8% |
| Mid (₹40k–60k) | 1,533 | 21.4% |
| Upper-Mid (₹60k–80k) | 1,432 | 20.0% |
| High (₹80k–100k) | 1,369 | 19.1% |
| **Total** | **7,162** | **100.0%** |

The ₹40k–60k band is the largest. The five PivotTable counts sum to the cleaned record total. During reconciliation, the row-level `Salary Band` values showed a one-record difference in the Low and Mid counts compared with this PivotTable; the PivotTable counts are reported here, and that one-record split discrepancy remains unresolved. The workbook does not include a formal normality test. The “Very High (>₹100k)” band has no records in the cleaned worksheet; its maximum salary is ₹99,967.

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
| Source Records | 7,168 |
| Records in cleaned worksheet | 7,162 |
| Difference | 6 |
| Hire Rate | 65.5% |
| Rejection Rate | 34.5% |
| Mean Salary | ₹49,887 |
| Median Salary | ₹49,625 |
| Standard Deviation | ₹28,342 |
| Q1 | ₹25,473.25 |
| Q3 | ₹74,389.25 |
| IQR | ₹48,916 |
| Upper IQR Fence (Q3 + 1.5 × IQR) | ₹147,763.25 |
| Minimum Salary (cleaned worksheet) | ₹1,007 |
| Maximum Salary (cleaned worksheet) | ₹99,967 |

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
| `README.md` | Project overview, methodology notes, and findings |
| `dashboard.png` | Dashboard screenshot |

---

## How to Use

1. Open `Hiring_Process_Analytics_Excel.xlsx` in Microsoft Excel 2021 or a compatible recent version.
2. Start on the `Dashboard` sheet for the summary view.
3. Open `Analysis` to review the five analysis tasks.
4. Review the cleaned records and derived columns in `Raw Data`.
5. Refer to `Summary Stats` for the statistical summary and the cleaning-reconciliation note above for the six-record difference.

---

## Author

**Salahuddin K M** — Data Analyst  
Portfolio: [erskm.github.io](https://erskm.github.io) | GitHub: [github.com/ErSKM](https://github.com/ErSKM)
