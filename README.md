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

-  Microsoft Excel [Download Here](https:microsoft.com)

i.  For Data Cleaning, preparation and Analysis

ii. Data Analysis
Excel (Pivot Tables, Charts): Excel helps to provides powerful features like Pivot Tables for quick aggregations and analysis, making it a go-to tool for many analysts.


-  SQL - Structured Query Language
i.   Quering of Data and Data Collection and Extraction, handling missing values, duplicates and standardization.
ii.  Helps in aggregations, grouping queries (like total sales, average order value, etc.) within the database.

-  Power BI - (Power Business Intelligence)
i.  Data visualisation: Effective for creating interactive dashboards with real-time data connections, filters, and drill-downs, ideal for reporting sales trends and KPIs.


### EXPLORATORY DATA ANALYSIS (WITH Excel)
#### Pivot table representation 
Total sales by Product
![Screenshot total sales by product](https://github.com/user-attachments/assets/e1135739-6a7e-4e26-b1ca-beb9a0ef4a25)

Total sales by Region
![Screenshot total sale by region](https://github.com/user-attachments/assets/99b22fd9-176e-4ae3-bba9-f73061e5a314)

Total sales by Month
![Screenshot total sales by month](https://github.com/user-attachments/assets/811f38e2-7d6d-4f61-ab15-2907ff77e1ac)

Average sales per product
![Screenshot avg sales by product](https://github.com/user-attachments/assets/e93289d4-9dcb-4953-9a90-69d220210ce6)

Total revenue by region
![Screenshot total revenue by region](https://github.com/user-attachments/assets/2d061f2f-6e66-470b-b01c-ad76ac87eb92)


### EXPLORATORY DATA ANALYSIS (WITH SQL)
It involves the exploring of Data to answer some questions about the Data such as:

-  Total sales for each product category;
```SQL
SELECT Product, SUM(Totalsales) As TotalSales
FROM orders
GROUP BY Product
```
-  Number of sales transaction in each region;
```SQL
SELECT Region, COUNT(*)As NumberOfTransaction
FROM Orders GROUP BY Region
```
-  Top selling product by total sales value;
```SQL
SELECT Product, SUM(TotalSales) As TotalSales
FROM orders
GROUP BY TotalSales DESC
LIMIT 1
```
-  Total revenue per product:
  ```SQL
SELECT Product, SUM(TotalSales)As TotalRevenue
FROM Orders
GROUP BY Product
```
- Monthly sales total for the current year;
```SQL
SELECT MONTH(OrderDate)As Month, SUM (TotalSales)As MonthlySales
FROM Orders
WHERE YEAR(OrderDate)=YEAR(CURDATED())
GROUP BY MONTH(OrderDate)
ORDER BY MONTH
```

-  Top 5 customer by totalpurchase amount;
```SQL
SELECT CustomerID,SUM(TotalSales) As TotalPurchase
FROM orders
GROUP BY CustomerID
ORDER BY TotalPurchase DESC
LIMIT 5
```
-  Percentage of total sales contributed by each region;
```SQL
SELECT Region,
SUM(TotalSales) As TotalSales,
(SUN(TotalSaless)/(SELECTSUM(TotalSales)FROM orders)*100) As PercentageOfTotalSales
FROM orders
GROUP BY Region
```
-  Products with no sale in the last quarter;
```SQL
SELECT DISTINCT Product
FROM orders
WHERE Product NOT IN(
SELECT Product
FROM orders
WHERE OrderDate>=DATE_SUB(CURDATE(),INTERVAL 3 MONTH)
)
```
### EXPLORATORY DATA ANALYSIS (WITH POWER BI)
The dashboard include a sales overview, top-performing products, and regional breakdowns.


![Screenshot Sales performance BI](https://github.com/user-attachments/assets/c09afd91-e948-4161-9371-5d4b5519c0f8)



 #### Visualizations and Analysis

-  Sum of Total Sales by Product: A bar chart compares the total sales by each product type. The Shirt and Shoes categories lead, with sales figures around 326.67 and 308.75, respectively, indicating these products are the top sellers.

-  Sum of Total Sales by Region: A pie chart shows the distribution of sales across four regions: South (44.16%), North (23.14%), East (18.42%), and West (14.29%). The South region has the highest sales, contributing nearly half of the total.

-  Count of Product by Region: Another pie chart represents the count of product transactions by region, suggesting where each product is most sold. The North and South regions have nearly equal transaction shares.

-  Sum of Total Sales by Month: A bar chart shows monthly sales. March has the highest sales (1.3M), followed by April (1.4M), indicating potential seasonal trends or successful marketing efforts during these months.

-  Product Sum Total by Year: A table breaks down each product's total sales over the years from 2022 to 2024, with cumulative totals. Products such as Shoes and Shirts again show consistently high totals across the years.


#### Insights

-  Product Performance: Shirts and Shoes are the top-performing products, showing higher demand compared to others like Socks and Jackets.

-  Regional Trends: The South region is the highest contributor to sales, indicating strong market presence or demand in that area.

-  Monthly Trends: Sales are highest in March and April, suggesting a seasonal trend or possibly an effective promotional strategy during those months.

-  Yearly Growth: Total sales have grown over time, with significant contributions from all product categories, particularly in 2024.


#### Conclusion: This dashboard provides a comprehensive view of sales performance across different dimensions, helping decision-makers understand product demand, regional preferences, and seasonal trends.


