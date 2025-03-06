**Retail Data Analysis**

**Project Overview**

The project's main focus is retail data analysis, which employs Excel and SQL (SSMS) to examine sales patterns, consumer behavior, and company performance. We derive valuable insights from Point of Sales (POS) data to assist merchants in improving customer satisfaction, increasing profitability, and optimizing their business strategies.

**Objective**

This project's principal goal is to:

Examine consumer transactions to determine preferences and trends in purchases.
Analyze how demographic variables affect sales.
Choose the payment options and sales channels that work best.
Determine product sales trends to improve inventory control.
Evaluate return transactions and reduce losses in revenue.
Produce insights that can be put to use to increase overall business efficiency.

**Tools & Technologies Used**

SQL (SSMS, SQL Server Management Studio):

used in relational databases to query, filter, and work with huge datasets.
used SQL queries to log transactions, analyze sales trends, and segment customers.
To get data ready for analysis, data transformation and cleaning were done.

**Business Problem**

A well-known retail establishment wants to use its Point of Sale (POS) system to obtain data-driven insights in order to:

Gain insight into consumer purchasing patterns by examining transaction data.
Determine which products are in high demand and when sales are at their highest to improve business performance.
By using demographic-based client segmentation, marketing techniques can be improved.
Determine the elements influencing product returns to cut down on operational inefficiencies.

**Data Overview**

There are three main tables in the dataset:

**1.Customer Table**

keeps track of client demographic information like:

Customer ID
Name
Gender
Age
City

**2. Transactions Table**

includes information about customer transactions, such as:

Transaction ID
Customer ID
Date of purchase
Payment method (Credit Card, Debit Card, UPI, COD, etc.)
Amount spent
Return status (whether the transaction was returned)

**3. Product Category Table**

contains information about the product category and subcategories:

Product ID
Product Category (Electronics, Clothing, Furniture, etc.)
Sub-category
Price
A thorough examination of customer behavior and sales patterns is made possible by the links between these tables, which are established by Customer ID and Product ID.

**Approach & Methodology**

**1. Data Preparation & Understanding**

Excel was used to extract data from SQL Server for additional reporting and analysis.
To evaluate the volume of data and guarantee completeness, the total number of rows in each table was counted.
examined the dataset for errors and missing values.
filtered out transactions that were incomplete or invalid.
To verify data consistency and spot seasonal patterns, the date range of transactions was examined.
To assess the financial impact of return transactions, they were identified and categorized.

**2. Data Analysis & Insights**

**(i) Transaction Channel Analysis:**

determined which payment options are most frequently utilized.
assessed payment inclinations based on client demographics.
The optimal transaction channels were suggested in order to maximize store payment tactics.

**(ii) Customer Demographic Insights:**

categorized clients by city, age, and gender in order to pinpoint important purchasing patterns.
examined expenditure trends according to demographic categories.
gave information about the shopping habits of various client segments.

**(iii) City-wise Sales Summary:**

Cities with the highest and lowest sales volumes were identified.
made suggestions for store expansion and promotions tailored to a particular location.

**(iv) Product Category & Sales Trends:**

examined the top-selling goods and markets.
Revenue contribution was tracked for each product category and subcategory.
suggested changes to inventory to satisfy customer demand.

**(v) Return Analysis & Impact:**

determined the proportion of transactions that had returns.
examined typical returns' causes according to product types.
offered methods for reducing returns and raising the caliber of the products.

**SQL Queries Implemented**

**(i) Total Available Customers**

SELECT COUNT(DISTINCT Customer_ID) AS Total_Customers FROM Customer;

determines how many distinct clients there are in the dataset overall.

**(ii) Total Transactions & Returns**

SELECT 
    COUNT(Transaction_ID) AS Total_Transactions,
    SUM(CASE WHEN Return_Status = 'Yes' THEN 1 ELSE 0 END) AS Returned_Transactions
FROM Transactions;

determines how many transactions and refunds there have been overall.

**(iii) Most Frequently Used Payment Method**

SELECT Payment_Method, COUNT(*) AS Usage_Count
FROM Transactions
GROUP BY Payment Method
ORDER BY Usage_Count DESC;

identifies the most widely accepted form of payment.

**(iv) Top 5 Cities with Highest Sales**

SELECT C.City, SUM(T.Amount) AS Total_Sales
FROM Transactions T
JOIN Customer C ON T.Customer_ID = C.Customer_ID
GROUP BY C.City
ORDER BY Total_Sales DESC
LIMIT 5;

identify the five cities with the most revenue.

**(v) Best-Selling Product Categories**

SELECT P.Product_Category, COUNT(T.Transaction_ID) AS Sales_Count
FROM Transactions T
JOIN Product_Category P ON T.Product_ID = P.Product_ID
GROUP BY Product Category
ORDER BY Sales_Count DESC;

determines which product categories are most commonly bought.

**Key Findings & Business Impact**

**(i) Customer Behavior Insights:**

Customers of different sexes have distinct buying inclinations.
Targeted promotions are improved by higher sales from particular cities and age groups.

**(ii) Sales Trends & Seasonal Demand:**

Certain months have the highest sales, which enables companies to adjust their marketing and stocking strategies accordingly.

**(iii) Optimized Payment Methods:**

The most popular payment options are credit cards and UPI, which allow for improved transaction processing techniques.

**(iv) Better Inventory Management:**

Data-driven stocking techniques decrease surplus inventory and increase product availability.

**(v) Reduction in Return Costs:**

determined the most frequent causes of product returns, enabling companies to put plans in place to reduce exchanges and refunds.

**Conclusion**

This project demonstrates proficiency in business intelligence, query optimization, and SQL-based data analysis. It exhibits the capacity to:

Draw insightful conclusions from huge datasets.
Determine the patterns and trends that influence company choices.
Make use of data-driven insights to optimize retail strategies.
To efficiently retrieve, filter, and summarize data, use SQL.
Excel can be used to effectively report and visualize findings.
