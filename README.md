# Pizza Store Sales Analysis – SQL

An end-to-end SQL project analyzing pizza store sales data to derive meaningful business insights. This project uses SQL (PostgreSQL/Oracle-compatible) to answer real-life operational questions, such as best-selling pizzas, revenue contribution, customer behavior, and category trends.

---

## 📌 Project Overview

This SQL project revolves around a database schema designed to manage and analyze sales data for a pizza store. The objective is to extract key business insights that help the store manager make data-driven decisions and optimize store performance.

---

## 🧱 Database Schema

The database consists of **four primary tables**:

### 🔹 `PIZZA_ORDER_DETAIL`
- `order_details_id`: Unique identifier for each entry.
- `order_id`: References `PIZZA_ORDER`.
- `pizza_id`: References `PIZZA_DETAIL`.
- `quantity`: Number of pizzas ordered.

### 🔹 `PIZZA_DETAIL`
- `pizza_id`: Unique ID for each pizza.
- `pizza_type_id`: References `PIZZA_TYPE`.
- `size`: Pizza size (Small, Medium, Large).
- `price`: Price of the pizza.

### 🔹 `PIZZA_ORDER`
- `order_id`: Unique ID for each order.
- `date`: Date of the order.
- `time`: Time of the order.

### 🔹 `PIZZA_TYPE`
- `pizza_type_id`: Unique ID for each type.
- `name`: Pizza name (e.g., Margherita).
- `category`: Vegetarian or Non-Vegetarian.
- `ingredients`: Ingredients used.

---

## 🎯 Why Does the Store Manager Need This?

This SQL analysis empowers the manager to:

- ✅ Analyze sales & revenue trends
- ✅ Identify peak order times and popular pizza sizes
- ✅ Manage inventory based on ingredient demand
- ✅ Discover best- and worst-performing pizzas
- ✅ Design data-backed promotions and offers

---

## 🛠️ Tools Used

- Oracle SQL
- SQL: `JOIN`, `GROUP BY`, `CTE`, `RANK()`, `WINDOW FUNCTIONS`, `AGGREGATES`
- CSV import using `\COPY` command
- GitHub for version control and documentation

---

## 🧾 Key Business Questions & SQL Solutions

| No. | Business Question                                                                 | SQL Technique Used                  |
|-----|------------------------------------------------------------------------------------|-------------------------------------|
| 1   | Total number of orders placed                                                     | `COUNT(DISTINCT)`                   |
| 2   | Total revenue from pizza sales                                                    | `SUM(quantity * price)`             |
| 3   | Highest-priced pizza                                                              | `ORDER BY price DESC LIMIT 1`       |
| 4   | Most common pizza size ordered                                                    | `GROUP BY size`                     |
| 5   | Top 5 most ordered pizza types                                                    | `ORDER BY SUM(quantity) DESC LIMIT` |
| 6   | Total quantity ordered per pizza category                                         | `JOIN + GROUP BY category`          |
| 7   | Distribution of orders by hour                                                    | `DATE_PART('hour', time)`           |
| 8   | Category-wise pizza distribution                                                  | `GROUP BY category`                 |
| 9   | Average pizzas ordered per day                                                    | `CTE + AVG()`                       |
| 10  | Top 3 revenue-generating pizzas                                                   | `SUM + ORDER BY revenue DESC`       |
| 11  | Revenue contribution % by pizza category                                          | `Subquery + CAST + CONCAT`          |
| 12  | Revenue contribution % by pizza type                                              | `GROUP BY name`                     |
| 13  | Cumulative revenue over time                                                      | `SUM() OVER (ORDER BY date)`        |
| 14  | Top 3 most ordered pizza types per category based on revenue                      | `RANK() OVER (PARTITION BY)`        |

---

## 📊 Key Insights

- 🍕 **Medium-sized pizzas** were the most ordered.
- 💰 **Top 3 pizzas** contributed to a **major share of total revenue**.
- ⏰ **Evening hours (6–8 PM)** saw the highest order volume.
- 🏷️ **Cheese and Classic categories** dominated in both count and revenue.
- 📈 Revenue showed **steady growth over time**, indicating healthy sales trends.

---

