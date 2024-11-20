<h2 align="center">POSTGRESQL</h2>
**<p align="center">learning URLs: <a href=""></a></p>**

---

## Comprehensive PostgreSQL Tutorial

This guide provides a full overview of the fundamental concepts you need to understand before diving into the `SELECT` statement in PostgreSQL.

### 1. Introduction to SQL and Relational Databases

**SQL (Structured Query Language)** is used to communicate with relational databases, where data is stored in tables with rows and columns. PostgreSQL is an open-source relational database system known for its robustness and advanced features.

### Key Concepts:

- **Tables**: Data is stored in structured tables.
- **Rows and Columns**: Each row represents a record, and columns represent the attributes of the data.
- **Relations**: Tables can be related to each other through keys.

### 2. Database Structure

#### Components of a Database:

- **Tables**: Store data in rows and columns.
- **Primary Key**: Uniquely identifies each record in a table.
- **Foreign Key**: Defines relationships between tables.
- **Indexes**: Used to speed up queries.

#### SQL for Table Creation:

```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50)
);
```

### 3. Basic SQL Commands

#### SELECT:

Used to retrieve data from a database.

```sql
SELECT * FROM employees;
```

#### INSERT:

Adds new data to a table.

```sql
INSERT INTO employees (name, department) VALUES ('John Doe', 'IT');
```

#### UPDATE:

Modifies existing data.

```sql
UPDATE employees SET department = 'HR' WHERE id = 1;
```

#### DELETE:

Removes data from a table.

```sql
DELETE FROM employees WHERE id = 1;
```

### 4. Data Types in PostgreSQL

PostgreSQL supports various data types. Some of the most common ones include:

- **INTEGER**: For whole numbers.
- **VARCHAR**: For variable-length strings.
- **TEXT**: For longer strings.
- **DATE**: For storing dates.
- **BOOLEAN**: For true/false values.
- **ARRAY**: For storing arrays of values.

### 5. Advanced Database Concepts

#### Indexes:

Indexes improve the performance of queries by allowing the database to find rows faster.

```sql
CREATE INDEX idx_employee_name ON employees(name);
```

#### JOIN:

Used to combine data from two or more tables.

```sql
SELECT e.name, d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.id;
```

### 6. Transactions and ACID Properties

A **transaction** is a sequence of operations that are executed as a single unit of work.

#### ACID Properties:

- **Atomicity**: Ensures that all operations within a transaction are completed.
- **Consistency**: Ensures the database remains consistent before and after a transaction.
- **Isolation**: Ensures that transactions do not interfere with each other.
- **Durability**: Ensures that once a transaction is committed, it remains so even in case of a crash.

```sql
BEGIN;
    UPDATE employees SET department = 'HR' WHERE id = 2;
COMMIT;
```

### 7. Working with PostgreSQL Tools

#### psql:

The command-line tool for interacting with PostgreSQL.

- **Basic commands**:
  - `\l`: List all databases.
  - `\dt`: List all tables in the current database.
  - `\q`: Quit `psql`.

#### pgAdmin:

A graphical user interface for managing PostgreSQL databases. Suitable for users who prefer visual tools over command-line interactions.

### 8. DDL and DML Commands

#### Data Definition Language (DDL):

- **CREATE**: To create new tables, databases, indexes.
- **ALTER**: To modify existing tables.
- **DROP**: To delete tables or databases.

#### Data Manipulation Language (DML):

- **SELECT**: To query data.
- **INSERT**: To add new data.
- **UPDATE**: To modify data.
- **DELETE**: To remove data.

### 9. User Management and Permissions

PostgreSQL allows you to manage users and their access to the database objects.

#### Create User:

```sql
CREATE USER new_user WITH PASSWORD 'password';
```

#### Grant Privileges:

```sql
GRANT SELECT ON employees TO new_user;
```

#### Revoke Privileges:

```sql
REVOKE ALL ON employees FROM new_user;
```

### 10. Backup and Restore

It's crucial to understand how to back up and restore databases.

#### Backup:

```bash
pg_dump mydatabase > mydatabase_backup.sql
```

#### Restore:

```bash
psql mydatabase < mydatabase_backup.sql
```

By mastering these topics, you'll be well-prepared to dive into advanced PostgreSQL queries and efficiently manage your databases.

---

## PostgreSQL SELECT Statement

