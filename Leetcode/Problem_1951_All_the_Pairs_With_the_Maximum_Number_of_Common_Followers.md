## Description

Table: Relations

| Column Name | Type |
| ----------- | ---- |
| user_id     | int  |
| follower_id | int  |

(user_id, follower_id) is the primary key for this table.
Each row of this table indicates that the user with ID follower_id is following the user with ID user_id.

### Write an SQL query to find all the pairs of users with the maximum number of common followers. In other words, if the maximum number of common followers between any two users is maxCommon, then you have to return all pairs of users that have maxCommon common followers. The result table should contain the pairs user1_id and user2_id where user1_id < user2_id. Return the result table in any order.

The query result format is in the following example:

Relations table:

| user_id | follower_id |
| ------- | ----------- |
| 1       | 3           |
| 2       | 3           |
| 7       | 3           |
| 1       | 4           |
| 2       | 4           |
| 7       | 4           |
| 1       | 5           |
| 2       | 6           |
| 7       | 5           |

Result table:

| user1_id | user2_id |
| -------- | -------- |
| 1        | 7        |

#### Method 1:

```sql

```
