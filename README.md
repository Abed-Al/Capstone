# Online Retail Data Set ( Segment Customers to levels )

## Overview

#### Data Set Information:
This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

Online Retail Data Set data set contains 8 columns, and around 540,000 rows.
You can download the data from UCI in this like: [_here_](https://archive.ics.uci.edu/ml/datasets/online+retail)

#### Columns descriptions:

1- InvoiceNo: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation.

2- StockCode: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.

3-Description: Product (item) name. Nominal.

4- Quantity: The quantities of each product (item) per transaction. Numeric.

5- InvoiceDate: Invice Date and time. Numeric, the day and time when each transaction was generated.

6-UnitPrice: Unit price. Numeric, Product price per unit in sterling.

7-CustomerID: Customer number. Nominal, a 5-digit integral number 
uniquely assigned to each customer.

8-Country: Country name. Nominal, the name of the country where each customer resides.


## The aim of this project:

Analysed the content of the E-Commerce database that contains the purchases made by more than 4000 customers over one year. 
The aim was to find out which customers would fit into different categories (Vip, Loyal, Middle, At Risk) in terms of who was most important for the company
Also, find answer for some question like:
    - Best buyers to  follow up with them and send them offers?
    - Best spent customers?
    - Countries bring the best sales from?
    - Number of customers in each country?
    - Customers that have the most orders to the least in all Customers?
    - Customer they have Just 1 orders and Customers they have between 1 and 20 orders?

## Cleaning & Processing

Used cleaning To extract most useful data, by:
    - Identifying variables relevant to modelling, and which to drop.
    - Interpreting continuous and categorical features.
    - Creating more model-friendly feature names.
    - Exploring opportunities for new feature creation.
    - Looking for erroneous, duplicated or missing data.
    
## Exploratory Data Analysis (EDA)
     To look at data and identify obvious errors, as well as better understand patterns within the data,
     detect outliers or anomalous events, find interesting relations among the variables.
png.png ![](https://github.com/Abed-Al/Capstone/blob/main/Project_img/Screenshot%20(1301).png)

## Techniques used: 
##### Python and Clustering Algorithm
##### Segment the customers with RFM method
    - Recency: How recently a customer has made a purchase
    - Frequency: How often a customer makes a purchase
    - Monetary Value: How much money a customer spends on purchases
#### - K-Means Segmentation
#### - Find the level of costumes and identify them to groups (Vip, Loyal, Middle, At Risk)

