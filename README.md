# Online Retail Customer Behavior Analysis

End-to-end data analytics project on a real e-commerce transaction dataset — data cleaning in **Python**, business analysis in **SQL (PostgreSQL)**, and an interactive dashboard in **Power BI**.

---

## Business Problem

A UK-based online retailer specializing in all-occasion gift-ware recorded 541,910 transactions between December 2010 and December 2011, across 4,372 identified customers, over 4,000 products, and sales to 38 countries. Despite this volume of data, the business has no structured view of which products and markets actually drive revenue, which customers are most valuable, or which are quietly disengaging — and a meaningful share of transactions come from unidentified guest/wholesale checkouts and order cancellations, both representing real, unquantified revenue impact.

**Question this project answers:**
> How can the company use its transaction data to identify its strongest revenue drivers, understand customer value and loyalty, and reduce losses from cancellations and customer disengagement?

---

## Dataset

- **Source:** [Online Retail II — UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii) (CC BY 4.0)
- **Raw size:** 541,910 rows · 8 columns
- **Period:** December 2010 – December 2011
- **Columns:** Invoice, StockCode, Description, Quantity, InvoiceDate, Price, Customer ID, Country

---

## Tech Stack

| Layer | Tools |
|---|---|
| Data Cleaning | Python, pandas |
| Database | PostgreSQL |
| Analysis | SQL (CTEs, window functions, conditional aggregation) |
| Visualization | Power BI |

---

## Project Structure

```
├── data_cleaning.py          # Python cleaning pipeline (raw → cleaned CSV)
├── online_retail_cleaned.csv # Cleaned, analysis-ready dataset
├── powerbi_views.sql         # SQL views feeding the Power BI dashboard
├── analysis_queries.sql      # 10 business-question SQL queries
├── dashboard.pbix            # Power BI dashboard file
├── dashboard_screenshot.png  # Dashboard preview image
├── Online_Retail_Analysis_Report.md   # Full write-up with findings
└── README.md
```

---

## Data Cleaning (Python)

Cleaning was scoped deliberately narrow: fix genuine data problems, but preserve real business signals rather than deleting anything inconvenient.

- **Backfilled missing product descriptions** (1,454 missing) using a StockCode → Description lookup — recovered 1,342, dropped the remaining 112 with no match anywhere in the data.
- **Removed 5,268 fully duplicate rows.**
- **Removed 2,754 non-product rows** (postage, fees, manual adjustments — StockCodes like `POST`, `DOT`, `M`, `D`, `AMAZONFEE`) that would otherwise distort "top products" analysis.
- **Removed 2,384 rows with Price ≤ 0** (free samples / data errors).
- **Standardized inconsistent Country values** (`Unspecified`, `European Community` → `Unknown`).
- **Deliberately kept:**
  - Missing Customer ID (24.9% of rows) — likely guest/wholesale checkouts, not bad data. Flagged rather than dropped, so revenue analysis isn't understated by a quarter.
  - Cancelled orders / negative Quantity — kept to measure cancellation rate and lost revenue as an actual finding, not noise.

Result: **531,392 clean, analysis-ready rows.**

---

## SQL Analysis

Ten business questions answered in PostgreSQL, covering:

1. Revenue by country
2. Returning customers who still spend above average
3. Top 5 products by revenue
4. UK vs. non-UK average order value
5. Identified vs. unidentified customer order value
6. Highest cancellation-rate products
7. Customer segmentation (New / Returning / Loyal)
8. Top 3 products per country
9. Repeat buyers vs. non-repeat spend comparison
10. Revenue by month (seasonality)

Full queries in [`analysis_queries.sql`](./analysis_queries.sql). Key SQL techniques used: CTEs, window functions (`ROW_NUMBER() OVER PARTITION BY`), conditional aggregation (`COUNT(*) FILTER (WHERE ...)`), and date parsing (`TO_TIMESTAMP`/`TO_CHAR`).

---

## Dashboard

![Dashboard](./dashboard_screenshot.png)

Built in Power BI, connected directly to PostgreSQL views:

- **KPI cards:** Total Revenue · Number of Customers · Average Order Value · Cancellation Rate %
- **Donut chart:** Identified vs. unidentified customer orders
- **Bar chart:** Revenue by country (top 10)
- **Bar chart:** Top 10 products by quantity sold
- **Line chart:** Revenue by month — seasonal trend
- **Bar chart:** Customer segment distribution (New / Returning / Loyal)

---

## Key Findings

*(Fill in with your real results once queries are run — see [`Online_Retail_Analysis_Report.md`](./Online_Retail_Analysis_Report.md) for the full breakdown per question.)*

- Revenue is heavily concentrated in [ insert top country / % ]
- Cancellations account for [ insert £ amount ] in lost revenue
- [ insert customer segment ] % of customers fall into the "Loyal" segment
- Clear seasonal peak in [ insert month ]

---

## What I'd Do Differently / Next Steps

- Extend the churn analysis with a full RFM (Recency, Frequency, Monetary) scoring model
- Investigate root causes behind the highest-cancellation-rate products
- Build a simple forecasting model on the monthly revenue trend

---

## About Me

**Samrina Sarkar Sammi** — M2 Data Science & Network Intelligence student, Télécom SudParis

[LinkedIn](https://www.linkedin.com/in/samrina-sarkar-sammi-a8b716424/) · [GitHub](https://github.com/samrinasarkar-sammi) · samrinasarkar@gmail.com
