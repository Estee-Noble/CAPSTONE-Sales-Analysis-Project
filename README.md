# CAPSTONE-Sales-Analysis-Project
#### This is where i documented my main LITA PROJECT on Sales Performance Analysis.
---

## Project Title: Sales Performance Analysis for a Retail store 

### Project Overview: 
#### This sales data provides the analysis of the sales performance of a retail store that will uncover key insights such as top-selling products,regional sales performance and the monthly sales trends and the main goal is to produce an interactive and attractive PowerBI dashboard that analyzes the findings.


### Project Objective: 
#### The main goal is to evaluate the sales performance of a retail store, identify patterns and trends, and provide actionable insights to improve profitability. This analysis will assess key metrics such as revenue, sales growth, customer preferences, and product performance.


### Data Collected 

The dataset includes the following key columns:

-  **Order ID**: Unique identifier for each transaction, used for order analysis and ensuring data accuracy.

-  **Customer ID**: Unique identifier for each customer, enabling customer segmentation and retention analysis.

-  **Product**: Identifies products sold, essential for product performance analysis.

-  **Region**: Indicates where the sale occurred, critical for regional performance analysis.

-  **Order Date**: Timestamp of the sale, allowing for time-based trend analysis.

-  **Quantity**: Number of units sold per order, used for calculating sales volume and analyzing customer purchasing behavior.

-  **Unit Price**: Price per unit of the product, essential for calculating total sales and assessing product pricing strategies.

-  **Total Sales**: Total revenue from each transaction (was calculated by multiplying Quantity and Unit Price).


### Scope of Analysis

The analysis will cover:
-  Sales Trends Over Time: Using the "Order Date" column, analyze sales trends by day, week, month, and year to identify high and low-performing periods.

-  Regional Performance: Using the "Region" column, evaluate sales performance by different regions to see how geography affects sales.

-  Product Performance: Track each "Product" to determine top-selling items, identify underperforming products, and analyze product categories.

-  Customer Behavior: Using "Customer ID," identify customer purchasing patterns, repeat purchases, and loyalty metrics.

-  Order Analysis: Using "Order ID" and "Quantity," assess the average quantity per order and high-volume products, which can inform stock management and promotional efforts.




### Key Performance Indicators (KPIs)
The KPIs includes:

-  Total Revenue (Total Sales): Total of the "Total Sales" column to get overall revenue within the selected period.

-  Average Order Value (AOV): Average revenue per "Order ID," calculated as Total Sales / Number of Orders.

-  Sales Growth Rate: Comparison of total revenue over different time periods (e.g., month-over-month or year-over-year growth).

-  Units Sold: Total of the "Quantity" column, showing total units sold for each product and across regions.

-  Customer Retention Rate: Calculated using "Customer ID" to identify repeat customers.

-  Top Products by Revenue and Quantity: Identifies products generating the most revenue and highest quantity sold.

-  Regional Performance: Revenue and units sold by "Region" to identify high and low-performing regions.

-  Seasonal Sales Variations: Analyzing "Order Date" to identify sales peaks and low periods, helping with inventory and promotional planning. 



### Tools Used

-  Microsoft Excel Download Here
i.  For Data Cleaning, preparation and Analysis
ii. Data Analysis
Excel (Pivot Tables, Charts): Excel helps to provides powerful features like Pivot Tables for quick aggregations and analysis, making it a go-to tool for many analysts.


-  SQL - Structured Query Language
i.  Quering of Data and Data Collection and Extraction, handling missing values, duplicates and standardization.
ii. Helps in aggregations, grouping queries (like total sales, average order value, etc.) within the database.

-  Power BI - (Power Business Intelligence)
i.  Data visualisation: Effective for creating interactive dashboards with real-time data connections, filters, and drill-downs, ideal for reporting sales trends and KPIs.


### EXPLORATORY DATA ANALYSIS (WITH Excel)
#### Pivot table representation 
Total sales by Product

Total sales by Region

Total sales by Month

Average sales per product

Total revenue by region



### EXPLORATORY DATA ANALYSIS (WITH SQL)
It involves the exploring of Data to answer some questions about the Data such as:
Top-selling product
monthly sales trend
sales for each product category
number of sales transaction in each region
highest selling product by total sales value
total revenue per product
monthly sales total for the current year
the top 5 customers by total purchase amount
percentage of total sales contributed by Each region
identify product with no sales in the last quarter

#### STEPS:
Convert excel sheet to csv
Remove headers
import the csv to my sql
Ensure to format the the date column into YYY-MM-DD while importing the csv into my sql.

-  Total sales for each product category;
SELECT Product, SUM(Totalsales) As TotalSales
FROM orders
GROUP BY Product

-  Number of sales transaction in each region;
SELECT Region, COUNT(*)As NumberOfTransaction
FROM Orders
GROUP BY Region

-  Top selling product by total sales value;
SELECT Product, SUM(TotalSales) As TotalSales
FROM orders
GROUP BY TotalSales DESC
LIMIT 1

-  Total revenue per product:
SELECT Product, SUM(TotalSales)As TotalRevenue
FROM Orders
GROUP BY Product

- Monthly sales total for the current year;
SELECT MONTH(OrderDate)As Month, SUM (TotalSales)As MonthlySales
FROM Orders
WHERE YEAR(OrderDate)=YEAR(CURDATED())
GROUP BY MONTH(OrderDate)
ORDER BY MONTH

-  Top 5 customer by totalpurchase amount;
SELECT CustomerID,SUM(TotalSales) As TotalPurchase
FROM orders
GROUP BY CustomerID
ORDER BY TotalPurchase DESC
LIMIT 5

-  Percentage of total sales contributed by each region;
SELECT Region,
SUM(TotalSales) As TotalSales,
(SUN(TotalSaless)/(SELECTSUM(TotalSales)FROM orders)*100) As PercentageOfTotalSales
FROM orders
GROUP BY Region

-  Products with no sale in the last quarter;
SELECT DISTINCT Product
FROM orders
WHERE Product NOT IN(
SELECT Product
FROM orders
WHERE OrderDate>=DATE_SUB(CURDATE(),INTERVAL 3 MONTH)
)

### EXPLORATORY DATA ANALYSIS (WITH POWER BI)
The dashboard include a sales overview, top-performing products, and 
regional breakdowns.