The `SELECT` statement in PostgreSQL is one of the most important and frequently used commands for retrieving data from tables. It provides numerous options for filtering, sorting, grouping, and limiting data. Below is a comprehensive guide to all the possible variations of the `SELECT` statement in PostgreSQL.

### 1. Basic SELECT Syntax

```sql
SELECT column1, column2 FROM table_name;
```

This simple command retrieves the specified columns from a table.

### 2. SELECT ALL

```sql
SELECT * FROM table_name;
```

Retrieves all columns from all rows in the table.

### 3. Filtering with WHERE

```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

Use the `WHERE` clause to filter records based on specific conditions.

```sql
SELECT name, age FROM employees WHERE age > 30;
```

### 4. Ordering Results with ORDER BY

```sql
SELECT column1, column2 FROM table_name ORDER BY column_name [ASC|DESC];
```

Sorts the result set based on one or more columns.

```sql
SELECT name, salary FROM employees ORDER BY salary DESC;
```

### 5. Limiting the Number of Rows with LIMIT

```sql
SELECT column1, column2 FROM table_name LIMIT number;
```

Limits the number of results returned by the query.

```sql
SELECT * FROM employees LIMIT 5;
```

### 6. OFFSET for Skipping Rows

```sql
SELECT column1, column2 FROM table_name LIMIT number OFFSET number;
```

The `OFFSET` keyword specifies how many rows to skip before starting to return rows.

```sql
SELECT * FROM employees LIMIT 5 OFFSET 10;
```

### 7. Using DISTINCT to Eliminate Duplicates

```sql
SELECT DISTINCT column1 FROM table_name;
```

Removes duplicate values from the result set.

```sql
SELECT DISTINCT department FROM employees;
```

### 8. Joining Tables with JOIN

#### a. INNER JOIN

```sql
SELECT column1, column2 FROM table1 INNER JOIN table2 ON table1.column = table2.column;
```

Returns rows that have matching values in both tables.

```sql
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments ON employees.department_id = departments.id;
```

#### b. LEFT JOIN

```sql
SELECT column1, column2 FROM table1 LEFT JOIN table2 ON table1.column = table2.column;
```

Returns all rows from the left table, even if there is no match in the right table.

#### c. RIGHT JOIN

```sql
SELECT column1, column2 FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;
```

Returns all rows from the right table, even if there is no match in the left table.

### 9. Using GROUP BY for Aggregations

```sql
SELECT column1, COUNT(*), AVG(column2) FROM table_name GROUP BY column1;
```

Groups the data by one or more columns and performs aggregate functions like `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`.

```sql
SELECT department, AVG(salary) FROM employees GROUP BY department;
```

### 10. Filtering Groups with HAVING

```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1 HAVING COUNT(*) > 1;
```

The `HAVING` clause filters groups created by the `GROUP BY` clause.

```sql
SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 5;
```

### 11. Using Subqueries

#### a. Subqueries in SELECT

```sql
SELECT column1, (SELECT AVG(salary) FROM employees) FROM table_name;
```

#### b. Subqueries in WHERE

```sql
SELECT name FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
```

### 12. Using UNION to Combine Results

```sql
SELECT column1 FROM table1 UNION SELECT column1 FROM table2;
```

The `UNION` operator combines the results of two or more queries and removes duplicates.

- **UNION ALL**: Includes duplicate values as well.

### 13. Window Functions

Window functions perform calculations across a set of table rows related to the current row without changing the result set.

```sql
SELECT name, salary, RANK() OVER (ORDER BY salary DESC) FROM employees;
```

### 14. CTE (Common Table Expressions) with WITH Clause

```sql
WITH employee_salaries AS (
    SELECT name, salary FROM employees WHERE department = 'HR'
)
SELECT * FROM employee_salaries;
```

The `WITH` clause allows you to write reusable subqueries.

### 15. CASE Statement for Conditional Logic

```sql
SELECT name,
       CASE
           WHEN salary > 50000 THEN 'High'
           WHEN salary > 30000 THEN 'Medium'
           ELSE 'Low'
       END as salary_grade
