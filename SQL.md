### Show all records from table with several conditions and date condition:
```sql
SELECT * FROM subscriptions WHERE subscription_type_id       (1, 2, 3) AND to >= NOW()
```
### Update table record with new price for a product:
```sql
UPDATE ps_product SET price = '340.990000' WHERE id_product = '6953';
```
### Show all records from table where name contains phrase
```sql
SELECT * FROM companies WHERE company_name like "%SELF BUSINES%"
```
### Show all records from table where name begins with phrase
```sql
SELECT * FROM companies WHERE company_name like "SELF BUSINES%"
```
### Show all records from table where name ends with phrase
```sql
SELECT * FROM companies WHERE company_name like "%SELF BUSINES"
```
### Delete record from table
```sql
DELETE FROM rating_institutions WHERE id = 4
```
### Show several records with conditions from two tables in one table 
```sql
SELECT qq.quiz_id, qqa.points
FROM
    quiz_question_answers AS qqa
    LEFT JOIN quiz_questions AS qq ON qqa.quiz_question_id = qq.id
WHERE
    qqa.points IN (55,155)
```
```sql
SELECT
    users.id
    users.name,
    subscriptions.subscription_type_id,
FROM
    users
    JOIN subscriptions ON users.id = subscriptions.user_id
```
### Show all records from table where client name is not empty
```sql
SELECT * FROM subscriptions WHERE client_name is not NULL

```
### Show all records from table where client name is empty and sorting from high to low id number 
```sql
SELECT * FROM subscriptions WHERE client_name is NULL ORDER BY id DESC

```
### Show all records from table where client name is empty and sorting from low to high id number 
```sql
SELECT * FROM subscriptions WHERE client_name is NULL ORDER BY id

```
### Select all records from table with condition and show maximum 10 results
```sql
SELECT * FROM companies WHERE status = 'closed' LIMIT 10
```
### Select all distinct records from table ordered and sorting in descending order
```sql
SELECT DISTINCT * FROM registrations ORDER BY created_at DESC
```
### Select all records from table where condition 1 AND condition 2 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' AND City='Berlin'
```
### Select all records from table where condition 1 OR condition 2 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' OR City='Berlin'
```
### Select all records from table where condition 1 AND condition 2 OR condition 1 AND condition 3 should be met
```sql
SELECT * FROM Customers WHERE Country='Germany' AND (City='Berlin' OR City='München')
```
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
### Select all records from a table where price is between some values
```sql
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20
```