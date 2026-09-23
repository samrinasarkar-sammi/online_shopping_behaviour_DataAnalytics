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
├── data_cleaning.ipynb          # Python cleaning pipeline (raw → cleaned CSV)
├── Dataset_online_shopping(UK).ZIP # Both Raw & Cleaned dataset
├── Business Problem Statement         
├── All bussinessa query.sql      # 10 business-question SQL queries
├── Customer Dashboard.pbix            # Power BI dashboard file
├── Online_Retail_Analysis_Report   # Full write-up with findings
├── Presentation of -Online retail customer behavior
└── README.md
```

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

---

## Power BI Dashboard

<img width="1086" height="689" alt="image" src="https://github.com/user-attachments/assets/f2ce3f81-0085-479b-835a-6a66a243dd48" />

---

## What I'd Do Differently / Next Steps

- Extend the churn analysis with a full RFM (Recency, Frequency, Monetary) scoring model
- Investigate root causes behind the highest-cancellation-rate products
- Build a simple forecasting model on the monthly revenue trend

---

## About Me

**Samrina Sarkar Sammi** — M2 Data Science & Network Intelligence student, Télécom SudParis

[LinkedIn](https://www.linkedin.com/in/samrina-sarkar-sammi-a8b716424/) · [GitHub](https://github.com/samrinasarkar-sammi) · samrinasarkar@gmail.com
