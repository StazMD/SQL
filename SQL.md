### Show all records from table with several conditions and date condition:
```
SELECT * FROM subscriptions WHERE subscription_type_id IN (1, 2, 3) AND to >= NOW()
```
### Update table with new price for a product:
```
UPDATE ps_product SET price = '340.990000' WHERE id_product = '6953';
```
### Show all values from table where name contains some phrase
```
SELECT * FROM companies WHERE company_name like "%SELF BUSINES%"
```
### Delete row from table
```
DELETE FROM rating_institutions WHERE id = 4
```
### Show several values with conditions from two tables in one table 
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
    users.name,
    subscriptions.subscription_type_id,
    users.id
FROM
    users
    JOIN subscriptions ON users.id = subscriptions.user_id
```
