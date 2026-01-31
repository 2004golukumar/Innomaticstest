# Food Delivery Data Analysis

## Project Overview
This project involves a comprehensive analysis of food delivery data, integrating information from `orders`, `users`, and `restaurants` datasets. The goal is to derive actionable insights related to customer behavior, restaurant performance, and revenue generation across different cities and membership tiers. The analysis covers various aspects, from identifying top-performing categories to understanding order patterns by membership type and restaurant ratings.

## Data Sources

The following datasets were used in this analysis:
-   `orders.csv`: Contains details about food orders, including `order_id`, `user_id`, `restaurant_id`, `order_date`, `total_amount`, and `restaurant_name`.
-   `users.json`: Contains user information such as `user_id`, `name`, `city`, and `membership` status.
-   `restaurants.sql`: A SQL script containing `CREATE TABLE` and `INSERT` statements to populate a `restaurants` table with `restaurant_id`, `restaurant_name`, `cuisine`, and `rating`.

## Data Preprocessing and Merging

1.  **Data Loading:**
    *   `orders` data was loaded from `orders.csv` into a pandas DataFrame.
    *   `users` data was loaded from `users.json` into a pandas DataFrame.
    *   `restaurants` data was loaded by:
        *   Establishing an in-memory SQLite database connection.
        *   Executing the `restaurants.sql` script to create and populate the `restaurants` table.
        *   Loading the `restaurants` table into a pandas DataFrame.
2.  **Data Merging:**
    *   `orders` DataFrame was merged with the `users` DataFrame on `user_id`.
    *   The resulting DataFrame was then merged with the `restaurants` DataFrame on `restaurant_id`.
    *   The final merged dataset, named `final_food_delivery_dataset.csv`, was saved for subsequent analysis.

## Analysis and Key Findings

The following analytical questions were addressed:

### 1. Total Revenue Generated by 'Gold' Members in Each City
-   **Finding:** Chennai was the city with the highest total revenue from 'Gold' members, with a total revenue of **₹1,080,909.79**.
    -   Pune: ₹1,003,012.32
    -   Bangalore: ₹994,702.59
    -   Hyderabad: ₹896,740.19

### 2. Cuisine with the Highest Average Order Value
-   **Finding:** **Mexican** cuisine has the highest average order value of **₹808.02**.
    -   Mexican: ₹808.02
    -   Italian: ₹799.45
    -   Indian: ₹798.47
    -   Chinese: ₹798.39

### 3. Number of Distinct Users with Total Orders Exceeding ₹1000
-   **Finding:** There are **2544** distinct users whose total orders exceeded ₹1000.

### 4. Total Revenue by Restaurant Rating Range
-   **Finding:** The rating range **4.6-5.0** generated the highest total revenue of **₹2,197,030.75**.
    -   4.6-5.0: ₹2,197,030.75
    -   3.0-3.5: ₹2,136,772.70
    -   4.1-4.5: ₹1,960,326.26
    -   3.6-4.0: ₹1,717,494.41

### 5. City with the Highest Average Order Value for Gold Members
-   **Finding:** **Chennai** has the highest average order value for 'Gold' members, with an average value of **₹808.46**.
    -   Chennai: ₹808.46
    -   Hyderabad: ₹806.42
    -   Bangalore: ₹793.22
    -   Pune: ₹781.16

### 6. Cuisine with Lowest Distinct Restaurants but Significant Revenue
-   **Finding:** **Chinese** cuisine has the lowest number of distinct restaurants (120) but still generates a substantial revenue of **₹1,930,504.65**.
    -   Chinese: 120 restaurants, Revenue: ₹1,930,504.65
    -   Italian: 126 restaurants, Revenue: ₹2,024,203.80
    -   Indian: 126 restaurants, Revenue: ₹1,971,412.58
    -   Mexican: 128 restaurants, Revenue: ₹2,085,503.09

### 7. Percentage of Orders by Gold Members
-   **Finding:** 'Gold' members account for **50%** of the total orders (4987 out of 10000 orders).

