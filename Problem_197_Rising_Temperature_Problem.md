## Description

### Write an SQL query to find all dates’ id with higher temperature compared to its previous dates (yesterday).

### Table: Weather.

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| recordDate  | date |
| temperature | int  |

id is the primary key for this table.
This table contains information about the temperature in a certain day.

Return the result table in any order.

The query result format is in the following example:

Activity table:
| id | recordDate | Temperature |
|----|------------|-------------|
| 1 | 2015-01-01 | 10 |
| 2 | 2015-01-02 | 25 |
| 3 | 2015-01-03 | 20 |
| 4 | 2015-01-04 | 30 |

Result table:
| id |
|----|
| 2 |
| 4 |

In 2015-01-02, temperature was higher than the previous day (10 -> 25).
In 2015-01-04, temperature was higher than the previous day (30 -> 20).

#### Method 1:

```sql
SELECT
    DISTINCT A.Id
FROM Weather AS A, Weather AS B
WHERE A.Temperature > B.Temperature
AND DATEDIFF(A.RecordDate, B.RecordDate) = 1;
```

#### Method 2:

```sql
SELECT
    DISTINCT W1.Id
FROM Weather AS W1
JOIN Weather AS W2
ON DATEDIFF(W1.RecordDate, W2.RecordDate) = 1
    AND W1.Temperature > W2.Temperature;
```

#### Method 3:

```sql
SELECT
    DISTINCT W1.Id
FROM Weather AS W1, Weather AS W2
WHERE W1.Temperature > W2.Temperature
    AND TO_DAYS(W1.RecordDate) - TO_DAYS(W2.RecordDate) = 1;

```
