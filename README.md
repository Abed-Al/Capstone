# Capstone Online Retail Data Set (Segment Customers to levels)


## Overview
As an online store company, you would want to group the customers into different clusters, so that you can make a customised marketing campaign for each of the groups. You would have to decide what the important business criterias are and how you would want to segregate the customers.
In this project I will try to divide the customers into different groups, based on their level. Also make some useful analysis to help the company decide on future business plans.

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

The aim of this project was to analyse the content of the E-Commerce database that contains the purchases made by more than 4000 customers over one year. The aim was to find out which customers would fit into different categories (Vip, Loyal, Middle, At Risk) in terms of who was most important for the company.
The goal was to find answers to the following questions:
- Best buyers to follow up with them and send them offers? 
- Best spent customers?
- Where do the countries with the most sales get their sales from?
- Number of customers in each country? 
- Customers that have the most orders? 
- Customers have between 1 and 20 orders?


## Cleaning & Processing

There are a few data preparation steps to take before I can start segmenting customers:
We started preparing the data by taking a few steps to clean the data, to make sure it is ready for segmenting customers:
##### -Looking for erroneous, duplicated or missing data.
##### -Identifying variables relevant to modelling and which to drop.
##### -Filtering our negative (canceled) orders. If you look at the Quantity column, you notice some negative values there - canceled or returned orders. I therefore needed to remove these orders.
##### -Handling NA values in the CustomerID field. Customer ID is crucial for this analysis, so I had to drop NA values there.
##### -Changing the InvoiceDate column to DateTime format. In order to prevent any issues with dates, I like to make sure all the data is in the appropriate format.
##### -Calculating the sales column by multiplying the Quantity and UnitPrice columns.
##### -Transforming data - each record represents the purchase history of individual customers.
    

## Exploring the data
The first task was to analyse the data and find the total number of products( stock codes), transactions(invoice number), and customers(customer ID) in the data. 
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/Take%20a%20look%20of%20the%20total%20number%20of%20products%2C%20InvoiceNo%20and%20customers.png)

## Exploratory Data Analysis (EDA)
To look at data and identify obvious errors, as well as better understand patterns within the data,
 detect outliers or anomalous events, find interesting relations among the variables.
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/outlear.png)
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/30%20Most%20spending%20customers.png)
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/Customers%20who%20have%2020%20orders%20or%20less.png)
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/The%20percentage%20of%20customers%20in%20each%20country.png)

## Techniques used: 
##### Python and Clustering Algorithm
##### Segment the customers with RFM method
Create new data (rfm_data): contains (CustomerID, recency, frequency, monetary) columns:

1-  Segment the customers to levels by find (Recency, Frequency, Monetary) for each customer:

Recency = The difference between the last order customers make and the last day of the data

Frequency = Number of orders based on (InvoiceNo) done by each customer

Monetary = The total amount the customer spend during the period of the data

png.png ![]()

2-   Find (Recency_score, Frequency_score, Monetary_score) by apply qcut function (Quantile-based discretization) to RFM data and create score column for each one.

3-  Add (RFM_Score) column which is sum of: (Recency_score, Frequency_score, Monetary_score).

4-  Add (RFM_segment) column which is show us the combined concatenated score of RFM.

The score will be between 3 and 15, because:

Lowest score is 3 = 1 Recency, 1 Frequency, 1 Monetary

Highest score is 15 = 5 Recency, 5 Frequency, 5 Monet
 
 png.png ![]()
 
 Find out RFM score segmentation
The score will by between 3 and 15, because:

Lowest score is 3 = 1 Recency, 1 Frequency, 1 Monetary

Highest score is = 5 Recency, 5 Frequency, 5 Monetary

Find out the mean for each score in (Recency,Frequency,Monetary) and (count, sum) Monetary

png.png ![]()

Divide the customer to groups (V_Vip, Vip, Loyal, Middle, Low)

png.png ![]()
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/Number%20customer%20in%20each%20Segment_Level.png)

#### - K-Means Segmentation
Produce an elbow plot to decide on a suitable number of clusters.
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/plot_elbow.png)

I think the best number of clusters is 4.


#### - Find the level of costumes and identify them to groups (Vip, Loyal, Middle, At Risk)
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/cluster%20level.png)
png.png ![](https://github.com/Abed-Al/Online-Retail-Data-Set-Segment-Customers-to-levels-/blob/main/Project_img/Plot%20Hierarchical%20Clustering%20Dendrogram%20(clustering%20tree).png)


## Conclusion
From the above analysis, we can see that there should be 4 clusters in our data.

To understand what these 4 clusters mean in a business scenario, we should look back at the table comparing the clustering performance of 3 and 4 clusters for the mean values of recency, frequency, and monetary metric.

On this basis, let us label the clusters as ‘New customers’, ‘Lost customers’, ‘Best customers’, and ‘At risk customers’.

## Challenges
One of the challenges on the project was using the RFM Segmentation method to segment the customers data and find the correct level for each customer. Another challenge was measuring how effective this method was compared with K-means clustering.

## Key Learning
I gained valuable experience with a number of new libraries, as well as sharpening my knowledge with libraries I was already familiar with.
Another key learning was understanding the importance of understanding your data in order to make the right assumptions. For example, the InvoiceNo, starting with character C, represents a canceled order and Quantities(Quantity) with Invoice number(InvoiceNo) starts with character C in NEGATIVE.

## Future Work
* Addition of new variables like Tenure: The number of days since the first transaction by each customer. This will enable us to determine how long each customer has been within the system.
* Conducting deeper segmentation on customers based on their geographical location, and demographic and psychographic factors.
* Incorporating data from the Google Analytics account of the business. Google Analytics is a great resource to track many important business metrics such as Customer Lifetime value, Traffic source/medium, PageViews per visit, Bounce rate of the company’s website.

## Ref:
-https://www.shopify.in/encyclopedia/customer-segmentation

-https://learn.datacamp.com/courses/customer-segmentation-in-python 

-https://looker.com/blog/creating-actionable-customer-segmentation-models

-https://www.business2community.com/customer-experience/4-types-of-customer-segmentation-all-marketers-should-know-02120397 

-https://towardsdatascience.com/customer-segmentation-in-online-retail-1fc707a6f9e

-https://www.intercom.com/blog/customer-segmentation/

-https://numpy.org/doc/stable/reference/generated/numpy.log.html
