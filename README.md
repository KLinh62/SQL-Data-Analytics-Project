# SQL & Power BI Data Analytics Project: Customer, Product & Sales Insights
Welcome to the Data Analytics Project — a complete analytics pipeline designed to extract, analyze, and visualize key business metrics across customers, products, and sales using SQL and Power BI.

> 📊 **BI Focus**: Data-driven decisions in customer engagement, product optimization, and revenue growth.

## 📘 Project Background
This project explores a retail sales dataset using SQL for data cleaning and analysis, and Power BI for visualization. The goal is to empower decision-makers with detailed, real-time insights to track KPIs on customer behaviour, product performance, and discover growth opportunities.

The focus lies in:
- Identifying **top-performing products**
- Understanding **customer purchasing behavior**
- Analyzing **sales trends** across time

---
## 🗂️ Data Structure Overview
The star schema design enhances performance for BI tools as well as allows efficient filtering, aggregation, and analysis by product and customer dimensions. Below is the entity relationship diagram:

![data-model](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_model.png)

Links:

- [Datasets](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/datasets): Access to the project dataset (.csv and .bak files).
- [Data Catalog](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_catalog.md): A comprehensive description of the datasets used in this analytical project, which were derived from the Gold layer of the [SQL Data Warehouse Project](https://github.com/KLinh62/SQL-Data-Warehouse-Project).

### Data Quality Checks

Basic validation tests were performed using SQL to ensure data quality:

- **Null Checks**: Verified missing values across primary fields
- **Data Types**: Ensured consistency (e.g., dates, prices, quantities)
- **Duplications**: Checked for duplicate records in `orders` and `order_items`
- **Joins Testing**: Validated foreign key relationships among tables

> **Note**: All required data validation and quality assurance (nulls, referential integrity, data types, duplicates, etc.) were already conducted during the **Silver** and **Gold Layer** development in the [SQL Data Warehouse Project](https://github.com/KLinh62/SQL-Data-Warehouse-Project/tree/main/tests).  
>  
> This ensures the data input for this project is clean, reliable, and analysis-ready.

---

## 🛠 Tools & Technologies

| Tool      | Purpose                             |
|-----------|-------------------------------------|
| SQL       | Data warehouse structure, querying  |
| Power BI  | Dashboarding and reporting          |
| GitHub    | Version control and collaboration   |


---
## 🧠 Analytical Process & Power BI Integration

This phase involves delving into the datasets to understand their characteristics, identify patterns, and uncover initial insights. A total of **12 SQL scripts** are developed to drive both **Exploratory Data Analysis (EDA)** and **Advanced Business Analytics**. These queries are executed using Microsoft SQL Server and the results exported for Power BI reporting.

Below is the mind map of both Exploratory Data Analysis & Advanced Business Analytics processes:
![data-analytics-steps](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/blob/main/docs/data-analytics-steps.png)

### 🔍 Phase 1: Exploratory Data Analysis (EDA) with SQL

SQL was extensively used for foundational understanding of the data. This enabled easy cleaning, profiling, and modelling of the data.

This phase involved delving into the datasets to understand their characteristics, identify patterns, and uncover initial insights. SQL queries were extensively used for:

1. Data Exploration: Initial overview of data, checking for completeness, unique values, and basic distributions across all tables.

2. Dimension Exploration: Analyzing the attributes within dimension tables (e.g., customer demographics, product categories) to understand their distinct values and impact.

3. Date Exploration: Examining temporal aspects of the data, such as sales over different dates, months, or years, to identify trends or anomalies.

4. Measures Exploration: Understanding the range, sum, average, and other statistical properties of key measures like sales_amount, quantity, and price.

5. Magnitude Analysis: Quantifying the size or scale of various data points (e.g., total sales by region, total customers).

6. Ranking Analysis: Identifying top N or bottom N entities based on specific measures (e.g., top-selling products, highest-value customers).






1. **Data Exploration**  
   - Reviewed data completeness, null values, unique identifiers  
   - Profiled numeric distributions, text lengths, and cardinality

2. **Dimension Exploration**  
   - Examined customer types, locations, and product categories  
   - Identified which segments had the highest order volumes

3. **Date Exploration**  
   - Aggregated sales by day, week, month, and year  
   - Uncovered seasonal trends and holiday-related spikes

4. **Measures Exploration**  
   - Calculated statistics on `quantity`, `price`, `total_sales_amount`  
   - Identified outliers and pricing anomalies

5. **Magnitude Analysis**  
   - Computed total revenue, customer counts, and product volumes  
   - Measured scale of business by region, brand, or customer type

6. **Ranking Analysis**  
   - Extracted top-N products, customers, and categories  
   - Enabled leaderboard visualizations in Power BI

---

### 📈 Phase 2: Advanced Analytics with SQL

More sophisticated queries were developed to dig deeper into business performance and customer behavior:

7. **Change-Over-Time Trends**  
   - Compared monthly and quarterly metrics year-over-year  
   - Visualized growth momentum and cyclicality

8. **Cumulative Analysis**  
   - Computed year-to-date sales and cumulative customer acquisition  
   - Enabled running total charts in Power BI

9. **Performance Analysis**  
   - Evaluated profit margins, unit economics, and category-level contribution  
   - Provided KPIs for product and customer profitability

10. **Part-to-Whole Analysis**  
   - Calculated category-level revenue share  
   - Supported donut/pie and stacked column charts

11. **Data Segmentation**  
   - Clustered customers by frequency, monetary value, and recency  
   - Enabled cohort and RFM-style segmentation charts

12. **Reporting for Power BI**  
   - Final SQL outputs (aggregated, clean, enriched) were exported as `.csv` files  
   - These were imported into Power BI to serve as **data sources** for interactive dashboards

---

### Table Mapping: SQL Scripts to Business Goals
Here’s a mapping table that explains the purpose of each SQL file:

| Script File                       | Description                                                  |
|----------------------------------|--------------------------------------------------------------|
| `00_init_database.sql`           | Initializes the DataWarehouseAnalytics database and creates the gold schema |
| `01_data_exploration.sql`        | Basic data profiling: null checks, row counts, distributions |
| `02_dimension_exploration.sql`   | Explore customer/product attributes and categories           |
| `03_date_exploration.sql`        | Identify trends by day, month, and year                      |
| `04_ranking_analysis.sql`        | Top-N products, customers, and categories                    |
| `05_measures_analysis.sql`       | Summary stats: min, max, avg, std of sales metrics           |
| `06_magnitude_analysis.sql`      | Aggregate totals by segment: sales, quantity, revenue        |
| `07_change_over_time.sql`        | Sales growth over time: MoM, QoQ                             |
| `08_cumulative_sales.sql`        | Running totals: YTD, MTD cumulative metrics                  |
| `09_performance_analysis.sql`    | Evaluate profitability and sales effectiveness               |
| `10_part_to_whole_analysis.sql`  | % contribution by product category or brand                  |
| `11_customer_segmentation.sql`   | Customer grouping by frequency, value, or recency            |
| `12_final_reporting_view.sql`    | Final reporting table for Power BI import                    |

### 📤 Usage

- Run scripts in order from `00` to `12`, or selectively for specific analysis needs.
- Export results from `12_final_reporting_view.sql` as `.csv` for Power BI.
- Join with dimensions in Power BI for full dashboard interactivity.
- 
----

### 🔗 Power BI Integration

Each query aligns with a specific visual on the dashboard. Here's how they connect:

| SQL Query Purpose          | Power BI Visual Example                     |
|---------------------------|---------------------------------------------|
| Top Products by Revenue   | Bar chart: Top 10 products                  |
| Monthly Sales Trend       | Line chart: Revenue over time               |
| Customer Segments         | Table: High-value vs low-value customers    |
| Category Contribution     | Donut chart: Sales % by product category    |
| Running Total Sales       | Area chart: Cumulative monthly revenue      |
| Regional Performance      | Map: Sales volume by country or region      |
| Repeat Purchase Behavior  | Matrix or bar chart: Frequency bands        |

All `.csv` outputs are stored in `/data/` and referenced in the Power BI `.pbix` file under `/reports/`.

> 💡 *Tip:* You can refresh the Power BI model easily by re-running the SQL scripts, exporting updated CSVs, and refreshing Power BI.

---

### ⚙️ Automation Potential

This SQL + Power BI pipeline is highly automatable. With a data warehouse and tools like Power BI Gateway or Python scripts, the refresh cycle can be scheduled for near real-time reporting.

---

## 📁 Repository Structure (Updated)



----

## 🔍 Steps of Data Analysis

The analytics process follows a modular and scalable SQL workflow:

1. **Data Preparation (Staging Layer)**  
   - Used clean Gold Layer tables as input  
   - Created additional fields: `order_month`, `order_year`, `total_amount`

2. **Data Enrichment (Transform Layer)**  
   - Joined `fact_sales` with `dim_customers` and `dim_products` for a unified reporting view  
   - Created analytical views segmented by customer demographics and product category

3. **Exploratory SQL Analysis**  
   - Top customers by total spending  
   - Most frequently purchased products  
   - Monthly revenue and order count trends  
   - Average basket size per order  

4. **Export to Power BI**  
   - Final SQL outputs saved as `.csv` for import  
   - DAX measures used to enhance interactivity  

> 📸 Screenshots will be included in the /visuals folder.

---

## 🧱 Project Architecture

### 📁 1. Data Warehouse Foundation (Repo 1)

SQL scripts 00–04 (exploration & base metrics):
- Initialize schema
- Perform dimensional modeling
- Join fact + dimension tables
- Validate granularity and measures

### 📁 2. Analytical Query Layer (Repo 2)

Scripts 05–13 (business-driven insights):
- Magnitude (revenue, orders)
- Time trends (growth, seasonality)
- Customer segments
- Product ranking & performance
- Reporting views

---
## SQL for Exploratory Analytics

This phase includes SQL scripts for data exploration, analytics, and reporting. These scripts cover various analyses such as database exploration, measures and metrics, time-based trends, cumulative analytics, segmentation, and more.

The SQL queries scripts help data analysts and BI professionals to quickly explore, segment, and analyze data within a relational database. Each script focuses on a specific analytical theme and demonstrates best practices for SQL queries.



## 📊 BI: Analytics & Reporting (Data Analytics)

### Objective

Develop SQL-based analytics to deliver detailed insights into:  
- **Customer Behavior**  
- **Product Performance**  
- **Sales Trends**

These insights empower stakeholders with key business metrics, enabling strategic decision-making.

### Power BI Dashboard Overview

The Power BI dashboard is structured into 3 key analytical views:

#### 1. 📦 Product Performance
- Top 10 Best-Selling Products
- Revenue by Category & Subcategory
- Product Sales Trends over Time

#### 2. 🧍 Customer Behavior
- Top Spending Customers
- Repeat Purchase Rate
- Orders per Customer per Month


#### 3. 💵 Sales Trends
- Monthly Revenue Trend
- Average Order Value (AOV)
- Revenue vs. Quantity Correlation

> 🧠 **Sample DAX Measures**:
```DAX
Total Sales = SUM(fact_sales[quantity] * dim_products[unit_price])
Avg Order Value = [Total Sales] / DISTINCTCOUNT(fact_sales[order_id])
Customer Count = DISTINCTCOUNT(dim_customers[customer_id])
```
---

## 📈 Executive Summary & Insights
🔹 Customer Insights
- A small % of customers contribute the majority of revenue (Pareto pattern)
- Loyal customers place more frequent and higher-value orders

🔹 Product Insights
- Electronics and accessories dominate in revenue
- Seasonality impacts certain product categories significantly

🔹 Sales Trends
- Revenue spikes observed during holiday months
- AOV steadily increasing — indicates successful upselling strategies

---


---

## 📊 Power BI Dashboard: Build Instructions

### 🔄 Step 1: Data Import

- Export key SQL views (from Repo 2) to `.csv`
  OR connect Power BI to your SQL database
- Recommended Views:
  - `vw_sales_by_month`
  - `vw_top_customers`
  - `vw_product_performance`
  - `vw_orders_by_segment`
  - `vw_channel_trends`

### 🗂 Step 2: Data Model Setup

- Ensure relationships:
  - `Date[Date]` → `Orders[OrderDate]`
  - `CustomerID`, `ProductID` as foreign keys
- Create Calendar Table if not imported

### 📐 Step 3: Measure Definitions

Create DAX KPIs like:

```DAX
Total Revenue = SUM(Orders[Revenue])
Avg Order Value = [Total Revenue] / COUNTROWS(Orders)
Return Rate = DIVIDE(SUM(Orders[IsReturn]), COUNTROWS(Orders))
```

More measures can be derived using SQL views or custom DAX logic.

---

## 📊 Dashboard Design Layout

### 1. **Executive Summary**
- Total Revenue
- Order Count
- Return Rate
- Revenue Trend (line chart)

### 2. **Customer Insights**
- Top Customers (bar chart)
- Orders by Age Group, Gender, or Region
- New vs Returning Customers
- Customer Lifetime Value (LTV)

### 3. **Product Performance**
- Top SKUs by Revenue / Orders
- Product Category Breakdown
- Discount Impact on Returns

### 4. **Sales Trends**
- Monthly/Quarterly Trend (line chart)
- Channel Performance (stacked column)
- Growth YOY / MOM (% change cards)

---

## 📌 Sample Insights

- 📈 65% of revenue comes from 3 key regions  
- 🎯 10% of customers generate 40% of revenue  
- ❗ Products with >20% discount have 2.5x higher return rate  
- 📉 Offline channel underperforms during Q2  

---

## 🚀 Future Enhancements

- RLS (row-level security) for sales managers  
- Drillthrough for product details  
- Integration with Python scripts for forecast  


---

📁 Repository Structure
sql
Copy
Edit


---
# SQL Data Analytics & Power BI Dashboard

This repository includes SQL scripts for data exploration, analytics, and reporting. These scripts cover various analyses such as database exploration, measures and metrics, time-based trends, cumulative analytics, segmentation, and more. 

The SQL queries scripts help data analysts and BI professionals to quickly explore, segment, and analyze data within a relational database. Each script focuses on a specific analytical theme and demonstrates best practices for SQL queries.

---


---
## 📁 Repository Structure
```
Data-Analytics-Project/
├── 📂 data/               → Raw CSV export of SQL queries
├── 📂 queries/            → SQL scripts for staging & analysis
├── 📂 visuals/            → Power BI screenshots
├── 📂 reports/            → Power BI (.pbix) file
├── README.md              → Project documentation
```

---

## 🧑‍💻 Author

**Nguyen Khanh Linh**  
📧 nklinh.620@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/khánh-linh-nguyễn-346115176)



## 🌟 About Me

Hi there! I'm **Linh Nguyen**, an Supply Chain professional who is passonate about data.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kh%C3%A1nh-linh-nguy%E1%BB%85n-346115176/)

