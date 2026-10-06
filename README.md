# Brazilian E-Commerce Marketing Strategy & Relational Data Analysis (SQL)

## Executive Summary
This project evaluates over 100,000 order transactions from Olist, Brazil's largest department store marketplace, using **MySQL Workbench**. By integrating multi-table relational data (orders, customers, payments, products, and reviews), this analysis identifies key revenue drivers, regional spending variations, customer retention gaps, and operational bottlenecks to build an executive marketing roadmap.

---

## Technical Architecture & Relational Schema
* **Database Engine:** MySQL Workbench 8.0
* **Data Structure:** Multi-table Relational Schema (`JOIN`s across orders, customers, products, payments, and reviews)
* **SQL Techniques Used:** Multi-table Joins, CTEs, Window Functions, Temporal Date Arithmetic, Aggregations, Customer Segmentation
* **Dataset:** [Olist Brazilian E-Commerce Dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

---

## Key Data Cleaning & Modeling Protocols
1. **Timestamp Normalization:** Cast raw string fields (`order_purchase_timestamp`, `order_delivered_customer_date`) to native `DATETIME` format to calculate delivery lead times.
2. **Order Fulfllment Filtering:** Isolated completed transactions from cancelled/unavailable statuses to prevent metrics skewing.
3. **Outlier & Noise Removal:** Excluded zero and negative freight charges/product prices to ensure pricing accuracy.

---

## Core Marketing & Performance Insights

### 1. Geographic Revenue Concentration
* **Southeast Regional Dominance:** Over **60% of total revenue** originates from just three states: São Paulo (SP), Rio de Janeiro (RJ), and Minas Gerais (MG).
* **Average Order Value (AOV) Variations:** While SP exhibits an AOV of R$ 136.39, non-Southeast states like Bahia (BA - R$ 169.76) and Santa Catarina (SC - R$ 162.58) demonstrate significantly higher basket sizes.

### 2. Category Performance & Revenue Drivers
* **Top Profit Categories:** Health & Beauty, Watches & Gifts, and Bed Bath & Table each generated over **R$ 1.2 Million**.
* **High Ticket vs. High Volume:**
  * *Watches & Gifts:* Drives premium revenue at an average item price of **R$ 199.04**.
  * *Bed, Bath & Table:* Drives sheer volume with **10,953 items sold** at an average price of **R$ 93.44**.

### 3. Customer Retention & Lifetime Value
* **Retention Deficit:** **96.9%** of buyers purchased only once on the platform.
* **Double Spend Power:** Repeat purchasers spend twice as much as one-time buyers (**R$ 305–R$ 320** vs. **R$ 160**).

### 4. Logistics Impact on Customer Ratings
* **Delivery Speed:** 5-star reviews average **10.6 days** delivery time, whereas 1-star reviews average **21.3 days**. Over **3,500 negative 1-star reviews** stem directly from late fulfillment.

---

## Strategic Marketing Roadmap
1. **Geo-Targeted Ad Spend:** Focus primary Google/Meta ad acquisition budgets on SP, RJ, and MG for lowest CPA. Direct high-ticket campaigns to BA and SC.
2. **Product Bundling:** Feature Health & Beauty and Watches in top-of-funnel creative. Create product bundles for Bed, Bath & Table to push basket size beyond R$ 160.
3. **Retention Automation:** Implement a 30-day automated post-purchase email sequence with cross-sell incentives to convert one-time buyers into repeat customers.

---

## Repository Structure
```text
├── brazilian-ecommerce-sql-cleaning-eda.sql  # Master SQL script (Cleaning, Joins, & EDA)
├── olist_ecommerce_marketing_report.pdf     # Executive PDF Marketing Report
├── results/                                  # Query result CSV exports
└── README.md                                 # Project documentation
