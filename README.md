🍕 Pizza Sales Project

📌 Introduction

This project analyzes pizza sales data to uncover trends and insights about customer ordering behavior.
The dataset includes details on orders, order details, pizzas, and pizza types.
Using SQL, I cleaned, joined, and queried the data to generate meaningful business insights.

The main objectives were to:

Identify top-selling pizzas

Calculate total revenue

Highlight key patterns in sales performance

Support better decision-making for inventory management, marketing, and menu planning

⚙️ Tech Stack

SQL (MySQL) – querying and analysis

PowerPoint – presentation of results

GitHub – version control & documentation

📊 Key Queries & Insights

Total Orders Placed

SELECT COUNT(order_id) AS total_orders FROM orders;


Total Revenue Generated

SELECT SUM(od.quantity * p.price) AS total_revenue
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id;


Highest Priced Pizza

SELECT pt.name, p.price
FROM pizza_types pt
JOIN pizzas p ON pt.pizza_type_id = p.pizza_type_id
ORDER BY p.price DESC
LIMIT 1;


Most Ordered Pizza Types (Top 5)

SELECT pt.name AS pizza_type, SUM(od.quantity) AS total_ordered
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id
JOIN pizza_types pt ON p.pizza_type_id = pt.pizza_type_id
GROUP BY pt.name
ORDER BY total_ordered DESC
LIMIT 5;


Top 3 Pizza Types by Revenue

SELECT pt.name, SUM(od.quantity * p.price) AS revenue
FROM pizza_types pt
JOIN pizzas p ON pt.pizza_type_id = p.pizza_type_id
JOIN order_details od ON od.pizza_id = p.pizza_id
GROUP BY pt.name
ORDER BY revenue DESC
LIMIT 3;


(Additional queries: order distribution by hour, pizza category analysis, avg pizzas per day, etc.)

📈 Outcomes

Identified best-selling pizza types and categories

Calculated total revenue and revenue by pizza type

Discovered ordering trends by time and date

Insights can help optimize menu offerings, marketing, and inventory planning

📂 Project Structure
📦 Pizza-Sales-Project
 ┣ 📊 Pizza Sales Project.pptx   # Presentation of results
 ┣ 📄 README.md                  # Project overview
 ┣ 📄 Portfolio.md               # Portfolio summary

🚀 Future Improvements

Build an interactive Power BI / Tableau dashboard

Automate reporting with Python + SQL

Expand dataset with customer demographics for deeper insights

👨‍💻 Author: Munawer Jabeen
📬 Reach me on LinkedIn
 | GitHub https://github.com/Mjabeen164/Pizza-Sales-Project-SQL-
