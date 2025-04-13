# TASK3-DA-INTERN
# 🧠 Task 3: SQL for Data Analysis – Chinook Database

### 🎯 Objective
To analyze structured data using SQL queries, including joins, aggregations, subqueries, and views using the Chinook eCommerce music database.

---

## 🗂 Dataset Used
- **Database**: Chinook SQLite Database
- **Source**: [GitHub - Chinook Database](https://github.com/lerocha/chinook-database)
- **File Used**: `Chinook_Sqlite.sqlite`
- **Tables Included**: `Customer`, `Invoice`, `InvoiceLine`, `Track`, `Genre`, `Employee`, etc.

---

## 🛠 Tools & Tech Stack
- Google Colab (Python + SQLite3)
- SQLite3
- Pandas (for reading query output)

---

## 📊 SQL Queries Executed

### ✅ 1. Top 5 Customers by Total Purchase
```sql
SELECT C.FirstName || ' ' || C.LastName AS Customer,
       SUM(I.Total) AS TotalSpent
FROM Customer C
JOIN Invoice I ON C.CustomerId = I.CustomerId
GROUP BY Customer
ORDER BY TotalSpent DESC
LIMIT 5;
