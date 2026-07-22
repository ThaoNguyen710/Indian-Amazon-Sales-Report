# Amazon Sales Analytics with SQL

## Project Overview

This project analyzes Amazon sales data using SQL to uncover insights into sales performance, customer purchasing behavior, and operational efficiency. The goal is to transform raw transactional data into actionable business insights that can support data-driven decision-making.

The analysis begins with cleaning the dataset in Python, followed by importing the cleaned data into MySQL for exploratory and advanced SQL analysis. The project demonstrates practical use of SQL features such as Common Table Expressions (CTEs), window functions, aggregate functions, ranking, and conditional aggregation to answer real-world business questions.

## Business Objectives

This project aims to answer questions such as:

Which states generate the highest revenue?
Which product categories contribute the most to sales?
How has revenue changed month over month?
How does Average Order Value (AOV) trend over time?
Which product categories have the highest return rates?
Which products experience the most cancellations before shipment?
Which cities and states generate the highest-value orders?
How much revenue is lost due to cancellations and failed deliveries?

The objective is to identify revenue opportunities, operational inefficiencies, and customer purchasing patterns that can help improve business performance.

## Tools Used
MySQL
SQL window functions
Common Table Expressions
Conditional aggregation

## Key Metrics
### Total Revenue
Total revenue is calculated by summing the amount field.
SUM(amount)

### Average Order Value
Average Order Value measures the average amount spent per order.
AOV = Total Revenue ÷ Number of Distinct Orders
Orders are first aggregated at the order_id level to avoid counting multi-item orders more than once.

### Return Rate
Return rate is calculated as:
Return Rate = Returned Orders ÷ Total Orders × 100

### Seven-Day Rolling AOV
The seven-day rolling AOV averages the daily AOV for the current day and previous six rows, helping reveal spending trends while reducing daily volatility.

## Key Business Insights
### 1. Revenue is concentrated in a small number of states

Maharashtra generated the highest total revenue, contributing nearly ₹13 million in sales. Karnataka ranked second with more than ₹10 million.
The top five states represent the company’s strongest geographic markets and contribute a substantial portion of total revenue.
This concentration means that changes in customer demand, inventory availability, or delivery performance in these states could have a meaningful effect on company-wide sales.

#### Recommendations
Prioritize inventory availability in the highest-revenue states.
Allocate more advertising resources to markets with proven customer demand.
Develop state-level customer retention campaigns.
Analyze customer characteristics in these states and test whether successful strategies can be replicated in lower-performing markets.
Avoid becoming overly dependent on a small number of states by developing promising secondary markets.

### 2. Sets are the leading category across major markets

The Set category generated the most revenue in several of the highest-performing states.
The category’s geographic consistency suggests that demand for Sets is not limited to one local market. It appears to be the company’s flagship category and an important driver of overall revenue.

#### Recommendations
Maintain sufficient inventory for popular Set products.
Use Sets as the centerpiece of promotional campaigns.
Expand the Set product line with additional designs, prices, and bundle options.
Feature high-performing Sets prominently on the homepage and category pages.
Use Set customers for cross-selling related products such as Bottoms, Kurtas, or accessories.

### 3. High-revenue states maintain relatively stable return rates

The highest-revenue states did not show unusually high return rates compared with one another.
This suggests that stronger sales performance is not being achieved at the cost of substantially higher product returns. It may also indicate effective fulfillment, appropriate product quality, or good alignment between customer expectations and delivered products.
However, the return-rate calculation only includes orders with statuses explicitly classified as returned or returning to the seller. Other cancellation or failed-delivery statuses should be analyzed separately.

#### Recommendations
Continue monitoring return rates in the most valuable states.
Examine return reasons rather than relying only on the final order status.
Compare return rates by state, category, product size, and fulfillment method.
Investigate categories with both high revenue and above-average returns.
Preserve successful fulfillment practices used in the leading markets.

