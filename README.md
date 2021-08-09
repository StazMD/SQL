# SQL queries that I use in my daily work

JOINS, INSERT INTO, UPDATE, DELETE, IN, LIKE, ORDER BY, DISTINCT, NULL, LIMIT, AND, OR, BETWEEN

# JOINS

### Show several records with conditions from two tables in one table 
```sql
SELECT
    qq.quiz_id, 
    qqa.points
FROM
    quiz_question_answers AS qqa
LEFT JOIN 
    quiz_questions AS qq ON qqa.quiz_question_id = qq.id
WHERE
    qqa.points IN (55,155)
```
```sql
SELECT 
    Orders.OrderID,
    Employees.LastName, 
    Employees.FirstName
FROM
    Orders
RIGHT JOIN 
    Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID
```
```sql
SELECT
    users.id,
    users.name,
    subscriptions.subscription_type_id
FROM
    users
JOIN subscriptions ON users.id = subscriptions.user_id
```

# INSERT INTO

### Insert new records in a table in specific columns
```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway')
```
### Add values for all the columns of the table
```sql
INSERT INTO Customers
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway')
```

# UPDATE

### Update table record with new price for a product:
```sql
UPDATE ps_product SET price = '340' WHERE id_product = 6953
```
### Update several records in a table
```sql
UPDATE Customers SET ContactName = 'Alfred Schmidt', City = 'Frankfurt' WHERE CustomerID = 1;
```

# DELETE

### Delete record from a table
```sql
DELETE FROM rating_institutions WHERE id = 4
```

# IN

### Show all records from a table with several conditions and date condition
```sql
SELECT * FROM subscriptions WHERE subscription_type_id IN (1, 2, 3) AND to >= NOW()
```
### Show all records from a table with another table's condition
```sql
SELECT * FROM Customers WHERE Country IN (SELECT Country FROM Suppliers);
```

# LIKE

### Show all records from a table where name contains a phrase
```sql
SELECT * FROM companies WHERE company_name like "%SELF BUSINES%"
```
### Show all records from a table where name begins with a phrase
```sql
SELECT * FROM companies WHERE company_name like "SELF BUSINES%"
```
### Show all records from a table where name ends with a phrase
```sql
SELECT * FROM companies WHERE company_name like "%SELF BUSINES"
```

# ORDER BY and DISTINCT

### Select all distinct records from a table ordered and sorting in descending order
```sql
SELECT DISTINCT * FROM registrations ORDER BY created_at DESC
```
### Select all distinct records from a table ordered and sorting in ascendng order
```sql
SELECT DISTINCT * FROM registrations ORDER BY created_at
```

# NULL

### Show all records from a table where client name is not empty
```sql
SELECT * FROM subscriptions WHERE client_name is not NULL

```
### Show all records from a table where client name is empty and sorting from high to low id number 
```sql
SELECT * FROM subscriptions WHERE client_name is NULL ORDER BY id DESC

```
### Show all records from a table where client name is empty and sorting from low to high id number 
```sql
SELECT * FROM subscriptions WHERE client_name is NULL ORDER BY id

```

# LIMIT

### Select all records from a table with condition and show maximum 10 results
```sql
SELECT * FROM companies WHERE status = 'closed' LIMIT 10
```

# AND, OR

### Select all records from a table where condition 1 AND condition 2 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' AND City = 'Berlin'
```
### Select all records from a table where condition 1 OR condition 2 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' OR City = 'Berlin'
```
### Select all records from a table where condition 1 AND condition 2 OR condition 1 AND condition 3 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' AND (City = 'Berlin' OR City = 'München')
```

# BETWEEN

### Select all records from a table where price is between some values
```sql
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20
```

### Select all records from a table orderDate date is between some dates
```sql
SELECT * FROM Orders WHERE OrderDate BETWEEN '2021-07-04' AND '2021-07-08'
```