### 8. Restaurant with Highest Average Order Value and Less Than 20 Orders
-   **Finding:** **Restaurant_294** has the highest average order value (**₹1040.22**) among restaurants with less than 20 orders (it had 13 orders).

### 9. Membership-Cuisine Combination with Highest Revenue
-   **Finding:** The combination of **Gold + Italian cuisine** generated the highest total revenue of **₹1,005,779.05**.
    -   Gold + Indian cuisine: ₹979,312.31
    -   Gold + Italian cuisine: ₹1,005,779.05
    -   Regular + Indian cuisine: ₹992,100.27
    -   Regular + Chinese cuisine: ₹952,790.91

### 10. Revenue by Quarter
-   **Finding:** **Quarter 3** had the highest total revenue of **₹2,037,385.10**.
    -   Quarter 3: ₹2,037,385.10
    -   Quarter 4: ₹2,018,263.66
    -   Quarter 1: ₹2,010,626.64
    -   Quarter 2: ₹1,945,348.72

### 11. Total Orders by Gold Members
-   **Finding:** Total number of orders placed by 'Gold' members: **4987**.

### 12. Total Revenue in Hyderabad
-   **Finding:** Total revenue generated in Hyderabad: **₹1,889,367.00**.

### 13. Distinct Users Who Placed Orders
-   **Finding:** Number of distinct users who placed at least one order: **2883**.

### 14. Average Order Value for Gold Members
-   **Finding:** The average order value for 'Gold' members was **₹797.15**.

### 15. Orders for Restaurants with High Rating (4.5 or higher)
-   **Finding:** Number of orders placed for restaurants with a rating of 4.5 or higher: **3374**.

### 16. Orders in Top Revenue City for Gold Members
-   **Finding:** Chennai was the city with the highest total revenue from 'Gold' members, and 'Gold' members placed **1337** orders in Chennai.

## Visualizations

Visualizations were generated to illustrate key findings, including:
-   Bar chart of Average Order Value by Cuisine.
-   Bar chart of Total Revenue by Restaurant Rating Range.
-   Bar chart of Total Revenue by Quarter.

## Conclusion and Insights

This analysis provides several key insights into the food delivery platform's operations:

*   **Gold Members are High Value:** 'Gold' members contribute significantly to total revenue, particularly in Chennai and for Italian cuisine. This suggests that loyalty programs are effective, and targeted marketing in top-performing cities for 'Gold' members could yield further growth.
*   **Mexican Cuisine Leads in AOV:** Mexican cuisine stands out with the highest average order value, indicating a premium pricing or higher quantity of items per order. Further investigation into why this cuisine performs well could inform menu strategies.
*   **High-Rated Restaurants Drive Orders:** A large number of orders are placed at restaurants with a rating of 4.5 or higher, emphasizing the importance of restaurant quality and customer satisfaction.
*   **Q3 is Peak Revenue Quarter:** Quarter 3 exhibits the highest revenue, which could be due to seasonal factors, promotional campaigns, or holiday periods. This insight can be used for inventory management and marketing efforts.
*   **Opportunities with Underperforming Restaurants:** 'Restaurant_294' shows a high average order value despite having fewer than 20 orders, suggesting a niche market or high-value offerings that could be scaled up with more visibility or marketing.
*   **Chinese Cuisine Efficiency:** Chinese cuisine generates substantial revenue with the fewest distinct restaurants, indicating high efficiency or strong demand for existing Chinese restaurants.

## Next Steps

*   Deep dive into Gold member behavior in Chennai to replicate strategies in other cities.
*   Explore the factors contributing to the high average order value of Mexican cuisine.
*   Analyze the characteristics of the 2883 distinct users to identify trends and opportunities for engagement.
*   Investigate the specific events or promotions that led to the peak revenue in Quarter 3.
*   Consider strategies to support and promote restaurants like 'Restaurant_294' with high AOV but low order counts.
*   Further analyze the Chinese cuisine market to understand its efficiency and potential for growth in restaurant count.
