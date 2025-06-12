# Taks7

# 📊 Basic Sales Summary using SQLite and Python

## 📝 Objective
To create a simple sales database using SQLite, run SQL queries through Python, and visualize basic sales metrics like **total quantity sold** and **total revenue** using `matplotlib`.

---

## 🧰 Tools Used

- **Python** (Standard Library)
  - `sqlite3` – for interacting with SQLite databases
  - `pandas` – for loading and working with query results
  - `matplotlib.pyplot` – for plotting bar charts
- **SQLite** – lightweight, serverless SQL engine (built-in with Python)
- **Jupyter Notebook** or `.py` file

---

## 🗃️ Dataset

A small in-memory dataset was used and inserted into a table named `sales`:

| product | quantity | price |
|---------|----------|-------|
| Apple   | 10       | 1.5   |
| Banana  | 5        | 0.8   |
| Orange  | 8        | 1.2   |
| Apple   | 7        | 1.5   |
| Banana  | 12       | 0.8   |
| Orange  | 3        | 1.2   |

---

## 📦 What the Script Does

1. **Creates SQLite database** (`sales_data.db`) and a `sales` table.
2. **Inserts sample data** into the table.
3. **Runs a SQL query** to get:
   - Total quantity sold per product
   - Total revenue per product
4. **Loads results** into a pandas DataFrame.
5. **Prints a summary table**.
6. **Plots a bar chart** of revenue per product.

---

## 🔍 SQL Query Used

```sql
SELECT product, 
       SUM(quantity) AS total_qty, 
       SUM(quantity * price) AS revenue
FROM sales 
GROUP BY product;
