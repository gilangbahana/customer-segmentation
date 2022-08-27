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
4. Create additional columns (variables) to be used for analysis later (Total Revenue,Months Since Last Arrival, Percent Canceled)
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
    - no debt-debt club for payment made without or using 1 month installments
    - pinjol friendly for payment made using 2 to 6 months installments
    - medium term for payment made using 7 to 12 months installments, and
    - long commitment for payment made using more than 12 months installments
2. Column `customer state` and `payment type` is converted to numeric using one hot encoding.
3. Optimal number of cluster is 4, based on elbow method metric.
![alt text](https://github.com/gilangbahana/customer-segmentation/blob/main/cust-segmentation-elbow-method.png)


#### Customer Segmentation Result
