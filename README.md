# 🧠 Sales Funnel Data Generation & Analysis

This project simulates a complete sales funnel dataset using Python and performs initial analysis using Excel and SQL. It's designed to showcase technical skills in data generation, preprocessing, and readiness for visualization and business insights.

---

## 📌 Project Overview

We created a **synthetic dataset** of 10,000 leads moving through a standard B2B/B2C sales funnel, including:

- Lead source
- Industry
- Conversion stage (awareness → deal closed)
- Revenue
- Profit
- Country

This dataset was built to:
- Practice and showcase analysis techniques
- Create a realistic, yet flexible dataset for Power BI / Tableau
- Demonstrate readiness for data analyst/business analyst roles

---

## 🧰 Tools Used

| Tool       | Purpose                              |
|------------|--------------------------------------|
| **Python (Jupyter)** | Generate realistic fake data using `pandas`, `numpy`, `faker` |
| **Excel**   | Initial data cleaning, exploration, KPIs |
| **SQL (SQLite / PostgreSQL)** | Querying for funnel metrics |
| **Tableau / Power BI** | Optional future visualization layer |

---

## 🧪 Steps Taken

### 1. Python (Data Generation)
- Generated 10,000 rows of lead data using Faker and NumPy
- Saved dataset to Excel using `pandas.to_excel()`
- Built fields like:
  - `Lead_ID`
  - `Stage` (Awareness, Consideration, Decision, etc.)
  - `Revenue`, `Profit`, `Cost`, `Country`

### 2. Excel (Initial Analysis)
- Cleaned missing/duplicate values
- Created PivotTables to summarize:
  - Total revenue per stage
  - Average profit margin per industry
  - Conversion count per country/source
- Built simple charts and KPIs

### 3. SQL (Data Insights)
- Imported Excel file into SQLite/Postgres
- Example queries:
```sql
-- Total revenue by lead source
SELECT lead_source, SUM(revenue) AS total_revenue
FROM leads
GROUP BY lead_source;

-- Average profit margin by industry
SELECT industry, AVG(profit / revenue * 100) AS avg_margin_pct
FROM leads
WHERE revenue > 0
GROUP BY industry;
