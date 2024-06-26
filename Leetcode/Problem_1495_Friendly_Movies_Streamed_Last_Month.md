## Description

Table: TVProgram

| Column Name  | Type    |
| ------------ | ------- |
| program_date | date    |
| content_id   | int     |
| channel      | varchar |

(program_date, content_id) is the primary key for this table.
This table contains information of the programs on the TV.
content_id is the id of the program in some channel on the TV.

Table: Content

| Column Name  | Type    |
| ------------ | ------- |
| content_id   | varchar |
| title        | varchar |
| Kids_content | enum    |
| content_type | varchar |

content_id is the primary key for this table.
Kids_content is an enum that takes one of the values ('Y', 'N') where:
'Y' means is content for kids otherwise 'N' is not content for kids.
content_type is the category of the content as movies, series, etc.

### Write an SQL query to report the distinct titles of the kid-friendly movies streamed in June 2020. Return the result table in any order.

The query result format is in the following example.

TVProgram table:

| program_date     | content_id | channel    |
| ---------------- | ---------- | ---------- |
| 2020-06-10 08:00 | 1          | LC-Channel |
| 2020-05-11 12:00 | 2          | LC-Channel |
| 2020-05-12 12:00 | 3          | LC-Channel |
| 2020-05-13 14:00 | 4          | Disney Ch  |
| 2020-06-18 14:00 | 4          | Disney Ch  |
| 2020-07-15 16:00 | 5          | Disney Ch  |

Content table:

| content_id | title          | Kids_content | content_type |
| ---------- | -------------- | ------------ | ------------ |
| 1          | Leetcode Movie | N            | Movies       |
| 2          | Alg. for Kids  | Y            | Series       |
| 3          | Database Sols  | N            | Series       |
| 4          | Aladdin        | Y            | Movies       |
| 5          | Cinderella     | Y            | Movies       |

Result table:

| title   |
| ------- |
| Aladdin |

#### Method 1:

```sql
SELECT
    DISTINCT C.title
FROM CONTENT AS C
JOIN TVPROGRAM AS TV
ON C.content_id = TV.content_id
WHERE MONTH(TV.program_date) = 6 AND YEAR(TV.program_date) = 2020 AND C.Kids_content = 'Y' AND C.content_type = 'Movies';
```
