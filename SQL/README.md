<!-- Practice: Clauses, Constraint, Data Type -->

# Create Database

```SQL
-- To create a database in SQL, We run the following command
CREATE DATABASE <_name_>;
-- MYSQL, POSTGRESQL are case insensitive: CREATE, Create, create are the same.
```

# Drop Database

```SQL
-- We use the clause DROP, To remove a database
DROP DATABASE <name>;
```

# Creating Table in SQL

```SQL
We run the command:
CREATE TABLE <_name_> (
    -- column_name + data type + constraint (if any)
)

Example,
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    -- (Primary key clause says the variable cannot be null and it is unique)
    first_name VARCHAR(60),
    last_name VARCHAR(60),
    email VARCHAR(80) UNIQUE,
    garage_designation CHAR
)
```

# Insert Data in SQL

```SQL
-- The clause INSERT INTO and VALUES, is used to add rows to a database

INSERT INTO employees VALUES (1, 'Alex', 'Wayne', 'alexwayne@gmail.com', 'A');
-- Note: We can also specify the columns for data to be added
INSERT INTO employees (
    id, first_name, last_name, email, garage_designation
    ) VALUES (
        1, 'Alex', 'Wayne', 'alexwayne@gmail.com', 'A'
);
-- But since we used the clause __AUTO_INCREMENT__, There would be no need to add the first column id (1), We do
INSERT INTO employees (
    first_name, last_name, email, garage_designation
    ) VALUES (
    'Alex', 'Wayne', 'alexwayne@gmail.com', 'A'
);

```

# Update row in SQL

```SQL
--The UPDATE <_name_of_table> is used
UPDATE <name_of_table>
SET first_name = 'Updated first_name', last_name = 'Updated last_name'
WHERE id = 1
-- id can be equal to anything, so as it is unique
```

# Deleting row from SQL

```SQL
We run the command
DELETE FROM <table_name> WHERE id = 1;
-- If we run the command __DELETE FROM <table_name>__; We risk deleting all our data in the database
```

# Adding extra columns

```SQL
ALTER TABLE <name_of_table>
ADD COLUMN phone_no VARCHAR(50);
```

# Date, Time, DateTime

```SQL
-- First we set variable name + data type + constraint (if any)
ALTER TABLE <name_of_table>
ADD COLUMN created_at DATE;
-- CURRENT_DATE() method will be used for Date
-- CURRENT_TIME() method will be used for Time
-- NOW() method will be used for TIMESTAMP (Date + Time)
```

# Dropping columns

```SQL
ALTER TABLE <name_of_table> DROP COLUMN <name_column>;
```

# Moving columns

```SQL
ALTER TABLE <name_of_table>
MODIFY COLUMN email VARCHAR(80) FIRST;
-- This would move the column to be the first column
ALTER TABLE <name_of_table>
MODIFY COLUMN email VARCHAR(80) AFTER first_name;

```

# Adding clause Unique to column

```SQL
ALTER TABLE <name_of_table>
ADD CONSTRAINT UNIQUE(<column_name>);
```

# Default clause

```SQL
-- We attach the clause DEFAULT when creating the table
CREATE TABLE <name_of_table> (
    user_role VARCHAR(20) DEFAULT 'customer'
)
```

# Foreign Key

```SQL
-- Foreign Key is used link two or more table together with using the clause INNER JOIN, LEFT JOIN, RIGHT JOIN
-- When creating the table, a foreign key name will be automatically created.
CREATE TABLE <name_of_table> (
    car_id INT,
    FOREIGN KEY (car_id) REFERENCES <another_table_name>(column_id/identifier);
)
-- After creating the table
ALTER TABLE <name_of_table>
ADD CONSTRAINT <name_of_fky> FOREIGN KEY (car_id) REFERENCES <another_table_name>(column_id/identifier);

-- Droping foreign key
ALTER TABLE <name_of_table>
DROP FOREIGN KEY <name_of_fky>
```

# Limit, Order By, Offset, Asc, Desc

