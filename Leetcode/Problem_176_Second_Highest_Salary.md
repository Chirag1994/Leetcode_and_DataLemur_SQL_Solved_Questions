## Description

### Write a SQL query to get the second highest salary from the Employee table.

### Table: Employee

| Id  | Salary |
| --- | ------ |
| 1   | 100    |
| 2   | 200    |
| 3   | 300    |

For example, given the above Employee table, the query should return 200 as the second highest salary. If there is no second highest salary, then the query should return null.

| SecondHighestSalary |
| ------------------- |
| 200                 |

#### Method 1:

```sql
SELECT
    MAX(Salary)
FROM Employee
WHERE Salary < (
    SELECT
        MAX(Salary)
    FROM Employee
)
```

#### Method 2:

```sql
SELECT (
    SELECT
        DISTINCT Salary
    FROM Employee
    ORDER BY Salary DESC
    LIMIT 1
) AS Second_Highest_Salary_Table
```
