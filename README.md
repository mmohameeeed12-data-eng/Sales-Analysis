# Sales Analysis Dashboard (Power BI)

<img width="1438" height="810" alt="Sales Dashboard Overview" src="https://github.com/user-attachments/assets/2c91223f-1942-4046-ba98-8ac0d4495d16" />

## Overview
This project features an interactive Power BI sales dashboard analyzing revenue drivers, order fulfillment statuses, and regional performance. 

The raw data was structured at an **order-line level** (multi-row transactions per order). To avoid duplicate calculations and optimize report performance, the data was transformed into a **Star Schema** model.

---

## Key Metrics
* **Total Revenue:** $30.09M
* **Total Orders:** 24K
* **Total Quantity Sold:** 86K
* **Average Unit Price:** $425
* **Total Taxes:** $2.93M

---

## Data Model

The data model uses a Star Schema design with a central **Fact** table surrounded by 5 **Dimension** tables connected via one-to-many (`1:*`) relationships.

<img width="1448" height="849" alt="Star Schema Architecture" src="https://github.com/user-attachments/assets/9f7741dd-255d-4a51-b455-e450970cf668" />

### Tables & Relationships

* **`Fact` Table (Order-line level):**
  * Stores transactions and core metrics: `OrderID`, `OrderDetailID`, `CustomerID`, `SalesPersonID`, `ProductID`, `ShipMethodID`, `StatusID`, `TerritoryID`, `OrderDate`, `DueDate`, `ShipDate`, `OrderQty`, `UnitPrice`, `LineTotal`, `TaxAmt`, `Freight`, `TotalDue`.

* **Dimension Tables:**
  * **`Dim_Product`** (`ProductID`): Product names, categories, and subcategories.
  * **`Dim_Territory`** (`TerritoryID`): Regions and territory groups.
  * **`Dim_Shipmethod`** (`ShipMethodID`): Shipping methods.
  * **`Dim_Status`** (`StatusID`): Order statuses (*Approved, Shipped, Cancelled, Backordered*).
  * **`Dim_date`** (`OrderDate`): Date dimensions (`Year`, `Month Name`, `Day Name`).

---

## Core DAX Measures
Created explicit DAX measures to handle dynamic aggregations across report filters:
* **`Total Revenue`**: Sum of line total revenue.
* **`Total Orders`**: Distinct count of unique order IDs.
* **`Total Quantity`**: Total items sold.
* **`Avg Unit Price`**: Average unit price across sold products.
* **`Total Taxes`**: Total tax collected.

---

## Main Insights
* **Top Categories:** **Bikes** bring in the highest revenue, followed by **Components** and **Clothing**.
* **Regional Performance:** **Canada** leads in total revenue and order count, while the **Central** territory shows the lowest activity.
* **Delivery Timeline:** Orders take an average of **~7 days** from order date to shipping, and **~5 days** from shipping to delivery.
