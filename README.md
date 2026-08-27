# 🔍 Inventory Shortage Root-Cause Analysis

> **MS SQL Server | Python | Jupyter Notebook | Excel | Data Visualization | Business Analytics**

An end-to-end data analytics project using **SQL Server**, **Python**, and **Excel** to investigate the root cause of recurring stock shortages across product categories, stores, and products for a retail business — and translate the findings into actionable, data-driven recommendations.

---

## 🎯 Business Objective

A recurring stock shortage problem is rarely explained by a single number — it requires looking beyond surface-level metrics. This analysis evaluates multi-dimensional inventory and sales performance to answer key strategic questions:

- Which product category is most exposed to stock shortages, and why?
- Is the shortage concentrated in specific stores, or is it a company-wide issue?
- Which products need the most urgent attention within the affected category?
- Do demand-side factors (promotions, discounts, seasonality) explain the fluctuation in sales?
- Is the current reorder policy leaving any real safety margin for demand variability?

---

## 📈 Key KPIs & Highlights

| Metric / KPI | Current Value / Finding |
|---|---:|
| 🛒 Most Affected Category | **Groceries** |
| 📦 Groceries Total Inventory Volume | **~10.9M units** |
| 🔄 Groceries Inventory Turnover | **0.29 (lowest efficiency among top-volume categories)** |
| 🏬 Top Shortage Stores | **S005 (2,544 incidents) & S003 (2,081 incidents)** |
| 🥇 Most Affected Product | **P0010 (1,177 shortage incidents)** |
| ⚖️ Order-to-Sales Buffer Ratio (all categories) | **~1.0014 – 1.0036 (virtually no safety margin)** |

---

## 🔍 Core Analysis Modules

### 1. Inventory Performance Analysis (SQL)
- **Inventory Turnover by Category:** Groceries carries the largest inventory volume in the business (~10.9M units) but with a relatively low turnover rate (0.29), meaning a large amount of stock sits idle without being cleared efficiently.
- **Store-Level Breakdown:** Stock shortages within Groceries appear across all five stores, not one — with **S005** and **S003** recording the highest incident counts.
- **Product-Level Ranking:** Using `RANK() OVER (PARTITION BY Category)`, product **P0010** emerged as the most affected item specifically within Groceries — a priority order that differs from the company-wide ranking.

### 2. Statistical & Correlation Analysis (Python)
- **Correlation Matrix:** Sales volume was tested against time, discounts, promotions, and pricing factors. No meaningful linear relationship was found, ruling out demand-side shifts as the root cause.
- **Order-to-Sales Buffer Ratio:** The ratio of units ordered to units actually sold was calculated across every category and store. The ratio sits almost exactly at **1.0** everywhere — meaning the business orders almost exactly what it expects to sell, leaving no real cushion for day-to-day demand variability.

### 3. Root Cause Identification
The shortage is **not** driven by insufficient total inventory (Groceries has the largest stock volume in the company) and **not** driven by an unusual spike in demand (no significant correlation found). The real driver is a **company-wide reorder policy** that sets order quantities equal to historical average sales, with no built-in safety buffer — a policy that hits Groceries the hardest due to its high sales volume and day-to-day volatility.

---

## 💡 Key Insights

- **Volume ≠ Availability:** Having the largest inventory volume doesn't protect a category from shortages if turnover is inefficient and reorder policy lacks a safety margin.
- **Systemic, Not Local:** The shortage pattern appears across all stores, indicating a company-wide policy issue rather than a management failure specific to one branch.
- **Demand Is Not the Culprit:** Statistical testing ruled out promotions, discounts, and seasonal effects as drivers of the shortage.
- **No Safety Margin:** Across every category, order quantities track the historical average almost exactly (~1.00 ratio), leaving no room to absorb normal demand fluctuation.

---

## 🧭 Strategic Business Recommendations

1. **Introduce a Demand-Based Safety Buffer:** Move away from ordering strictly at the historical average, and build in a buffer proportional to each category's demand variability.
2. **Prioritize Groceries First:** Given its scale and volatility, Groceries should be the first category to receive an adjusted reorder policy.
3. **Focus on High-Incident Stores:** Stores S005 and S003 should be monitored closely as the policy adjustment is rolled out.
4. **Review Top Affected Products:** Products P0010, P0008, P0004, P0009, and P0001 should be reviewed first within Groceries before extending the policy company-wide.
5. **Extend Gradually:** Once validated at the category level, apply the same logic down to the store and product level.

---

## 🛠️ Tools & Technologies

- **SQL / MS SQL Server:** Aggregations, Window Functions (`RANK() OVER PARTITION BY`), Grouped Queries, Joins.
- **Python / Jupyter Notebook:** Data analysis and statistical testing.
- **ipython-sql & SQLAlchemy:** Direct SQL Server connection and query execution inside Jupyter.
- **Pandas & NumPy:** Data manipulation, aggregation, and correlation analysis.
- **Matplotlib & Seaborn:** Data visualization, correlation heatmaps, and custom chart styling.
- **Excel:** Initial data exploration and pivot-based overview.

---

## 📁 Repository Contents

| File | Description |
|---|---|
| `sales_data.csv` | Transaction-level dataset containing store, product, category, inventory, and sales details |
| `Inventory_Sales_Analysis.pdf` | Full exported analysis notebook with SQL queries, Python statistical testing, visuals, and business recommendations |
| `README.md` | Comprehensive project documentation |

---

## 👩‍💻 Author

### Yasmen Saber

**Data Analyst | SQL | Python | Excel**

Passionate about transforming raw data into strategic business insights and building actionable analytical reports.

---

## 🔗 Connect With Me

- 💼 [LinkedIn](https://www.linkedin.com/in/yasmen-saber/)
- 💻 [GitHub](https://github.com/YasmenSaber)

---

### ⭐ Feel free to explore the repository and leave a star if you find this project valuable!
