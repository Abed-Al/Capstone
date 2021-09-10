# GA-Capstone Online Retail Data Set

## Data Set Information:

This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

Online Retail Data Set data set contains 8 columns, and around 540,000 rows.
You can download the data from UCI in this like: [_here_](https://archive.ics.uci.edu/ml/datasets/online+retail)



## Columns descriptions:

1- InvoiceNo: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation.

2- StockCode: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.

3-Description: Product (item) name. Nominal.

4- Quantity: The quantities of each product (item) per transaction. Numeric.

5- InvoiceDate: Invice Date and time. Numeric, the day and time when each transaction was generated.

6-UnitPrice: Unit price. Numeric, Product price per unit in sterling.

7-CustomerID: Customer number. Nominal, a 5-digit integral number 
uniquely assigned to each customer.

8-Country: Country name. Nominal, the name of the country where each customer resides.


## The aim of this project is to answer some question like:
    - Best buyers to  follow up with them and send them offers?
    - Best spent customers?
    - Countries bring the best sales from?
    - Number of customers in each country?
    - Customers that have the most orders to the least in all Customers?
    - Customer they have Just 1 orders and Customers they have between 1 and 20 orders?
    
    
## Technique used

#### Python and Machine Learning Algorithm
 
##### Segment the customers with RFM method
    Recency: How recently a customer has made a purchase
    Frequency: How often a customer makes a purchase
    Monetary Value: How much money a customer spends on purchases

## Process: 
#### - Data Preparation (cleaning)
     To extract most useful data
#### - Exploratory Data Analysis (EDA)
     To look at data and identify obvious errors, as well as better understand patterns within the data, detect outliers or anomalous events,
     find interesting relations among the variables.
#### - K-Means Segmentation
#### - Find the level of costumes and identify them to groups (Vip, Loyal, Middle, At Risk)

