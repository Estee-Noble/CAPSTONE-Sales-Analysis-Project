# CAPSTONE-Sales-Analysis-Project
#### This is where i documented my main LITA PROJECT on Sales Performance Analysis.
---

## Project Title: Sales Performance Analysis for a Retail store 

### Project Overview: This sales data provides the analysis of the sales performance of a retail store that will uncover key insights such as top-selling products,regional sales performance and the monthly sales trends and the main goal is to produce an interactive and attractive PowerBI dashboard that analyzes the findings.


### Project Objective: The main goal is to evaluate the sales performance of a retail store, identify patterns and trends, and provide actionable insights to improve profitability. This analysis will assess key metrics such as revenue, sales growth, customer preferences, and product performance.


### Data Collected 

The dataset includes the following key columns:

Order ID: Unique identifier for each transaction, used for order analysis and ensuring data accuracy.

Customer ID: Unique identifier for each customer, enabling customer segmentation and retention analysis.

Product: Identifies products sold, essential for product performance analysis.

Region: Indicates where the sale occurred, critical for regional performance analysis.

Order Date: Timestamp of the sale, allowing for time-based trend analysis.

Quantity: Number of units sold per order, used for calculating sales volume and analyzing customer purchasing behavior.

Unit Price: Price per unit of the product, essential for calculating total sales and assessing product pricing strategies.

Total Sales: Total revenue from each transaction (was calculated by multiplying Quantity and Unit Price).


### Scope of Analysis

The analysis will cover:
Sales Trends Over Time: Using the "Order Date" column, analyze sales trends by day, week, month, and year to identify high and low-performing periods.

Regional Performance: Using the "Region" column, evaluate sales performance by different regions to see how geography affects sales.

Product Performance: Track each "Product" to determine top-selling items, identify underperforming products, and analyze product categories.

Customer Behavior: Using "Customer ID," identify customer purchasing patterns, repeat purchases, and loyalty metrics.

Order Analysis: Using "Order ID" and "Quantity," assess the average quantity per order and high-volume products, which can inform stock management and promotional efforts.




###Key Performance Indicators (KPIs)
The KPIs includes:

Total Revenue (Total Sales): Total of the "Total Sales" column to get overall revenue within the selected period.

Average Order Value (AOV): Average revenue per "Order ID," calculated as Total Sales / Number of Orders.

Sales Growth Rate: Comparison of total revenue over different time periods (e.g., month-over-month or year-over-year growth).

Units Sold: Total of the "Quantity" column, showing total units sold for each product and across regions.

Customer Retention Rate: Calculated using "Customer ID" to identify repeat customers.

Top Products by Revenue and Quantity: Identifies products generating the most revenue and highest quantity sold.

Regional Performance: Revenue and units sold by "Region" to identify high and low-performing regions.

Seasonal Sales Variations: Analyzing "Order Date" to identify sales peaks and low periods, helping with inventory and promotional planning. 



### Tools and Steps for Analysis 

Data Collection and Extraction
SQL: Help in querying data directly from databases, filtering tables and it is ideal for handling large datasets and ensuring efficient data extraction.

Excel: Used for initial data exploration.

2. Data Cleaning and Preparation
SQL: SQL commands was used to handle data cleaning tasks directly within the database, such as handling missing value,duplicates, and standardization.

Power Query in Excel: Power Query allows for data transformation and automation in Excel, making it helpful for users working with smaller datasets or familiar with Excel.

3. Data Analysis
Excel (Pivot Tables, Charts): Excel helps to provides powerful features like Pivot Tables for quick aggregations and analysis, making it a go-to tool for many analysts.

SQL: Helps in aggregations, grouping queries (like total sales, average order value, etc.) within the database. 

4. Data Visualization and Reporting
Power BI: Power BI is highly effective for creating interactive dashboards with real-time data connections, filters, and drill-downs, ideal for reporting sales trends and KPIs.
