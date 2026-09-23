# Online Retail Customer Behavior Analysis
 End-to-end data analytics project on a real e-commerce transaction dataset — data cleaning in Python, business analysis in SQL (PostgreSQL), and an interactive dashboard in Power BI.

# Business Problem

A UK-based online retailer specializing in all-occasion gift-ware recorded 541,910 transactions between December 2010 and December 2011, across 4,372 identified customers, over 4,000 products, and sales to 38 countries. Despite this volume of data, the business has no structured view of which products and markets actually drive revenue, which customers are most valuable, or which are quietly disengaging — and a meaningful share of transactions come from unidentified guest/wholesale checkouts and order cancellations, both representing real, unquantified revenue impact.

# Question this project answers:
How can the company use its transaction data to identify its strongest revenue drivers, understand customer value and loyalty, and reduce losses from cancellations and customer disengagement?

# Dataset
Source: Online Retail II — UCI Machine Learning Repository (CC BY 4.0)
Raw size: 541,910 rows · 8 columns
Period: December 2010 – December 2011
Columns: Invoice, StockCode, Description, Quantity, InvoiceDate, Price, Customer ID, Country

# Tech Stack
Layer	Tools
Data Cleaning	Python, pandas
Database	PostgreSQL
Analysis	SQL (CTEs, window functions, conditional aggregation)
Visualization	Power BI
