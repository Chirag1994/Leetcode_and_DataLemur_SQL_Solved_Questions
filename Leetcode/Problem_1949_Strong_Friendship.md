## Description

Table: Friendship

| Column Name | Type |
| ----------- | ---- |
| user1_id    | int  |
| user2_id    | int  |

(user1_id, user2_id) is the primary key for this table.
Each row of this table indicates that the users user1_id and user2_id are friends.
Note that user1_id < user2_id.
A friendship between a pair of friends x and y is strong if x and y have at least three common friends.

### Write an SQL query to find all the strong friendships. Note that the result table should not contain duplicates with user1_id < user2_id. Return the result table in any order.

The query result format is in the following example:

Friendship table:

| user1_id | user2_id |
| -------- | -------- |
| 1        | 2        |
| 1        | 3        |
| 2        | 3        |
| 1        | 4        |
| 2        | 4        |
| 1        | 5        |
| 2        | 5        |
| 1        | 7        |
| 3        | 7        |
| 1        | 6        |
| 3        | 6        |
| 2        | 6        |

Result table:

| user1_id | user2_id | common_friend |
| -------- | -------- | ------------- |
| 1        | 2        | 4             |
| 1        | 3        | 3             |

#### Method 1:

```sql

```
