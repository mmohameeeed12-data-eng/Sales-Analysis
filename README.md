# 📊 Sales Analysis & Interactive Power BI Report

<img width="1438" height="810" alt="Sales Dashboard Overview" src="https://github.com/user-attachments/assets/2c91223f-1942-4046-ba98-8ac0d4495d16" />

## 📌 Executive Summary
An end-to-end interactive Power BI report designed to analyze sales performance, revenue drivers, order fulfillment statuses, and regional distributions. The project involved converting raw order-line data into an optimized **Star Schema** to ensure accurate aggregation and seamless analytical reporting.

---

## 📈 Key Business Metrics
* **Total Revenue:** $30.09M
* **Total Orders:** 24K
* **Total Quantity Sold:** 86K
* **Average Unit Price:** $425
* **Total Taxes:** $2.93M

---

## 🔍 Key Insights & Findings
* **Product Categories:** **Bikes** dominate total revenue, followed by **Components** and **Clothing**.
* **Geographical Distribution:** **Canada** is the top-performing territory across both sales value and order volume, while **Central** represents the weakest region.
* **Fulfillment Timeline:** Standard delivery timelines average **~7 days** from Order to Ship Date, and **~5 days** from Ship to Delivery across all territories.
* **Order Health:** Granular tracking implemented for **Backordered** and **Cancelled** orders to isolate problematic order channels.

---

## 🏗️ Data Architecture & Modeling
Because source transactions exist at the **product/order-line level**, simple row counts lead to duplicate calculations. To solve this:
* Transformed raw data into a clean **Star Schema** (separating Fact and Dimension tables).
* Implemented custom **DAX Measures** for dynamic filtering across territories, categories, and order statuses.
* Optimized reporting performance for faster analytical queries in Power BI.

---

## 📂 Repository Contents
* `Sales_dynamic_Dashboard.pbix` — Interactive Power BI Dashboard file.
* `Sales_star_sch.xlsx` — Data model & transformed dataset structure.
* `README.md` — Project documentation.