FROM employees;
```

The `CASE` statement returns values conditionally based on the logic you define.

### 16. SELECT INTO to Create New Tables

```sql
SELECT column1, column2 INTO new_table FROM table_name;
```

This command copies data into a new table.

```sql
SELECT * INTO employees_backup FROM employees;
```

### 17. Using EXISTS to Check for Row Existence

```sql
SELECT column1 FROM table_name WHERE EXISTS (SELECT 1 FROM other_table WHERE condition);
```

The `EXISTS` clause checks whether a subquery returns any rows.

```sql
SELECT name FROM employees WHERE EXISTS (SELECT 1 FROM departments WHERE id = employees.department_id);
```

### 18. ARRAY and JSON Functions

PostgreSQL supports complex data types like arrays and JSON.

```sql
SELECT name FROM employees WHERE hobbies @> ARRAY['sports', 'music'];
```

For JSON data:

```sql
SELECT json_data->>'name' FROM json_table WHERE json_data->>'status' = 'active';
```

### 19. COALESCE for Handling NULL Values

```sql
SELECT name, COALESCE(phone, 'No Phone') FROM employees;
```

`COALESCE` returns the first non-NULL value in the list.

These examples cover all the possible variations of the `SELECT` statement in PostgreSQL. By mastering these, you can execute even the most complex queries and retrieve data efficiently from your database.

---

## PostgreSQL Column Aliases

In PostgreSQL, **column aliases** allow you to assign a temporary name to columns in the result set of a query. Aliases improve readability, especially when working with complex expressions, functions, or when the original column names are lengthy.

### 1. Basic Syntax of Column Aliases

The `AS` keyword is used to assign an alias to a column. Using `AS` is optional, and you can simply write the alias after the column or expression.

### Syntax:

```sql
SELECT column_name AS alias_name FROM table_name;
```

OR without using `AS`:

```sql
SELECT column_name alias_name FROM table_name;
```

### 2. Basic Examples

Here are some basic examples of using column aliases in PostgreSQL.

#### Example 1: Renaming a Column

Suppose you have a table `employees` with columns `first_name` and `last_name`, and you want to rename `first_name` to `Name` in the result:

```sql
SELECT first_name AS Name, last_name FROM employees;
```

Result:

```
 Name  | last_name
-------|-----------
 John  | Doe
 Jane  | Smith
```

#### Example 2: Using Calculations

You can also apply aliases to calculated expressions. For example, if you have a table `orders` and want to display the total of `quantity` and `price` as `total`:

```sql
SELECT quantity * price AS total FROM orders;
```

### 3. Aliasing Functions and Expressions

You can assign aliases not only to base columns but also to functions and calculated expressions.

#### Example 3: Using Functions with Aliases

In this example, the `CONCAT` function concatenates `first_name` and `last_name`, and we assign an alias `full_name` to the result:

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;
```

Result:

```
 full_name
-----------
 John Doe
 Jane Smith
```

### 4. Special Considerations for Alias Names

- **Using Quotation Marks**: If your alias contains spaces or special characters, you must use **double quotes** (`"`).
- **Without Quotes**: For simple names, quotes are not required.

#### Example 4: Using Quotation Marks for Alias Names

If you want an alias like `Total Price`, you need to use double quotes:

```sql
SELECT price * quantity AS "Total Price" FROM orders;
```

Result:

```
 Total Price
------------
  100.00
  250.00
```

### 5. Aliases in Join Queries

When working with join queries or complex table structures, aliases help make the output more understandable by renaming columns.

#### Example 5: Using Column Aliases in a Join Query

Suppose you have two tables `employees` and `departments`. You want to display the employee's name along with their department name, and assign aliases for clarity:

```sql
SELECT e.first_name AS EmployeeName, d.department_name AS Department FROM employees e JOIN departments d ON e.department_id = d.department_id;
```

Result:

```
 EmployeeName | Department
--------------|------------
 John         | IT
 Jane         | Sales
```

### 6. Combining Aliases with Subqueries

Aliases can be particularly useful in subqueries to simplify the handling of derived data.

#### Example 6: Using Aliases in a Subquery

Suppose you are calculating the total price for an order in a subquery and want to give it a clear alias:

```sql
SELECT order_id, (SELECT SUM(price) FROM order_items WHERE order_items.order_id = orders.order_id) AS total_price
FROM orders;
```

### 7. Final Tips

- **No Duplicate Aliases**: Each alias in a query must be unique. Avoid reusing alias names.
- **Case Sensitivity**: Aliases are case-insensitive unless enclosed in double quotes. If enclosed in quotes, they are case-sensitive. PostgreSQL converts unquoted alias names to lowercase by default.

---

## PostgreSQL ORDER BY

