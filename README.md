# MySQL-LearnCode.md
MySQL Learn Code
# 🗄️ MySQL Cheat Sheet

## 📌 What is MySQL?

MySQL is a Relational Database Management System (RDBMS) used to store, organize, and manage data.

Common Uses:

* User Accounts
* Product Information
* Orders
* Blog Posts
* Contact Form Data

---

# 🚀 Connect to MySQL

Using PHP:

```php
$conn = mysqli_connect(
    "localhost",
    "root",
    "",
    "coffee_shop"
);
```

---

# 📂 Create Database

```sql
CREATE DATABASE coffee_shop;
```

View databases:

```sql
SHOW DATABASES;
```

Use a database:

```sql
USE coffee_shop;
```

---

# 📋 Create Table

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

# 🔍 View Tables

```sql
SHOW TABLES;
```

---

# 📄 View Table Structure

```sql
DESCRIBE users;
```

or

```sql
DESC users;
```

---

# ➕ Insert Data

```sql
INSERT INTO users (name, email)
VALUES ('Shazwan', 'shazwan@email.com');
```

Insert multiple rows:

```sql
INSERT INTO users (name, email)
VALUES
('Ali', 'ali@email.com'),
('Ahmad', 'ahmad@email.com');
```

---

# 📤 Select Data

## Select All

```sql
SELECT * FROM users;
```

---

## Select Specific Columns

```sql
SELECT name, email
FROM users;
```

---

## Select One Record

```sql
SELECT *
FROM users
WHERE id = 1;
```

---

# 🔎 WHERE Clause

```sql
SELECT *
FROM users
WHERE name = 'Shazwan';
```

Examples:

```sql
WHERE age > 18
WHERE age < 18
WHERE age >= 18
WHERE age <= 18
WHERE age != 18
```

---

# 📊 ORDER BY

## Ascending

```sql
SELECT *
FROM users
ORDER BY name ASC;
```

---

## Descending

```sql
SELECT *
FROM users
ORDER BY id DESC;
```

---

# 🔢 LIMIT

Get the first 5 records:

```sql
SELECT *
FROM users
LIMIT 5;
```

---

# ✏️ Update Data

```sql
UPDATE users
SET name = 'John'
WHERE id = 1;
```

---

# ❌ Delete Data

Delete one record:

```sql
DELETE FROM users
WHERE id = 1;
```

Delete all records:

```sql
DELETE FROM users;
```

---

# 🧹 Drop Table

Delete a table permanently:

```sql
DROP TABLE users;
```

---

# 🏢 Alter Table

## Add Column

```sql
ALTER TABLE users
ADD phone VARCHAR(20);
```

---

## Remove Column

```sql
ALTER TABLE users
DROP COLUMN phone;
```

---

# 🔍 Search with LIKE

```sql
SELECT *
FROM users
WHERE name LIKE '%wan%';
```

Examples:

```sql
'wan%'
Starts with "wan"

'%wan'
Ends with "wan"

'%wan%'
Contains "wan"
```

---

# 📈 Aggregate Functions

## Count Records

```sql
SELECT COUNT(*)
FROM users;
```

---

## Sum

```sql
SELECT SUM(price)
FROM products;
```

---

## Average

```sql
SELECT AVG(price)
FROM products;
```

---

## Maximum Value

```sql
SELECT MAX(price)
FROM products;
```

---

## Minimum Value

```sql
SELECT MIN(price)
FROM products;
```

---

# 📦 Primary Key

```sql
id INT AUTO_INCREMENT PRIMARY KEY
```

Purpose:

* Unique identifier
* Cannot be duplicated
* Automatically increments

Example:

```text
1
2
3
4
```

---

# 🔗 Foreign Key

Example:

```sql
CREATE TABLE orders (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    FOREIGN KEY (user_id)
    REFERENCES users(id)
);
```

Used to connect tables.

---

# 🔄 INNER JOIN

Combine related data from multiple tables.

Users Table:

```text
id | name
1  | Shazwan
```

Orders Table:

```text
id | user_id
1  | 1
```

Query:

```sql
SELECT users.name, orders.id
FROM users
INNER JOIN orders
ON users.id = orders.user_id;
```

---

# 🔒 Common Data Types

| Data Type    | Description              |
| ------------ | ------------------------ |
| INT          | Whole numbers            |
| VARCHAR(255) | Short text               |
| TEXT         | Long text                |
| FLOAT        | Decimal numbers          |
| DATE         | Date                     |
| DATETIME     | Date and time            |
| TIMESTAMP    | Auto-generated timestamp |
| BOOLEAN      | True/False               |

---

# ⭐ Most Common SQL Commands

```sql
CREATE DATABASE
CREATE TABLE
SHOW TABLES
INSERT INTO
SELECT
UPDATE
DELETE
WHERE
ORDER BY
LIMIT
ALTER TABLE
DROP TABLE
INNER JOIN
```

---

# 🚀 Real-World Examples

## Get All Users

```sql
SELECT *
FROM users;
```

---

## Find User by Email

```sql
SELECT *
FROM users
WHERE email = 'user@email.com';
```

---

## Login Check

```sql
SELECT *
FROM users
WHERE email = 'user@email.com'
AND password = '123456';
```

---

## Latest Products

```sql
SELECT *
FROM products
ORDER BY id DESC
LIMIT 5;
```

---

## Count Total Users

```sql
SELECT COUNT(*)
FROM users;
```

---

# 💡 Typical PHP + MySQL Workflow

```text
HTML Form
     ↓
PHP Receives Form Data
     ↓
MySQL Stores Data
     ↓
PHP Retrieves Data
     ↓
Display Results on Website
```

Example:

```text
Contact Form
     ↓
Submit
     ↓
PHP
     ↓
MySQL Database
     ↓
Admin Dashboard
```

This is the foundation of most traditional web applications built with PHP and MySQL.
