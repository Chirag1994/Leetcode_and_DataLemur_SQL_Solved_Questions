## Description

Table: Visits

| Column Name | Type |
| ----------- | ---- |
| visit_id    | int  |
| customer_id | int  |

visit_id is the primary key for this table.
This table contains information about the customers who visited the mall.

Table: Transactions

| Column Name    | Type |
| -------------- | ---- |
| transaction_id | int  |
| visit_id       | int  |
| amount         | int  |

transaction_id is the primary key for this table.
This table contains information about the transactions made during the visit_id.

### Write an SQL query to find the IDs of the users who visited without making any transactions and the number of times they made these types of visits. Return the result table sorted in any order.

The query result format is in the following example:

Visits table:

| visit_id | customer_id |
| -------- | ----------- |
| 1        | 23          |
| 2        | 9           |
| 4        | 30          |
| 5        | 54          |
| 6        | 96          |
| 7        | 54          |
| 8        | 54          |

Transactions table:

| transaction_id | visit_id | amount |
| -------------- | -------- | ------ |
| 2              | 5        | 310    |
| 3              | 5        | 300    |
| 9              | 5        | 200    |
| 12             | 1        | 910    |
| 13             | 2        | 970    |

Result table:

| customer_id | count_no_trans |
| ----------- | -------------- |
| 54          | 2              |
| 30          | 1              |
| 96          | 1              |

#### Method 1:

```sql
SELECT
    customer_id,
    COUNT(visit_id) as count_no_trans
FROM visits
WHERE visit_id NOT IN (SELECT DISTINCT visit_id FROM TRANSACTIONS)
GROUP BY customer_id;
```
