## Description

Table: Calls

| Column Name | Type |
| ----------- | ---- |
| from_id     | int  |
| to_id       | int  |
| duration    | int  |

This table does not have a primary key, it may contain duplicates.
This table contains the duration of a phone call between from_id and to_id.
from_id != to_id

### Write an SQL query to report the number of calls and the total call duration between each pair of distinct persons (person1, person2) where person1 < person2.

Return the result table in any order.

The query result format is in the following example:

Calls table:

| from_id | to_id | duration |
| ------- | ----- | -------- |
| 1       | 2     | 59       |
| 2       | 1     | 11       |
| 1       | 3     | 20       |
| 3       | 4     | 100      |
| 3       | 4     | 200      |
| 3       | 4     | 200      |
| 4       | 3     | 499      |

Result table:

| person1 | person2 | call_count | total_duration |
| ------- | ------- | ---------- | -------------- |
| 1       | 2       | 2          | 70             |
| 1       | 3       | 1          | 20             |
| 3       | 4       | 4          | 999            |

#### Method 1:

```sql

```
