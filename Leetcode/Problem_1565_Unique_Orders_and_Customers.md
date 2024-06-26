## Description

Table: Orders

| Column Name | Type |
| ----------- | ---- |
| order_id    | int  |
| order_date  | date |
| customer_id | int  |
| invoice     | int  |

order_id is the primary key for this table.
This table contains information about the orders made by customer_id.

### Write an SQL query to find the number of unique orders and the number of unique customers with invoices > $20 for each different month. Return the result table sorted in any order.

The query result format is in the following example:

Orders table:

| order_id | order_date | customer_id | invoice |
| -------- | ---------- | ----------- | ------- |
| 1        | 2020-09-15 | 1           | 30      |
| 2        | 2020-09-17 | 2           | 90      |
| 3        | 2020-10-06 | 3           | 20      |
| 4        | 2020-10-20 | 3           | 21      |
| 5        | 2020-11-10 | 1           | 10      |
| 6        | 2020-11-21 | 2           | 15      |
| 7        | 2020-12-01 | 4           | 55      |
| 8        | 2020-12-03 | 4           | 77      |
| 9        | 2021-01-07 | 3           | 31      |
| 10       | 2021-01-15 | 2           | 20      |

Result table:

| month   | order_count | customer_count |
| ------- | ----------- | -------------- |
| 2020-09 | 2           | 2              |
| 2020-10 | 1           | 1              |
| 2020-12 | 2           | 1              |
| 2021-01 | 1           | 1              |

#### Method 1:

```sql
SELECT
    LEFT(order_date, 7) AS `month`,
    COUNT(DISTINCT customer_id) AS customer_count,
    COUNT(DISTINCT order_id) AS order_count
FROM ORDERS
WHERE invoice > 20
GROUP BY `month`;
```
