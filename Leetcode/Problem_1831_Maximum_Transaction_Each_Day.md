## Description

Table: Transactions

| Column Name    | Type     |
| -------------- | -------- |
| transaction_id | int      |
| day            | datetime |
| amount         | int      |

transaction_id is the primary key for this table.
Each row contains information about one transaction.

### Write an SQL query to report the IDs of the transactions with the maximum amount on their respective day. If in one day there are multiple such transactions, return all of them. Return the result table in ascending order by transaction_id.

The query result format is in the following example:

Transactions table:

| transaction_id | day                 | amount |
| -------------- | ------------------- | ------ |
| 8              | 2021-04-03 15:57:28 | 57     |
| 9              | 2021-04-28 08:47:25 | 21     |
| 1              | 2021-04-29 13:28:30 | 58     |
| 5              | 2021-04-28 16:39:59 | 40     |
| 6              | 2021-04-29 23:39:28 | 58     |

Result table:

| transaction_id |
| -------------- |
| 1              |
| 5              |
| 6              |
| 8              |

#### Method 1:

```sql

```