### 4. Smaller states generate high AOV but low total revenue

Smaller markets such as Ladakh and Nagaland generated some of the highest Average Order Values even though their total revenue and order volumes were relatively low.
Customers in these regions appear to spend more when they place an order, but the current customer base is small.
The high AOV results should therefore be interpreted carefully. A small number of expensive orders can significantly increase the average in low-volume states.
To reduce this problem, the analysis includes only states with at least ten orders.

#### Recommendations
Maintain access to premium products in high-AOV states.
Test targeted customer-acquisition campaigns before making major inventory investments.
Use low-cost digital campaigns to determine whether the customer base can be expanded.
Monitor order volume alongside AOV.
Consider regional delivery costs and fulfillment capacity before expanding.

### 5. Customer spending weakened in April and increased in May

The seven-day rolling AOV showed a decline during April, indicating that customers were spending less per order during this period.
AOV increased sharply in early May and remained elevated during much of the month. May was therefore the strongest period for customer spending.
During June, rolling AOV remained approximately between ₹653 and ₹668. Spending declined from the May peak but stabilized above much of the April level.
The May increase could be connected to seasonal demand, promotions, larger shopping baskets, or changes in product mix. However, the trend alone does not prove which factor caused the increase.

#### Recommendations
Review promotions, campaigns, and product launches that occurred in May.
Compare category sales shares across April, May, and June.
Identify whether customers bought more items or more expensive products in May.
Repeat successful May campaigns when appropriate.
Develop campaigns to reduce spending declines during weaker periods such as April.

### 6. Saree, Set, and Western Dress generate high-value orders

Saree had the highest average seven-day rolling AOV at approximately ₹933.27. Set followed at approximately ₹877.18, while Western Dress produced an average rolling AOV of approximately ₹792.10.
These categories consistently produced higher-value transactions and are likely important contributors to changes in overall AOV.
Set also combined high AOV with substantial order volume and revenue, making it particularly important to the business.

#### Recommendations
Feature Sarees and Sets in premium marketing campaigns.
Place these categories prominently on the homepage.
Create personalized recommendations based on premium-category browsing.
Test bundles that combine premium products with complementary lower-priced products.
Avoid relying only on high AOV; evaluate revenue, margin, and order volume together.

### 7. Set is the strongest overall product category

Set generated approximately ₹39.2 million in revenue from 44,738 orders while maintaining an AOV of approximately ₹876.26.
This combination of high revenue, high order volume, and high AOV makes Set the strongest overall category in the dataset.
Kurta generated a similar number of orders but had a substantially lower AOV. This indicates that Kurta attracts customer demand but has opportunities for increasing basket value.
Western Dress and Ethnic Dress produced premium purchasing behavior but had lower sales volumes.

#### Recommendations
Protect the Set category from stockouts.
Expand successful Set designs and price points.
Use product bundles and cross-selling to increase Kurta AOV.
Use targeted advertising to expand the customer base for Western Dress and Ethnic Dress.
Compare gross margin across categories before increasing promotional spending.

### 8. Promotions are associated with higher AOV

Across the major product categories, promotional orders had a higher Average Order Value than non-promotional orders.
The largest observed effects included:
Kurta: AOV increased from approximately ₹450.84 to ₹515.75, an increase of about 14.4%.
Bottom: AOV increased from approximately ₹347.40 to ₹401.46, an increase of about 15.6%.
Western Dress showed a smaller difference between promoted and non-promoted orders. This suggests that customers may be relatively willing to purchase Western Dresses without a discount.

#### Recommendations
Focus promotions on categories such as Kurta, Bottom, and Ethnic Dress, where the promotional AOV difference is larger.
Use bundles or minimum-spend promotions to encourage larger orders.
Use premium branding and targeted product discovery for Western Dress instead of frequent broad discounts.
Compare promotional revenue with discount cost and gross margin.
Conduct controlled experiments before concluding that promotions caused the higher AOV.
