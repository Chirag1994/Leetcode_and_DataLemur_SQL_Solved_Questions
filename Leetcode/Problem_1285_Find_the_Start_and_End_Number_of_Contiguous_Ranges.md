## Description

Table: Logs

| Column Name | Type |
| ----------- | ---- |
| log_id      | int  |

id is the primary key for this table.
Each row of this table contains the ID in a log Table.

### Since some IDs have been removed from Logs. Write an SQL query to find the start and end number of continuous ranges in table Logs. Order the result table by start_id.

The query result format is in the following example:

Logs table:

| log_id |
| ------ |
| 1      |
| 2      |
| 3      |
| 7      |
| 8      |
| 10     |

Result table:

| start_id | end_id |
| -------- | ------ |
| 1        | 3      |
| 7        | 8      |
| 10       | 10     |

#### Method 1:

```sql

```
