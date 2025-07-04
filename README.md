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


## Question No. 1
------FROM [dbo].[KMS Sql Case Study]
GROUP BY Product_Category
ORDER BY Total_Sales DESC
-------


