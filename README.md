# E-Commerce Sales Data Analysis (SQL Project)

## Project Overview
Yeh project e-commerce sales data par SQL queries run karke business insights nikalne ke liye banaya gaya hai. Isme customer behavior, product category performance, aur monthly revenue trends ko analyze kiya gaya hai.

## Database & Tools Used
* **Platform:** SQLite Online (sqliteonline.com)
* **Language:** SQL (DDL, DML, Joins, Aggregations)

## Key Queries & Analysis

### 1. Total Revenue by Category
Yeh query batati hai ke kis product category se sab se zyada revenue generate hua hai.
```sql
SELECT category, SUM(amount) AS total_revenue
FROM orders
GROUP BY category
ORDER BY total_revenue DESC;
```
### 2. Top Spending Customers
Yeh query hamare sab se loyal aur valuable customers ko unki total spending ke mutabiq identify karti hai.
```sql
SELECT c.customer_name, c.city, SUM(o.amount) AS total_spent
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id
ORDER BY total_spent DESC;
```
### 3. Monthly Sales Trend
Yeh query har mahine ke total orders aur total revenue ko track karti hai.
```sql                                                                                                                               SELECT strftime('%Y-%m', order_date) AS month, 
       COUNT(order_id) AS total_orders, 
       SUM(amount) AS monthly_revenue
FROM orders
GROUP BY month;
```
## Key Insights
* **Electronics** is the highest revenue-generating product category in the store.
* **Ali Khan** has been identified as the top-spending customer, showing the highest customer value.
* Monthly sales tracking helps monitor overall business growth and revenue trends consistently.
