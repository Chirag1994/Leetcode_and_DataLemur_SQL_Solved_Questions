## Description

Table: Points

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| x_value     | int  |
| y_value     | int  |

id is the primary key for this table.
Each point is represented as a 2D Dimensional (x_value, y_value).

### Write an SQL query to report of all possible rectangles which can be formed by any two points of the table. Each row in the result contains three columns (p1, p2, area) where:

    - p1 and p2 are the id of two opposite corners of a rectangle and p1 < p2.
    - Area of this rectangle is represented by the column area.

Report the query in descending order by area in case of tie in ascending order by p1 and p2.

Points table:

| id  | x_value | y_value |
| --- | ------- | ------- |
| 1   | 2       | 8       |
| 2   | 4       | 7       |
| 3   | 2       | 10      |

Result table:

| p1  | p2  | area |
| --- | --- | ---- |
| 2   | 3   | 6    |
| 1   | 2   | 2    |

#### Method 1:

```sql

```
