# SQL Retail Data Analytics Project

This project establishes a complete analytics pipeline for retail data, utilizing SQL for robust data analysis and Power BI for dynamic visualization. The objective is to generate actionable insights into customer behavior, product performance, and sales trends, thereby empowering strategic, data-driven decision-making. This project leverages a comprehensive suite of SQL scripts and Power BI to perform everything from initial data exploration to advanced analytics and final reporting.

> - **SQL Focus**: Robust data preparation, exploration, and advanced analytical query development within a relational database.
> 
> - **BI Focus**: Data-driven decisions in customer engagement, product optimization, and revenue growth.

---

## 📦 Project Background

This Data Analytics Project is built for a simulated retail company aiming to improve decision-making across customer behavior, product performance, and sales trends.

The company has accumulated large volumes of sales data but lacked proper analytical processing and visualization. This project leverages SQL for data preparation and Power BI for business intelligence reporting, uncovering patterns that support growth and operational improvements.

Key business metrics and insights are explored through:

- Identifying **top-performing products**
- Understanding **customer purchasing behavior**
- Analyzing **sales trends** across time

> *Links*:
> 
> The interactive Power BI dashboard can be downloaded [here]()
> 
> The SQL queries utilized to perform ETL on the raw data to produce a clean, enriched, and analysis-ready dataset can be found [here](https://github.com/KLinh62/SQL-Data-Warehouse-Project/tree/main/scripts).
> 
> The SQL queries utilized to inspect and perform quality checks (performed in Silver and Gold Layer) can be found [here](https://github.com/KLinh62/SQL-Data-Warehouse-Project/tree/main/tests).
> 
> Targeted SQL queries regarding various business questions can be found [here](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/scripts).

---
## 🗂️ Data Structure & Quality Checks
For this analysis project, the retail dataset utilized was derived from the Gold Layer of the [SQL Data Warehouse Project](https://github.com/KLinh62/SQL-Data-Warehouse-Project). The dataset consists of 3 tables: dim_customers, dim_products, and fact_sales, with a total of 108,127 records in the fact table. 

The data model follows a star schema design to enhance performance for BI tools later. Below is the entity relationship diagram:

![data-model](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_model.png)

> - [Datasets](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/datasets): Access to the project dataset (.csv and .bak files).
> - [Data Catalog](https://github.com/KLinh62/SQL-Data-Warehouse-Project/blob/main/docs/data_catalog.md): A comprehensive description of the datasets used in this analytical project.

Prior to the beginning of this analysis project, a variety of checks were conducted for data validation and quality assurance. It ensures the data input for this project is clean, reliable, and analysis-ready.  

> - The SQL queries utilized to inspect and perform quality checks can be found [here](https://github.com/KLinh62/SQL-Data-Warehouse-Project/tree/main/tests). 

---

## 🛠 Tools & Technologies

| Tool      | Purpose                             |
|-----------|-------------------------------------|
| SQL       | Data warehouse structure, querying  |
| Power BI  | Dashboarding and reporting          |
| GitHub    | Version control and collaboration   |

---
## 🧠 Data Analysis & Visualization Steps

This project involves delving into the datasets to understand their characteristics, identify patterns, and uncover initial insights. A total of **12 SQL scripts** are developed to drive both **Exploratory Data Analysis (EDA)** and **Advanced Business Analytics**. These queries are executed using Microsoft SQL Server and the results exported for Power BI reporting.

> The SQL queries for data analysis can be found [here](https://github.com/KLinh62/SQL-PowerBI-Data-Analytics-Project/tree/main/scripts)

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

### 🔗 Phase 3: Building dashboards with Power BI

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

> All `.csv` outputs are stored in `/data/dashboard-inputs/` and referenced in the Power BI `.pbix` file under `/reports/`.

### ⚙️ Automation Potential

This SQL + Power BI pipeline is highly automatable. With a data warehouse and tools like Power BI Gateway or Python scripts, the refresh cycle can be scheduled for near real-time reporting.

---

## 🧑‍💻 Author

**Nguyen Khanh Linh**  
📧 nklinh.620@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/khánh-linh-nguyễn-346115176)



## 🌟 About Me

Hi there! I'm **Linh Nguyen**, an Supply Chain professional who is passonate about data.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kh%C3%A1nh-linh-nguy%E1%BB%85n-346115176/)

