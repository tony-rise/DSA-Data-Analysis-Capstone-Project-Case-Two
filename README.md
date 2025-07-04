# DSA Data Analysis Capstone Project Documentation

## Introduction: 
My name Ibor Anthony Nornu from Rivers State (Nigeria) a student of the Incubator Hub (Digital SkillUp Africa Training Programme). My course of choice was Data Analysis and it was really an interesting journey for the past three (3) months. I have gone through an extensive mentorship session in Microsoft Excel, Structured Query Language (SQL) and Power BI.

I have been mentored by industry expert facilitators with so many years of experience in the Data space and also connected with Squad mates from various part of the country and beyond.

This project is where I started to showcase my technical/digital skills in Data Analysis that I acquired from the Incubator Hub (DSA) with practical hands-one training to demonstrate my analytical thinking, technical skill, and storytelling capabilities through data.


## Project Instructions
We are required to select any 2 out of the 3 case studies shared with us for this project. For each selected case study, we are to carry out a comprehensive Exploratory Data Analysis (EDA) using the appropriate analytical tools and techniques relevant to the context of each dataset accordingly.


## Table of Content

### Data Source
For the DSA Capstone Project, all the necessary Data set required to carry-out this detailed analysis were shared on our Learning Management System (LMS) Powered by Canvas.
In view of this, my Data Source for this project was the Learning Management System (LSM) by CANVAS.


