## Description

Table: Friendship

| Column Name | Type |
| ----------- | ---- |
| user1_id    | int  |
| user2_id    | int  |

(user1_id, user2_id) is the primary key for this table.
Each row of this table indicates that there is a friendship relation between user1_id and user2_id.

Table: Likes

| Column Name | Type |
| ----------- | ---- |
| user_id     | int  |
| page_id     | int  |

(user_id, page_id) is the primary key for this table.
Each row of this table indicates that user_id likes page_id.

### Write an SQL query to recommend pages to the user with user_id = 1 using the pages that your friends liked. It should not recommend pages you already liked. Return result table in any order without duplicates.

The query result format is in the following example:

Friendship table:

| user1_id | user2_id |
| -------- | -------- |
| 1        | 2        |
| 1        | 3        |
| 1        | 4        |
| 2        | 3        |
| 2        | 4        |
| 2        | 5        |
| 6        | 1        |

Likes table:

| user_id | page_id |
| ------- | ------- |
| 1       | 88      |
| 2       | 23      |
| 3       | 24      |
| 4       | 56      |
| 5       | 11      |
| 6       | 33      |
| 2       | 77      |
| 3       | 77      |
| 6       | 88      |

Result table:

| recommended_page |
| ---------------- |
| 23               |
| 24               |
| 56               |
| 33               |
| 77               |

#### Method 1:

```sql

```
