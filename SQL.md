### From table *subscriptions* where column *subscription_type_id* value is 1 and 2 and 3 AND column *to* is more or equal date now select all records:
```
SELECT * FROM subscriptions WHERE subscription_type_id IN (1, 2, 3) AND to >= NOW()
```
### Set *price* 340.990000 to product with *id_product* value 6953 in table *site.ps_product*: 
```
UPDATE site.ps_product SET price = '340.990000' WHERE id_product = '6953';
```
### From table **companies** show all records if there is a phrase *SELF BUSINES* in the **company_name** column:
```
SELECT * FROM companies WHERE company_name like "%SELF BUSINES%"
```