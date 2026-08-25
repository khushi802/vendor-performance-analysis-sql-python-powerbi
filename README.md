# Vendor Performance Analysis

An end-to-end data analytics project focused on evaluating vendor performance, profitability, purchasing efficiency, inventory turnover, and brand performance using **SQL, Python, and Power BI**.

The project transforms raw transactional data stored across multiple tables into an aggregated vendor-level dataset and uses data analysis, statistical techniques, and interactive visualization to generate actionable business insights.

---

## 📌 Project Overview

Effective vendor and inventory management is essential for maintaining profitability and operational efficiency in retail and wholesale businesses.

This project analyzes vendor sales, purchases, pricing, inventory, and freight-related data to answer key business questions such as:

* Which vendors and brands are performing the best?
* Which vendors and brands are underperforming?
* How dependent is the business on its top vendors?
* Does bulk purchasing reduce unit purchase prices?
* Which vendors have low inventory turnover?
* How much capital is tied up in unsold inventory?
* Is there a significant difference in profitability between high- and low-performing vendors?
* Which low-sales, high-margin brands may require promotional or pricing adjustments?

---

## 🎯 Business Objectives

The main objectives of this analysis are:

1. Identify top-performing vendors and brands based on sales.
2. Identify low-performing vendors based on inventory turnover.
3. Identify brands with low sales but high profit margins.
4. Analyze vendor purchase contribution and dependency.
5. Understand the impact of bulk purchasing on unit purchase prices.
6. Calculate the capital locked in unsold inventory.
7. Compare profitability between high- and low-performing vendors.
8. Statistically validate differences in vendor profitability.
9. Provide business recommendations based on the analysis.

---

## 🛠️ Tools & Technologies

| Tool / Technology    | Purpose                                                   |
| -------------------- | --------------------------------------------------------- |
| **SQL**              | Data exploration, aggregation, joins, and data extraction |
| **SQLite**           | Database storage                                          |
| **Python**           | Data cleaning, feature engineering, EDA, and analysis     |
| **Pandas**           | Data manipulation and analysis                            |
| **NumPy**            | Numerical operations                                      |
| **Matplotlib**       | Data visualization                                        |
| **Seaborn**          | Statistical visualization                                 |
| **SciPy**            | Statistical analysis and hypothesis testing               |
| **SQLAlchemy**       | Database connectivity                                     |
| **Jupyter Notebook** | Exploratory data analysis                                 |
| **Power BI**         | Interactive dashboard and reporting                       |

---

## 📂 Project Structure

```text
Vendor-Performance-Analysis/
│
├── data/
│   └── inventory.db
│
├── scripts/
│   ├── ingestion_db.py
│   └── get_vendor_summary.py
│
├── notebooks/
│   ├── Exploratory Data Analysis.ipynb
│   └── Vendor Performance Analysis.ipynb
│
├── dashboard/
│   └── vendor_performance_dashboard.pbix
│
├── reports/
│   └── Vendor Performance Report.pdf
│
├── logs/
│   └── ingestion.log
│
└── README.md
```

---

## 🔄 Project Workflow

```text
Raw CSV Files
      ↓
Data Ingestion
      ↓
SQLite Database
      ↓
SQL Data Exploration
      ↓
Data Aggregation & Joins
      ↓
Vendor Sales Summary
      ↓
Data Cleaning & Feature Engineering
      ↓
Exploratory Data Analysis
      ↓
Statistical Analysis
      ↓
Business Insights
      ↓
Power BI Dashboard
      ↓
Final Report & Recommendations
```

---

## 🗄️ Database & Data Processing

The raw CSV files are first imported into a SQLite database named `inventory.db`.

The database contains multiple tables related to:

* Purchases
* Purchase Prices
* Vendor Invoices
* Beginning Inventory
* Ending Inventory
* Sales

SQL is then used to explore the database and combine the required information from different tables.

Because the sales data contains a very large number of records, the analysis uses aggregated summary tables to improve query performance and make the data suitable for further analysis and dashboarding.

A final `vendor_sales_summary` table is created containing vendor- and brand-level information required for the analysis.

---

## 🧹 Data Cleaning & Feature Engineering

The vendor sales summary is cleaned before performing the detailed analysis.

Key data preparation steps include:

* Handling missing values
* Correcting inconsistent data types
* Removing unnecessary white spaces from vendor names
* Handling products with no sales
* Identifying negative gross profit
* Removing invalid records for specific analyses
* Detecting outliers
* Filtering records based on meaningful business conditions

### Derived Metrics

Several important metrics are created during the analysis.

**Gross Profit**

```text
Gross Profit = Total Sales Dollars - Total Purchase Dollars
```

**Profit Margin**

```text
Profit Margin = (Gross Profit / Total Sales Dollars) × 100
```

**Stock Turnover**

```text
Stock Turnover = Total Sales Quantity / Total Purchase Quantity
```

**Sales-to-Purchase Ratio**

```text
Sales-to-Purchase Ratio =
Total Sales Dollars / Total Purchase Dollars
```

These metrics are used to evaluate profitability, sales performance, inventory efficiency, and vendor performance.

---

## 📊 Exploratory Data Analysis

Exploratory Data Analysis is performed using Python, Pandas, Matplotlib, and Seaborn.

