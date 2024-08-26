# Introduction to SQL

SQL (Structured Query Language) is a standard programming language used to manage and manipulate relational databases. It is widely used for querying, updating, and managing data.

## Key SQL Concepts

### 1. **Databases and Tables**

A **database** is a collection of data organized in a structured format. Within a database, data is stored in **tables**. A table is made up of rows and columns, where each row represents a unique record, and each column represents a field in that record.

### 2. **SQL Statements**

SQL provides a variety of statements to interact with data. The most common SQL statements are:

- **SELECT**: Retrieves data from a database.
- **INSERT**: Adds new data into a database.
- **UPDATE**: Modifies existing data.
- **DELETE**: Removes data from a database.
- **CREATE TABLE**: Creates a new table.
- **DROP TABLE**: Deletes an existing table.

## Basic SQL Syntax

### 1. **Creating a Table**

To create a new table in a database, use the `CREATE TABLE` statement:

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Age INT,
    Department VARCHAR(50)
);
```
INSERT: Adds new records to a table.


```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);

INSERT INTO customers (name, email) VALUES ('John Doe', 'john@example.com');
UPDATE: Modifies existing records in a table.

```

```sql
UPDATE table_name SET column1 = value1 WHERE condition;

UPDATE products SET price = 19.99 WHERE id = 1001;
DELETE: Removes records from a table.

```

```sql

DELETE FROM table_name WHERE condition;

DELETE FROM orders WHERE order_date < '2023-01-01';
Intermediate SQL Concepts
JOINs: Combines rows from two or more tables based on a related column.

```

```sql
SELECT * FROM table1
INNER JOIN table2 ON table1.column = table2.column;

SELECT orders.order_id, customers.name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.id;
Aggregate Functions: Perform calculations on a set of values and return a single result.

```
```sql

SELECT AVG(column_name) FROM table_name;

SELECT COUNT(*) AS total_employees, AVG(salary) AS average_salary
FROM employees;
GROUP BY: Groups rows that have the same values in specified columns.
```

```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1;
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department;
Advanced SQL Techniques
Subqueries: A query nested inside another query.
```

```sql
SELECT column_name FROM table_name
WHERE column_name IN (SELECT column_name FROM another_table);
SELECT product_name
FROM products
WHERE category_id IN (SELECT id FROM categories WHERE name = 'Electronics');
Window Functions: Perform calculations across a set of rows that are related to the current row.
```

```sql
SELECT column1, column2,
       AVG(column2) OVER (PARTITION BY column1) AS avg_value
FROM table_name;
SELECT employee_name, department, salary,
       AVG(salary) OVER (PARTITION BY department) AS dept_avg_salary
FROM employees;
Common Table Expressions (CTEs): Temporary named result set created within a SELECT statement.
```

```sql
WITH cte_name AS (
    SELECT column1, column2 FROM table_name WHERE condition
)
SELECT * FROM cte_name;

WITH high_value_orders AS (
    SELECT * FROM orders WHERE total_amount > 1000
)
SELECT customer_id, AVG(total_amount) AS avg_order_value
FROM high_value_orders
GROUP BY customer_id;
```

Best Practices
Use meaningful table and column names: Choose clear, descriptive names for better readability.
Optimize queries: Use indexes on frequently queried columns and avoid selecting unnecessary data.
Use parameterized queries: Prevent SQL injection attacks by using prepared statements.
Regular backups: Implement a robust backup strategy to prevent data loss.
Normalize your database: Design your schema to minimize data redundancy and improve data integrity.
Use transactions: Ensure data consistency when performing multiple related operations.
Document your database: Maintain up-to-date documentation of your schema and important queries.
Regular maintenance: Perform routine tasks like updating statistics and rebuilding indexes.
By mastering these SQL concepts and following best practices, you'll be well-equipped to work with databases effectively and efficiently.