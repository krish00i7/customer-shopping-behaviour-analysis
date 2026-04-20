# Customer Shopping Behaviour Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-MySQL-orange?logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> **End-to-end data analytics project** analyzing retail customer shopping behaviour across 3,900 records using Python, SQL, and Power BI — covering the full pipeline from data cleaning and feature engineering to business intelligence dashboards and strategic recommendations.

---

## 🎯 Objective

Retail businesses generate vast amounts of transactional data that often goes underutilized. This project applies the complete data analytics workflow — **data wrangling → exploratory analysis → SQL-based business querying → interactive visualization** — to uncover actionable insights on customer segmentation, product performance, discount effectiveness, and revenue drivers.

---

## 📊 Key Highlights

| Metric | Value |
|---|---|
| 📁 Records Analyzed | 3,900 customers |
| 🧾 Features | 19 columns (+ 2 engineered) |
| 💰 Total Revenue Analyzed | $233,081 |
| 🛒 Avg. Purchase Amount | $59.76 |
| 📍 Geographic Coverage | All 50 US states |
| 🏷️ Product Categories | 4 (Clothing, Footwear, Outerwear, Accessories) |
| 🛍️ Unique Products | 25 items |
| 🔍 SQL Business Queries | 10 |

---

## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| **Python** (Pandas) | Data cleaning, null imputation, feature engineering |
| **Jupyter Notebook** | Exploratory Data Analysis (EDA) |
| **SQL** (MySQL) | Business analysis, CTEs, window functions |
| **Power BI** | Interactive dashboard & data storytelling |

---

## 📁 Repository Structure

```
customer-shopping-behaviour-analysis/
│
├── data/
│   └── cleaned_customer_data.csv         # Preprocessed dataset ready for analysis
│
├── notebook/
│   └── data_preprocessing.ipynb          # EDA & data transformation pipeline
│
├── sql/
│   └── analysis_queries.sql              # 10 structured business queries
│
├── dashboard/
│   ├── customer_behaviour_analysis_dashboard.pbix   # Power BI dashboard
│   └── customer_behaviour_analysis_dashboard.pdf    # Dashboard (PDF export)
│
├── report/
│   └── Customer_Shopping_Behavior_Analysis_report.pdf
│
└── presentation/
    └── customer_insights_presentation.pdf
```

---

## 🔧 Data Preprocessing Pipeline

All preprocessing was done in Python using Pandas (`notebook/data_preprocessing.ipynb`).

**Cleaning**
- Identified and handled null values in `review_rating` — imputed using **category-level median** to preserve distribution integrity
- Standardized all column names to `snake_case` and removed special characters

**Feature Engineering**
- `age_group` — Derived using **quartile binning** (`pd.qcut`) into four segments: *Young Adult, Adult, Middle-aged, Senior*
- `purchase_frequency_days` — Mapped text frequency labels (e.g., `"Weekly"`) to numeric day values (e.g., `7`) for quantitative analysis
- Identified and dropped a redundant column (`promo_code_used`) confirmed to be 100% identical to `discount_applied`

---

## 🔍 SQL Business Analysis

10 queries covering segmentation, revenue, product performance, and customer behaviour (`sql/analysis_queries.sql`):

| # | Business Question | Technique Used |
|---|---|---|
| Q1 | Revenue by gender | `GROUP BY`, `SUM` |
| Q2 | Discount users spending above average | Subquery, `WHERE` filter |
| Q3 | Top 5 products by review rating | `AVG`, `ORDER BY`, `LIMIT` |
| Q4 | Standard vs. Express shipping spend | Conditional `GROUP BY` |
| Q5 | Subscriber vs. non-subscriber revenue | `COUNT`, `AVG`, `SUM` |
| Q6 | Products with highest discount usage rate | `CASE WHEN`, percentage calculation |
| Q7 | Customer segmentation (New / Returning / Loyal) | `CTE`, `CASE WHEN` |
| Q8 | Top 3 products per category | `CTE`, `ROW_NUMBER()` window function |
| Q9 | Repeat buyers and subscription likelihood | Filtered `GROUP BY` |
| Q10 | Revenue contribution by age group | `GROUP BY`, `ORDER BY` |

---

## 📈 Dashboard & Insights

The Power BI dashboard (`dashboard/`) provides an interactive view across:

- **Revenue segmentation** by gender, age group, and product category
- **Subscription impact** on average spend and total revenue
- **Seasonal trends** in purchasing behaviour
- **Shipping type & payment method** distribution
- **Discount effectiveness** across product lines

> 📄 A PDF export is available in the `dashboard/` folder — no Power BI Desktop required to view it.

---

## 💡 Business Insights Uncovered

- **Gender split:** Male customers account for ~68% of transactions vs. ~32% female — indicating opportunity for targeted female-focused campaigns
- **Subscription value:** Subscribed customers represent ~27% of the base but reveal a measurable difference in purchase frequency and spend
- **Discount behaviour:** Not all high-discount products correlate with high revenue — some discounted items underperform, suggesting a pricing strategy review
- **Age segmentation:** Middle-aged and Senior groups drive the majority of total revenue despite similar transaction volumes across groups

---

## 🚀 How to Run

**Clone the repo**
```bash
git clone https://github.com/Krish00i7/customer-shopping-behaviour-analysis.git
cd customer-shopping-behaviour-analysis
```

**Run the notebook**
```bash
pip install pandas jupyter
jupyter notebook notebook/data_preprocessing.ipynb
```

**Run SQL queries**  
Import `data/cleaned_customer_data.csv` into MySQL as a table named `customer`, then run the queries in `sql/analysis_queries.sql`.

**Open the dashboard**  
Open `dashboard/customer_behaviour_analysis_dashboard.pbix` in **Power BI Desktop**, or view the PDF export directly.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
