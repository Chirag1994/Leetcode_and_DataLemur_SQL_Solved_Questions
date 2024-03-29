## Description

Table: Boxes

| Column Name  | Type |
| ------------ | ---- |
| box_id       | int  |
| chest_id     | int  |
| apple_count  | int  |
| orange_count | int  |

box_id is the primary key for this table.
chest_id is a foreign key of the chests table.
This table contains information about the boxes and the number of oranges and apples they contain. Each box may contain a chest, which also can contain oranges and apples.

Table: Chests

| Column Name  | Type |
| ------------ | ---- |
| chest_id     | int  |
| apple_count  | int  |
| orange_count | int  |

chest_id is the primary key for this table.
This table contains information about the chests we have, and the corresponding number if oranges and apples they contain.

### Write an SQL query to count the number of Apples and oranges we have in the boxes. If a box contains a chest, you should also include the number of apples and oranges it has. Return the result table in any order.

The query result format is in the following example:

Boxes table:

| box_id | chest_id | apple_count | orange_count |
| ------ | -------- | ----------- | ------------ |
| 2      | null     | 6           | 15           |
| 18     | 14       | 4           | 15           |
| 19     | 3        | 8           | 4            |
| 12     | 2        | 19          | 20           |
| 20     | 6        | 12          | 9            |
| 8      | 6        | 9           | 9            |
| 3      | 14       | 16          | 7            |

Chests table:

| chest_id | apple_count | orange_count |
| -------- | ----------- | ------------ |
| 6        | 5           | 6            |
| 14       | 20          | 10           |
| 2        | 8           | 8            |
| 3        | 19          | 4            |
| 16       | 19          | 19           |

Result table:

| apple_count | orange_count |
| ----------- | ------------ |
| 151         | 123          |

#### Method 1:

```sql

```
