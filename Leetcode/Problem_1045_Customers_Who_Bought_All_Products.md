## Description

Table: Customer

| Column Name | Type |
| ----------- | ---- |
| customer_id | int  |
| product_key | int  |

product_key is a foreign key to Product table.

Table: Product

| Column Name | Type |
| ----------- | ---- |
| product_key | int  |

product_key is the primary key column for this table.

### Write an SQL query for a report that provides the customer ids from the Customer table that bought all the products in the Product table. Return the result table in any order.

The query result format is in the following example:

Customer table:
| customer_id | product_key |
|-------------|-------------|
| 1 | 5 |
| 2 | 6 |
| 3 | 5 |
| 3 | 6 |
| 1 | 6 |

Product table:
| product_key |
|-------------|
| 5 |
| 6 |

Result table:
| customer_id |
|-------------|
| 1 |
| 3 |

#### Method 1:

```sql

```
