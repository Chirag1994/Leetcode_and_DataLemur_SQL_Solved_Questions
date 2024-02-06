## Description

### Write a SQL query to get the second highest salary from the Employee table.

### Table: Employee

+----+--------+
| Id | Salary |
+----+--------+
| 1 | 100 |
| 2 | 200 |
| 3 | 300 |
+----+--------+

For example, given the above Employee table, the query should return 200 as the second highest salary. If there is no second highest salary, then the query should return null.

+---------------------+
| SecondHighestSalary |
+---------------------+
| 200 |
+---------------------+

```sql
SELECT
    P.first_name,
    P.last_name,
    A.city,
    A.state
FROM Person AS P
LEFT JOIN Address AS A
ON P.person_id = A.person_id
```
