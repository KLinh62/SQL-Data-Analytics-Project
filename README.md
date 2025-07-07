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
## 📈 Executive Summary & Insights
🔹 **Customer Insights**

- A small % of customers contribute the majority of revenue (Pareto pattern)

- Loyal customers place more frequent and higher-value orders

🔹 **Product Insights**

- Electronics and accessories dominate in revenue

- Seasonality impacts certain product categories significantly

🔹 **Sales Trends**

- Revenue spikes observed during holiday months

- AOV steadily increasing — indicates successful upselling strategies

---
## 🗂️ Data Structure Overview
The star schema design enhances performance for BI tools as well as allows efficient filtering, aggregation, and analysis by product and customer dimensions. Below is the entity relationship diagram:

![data-model](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_model.png)

> Links:
>
> - [Datasets](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/datasets): Access to the project dataset (.csv and .bak files).
> - [Data Catalog](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_catalog.md): A comprehensive description of the datasets used in this analytical project, which were derived from the Gold layer of the [🛄SQL Data Warehouse Project](https://github.com/KLinh62/SQL-Data-Warehouse-Project).

### Data Quality Checks

Basic validation tests were performed using SQL to ensure data quality:

- **Null Checks**: Verified missing values across primary fields
- **Data Types**: Ensured consistency (e.g., dates, prices, quantities)
- **Duplications**: Checked for duplicate records in `orders` and `order_items`
- **Joins Testing**: Validated foreign key relationships among tables

> **Note**: All required data validation and quality assurance (nulls, referential integrity, data types, duplicates, etc.) were already conducted during the **Silver** and **Gold Layer** development in the SQL Data Warehouse Project's [📁tests folder](https://github.com/KLinh62/SQL-Data-Warehouse-Project/tree/main/tests).  

This ensures the data input for this project is clean, reliable, and analysis-ready.

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

> [Link to SQL Scripts](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/scripts)

Below is the mind map of both Exploratory Data Analysis & Advanced Business Analytics processes:
![data-analytics-steps](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/blob/main/docs/data-analytics-steps.png)

### 🔍 Phase 1: Exploratory Data Analysis (EDA) with SQL

SQL was extensively used for foundational understanding of the data. This enabled easy cleaning, profiling, and modelling of the data.

1. **Data Exploration**: Initial overview of data structure (the list of tables and their schemas), inspecting the columns and metadata for specific tables.

2. **Dimension Exploration**: Exploring the attributes within dimension tables (e.g., customer demographics, product categories) to understand their distinct values and impact.

3. **Date Exploration**: Examining temporal boundaries of key data points, such as sales date boundaries or customer age range.

4. **Measures Exploration**: Calculating the aggregated metrics (e.g., ranges, totals, averages) of key measures like sales_amount, quantity, and price.  Generate a Report that shows all key metrics of the business.

5. **Magnitude Analysis**: Quantifying the data and group the results by specific dimensions (e.g., Compute total revenue, customer counts, and product volumes, then measure the metrics magnitude by region, brand, or customer type)

6. **Ranking Analysis**: Identifying top N or bottom N entities based on specific measures (e.g., top-selling products, highest-value customers).

---

### 📈 Phase 2: Advanced Analytics with SQL

Building upon the EDA, more complex SQL queries were developed to dig deeper into business performance and customer behavior.

7. **Change-Over-Time Trends**: Analyzing how key metrics evolve over time (e.g., monthly sales growth, product performance across quarters), identifying seasonality for time-series analysis.

8. **Cumulative Analysis**: Calculating running totals or cumulative sums for key metrics (e.g., cumulative sales over the year) to track performance over time cumulatively. Useful for growth analysis or identifying long-term trends.

9. **Performance Analysis**: Evaluating the performance of products, customers, or regions over time (e.g., sales performance against targets, product line profitability, category-level contribution). Useful for benchmarking and identifying high-performing entities, as well as tracking yearly trends and growth.

10. **Part-to-Whole Analysis**: Determining the contribution of individual metrics across dimensions or time periods to evaluate differences between categories (e.g., percentage of total sales by each product category). Useful for A/B testing or regional comparisons. > Supported donut/pie and stacked column charts

11. **Data Segmentation**: Grouping data into meaningful categories to reveal insights within specific segments (i.e., group customers by spending behavior, group products by cost ranges). Used for customer segmentation, product categorization, or regional analysis.

12. **Reporting**: Generating two consolidated views of key metrics, behaviors, and performance indicators for customers and products, enabling data-driven decision-making. These SQL Views are then exported as .csv files, and imported into PowerBI for to serve as **data sources** for interactive dashboards.

----

## 🔗 Phase 3: Power BI Integration

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

