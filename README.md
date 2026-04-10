# Hiring Process Analytics — Excel (Advanced)

**Tool:** Microsoft Excel (Power Query, Pivot Tables, Statistical Functions, Charts, Dashboard)  
**Dataset:** Hiring Process Statistics — 7,168 applicant records from a multinational company  
**Domain:** HR Analytics / Talent Acquisition  
**Status:** Completed

---

## Project Overview

This project analyzes the hiring process data of a multinational company to uncover patterns in gender distribution, salary structure, departmental activity, and position-tier composition. The goal is to provide data-driven insights that can help the HR department improve hiring decisions and understand workforce trends.

The analysis covers five specific business questions across gender, salary, and organizational structure dimensions.

---

## Dataset Description

| Column | Description |
|---|---|
| `application_id` | Unique identifier per applicant |
| `Interview Date` | Date and time of the interview |
| `Status` | Outcome — Hired or Rejected |
| `Gender` | Applicant gender (Male / Female / Not Disclosed) |
| `Department` | One of 9 company departments |
| `Position Code` | Coded job position (e.g., c5, i7, b9) |
| `Position Tier` | Derived tier from position code (Clerical / Intermediate / Business / Management / Non-Technical) |
| `Salary` | Offered salary in INR |
| `Salary Band` | Salary range bucket (Very Low to High) |

**Raw records:** 7,168  
**Records after cleaning:** 7,162  
**Outliers removed:** 5 (2 implausibly low salaries below ₹1,000 + 3 above IQR upper fence of ₹1,47,959)

---

## Excel Techniques Used

- **Power Query** — Data load, column renaming, data type enforcement
- **Custom Columns** — Position Tier (IF + LEFT formula), Salary Band (nested IF), Gender Group (clubbing undisclosed entries)
- **Pivot Tables** — Cross-tabulations for all 5 analysis tasks with calculated fields
- **Statistical Functions** — AVERAGE, MEDIAN, STDEV, QUARTILE, COUNTIFS, AVERAGEIFS
- **IQR Outlier Detection** — Q1, Q3, IQR computed; upper/lower fences used to flag and remove outliers
- **Charts** — Pie, Clustered Bar, Horizontal Bar, Column/Histogram, Donut
- **Dashboard** — KPI cards, chart grid layout

---

## Analysis Tasks and Key Findings

### A. Gender Distribution of Hires
- **Total Hired:** 4,692 out of 7,162 applicants (65.5% hire rate)
- **Males hired:** 2,561 | **Females hired:** 1,853 | **Not Disclosed hired:** 278
- Male applicants make up 57% of the total pool; females 37%
- Hire rates are broadly proportional across genders — no significant hiring bias observed

### B. Average Salary
- **Mean salary:** ₹49,887
- **Median salary:** ₹49,625 (close to mean — confirms near-symmetric distribution)
- **Std deviation:** ₹28,342
- General Management offers the highest average salary (₹55,295); Marketing the lowest (₹48,490)

### C. Salary Distribution
- Salary is approximately normally distributed across 5 bands
- The ₹40k–60k mid-range is the most common band (1,533 records — 21.4%)
- Distribution is fairly even, with no extreme skew after outlier removal
- Note: "Very High (>100k)" band has 0 records post-outlier removal; max salary is ₹99,967

### D. Departmental Analysis
- **Operations Department** dominates with 2,771 applicants (38.7%)
- **Service Department** is second at 2,052 (28.6%)
- Together, Operations and Service account for 67.3% of all hiring activity
- Human Resource Department has the lowest volume (97 applicants — 1.4%)

### E. Position Tier Analysis
- **Clerical tier** is the largest: 4,091 records (57.1%)
- **Intermediate tier:** 2,603 records (36.4%)
- Clerical + Intermediate = 93.5% of all positions
- Management and Non-Technical tiers each have only 3 records — extremely sparse representation in this dataset

---

## Statistical Summary

| Metric | Value |
|---|---|
| Total Records | 7,168 |
| Records after cleaning | 7,162 |
| Outliers removed | 5 |
| Hire Rate | 65.5% |
| Rejection Rate | 34.5% |
| Mean Salary | ₹49,887 |
| Median Salary | ₹49,625 |
| Std Deviation | ₹28,342 |
| Q1 | ₹25,473 |
| Q3 | ₹74,389 |
| IQR | ₹48,916 |
| Upper Outlier Fence (Q3 + 1.5×IQR) | ₹1,47,763 |
| Min Salary (post-cleaning) | ₹1,007 |
| Max Salary (post-cleaning) | ₹99,967 |

---

## Workbook Structure

| Sheet | Contents |
|---|---|
| `Raw Data` | Cleaned dataset (7,162 rows) with all derived columns |
| `Analysis` | Pivot Tables and formula blocks for Tasks A–E |
| `Summary Stats` | Full statistical summary table |
| `Dashboard` | KPI cards + 5 charts in dashboard layout |

---

## Files

| File | Description |
|---|---|
| `HiringOperation_Raw_Data.xlsx` | Full Excel workbook with all analysis |
| `README.md` | This file |
| `screenshots/dashboard.png` | Dashboard screenshot for portfolio preview |

---

## How to Use

1. Open `HiringOperation_Raw_Data.xlsx` in Microsoft Excel (2016 or later)
2. Start on the `Dashboard` sheet for the summary view
3. Navigate to `Analysis` to see the individual Pivot Tables and task answers
4. `Raw Data` contains the cleaned dataset with all derived columns
5. `Summary Stats` contains the statistical reference table

---

## Author

**Salahuddin K M** — Data Analyst  
Portfolio: [erskm.github.io](https://erskm.github.io) | GitHub: [github.com/ErSKM](https://github.com/ErSKM)
