## Description

Table: Contests

| Column Name  | Type |
| ------------ | ---- |
| contest_id   | int  |
| gold_medal   | int  |
| silver_medal | int  |
| bronze_medal | int  |

contest_id is the primary key for this table.
This table contains the LeetCode contest ID and the user IDs of the gold, silver, and bronze medalists.
It is guaranteed that any consecutive contests have consecutive IDs and that no ID is skipped.

Table: Users

| Column Name | Type    |
| ----------- | ------- |
| user_id     | int     |
| mail        | varchar |
| name        | varchar |

user_id is the primary key for this table.
This table contains information about the users.

### Write an SQL query to report the name and the mail of all interview candidates. A user is an interview candidate if at least one of these two conditions is true:

    - The user won any medal in three or more consecutive contests. The user won the gold medal in three or more different contests (not necessarily consecutive). Return the result table in any order.

The query result format is in the following example:

Contests table:

| contest_id | gold_medal | silver_medal | bronze_medal |
| ---------- | ---------- | ------------ | ------------ |
| 190        | 1          | 5            | 2            |
| 191        | 2          | 3            | 5            |
| 192        | 5          | 2            | 3            |
| 193        | 1          | 3            | 5            |
| 194        | 4          | 5            | 2            |
| 195        | 4          |

Users table:

| user_id | mail               | name  |
| ------- | ------------------ | ----- |
| 1       | sarah@leetcode.com | Sarah |
| 2       | bob@leetcode.com   | Bob   |
| 3       | alice@leetcode.com | Alice |
| 4       | hercy@leetcode.com | Hercy |
| 5       | quarz@leetcode.com | Quarz |

Result table:

| name  | mail               |
| ----- | ------------------ |
| Sarah | sarah@leetcode.com |
| Bob   | bob@leetcode.com   |
| Alice | alice@leetcode.com |
| Quarz | quarz@leetcode.com |

#### Method 1:

```sql

```
