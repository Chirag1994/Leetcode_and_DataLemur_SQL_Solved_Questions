## Description

Table: UserVisits

| Column Name | Type |
| ----------- | ---- |
| user_id     | int  |
| visit_date  | date |

This table does not have a primary key.
This table contains logs of the dates that users vistied a certain retailer.
Assume today’s date is ‘2021-1-1’.

### Write an SQL query that will, for each user_id, find out the largest window of days between each visit and the one right after it (or today if you are considering the last visit). Return the result table ordered by user_id.

The query result format is in the following example:

UserVisits table:

| user_id | visit_date |
| ------- | ---------- |
| 1       | 2020-11-28 |
| 1       | 2020-10-20 |
| 1       | 2020-12-3  |
| 2       | 2020-10-5  |
| 2       | 2020-12-9  |
| 3       | 2020-11-11 |

Result table:

| user_id | biggest_window |
| ------- | -------------- |
| 1       | 39             |
| 2       | 65             |
| 3       | 51             |

#### Method 1:

```sql

```
