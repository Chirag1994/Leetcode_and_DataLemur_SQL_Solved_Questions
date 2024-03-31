## Description

Table: Employees

| Column Name | Type    |
| ----------- | ------- |
| employee_id | int     |
| name        | varchar |
| reports_to  | int     |
| age         | int     |

employee_id is the primary key for this table.
This table contains information about the employees and the id of the manager they report to. Some employees do not report to anyone (reports_to is null).

### Write an SQL query to report the ids and the names of the people that other employees reported to (excluding null values), the number of employees who report to them, and the average age of those members rounded to the nearest integer. Return the result table ordered by employee_id.

The query result format is in the following example:

Employees table:

| employee_id | name    | reports_to | age |
| ----------- | ------- | ---------- | --- |
| 9           | Hercy   | null       | 43  |
| 6           | Alice   | 9          | 41  |
| 4           | Bob     | 9          | 36  |
| 2           | Winston | null       | 37  |

Result table:

| employee_id | name  | reports_count | average_age |
| ----------- | ----- | ------------- | ----------- |
| 9           | Hercy | 2             | 39          |

#### Method 1:

```sql
SELECT
    E1.reports_to AS employee_id,
    E2.name AS name,
    COUNT(E1.reports_to) AS reports_count,
    ROUND(AVG(E1.age),0) AS average_age
FROM EMPLOYEES AS E1 JOIN EMPLOYEES AS E2
ON E1.reports_to = E2.employee_id
GROUP BY E1.reports_to
ORDER BY E1.reports_to
```