```SQL
-- When querying data from our database, best practice would be to use the LIMIT clause
SELECT * FROM <table_name> LIMIT 3;

-- We can also use Order By. Default is ASC
SELECT * FROM <table_name> ORDER BY id ASC LIMIT 3;
SELECT * FROM <table_name> ORDER BY id DESC LIMIT 3;

-- Using offset clause
SELECT * FROM <table_name> ORDER BY id DESC LIMIT 3 OFFSET 2;
```

# View clause

```SQL
-- This is a virtual table, it is not a real table but sql queries and clauses can be performed on the table. And it updates when there is a change to any of the copied table
CREATE VIEW my_first_view AS SELECT * FROM <table_name>;
DROP VIEW my_first_view;
```

# Self Join

```SQL
-- We join a table to itself, Example: we create an extra column to check who answers to who (supervisor_id)
SELECT a.first_name, a.last_name, CONCAT(b.first_name, ' ', b.last_name)
AS supervisor FROM employees AS a
LEFT JOIN employees AS b
ON a.supervisor_id = b.id;
```

# INDEXES

```SQL
-- Indexes are used to find values in a column more quicky
-- SELECT it is more faster using index
-- UPDATE clause is a bit slower while using indexes

SHOW INDEX FROM <table_name>
-- If we had a primary key clause, it will show that column as an index
CREATE INDEX fullname_idx ON employees(first_name, last_name);
-- employees is the table name, while the values inside the parentesis is the column
ALTER TABLE <table_name> DROP INDEX fullname_idx;
```

# IN clause

```SQL
-- Used with WHERE clause
SELECT * FROM employees WHERE column IN (1, 2, 3);
SELECT * FROM employees WHERE column NOT IN (1, 2, 3);
```

# Subquery

```SQL
-- A query inside another query
SELECT * FROM customer WHERE id NOT IN (SELECT customer_id FROM transactions);
```

# GROUP BY clause

```SQL
-- Mostly used with functions aggregates such as SUM, MIN, MAX, COUNT
-- Rollup is a clause the creates a new row with the aggregate sum of the column we GROUP BY

SELECT SUM(amount), created_at FROM transactions GROUP BY created_at;
-- This will sum the amount of transaction that occured that day, e.g 03-02-2024 have eight transaction, it will sum all the transactions that occured that day

SELECT SUM(amount), created_at FROM transactions GROUP BY created_at WITH ROLLUP;
-- It creates another row that sums / aggregages the aggregate function

-- We use HAVING instead of WHERE clause when using GROUP BY
SELECT SUM(amount), created_at FROM transactions GROUP BY created_at HAVING amount >= 49;
-- This only sums the transaction where the amount is greater than 49
```

# Procedures

```SQL
-- Procedures are prepared SQL codes that are saved, that are called when we have a query we mostly executes
-- To create a procedure, we create another symbol for delimeter
DELIMETER $$
CREATE PROCEDURE get_distinct_users()
BEGIN
    SELECT DISTINCT first_name, amount, FROM users;
END $$

DELIMETER ;

-- Call procedure
CALL get_distinct_users();

-- To drop the procedure
DROP PROCEDURE get_distinct_users;

-- Passing params
DELIMETER $$
CREATE PROCEDURE get_user(IN id INT)
BEGIN
    SELECT first_name, amount, FROM users WHERE id = id;
END $$

DELIMETER ;

CALL get_user(3);
```

# Triggers

```SQL
-- When an event happens, do something,
-- Key Item: BEFORE / AFTER
-- Method: INSERT, UPDATE, DELETE
-- It is used for checking data, handling errors, auditing

CREATE TRIGGER myTrigger
BEFORE/AFTER INSERT/UPDATE/DELETE ON table_name FOR EACH ROW
SET column_param = new_data / prefix with NEW.new_data or OLD.new_data;

-- Also
CREATE TRIGGER myTrigger
BEFORE/AFTER INSERT/UPDATE/DELETE ON table_name FOR EACH ROW
UPDATE table_name
SET column_param = new_data / prefix with NEW.new_data or OLD.new_data
WHERE id = id;

```
