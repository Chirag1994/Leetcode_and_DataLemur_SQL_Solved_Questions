## Description

Table: Employees

| Column Name | Type    |
| ----------- | ------- |
| employee_id | int     |
| name        | varchar |

employee_id is the primary key for this table.
Each row of this table indicates the name of the employee whose ID is employee_id.

Table: Salaries

| Column Name | Type |
| ----------- | ---- |
| employee_id | int  |
| salary      | int  |

employee_id is the primary key for this table.
Each row of this table indicates the salary of the employee whose ID is employee_id.

### Write an SQL query to report the IDs of all the employees with missing information. The information of an employee is missing if:

    - The employee’s name is missing, or
    - The employee’s salary is missing.

Return the result table ordered by employee_id in ascending order.

The query result format is in the following example:

Employees table:

| employee_id | name     |
| ----------- | -------- |
| 2           | Crew     |
| 4           | Haven    |
| 5           | Kristian |

Salaries table:

| employee_id | salary |
| ----------- | ------ |
| 5           | 76071  |
| 1           | 22517  |
| 4           | 63539  |

Result table:

| employee_id |
| ----------- |
| 1           |
| 2           |

#### Method 1:

```sql
SELECT
    employee_id
FROM (
    SELECT employee_id FROM EMPLOYEES
    UNION ALL
    SELECT employee_id FROM SALARIES
) AS TEMP
GROUP BY employee_id
HAVING COUNT(employee_id) = 1
ORDER BY employee_id
```
