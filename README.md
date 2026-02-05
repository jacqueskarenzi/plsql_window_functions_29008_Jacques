# plsql_window_functions_29008_Jacques
# Step 1 & 2: Problem Definition & Success Criteria
- You must define a specific business scenario. Below is a high-scoring framework you can adapt:


- Business Context: A Retail Electronics Chain specializing in regional sales across East Africa.


- Data Challenge: The company struggles to track salesperson performance across different regions and lacks visibility into month-over-month revenue trends and customer loyalty tiers.


- Expected Outcome: Identification of top-performing regions and a clear segmentation of customers for a new loyalty program.

Success Criteria (Required 5 Goals) 


- Top 5 Salespeople per Region: Using $RANK()$.


Cumulative Regional Revenue: Using $SUM() \text{ OVER()}$.


Revenue Growth Rate: Using $LAG()$ or $LEAD()$.


Customer Spending Quartiles: Using $NTILE(4)$.


Quarterly Moving Average: Using $AVG() \text{ OVER()}$.
