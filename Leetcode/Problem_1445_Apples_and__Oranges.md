## Description

Table: Sales

| Column Name | Type |
| ----------- | ---- |
| sale_date   | date |
| fruit       | enum |
| sold_num    | int  |

(sale_date,fruit) is the primary key for this table.
This table contains the sales of "apples" and "oranges" sold each day.

### Write an SQL query to report the difference between number of apples and oranges sold each day. Return the result table ordered by sale_date in format (‘YYYY-MM-DD’).

The query result format is in the following example:

Sales table:

+------------+------------+-------------+
| sale_date | fruit | sold_num |
| sale_date | fruit | sold_num |
|------------|---------|----------|
| 2020-05-01 | apples | 10 |
| 2020-05-01 | oranges | 8 |
| 2020-05-02 | apples | 15 |
| 2020-05-02 | oranges | 15 |
| 2020-05-03 | apples | 20 |
| 2020-05-03 | oranges | 0 |
| 2020-05-04 | apples | 15 |
| 2020-05-04 | oranges | 16 |

Result table:

| sale_date  | diff |
| ---------- | ---- |
| 2020-05-01 | 2    |
| 2020-05-02 | 0    |
| 2020-05-03 | 20   |
| 2020-05-04 | -1   |

#### Method 1:

```sql

```
