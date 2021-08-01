### Select all records from table *subscriptions* where column *subscription_type_id* value is 1 and 2 and 3 AND column *to* is more or equal date now

```SELECT * FROM subscriptions WHERE subscription_type_id IN (1, 2, 3) AND `to` >= NOW()```

