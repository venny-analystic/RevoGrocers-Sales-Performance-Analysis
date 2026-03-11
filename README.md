# RevoGrocers 
## Sales Performance Analysis

## SECTION 1: PROJECT OVERVIEW
### Summary/Context
This project analyzes sales performance for RevoGrocers, a grocery retail business, to optimize sales strategies and enhance customer experience. Using a Kaggle dataset, the analysis identifies revenue patterns and customer behavior to support data-driven decision-making. The study concludes that growth should shift from customer acquisition to value maximization per customer.

### Goals
The primary objective is to identify product categories driving sales and understand customer purchasing patterns. The project seeks to determine which categories contribute most to revenue, assess price elasticity, and identify high-value customers. Ultimately, it aims to provide actionable insights for inventory prioritization and loyalty program development.

### Process
The analysis was conducted using SQL to query sales transactions, product data, and customer records. Key steps included calculating revenue after discounts, analyzing the correlation between sales volume and net revenue, and determining unique customer reach per category. Additionally, window functions were employed to identify the top user and calculate cumulative lifetime value.

### Output
The Top 5 categories—Confections, Meat, Poultry, Cereals, and Snails—account for 52.88% of total revenue, with Confections alone contributing 12.87%. While customer reach is high (97K–98K per category), the repeat purchase rate varies from 25% to 44%. We recommend implementing a VIP loyalty program and optimizing Grain category pricing to increase volume and conversion of one-time buyers.

## SECTION 2: SCOPE OF WORK / ACHIEVEMENTS (AQS FRAMEWORK)
- Analyzed revenue across 11 product categories, identifying Confections as the top driver generating approximately $556.93 million net revenue.
- Identified that the Top 5 categories collectively account for 52.88% of the company's total net revenue.
- Determined that 55%–75% of customers are one-time buyers, highlighting a major opportunity for retention-focused marketing.
- Isolated Customer ID 94800 as the top-value user to model purchasing patterns for a new VIP loyalty program.

## SECTION 3: TOOLS & METHODS
### A. Tools
- SQL (PostgreSQL / BigQuery)
- Data Aggregation
- Business Analytics
- Root Cause Analysis (5 Whys)

### B. Methods
- Data Aggregation (SUM, COUNT, AVG)
- Table Joining (JOIN, LEFT JOIN)
- Window Functions (SUM OVER, PARTITION BY)
- Correlation Analysis (Revenue vs. Volume, Price vs. Reach)
- Pareto (80/20) Principle Application
- Cohort/Loyalty Analysis (Repeat Purchase Rate calculation)

### Dataset Source:  
https://console.cloud.google.com/bigquery?pli=1&project=fsda-sql-01&ws=!1m0

## SECTION 4: VISUAL SUGGESTIONS
- Category Revenue Contribution Pie Chart: A visual representing the 12.87% contribution of Confections and the 52.88% share of the Top 5 categories.
- Revenue vs. Units Sold Scatter Plot: To illustrate the strong positive correlation between net revenue and sales volume across categories.
- Customer Reach vs. Repeat Purchase Bar Chart: A comparison showing uniform customer reach (97K-98K) against the varying repeat purchase rates (25%-44%)
- Top User Cumulative Revenue Line Graph: A visualization of Customer ID 94800’s spending velocity and lifetime value milestones over time.
- Average Price vs. Revenue Matrix: A chart plotting categories like Grain (high price, low repeat) versus Confections (moderate price, high volume).

## Key SQL Queries
### Revenue by Product Category
```sql
SELECT category,
       SUM(revenue) AS total_revenue
FROM sales
GROUP BY category
ORDER BY total_revenue DESC;
```
This query identifies the highest revenue-generating product categories.

### Custumers Purchase Frequency
SELECT customer_id,
       COUNT(order_id) AS purchase_frequency
FROM orders
GROUP BY customer_id
ORDER BY purchase_frequency DESC;
This query identifies high-value customers based on purchase frequency.

### Average Order Value
SELECT AVG(order_amount) AS average_order_value
FROM orders;
Used to measure customer spending behavior.

## Analytical Approach
The analysis was conducted using SQL queries to extract key business insights from sales and transaction data.
The approach included:
- Aggregation functions (SUM, AVG, COUNT)
- Grouping data using GROUP BY
- Identifying top-performing categories
- Evaluating customer purchasing behavior
- Investigating operational inefficiencies using root cause analysis 

## Key Insights
- Sales performance is influenced by product category and customer purchasing behavior.
- Certain products contribute significantly to total revenue.
- Customer transaction patterns indicate opportunities for targeted promotions.

## Business Impact
The analysis helps RevoGrocers understand:
- Which product categories drive the most revenue
- Customer purchasing patterns
- Potential pricing sensitivity
- Operational inefficiencies causing product damage
These insights support better decision-making in pricing strategy, inventory management, and logistics optimization.

## Business Recommendations
- Focus inventory and marketing efforts on the top five revenue-driving categories, particularly Confections, which generates the highest net revenue.
- Implement a loyalty program targeting high-value customers to increase repeat purchases and lifetime value.
- Optimize pricing strategies for underperforming categories such as Grain products to stimulate demand and improve sales volume.
- Develop targeted promotions for one-time buyers to convert them into repeat customers and increase customer retention.

## Project Files
- RevoGrocers_Sales_Analysis.pdf : Project presentation
- RevoGrocers_Sales_Dataset.csv : Dataset used for analysis

## Author
Venny Amilia Deslaweny