The `ORDER BY` clause in PostgreSQL is used to sort the results of a query based on one or more columns. It allows you to sort the results in ascending or descending order. Additionally, `ORDER BY` supports features like sorting by multiple columns, handling `NULL` values, and more.
In this guide, we'll cover all possible use cases of the `ORDER BY` clause.

### 1. Simple Sorting by One Column

To sort results by a specific column, use the `ORDER BY` clause as follows:

```sql
SELECT *
FROM table_name
ORDER BY column_name;
```

By default, the results are sorted in **ascending** order.

Example:

```sql
SELECT *
FROM employees
ORDER BY salary;
```

Here, the results will be sorted by the `salary` column in ascending order.

### 2. Sorting in Descending Order

If you want the results in **descending** order, use the `DESC` keyword:

```sql
SELECT *
FROM table_name
ORDER BY column_name DESC;
```

Example:

```sql
SELECT *
FROM employees
ORDER BY salary DESC;
```

This query will sort the results by the `salary` column in descending order.

### 3. Sorting by Multiple Columns

You can sort the results by more than one column. In this case, the first column has higher precedence, and the subsequent columns will be used to sort in case of ties in the first column:

```sql
SELECT *
FROM table_name
ORDER BY column1, column2;
```

Example:

```sql
SELECT *
FROM employees
ORDER BY department, salary DESC;
```

In this example, the results are first sorted by `department` in ascending order, and within each department, they are sorted by `salary` in descending order.

### 4. Mixing `ASC` and `DESC`

You can combine ascending and descending order for different columns:

```sql
SELECT *
FROM employees
ORDER BY department ASC, salary DESC;
```

Here, the `department` column is sorted in ascending order, and the `salary` column is sorted in descending order.

### 5. Sorting Based on Calculations and Functions

You can sort the results based on expressions or functions. For example, sorting by the sum of two columns:

```sql
SELECT id, salary, bonus
FROM employees
ORDER BY (salary + bonus) DESC;
```

In this example, the results are sorted by the sum of `salary` and `bonus` in descending order.

### 6. Sorting with `NULL` Values

By default, in PostgreSQL, `NULL` values appear last in ascending order and first in descending order. However, you can modify this behavior using the following keywords:

- `NULLS FIRST`: Puts `NULL` values at the beginning.
- `NULLS LAST`: Puts `NULL` values at the end.
  Example:

```sql
SELECT *
FROM employees
ORDER BY salary ASC NULLS FIRST;
```

This query sorts the results in ascending order and places the `NULL` values at the beginning.

Or:

```sql
SELECT *
FROM employees
ORDER BY salary DESC NULLS LAST;
```

Here, the `NULL` values will be placed at the end of the results.

### 7. Sorting Using Conditional Expressions

You can use conditional expressions to sort based on a specific condition:

```sql
SELECT id, name, salary
FROM employees
ORDER BY CASE
    WHEN salary > 50000 THEN 'high'
    ELSE 'low'
END DESC;
```

In this example, employees with a salary greater than 50,000 will be sorted first (labeled as 'high').

### 8. Sorting by Alias

If you want to sort by a calculated or aliased column, you can use the alias in the `ORDER BY` clause:

```sql
SELECT id, salary + bonus AS total_compensation
FROM employees
ORDER BY total_compensation DESC;
```

In this example, sorting is done based on the `total_compensation` column, which is a calculated column.

### 9. Case-Insensitive Sorting

By default, PostgreSQL is case-sensitive in sorting. If you want to sort in a case-insensitive manner, you can use the `LOWER()` function:

```sql
SELECT name
FROM employees
ORDER BY LOWER(name);
```

This query sorts the names in a case-insensitive manner.

### 10. Sorting Based on Geographical Distance

In PostgreSQL, using geographical data (such as GPS coordinates), you can sort based on the distance from a point. For example:

```sql
SELECT id, location
FROM places
ORDER BY location <-> 'POINT(50 50)';
```

Here, the results are sorted based on the distance from a specific point.

### Summary

The `ORDER BY` clause is a powerful tool for sorting query results in PostgreSQL, offering flexibility with:

- Sorting in ascending or descending order.
- Sorting by multiple columns.
- Controlling how `NULL` values are sorted.
- Sorting based on calculations and functions.
- Case-sensitive or case-insensitive sorting.
- Sorting based on conditions.
  Depending on your needs, you can use this clause in various ways to get the desired result.

---
