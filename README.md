# Customer Segmentation using E-Commerce Data, covers Data Cleaning & Preparation, EDA and Clustering Analysis

## Overview / Case Background
Gustavo just started an e-commerce startup based in Portugal that recently open an online website to sell their product. Fortunately, Gustavo is launching their website when the covid-19 hits and making them grow faster than ever. However, Gustavo is still not using targeted marketing which hurts their marketing budget as only a fraction of their user comes back to their website. Gustavo needs your help to increase their marketing conversion rate by doing more targeted marketing using customer segmentation so that it will not hurt their budget.

## Data Source
1. [orders_dataset](https://drive.google.com/file/d/1uyCnPoFi_KrrESfBSfG0e66Gc_7a_lVq/view?usp=sharing).
2. [customers_dataset](https://drive.google.com/file/d/1YZ60mAob9Q0ce2QVEIOZ2-DZTerV4DSx/view?usp=sharing).
3. [order_payments_dataset](https://drive.google.com/file/d/1dnisZ_3NjqluJwo96DKfPLja0RM2cvXf/view?usp=sharing).

## Data Preparation and Cleaning
1. Not all columns will be selected for analysis process, only columns with related information will be used.
2. Check for missing value, data types, duplicate values, invalid values, and outliers.
3. Renaming columns name for clarity purpose.
4. Create additional columns (variables) to be used for analysis later `payment_installments_cat`.
5. Join all required column and table to one dataframe named as `dfco`, using merge functions in python.

## EDA Process
In this project we will do analysis for several aspect, such as:
1. The median of payment ($) made by customer, around $50-$100. The behaviour of the distribution show positive skewness.
2. Number of orders per month, which the peak of goods sold happened in November 2017 with total order is 7014 items.
3. Daily orders trend, which surprisingly the customer tend to buy goods on weekdays and less on weekends.
4. Percentage of orders per payment type, which customer prefer to buy using credit card.
5. Customer distribution by State, which top customer based on total payment value come from Sau Paulo.

## Customer Segmentation using Clustering Analysis
In order to create customer segmentation, following columns will be used for references:
1. Creating new columns, called `payment_installments_cat`, which categorize payment installment to 4 category named:
    - 'no debt-debt club' for payment made without or using 1 month installments
    - 'pinjol friendly' for payment made using 2 to 6 months installments
    - 'medium term' for payment made using 7 to 12 months installments, and
    - 'long commitment' for payment made using more than 12 months installments
2. Column `customer state` and `payment type` is converted to numeric using one hot encoding.
3. Optimal number of cluster is 4, based on elbow method metric.
![alt text](https://github.com/gilangbahana/customer-segmentation/blob/main/cust-segmentation-elbow-method.png)
4. Then, the summary of each cluster is shown in table below:
![alt text](https://github.com/gilangbahana/customer-segmentation/blob/main/cluster-customer-segmentation.JPG)

## Analysis Insight
From the clustering analysis, we got 4 clusters and the characteristics of each cluster.
1. cluster 0 = `team lunas`
    - Average spending is around $46.91.
    - Most of the customers using credit card without installments.

2. cluster 1 = `team cc & offline payment`
    - Average spending is around $176.84.
    - Most of the customers using credit card with <= 6 months installments. Beside credit card, they are also using boleto (some kind of offline payment, common in Brazil, in Indonesia very similar with pay in Indomaret/Alfamart).

3. cluster 2 = `team buy now, pay later`
    - Average spending is around $274.67.
    - Most of the customers pay using credit card within 1 year installments (medium term).

4. cluster 3 = `team cc short term`
    - Average spending is around $105.92.
    - Most of the customers pay using credit card with <= 6 months installments, meaning that they are pinjol friendly 🤑.

## Recommendation
For the better sales at the future, there are several method for sales & marketing program to be evaluate later:

#### General Recommendation
Most of the customers on every cluster based on Sao Paulo. In order to re-engage them to repurchase in our e-commerce, or to attract new customer based on that city, we can give free shipping cost to Sao Paulo customer.

#### Spesific Recommendation
1. Cluster 0 named as "team lunas", because they tend to purchase goods directly with credit card without installments.
They spend $47 on average, with minimum purchase is $0 (they purchase something and pay using voucher or gift card) and maximum purchase $76.
We can make bundling promotions on the items they usually buy, and expect their spending behaviour will improve.

2. Cluster 1 named as "team cc & offline payment".
They spend $176 on average, with minimum purchase is $141 and maximum purchase $226.
This is our second biggest spender in our e-commerce. In order to target this cluster, we have to improve our boleto payment more seamless, because this cluster rely on credit card and boleto.
We can also give specialized discount if people pay the items using boleto.

3. Cluster 2 named as "team buy now pay later".
They spend $274 on average, with minimum purchase is $226 and maximum purchase $344.
This is our highest spender in our e-commerce. In order to target this cluster, we have to give more incentive for people paying with credit card + installments.
We can partner with bank, and give various bank-related discounts. We can also give 0% interest for the installments.

4. Cluster 3 named as "team cc short term".
They spend $106 on average, with minimum purchase is $76 and maximum purchase $141.
This cluster behaviour also pay for items in our e-commerce using credit card, but they tend to use short installments (<6 months).
We can use similar strategy to attract customer from this cluster with strategy from cluster 2. We can give incentive by offering more bank-related discounts, and give 0% interest for the installments.


#### Presentation Deck
[Customer Segmentation Deck](https://github.com/gilangbahana/customer-segmentation/blob/main/e-commerce%20customer%20segmentation.pdf)
