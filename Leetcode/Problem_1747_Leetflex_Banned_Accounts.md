## Description

Table: LogInfo

| Column Name | Type     |
| ----------- | -------- |
| account_id  | int      |
| ip_address  | int      |
| login       | datetime |
| logout      | datetime |

There is no primary key for this table, and it may contain duplicates.
The table contains information about the login and logout dates of Leetflex accounts. It also contains the IP address from which the account logged in and out.
It is guaranteed that the logout time is after the login time.

### Write an SQL query to find the account_id of the accounts that should be banned from Leetflex. An account should be banned if it was logged in at some moment from two different IP addresses. Return the result table in any order.

The query result format is in the following example:

LogInfo table:

| account_id | ip_address | login               | logout              |
| ---------- | ---------- | ------------------- | ------------------- |
| 1          | 1          | 2021-02-01 09:00:00 | 2021-02-01 09:30:00 |
| 1          | 2          | 2021-02-01 08:00:00 | 2021-02-01 11:30:00 |
| 2          | 6          | 2021-02-01 20:30:00 | 2021-02-01 22:00:00 |
| 2          | 7          | 2021-02-02 20:30:00 | 2021-02-02 22:00:00 |
| 3          | 9          | 2021-02-01 16:00:00 | 2021-02-01 16:59:59 |
| 3          | 13         | 2021-02-01 17:00:00 | 2021-02-01 17:59:59 |
| 4          | 10         | 2021-02-01 16:00:00 | 2021-02-01 17:00:00 |
| 4          | 11         | 2021-02-01 17:00:00 | 2021-02-01 17:59:59 |

Result table:

| account_id |
| ---------- |
| 1          |
| 4          |

#### Method 1:

```sql

```
