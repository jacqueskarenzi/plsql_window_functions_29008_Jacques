# plsql_window_functions_29008_Jacques
# Step 1 & 2: Problem Definition & Success Criteria

- Business Context: A Retail Electronics Chain specializing in regional sales across East Africa.


- Data Challenge: The company struggles to track salesperson performance across different regions and lacks visibility into month-over-month revenue trends and customer loyalty tiers.


- Expected Outcome: Identification of top-performing regions and a clear segmentation of customers for a new loyalty program.

Success Criteria (Required 5 Goals) 


- Top 5 Salespeople per Region: Using $RANK()$.


Cumulative Regional Revenue: Using $SUM() \text{ OVER()}$.


Revenue Growth Rate: Using $LAG()$ or $LEAD()$.


Customer Spending Quartiles: Using $NTILE(4)$.


Quarterly Moving Average: Using $AVG() \text{ OVER()}$.

# Step 3: Database Schema Design

● Customers Table: customer_id (PK), customer_name, region.

● Products Table: product_id (PK), product_name, category, price.

● Transactions Table: transaction_id (PK), customer_id (FK), product_id (FK), amount,
transaction_date.
# ER diagram
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/db4fd9f2-17d3-4514-ae4c-f09163af95f9" />

# Step 4: Part A - SQL JOINS Implementation

# JOIN Type Purpose
- INNER JOIN Retrieve successful transactions with full customer and product details.

- LEFT JOIN Find "Ghost Customers" those registered who haven't bought anything.

- RIGHT JOIN Identify products in the inventory that have zero sales records.

- FULL OUTER JOIN Create a complete master list of all entities, highlighting gaps in data.

- SELF JOIN Compare a customer's current purchase against their previous one.

# Step 5: Part B - Window Functions Implementation

1. Ranking: Use $DENSE\_RANK()$ to find the top products by revenue.
![rank](https://github.com/user-attachments/assets/b0bba09a-7158-4c92-8bb2-79a41372c7f9)

2. Aggregate: Use $SUM() \text{ OVER(ORDER BY date ROWS BETWEEN 2
PRECEDING AND CURRENT ROW)}$ for a 3-day rolling total.
![navigation](https://github.com/user-attachments/assets/e44704d1-8d84-49e3-bd81-c5239757318c)

3. Navigation: Use $LAG()$ to compare this month's sales to last month's.
![navigation](https://github.com/user-attachments/assets/e44704d1-8d84-49e3-bd81-c5239757318c)

4. Distribution: Use $CUME\_DIST()$ to find the percentile ranking of customer
spending.
![distribution](https://github.com/user-attachments/assets/682a7841-f055-4b13-b76f-9f61baa2d0c6)

# REFERENCES
- https://www.postgresql.org/docs/current/tutorial-window.html
- https://www.postgresql.org/docs/current/tutorial.html
- https://www.postgresql.org/docs/current/queries-table-expressions.html
- https://www.pgtutorial.com/postgresql-window-functions/
# “All sources were properly cited. Implementations and analysis represent original work. No AIgenerated content was copied without attribution or adaptation.”

  
  
