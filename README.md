# ElektroMax-Sales-Performance-Dashboard-Power-BI-Portfolio-Project

# 📊 ElektroMax Sales Performance Dashboard — Power BI Portfolio Project

An analytics dashboard for **ElektroMax**, an electronics retail chain operating 10 stores across several regions in Indonesia. This project demonstrates an end-to-end data analytics workflow: data cleaning, data modeling (star schema), DAX measure creation, and delivering business insights through an interactive dashboard.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Modeling-blue)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-217346?logo=microsoftexcel&logoColor=white)

---

## 🎯 Background & Objectives

ElektroMax's management needed a single source of truth to monitor sales performance across all stores, evaluate product profitability, and understand customer behavior. This dashboard was built to answer the following business questions:

- How do monthly revenue and transaction trends compare year-over-year (YoY)?
- Which stores are over/under-performing against their targets?
- Which product categories are the most profitable (highest Gross Profit Margin)?
- Who are the most valuable customer segments, and how effective are the promotional campaigns?

## 🗂️ About the Dataset

The dataset is a **star schema** (1 fact table + 6 dimension tables) simulating electronics retail transactions from 2023–2024:

| Table | Rows | Description |
|---|---|---|
| `FACT_PENJUALAN` (Sales) | ~56,700 | Transaction details: quantity, price, discount, COGS, gross profit, payment method, transaction status |
| `DIM_PRODUK` (Product) | 31 | Category, subcategory, brand, normal & cost price |
| `DIM_WAKTU` (Date) | 1,096 | Daily calendar 2023–2025 (day, week, month, quarter, holidays) |
| `DIM_PELANGGAN` (Customer) | 521 | Segment (Regular/Silver/Gold/Platinum), city, age group |
| `DIM_TOKO` (Store) | 10 | Region, store format, floor area, monthly target |
| `DIM_KARYAWAN` (Employee) | 30 | Sales staff per store |
| `DIM_PROMOSI` (Promotion) | 18 | Promotion type, active period, discount value |

The data was intentionally made **"dirty"** to simulate real-world raw data conditions, including:
- Mixed number formats (e.g. prices stored as text `"Rp 11.000.000"` in some rows, plain numbers in others)
- Missing values / placeholders (`"-"`) in fields like phone numbers
- Inconsistent date formats across rows
- Duplicates and outliers in some transactions

### 🧹 Data Cleaning Process (Power Query)
- Standardized currency formatting (stripped `"Rp"` and thousands separators) into proper numeric types
- Handled missing values and duplicates
- Converted and validated date data types
- Built relationships between tables (1 fact table – many dimension tables) using a star schema in the Power BI data model

## 📐 Methodology
1. **Data Cleaning** — Power Query (transforming and standardizing raw data)
2. **Data Modeling** — Star schema, one-to-many relationships between `FACT_PENJUALAN` and the dimension tables
3. **DAX Measures** — calculations for Total Revenue, Gross Profit, GPM%, YoY Growth, Average Ticket Size, Purchase Frequency, etc.
4. **Visualization** — 3 interactive dashboard pages with slicers (Region, Year, Subcategory, Segment, City)

## 📈 Dashboard Overview

### 1️⃣ Overview
A high-level summary of overall business performance.
- **Total Revenue Rp290.73 billion** (up **48.84%** YoY from Rp195.33 billion)
- **Gross Profit Rp89.81 billion** with a **Gross Profit Margin of 30.89%**
- **56,728 transactions**, up **49.65%** YoY
- Monthly revenue and transaction trends vs. previous year
- Revenue breakdown by product subcategory — **TVs** are the top contributor (Rp92 billion), followed by ACs (Rp71 billion) and Refrigerators (Rp47 billion)
- Store-level target achievement table

### 2️⃣ Products & Stores
In-depth analysis of store and product performance.
- Revenue comparison across stores and regions
- Revenue distribution by region (Region 2 contributes the largest share, 39.82%)
- Gross Profit Margin by subcategory — **Small Appliances** and **Water Heaters** have the highest GPM (~33.8%)
- Full product detail table with GPM%, total units sold, and YoY growth per category

### 3️⃣ Customers
Focused on customer behavior and segmentation.
- **521 active customers**, average purchase frequency of **108.88** (up 49.65% YoY)
- **35.61%** of transactions used a promotion
- **Return rate of 10.01%**
- Payment method breakdown (QRIS and Bank Transfer are the most common)
- Customer segmentation (Regular, Platinum, Gold, Silver) with revenue, frequency, and GPM per segment
- Effectiveness of each promotional campaign on revenue and transaction count

## 🛠️ Tools Used
- **Power BI Desktop** — data modeling & visualization
- **Power Query (M)** — data cleaning & transformation
- **DAX** — measure and KPI calculations
- **Microsoft Excel** — raw data source

## 🚀 How to Use
1. Clone this repository
2. Open the `.pbix` file with Power BI Desktop
3. Refresh the data if needed (raw data is in the `/data` folder)
4. Explore the dashboard using the slicers in the top-right corner of each page

## 📌 Key Insights
- Revenue growth (+48.84% YoY) closely tracks transaction growth (+49.65% YoY), indicating growth is driven by **volume**, not by an increase in average price
- TVs and ACs together account for over 55% of total revenue — these core categories require close stock management
- A double-digit return rate (10.01%) stands out as an area worth investigating further, especially in high-volume categories
- Most stores have already exceeded their monthly targets (achievement % above 100%), suggesting targets may need to be recalibrated for the next period

## 👤 Author
Built as part of a data analyst portfolio.
Feel free to connect / reach out with feedback 🙌

---
*The dataset is synthetic/simulated and was created specifically for practice and portfolio purposes.*