## Tools Usage
The following applications were installed for our lectures and was also be utilized for the duration of this project. The facilitators guided us thoroughly on the use of this applications during the course of the training to enable us get the best results in our Data Analysis journey.
- Microsoft Excel [DOWNLOAD HERE](https://www.microsoft.com/en/microsoft-365/excel?market=af#Plans-pricing)
  - Primarily used for organizing, calculating, and analyzing data through spreadsheets.
- SQL Server Management Studio [DOWNLOAD HERE](https://learn.microsoft.com/en-us/ssms/install/install)
  - Used to connect to and manage SQL Server instances, including creating, modifying, and deleting databases etc.
- Power Business Integration (BI) [DOWNLOAD HERE](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
  - Used to transform and model that data, and then create interactive dashboards and reports to gain insights and make data-driven decisions.


## Project Structure

## Selected Case Study 2 (Kultra Mega Stores (KMS) Inventory)

### Case Study Overview

Kultra Mega Stores (KMS), headquartered in Lagos, specialises in office supplies and furniture. Its customer base includes individual consumers, small businesses (retail), and large corporate clients (wholesale) across Lagos, Nigeria. 

I was engaged as a Business Intelligence Analyst to support the Abuja division of KMS. The Business Manager has shared an Excel file containing order data from 2009 to 2012 and has requested that you analyze the data and present your key insights and findings.

## Dataset Description
The dataset contains information from the company sales Data which included but not limited to: the Order Date, Order priority, order quantity, sales, discount, shipping mode and others.


## Explanatory Data Analysis (EDA)
This process involved the exploration of the Data Set provided to Apply the SQL skills from the DSA Data Analysis classes and solve both case scenarios as shared in the document. 

### Case Scenario One
1. Which product category had the highest sales? 
2. What are the Top 3 and Bottom 3 regions in terms of sales? 
3. What were the total sales of appliances in Ontario? 
4. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers 
5. KMS incurred the most shipping cost using which shipping method?

### Case Scenario Two
6. Who are the most valuable customers, and what products or services do they typically purchase? 
7. Which small business customer had the highest sales? 
8. Which Corporate Customer placed the most number of orders in 2009 – 2012? 
9. Which consumer customer was the most profitable one? 
10. Which customer returned items, and what segment do they belong to? 
11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer


## Results 
After a detailed breakdown of SQL queries entries, we arrived at the following results:

### Case Scenario One

### Question No. 1 
Which product category had the highest sales?

```SQL
FROM [dbo].[KMS Sql Case Study]
GROUP BY Product_Category
ORDER BY Total_Sales DESC
```

### Question No. 2a
2. What are the Top 3 and Bottom 3 regions in terms of sales?

```SQL
SELECT top 3 Region, SUM(Sales) AS Total_Sales
FROM [dbo].[KMS Sql Case Study]
GROUP BY Region
ORDER BY Total_Sales DESC
```

### Question No. 2B Bottom 3 regions in terms of sales?
```SQL
SELECT top 3 Region, SUM(Sales) AS Total_Sales
FROM [dbo].[KMS Sql Case Study]
GROUP BY Region
ORDER BY Total_Sales ASC
```

### Question No. 3  What were the total sales of appliances in Ontario? 
``` SQL
SELECT SUM(Sales) AS Total_Appliance_Sales_Ontario
FROM [dbo].[KMS Sql Case Study]
WHERE Product_Sub_Category = 'Appliances'
  AND Province = 'Ontario';
```

### Question No. 4 Advise the management of KMS on what to do to increase the revenue from the bottom 
10 customers  
```SQL
select top 10 customer_name, sum (sales) as Revenue
  from [dbo].[KMS Sql Case Study]
  group by customer_name
  order by Revenue asc
```

### ADVISE 
- I firmly recommend complementary or higher-end products at checkout or through marketing emails.
- Also to consider free shipping thresholds or more reliable shipping methods to low-value customers to boost customer satisfaction.


### Question No. 5 KMS incurred the most shipping cost using which shipping method? 
```SQL
SELECT top 1 ship_mode, SUM (shipping_cost) AS total_shipping_cost
FROM [dbo].[KMS Sql Case Study]
GROUP BY ship_mode 
ORDER BY total_shipping_cost DESC
```


### Case Scenario Two

### Question No. 6 Who are the most valuable customers, and what products or services do they typically 
purchase? 
```SQL
SELECT TOP 5 Customer_Name, Product_Name, SUM(SALES) AS VALUABLE_CUSTOMERS FROM [KMS Sql Case Study]
GROUP BY Customer_Name, Product_Name
ORDER BY VALUABLE_CUSTOMERS DESC
```


### Question No. 7 Which small business customer had the highest sales? 
``` SQL
SELECT top 1 Customer_name, SUM(Sales) AS Total_Sales
FROM [dbo].[KMS Sql Case Study]
where Customer_Segment = 'small business'
GROUP BY Customer_name
ORDER BY Total_Sales DESC
```

### Question No. 8 Which Corporate Customer placed the most number of orders in 2009 – 2012? 
```SQL
select top 1 Customer_Name, count (Order_ID) As Number_of_Order
from [dbo].[KMS Sql Case Study]
where Customer_Segment = 'Corporate' AND
Order_Date between '2009-01-01' and '2012-12-31'
group by Customer_Name
order by Number_of_Order desc
```


### Question No. 9 Which consumer customer was the most profitable one? 
```SQL
select top 1 Customer_Name, sum(profit) as [Most Profitable] from [KMS Sql Case Study]
where Customer_Segment = 'Consumer'
group by Customer_Name
order by [Most Profitable] desc
```

### Question No. 10 Which customer returned items, and what segment do they belong to? 
``` SQL
select  Order_Status.Order_ID, [KMS Sql Case Study].Customer_Name, [KMS Sql Case Study].Customer_Segment, Order_Status.Status
from [KMS Sql Case Study]
join Order_Status
on
[KMS Sql Case Study].Order_ID = Order_Status .Order_ID
```


### Question No. 11  If the delivery truck is the most economical but the slowest shipping method and 
Express Air is the fastest but the most expensive one, do you think the company 
appropriately spent shipping costs based on the Order Priority? Explain your answer 

```SQL
select Order_Priority, Ship_Mode,
Count(Order_ID) as Total_Delivery,
ROUND(SUM(Sales - Profit),2) AS EstimatedShippingCost,
AVG(DATEDIFF(day, [Order_Date], [Ship_Date])) AS AvgShipDays
from [KMS Sql Case Study]
group by Order_Priority, Ship_Mode
```

## Explanation
High-priority orders (e.g., Critical or High) were shipped using faster but more expensive methods like Express Air.

Low-priority orders (e.g., Low or Not Specified) were shipped using slower but more economical methods like Delivery Truck.



## Recommendations

I strongly recommend that the company target "Corporate" and "Small Business" customers with high-margin products or volume-based deals. There is a high margin on bulk purchase from this segment.


## Contributions

- I suggest the company looks deeply into overspending on shipping without proportionate return on investment
- Another contribution I made for the company was to suggest for them to focus on marketing executive furniture and printing equipment like the Global Troy chairs and HP LaserJet printers because of its high revenue yielding capabilities.