The analysis includes:

* Summary statistics
* Distribution plots
* Box plots
* Outlier analysis
* Correlation analysis
* Vendor-level analysis
* Brand-level analysis
* Profitability analysis
* Inventory turnover analysis

The analysis identifies relationships between purchasing, sales, pricing, profitability, and inventory turnover.

---

## 🔍 Key Business Analysis

### 1. Low-Sales, High-Margin Brands

Brands with low sales but high profit margins are identified as potential promotional or pricing opportunities.

The analysis uses percentile-based thresholds to identify these brands.

**198 brands** were identified as having low sales but relatively high profit margins.

These brands may benefit from:

* Promotional campaigns
* Pricing adjustments
* Increased visibility
* Marketing support

---

### 2. Top Vendors & Brands by Sales

Vendor and brand sales are aggregated and ranked to identify the strongest contributors to revenue.

The analysis highlights the vendors and brands generating the highest sales values and helps identify the company's most important commercial relationships.

---

### 3. Vendor Purchase Contribution

Vendor purchase contribution is calculated by comparing each vendor's total purchase dollars with total procurement.

The analysis shows that the **top 10 vendors contribute approximately 65.7% of total purchases**.

This indicates a significant dependency on a relatively small group of vendors and highlights a potential vendor concentration risk.

---

### 4. Impact of Bulk Purchasing

The analysis investigates whether purchasing larger quantities results in lower unit purchase prices.

Orders are categorized into different purchase-size groups and their average unit purchase prices are compared.

The analysis shows that:

* Smaller orders have substantially higher unit costs.
* Larger orders have significantly lower unit costs.
* Bulk purchasing can reduce unit purchase cost by approximately **72%**.

This provides a strong basis for negotiating bulk purchasing arrangements with vendors.

---

### 5. Low Inventory Turnover Vendors

Vendors with a stock turnover ratio below **1** are considered low-performing from an inventory-efficiency perspective.

Low turnover indicates that inventory is being purchased faster than it is being sold, which can increase holding costs and tie up working capital.

---

### 6. Unsold Inventory Capital

The project calculates the amount of capital tied up in unsold inventory.

The analysis identifies approximately **$2.7M in unsold inventory capital**.

This highlights the importance of:

* Better demand planning
* Inventory optimization
* Reducing slow-moving stock
* Reviewing purchasing decisions

---

## 📈 Statistical Analysis

The project also uses statistical techniques to compare profitability between different vendor groups.

Vendors are categorized into:

* **Top performers:** vendors above the 75th percentile in sales
* **Low performers:** vendors below the 25th percentile in sales

Confidence intervals are calculated for profit margins, followed by hypothesis testing to determine whether the difference between the groups is statistically significant.

The analysis shows that low-performing vendors can have **higher average profit margins than high-sales vendors**, indicating that sales volume alone does not necessarily represent profitability.

---

## 📊 Power BI Dashboard

The final analysis is presented through an interactive Power BI dashboard.

### Dashboard KPIs

* Total Sales
* Total Purchase
* Gross Profit
* Profit Margin
* Unsold Capital

### Dashboard Visualizations

* Purchase Contribution %
* Top Vendors by Sales
* Top Brands by Sales
* Low Performing Vendors
* Low Performing Brands

The dashboard provides a concise view of vendor performance, profitability, procurement concentration, and inventory-related risks.

---

## 💡 Key Insights

* The top 10 vendors contribute approximately **65.7% of total purchases**, indicating vendor concentration risk.
* Approximately **$2.7M** of capital is tied up in unsold inventory.
* Bulk purchasing can reduce unit purchase costs by approximately **72%**.
* **198 brands** were identified as low-sales, high-margin opportunities.
* Low-performing vendors can have higher profit margins than high-sales vendors.
* Higher sales volume does not necessarily guarantee higher profitability.
* Inventory turnover is an important indicator for identifying slow-moving inventory and inefficient purchasing.

---

## 💼 Business Recommendations

Based on the analysis:

### Vendor Diversification

Reduce excessive dependency on a small number of vendors by developing relationships with additional suppliers.

### Inventory Optimization

Review slow-moving inventory and improve purchasing decisions to reduce capital tied up in unsold stock.

### Bulk Purchasing

Use larger purchase quantities strategically where demand supports it to take advantage of lower unit costs.

### Pricing & Promotion

Review low-sales, high-margin brands and consider promotional or pricing strategies to increase their sales volume.

### Vendor Strategy

Use both sales performance and profitability when evaluating vendors rather than relying on sales volume alone.

---

## 📑 Project Deliverables

The project produces:

* SQLite database
* SQL-based data aggregation
* Python data-processing scripts
* Exploratory Data Analysis notebooks
* Vendor performance analysis
* Statistical analysis
* Power BI dashboard
* Final business report

---

## 🚀 Project Outcome

This project demonstrates an end-to-end data analytics workflow, starting from raw transactional data and database management through SQL analysis, Python-based EDA, statistical validation, Power BI visualization, and business recommendations.

The analysis provides data-driven insights into vendor dependency, purchasing efficiency, profitability, inventory turnover, and opportunities for improving vendor and brand performance.

---

## 👤 Author

**Khushi Singh**

Data Analytics Project
SQL | Python | Power BI | Data Analysis
