# Data-Analysis-Power-BI-Project
This project involved building an interactive Power BI dashboard to analyze 27K+ BigBasket products by ratings and pricing. Added calculated fields like discount % and rating buckets to uncover insights on product value. The dashboard includes KPIs and visual comparisons to support decisions in marketing, pricing, and inventory.

# BigBasket Product Performance Analysis
## 1. Problem Statement
As a data analyst for a retail store aggregator working for BigBasket, our goal is to analyze   product performance analysis to understand which brands and product categories perform best based on customer ratings and pricing. This analysis helps BigBasket identify top-performing products and brands based on ratings and pricing, enabling smarter promotions, better inventory decisions, and improved customer satisfaction by promoting highly rated, value-for-money products and optimizing low-performing ones. This can boost customer trust, increase repeat purchases, and drive overall sales growth.

## 2. Data Preprocessing Steps
•	Removed trailing spaces from text columns
•	Added Discount % column to analyze price reductions across products.
•	Created Rating Bucket to categorize customer ratings into performance levels.
•	Handled missing values and removed infinite values in discount calculations.
•	 Standardized data types to ensure smooth Power BI compatibility.
•	Prepared dataset for visual KPIs, filters, and drilldown analysis in Power BI.

## 3. Power BI Report Pages
•	KPI Cards: Total Products, Avg Price, Avg Rating, Avg Discount
•	Area chart :  Sum of market price  and Sum of sales by Sub category
•	Line and Stacked column chart : Sum of price by brand and category
•	Dochart : Sum of rating by category
•	Stacked Bar Chart: Sum of rating by category
•	Donut chart: Sum of market price by category

## 4. DAX Measures Used
•	Measure Name	DAX Formula
•	Total Products	Total Products = COUNTROWS(Table1)
•	Average Sale Price	Avg sale price = AVERAGE(Table1[sale_price])
•	Average Product Rating	Avg Product Rating = AVERAGE(Table1[rating])
•	Average Discount %	Avg Discount % = AVERAGE(Table1[Discount %])
•	Total Price	SUMX(Hotels, Hotels[Price] + Hotels[Tax])
•	Discount %	Discount % = 
IF(
    [market_price] > 0, 
    ([market_price] - [sale_price]) / [market_price], 
    BLANK()
)
🔹 Rating Bucket
DAX
CopyEdit
Rating Bucket = 
SWITCH(
    TRUE(),
    [rating] >= 4.5, " Excellent (4.5+)",
    [rating] >= 4.0, " Good (4.0 - 4.5)",
    [rating] >= 3.0, " Average (3.0 - 4.0)",
    [rating] > 0,    " Poor (<3.0)",
    TRUE,            " No Rating"
)

## 5. Report Insights 
•	Q1: Which product category has the highest average rating??
•	Q2: Which  category has the highest discount percentage?
•	Q3: What percentage of products are rated Excellent (4.5+)?
•	Q4: Are higher-rated products usually more expensive?
•	Q5: Which subcategory offers the best value (high rating + low discount need)?
•	Q6: Are there categories where high discounts still get low ratings?•	Q7: Which brands offer maximum discounts but low ratings?
•	Q7: Which brands offer maximum discounts but low ratings?
•	Q8: What’s the distribution of products across rating buckets?

## 6. Dashboard

<a href = "https://github.com/richabhagat09/Data-Analysis-Power-BI-Project-/commit/7b248104fcf5742fd9ddacc3a0d80a8fc66da88b"> View dashboard </a>
