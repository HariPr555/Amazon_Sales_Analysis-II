# Amazon_Sales_Analysis-II
This Power BI report delivers a dynamic analysis of Amazon's sales data, offering fresh insights into customer demographics, product trends, and sales performance across branches. Through interactive visuals, it highlights key patterns in purchasing behavior, top-performing products, and branch-specific dynamics. These insights empower Amazon to craft data-driven strategies that elevate customer experience, fine-tune product portfolios, and maximize revenue growth in an increasingly competitive market.

# Sales Analysis
![Amazon_Sales_Analysis](https://github.com/user-attachments/assets/a064f9b5-a60a-4eda-8109-ab0f28d0dbdf)

# Product Analysis
![Amazon_Product_Analysis](https://github.com/user-attachments/assets/ab611b60-e8d0-407d-8343-f459f69e0120)

# Customer Analysis
![Amazon_Customer_Analysis](https://github.com/user-attachments/assets/71d8637b-561f-4c2b-b017-830029e22c25)

# 1. Background
Amazon is a global e-commerce leader, offering a wide range of products across multiple categories.The company is known for its customer-centric approach, vast product offerings, and innovations like Amazon Prime and Alexa. Its sales data provides insights into customer preferences, product performance, and revenue trends across different regions. Analyzing this data helps businesses optimize strategies for better market targeting and inventory management.

# 2. Project Objectives
The major aim of this project is to gain insight into the sales data of Amazon to understand the different factors that affect sales of the different branches.
- Product Analysis
- Sales Analysis
- Customer Analysis

# 3. Technical Stacks
Data Visualization Tool: Power BI

Data Source: CSV containing Amazon Sales data

# 4. Data Understanding
This dataset contains 1000 sales transactions from three different branches of Amazon, respectively located in Mandalay, Yangon and Naypyitaw.
- Sales  : Invoice ID, Branch, City, Unit price, Quantity, VAT,  Total, Payment  method, Cogs, Gross Margin Percentage and Gross Income
- Product : Product line, unit price
- Customer : Gender, Customer type

# 5. Data Preprocessing

- **Remove Empty Columns and Rows**: Identify and remove any empty columns and rows.
- **Remove Duplicates**: Deduplication of data to avoid redundancy.
- **Rename Columns**: Ensure appropriate names are used for better analysis.
- **Change Data Types**: Ensure columns have appropriate data types (e.g., dates, numbers, text).
- **Handle null values**: Replaced null values with “Not Available”
- **Standardize Values**: Replaced and formatted values to maintain data consistency.

# 6. Data Modelling
- Create Fact and Dimension Tables:
  - Fact Table: Sales
  - Dimension Tables: Date
- Data Formatting
- Generate Hierarchies
- DAX

# 7. DAX
**Calculated Measures**
- Total Revenue = sum('Sales'[Revenue])
- Total Quantity = sum('Sales'[Quantity])
- Total Revenue No filter = CALCULATE(sum('Sales'[Revenue]), ALL('Sales'))
- Product Line Count No filters = CALCULATE(COUNTROWS(SUMMARIZE('Sales', 'Sales'[Product line])), ALL('Sales'))
- Average Line Sales = DIVIDE([Total Revenue No filter], [Product Line Count No filters], 0)
- Line Total Sales = sum('Sales'[Revenue])
- Sales Performance = if([Line Total Sales] > [Average Line Sales], "Good", "Bad")
- Male customers = CALCULATE(COUNT('Sales'[Gender]), 'Sales'[Gender]="Male")
- Female customers = CALCULATE(COUNT('Sales'[Gender]), 'Sales'[Gender]="Female")

# 8. Report Visualization
  # Product Analysis
  - **Total Revenue by Product Line**
      -  Fashion accessories contribute the highest revenue (₹56.14K or 17.38%), followed closely by Health and beauty (₹55.12K or 17.07%). These are clearly the top-performing categories in terms of revenue.

  - **Total Sales by Product Line**
    - Electronic accessories recorded the highest number of sales (971), followed closely by Food and beverages (952). Interestingly, Health and beauty has the lowest sales despite contributing high revenue,           indicating it may have higher-priced items.

  - **Sales Performance Report**
    - All product lines show positive performance except for Health and beauty, which is marked as “Bad,” indicating it may need attention to boost sales.

  - **Average Rating by Product Line**
    - Food and beverages has the highest average rating (7.11), suggesting strong customer satisfaction, while Home and lifestyle has the lowest rating (6.84), indicating potential dissatisfaction.

# Sales Analysis
- **Total Revenue by Branch**
  -  Branch B has generated the most revenue (₹110.57K or 34.24%), while Branches A and C have almost identical shares (around 32.88%). This could indicate a relatively balanced performance across branches.

- **Total Sales by Branch**
  - Branch A has achieved the most sales (1,859), while Branch B has slightly fewer sales (1,820), suggesting similar performance levels, but Branch C is slightly lower (1,831).

- **Total Revenue by Month**
  - January has the highest revenue (₹116K), with a significant dip in February (₹97K), followed by a recovery in March (₹109K). Understanding the causes behind the February dip could help smooth out these           fluctuations.

- **Total Revenue by Time of Day**
  - The afternoon generates the highest revenue (₹173K), while the morning brings in the least (₹62K). This suggests afternoon shoppers are more engaged and likely to make purchases.
 
 # Customer Analysis
  - **Customer Analysis Report**
      -  Food and beverages have the highest total ratings (174), with an average score of 7.11, indicating a relatively high customer satisfaction. Home and lifestyle has the lowest average rating (6.84), which          could suggest room for product improvement or better customer engagement.

  - **Ratings by Branch and Gender**
    - Branch A has received the most ratings overall, particularly from female customers, while Branch B has almost equal engagement from both genders. Branch C has fewer total ratings, but women seem to               contribute more.

  - **Predominant Gender**
    - Female customers play a major role in this dataset, likely driving more sales and engagement.

  - **Most Revenue by Customer Type**
    - Members are a high-value customer segment. Offering loyalty benefits or exclusive deals for members could strengthen this relationship and boost sales.

- **Average of Rating by Month**
    - Ratings were highest in February (7.07) but dropped in March (6.84). This decrease in customer satisfaction should be investigated to understand possible causes.

- **Average of Rating by Time of Day**
    - Afternoon customers give the highest ratings (7.00), while evening ratings are the lowest (6.93). This may indicate that customer experience or service quality drops in the evening.

# 9. Product Strategies
- **Enhance High-Performing Product Lines** : Invest in marketing and expanding the "Food and Beverages" line to further boost its already strong performance.
- **Revitalize Underperforming Lines** : Reevaluate the "Health and Beauty" product line, considering new product introductions, pricing adjustments, or targeted promotions to improve sales.
- **Leverage Product Ratings** : Promote highly-rated products, like those in the "Food and Beverages" line, to attract quality-conscious customers.

# 10. Sales Strategies
- **Capitalize on Peak Sales Periods** : Focus promotions and inventory around afternoons, especially on Saturdays, to maximize revenue.
- **Boost Sales During Low Periods** : Implement targeted campaigns or discounts on Mondays to increase sales during slower periods.
- **Optimize Branch Performance** :  Replicate the successful strategies of Branch A in other branches to improve overall sales.

# 11. Customer Strategies
- **Strengthen Loyalty Programs** : Since members contribute significantly to revenue, enhancing loyalty programs and personalized offers will help retain these valuable customers.
- **Gender-specific Marketing** : Tailor product offerings and marketing campaigns to the gender preferences observed in each branch, ensuring that each customer segment feels catered to.
- **Encourage Feedback** : Foster customer engagement by encouraging feedback during peak times, such as afternoons, to gather valuable insights for continuous improvement.

# 11. Future Scope
- **Predictive Analytics**: Implement models for sales forecasting and churn prediction to anticipate future trends and retain customers effectively.
- **Sentiment Analysis**: Integrate customer reviews to gauge sentiment trends, helping to understand customer satisfaction and product quality.

