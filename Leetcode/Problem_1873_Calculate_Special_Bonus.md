## Description

Table: Employees

| Column Name | Type    |
| ----------- | ------- |
| employee_id | int     |
| name        | varchar |
| salary      | int     |

employee_id is the primary key for this table.
Each row of this table indicates the employee ID, employee name, and salary.

### Write an SQL query to calculate the bonus of each employee. The bonus of an employee is 100% of their salary if the ID of the employee is an odd number and the employee name does not start with the character ‘M’. The bonus of an employee is 0 otherwise. Return the result table ordered by employee_id.

The query result format is in the following example:

Employees table:

| employee_id | name    | salary |
| ----------- | ------- | ------ |
| 2           | Meir    | 3000   |
| 3           | Michael | 3800   |
| 7           | Addilyn | 7400   |
| 8           | Juan    | 6100   |
| 9           | Kannon  | 7700   |

Result table:

| employee_id | bonus |
| ----------- | ----- |
| 2           | 0     |
| 3           | 0     |
| 7           | 7400  |
| 8           | 0     |
| 9           | 7700  |

#### Method 1:

```sql
SELECT
    employee_id,
    (CASE WHEN employee_id % 2 != 0 AND LEFT(name, 1) != 'M' THEN salary
        ELSE 0 END) AS bonus
FROM EMPLOYEES
ORDER BY employee_id
```
