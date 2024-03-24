## Description

### Table: Project

| Column Name | Type |
| ----------- | ---- |
| project_id  | int  |
| employee_id | int  |

(project_id, employee_id) is the primary key of this table.
employee_id is a foreign key to Employee table.

### Table: Employee

| Column Name      | Type    |
| ---------------- | ------- |
| employee_id      | int     |
| name             | varchar |
| experience_years | int     |

employee_id is the primary key of this table.

## Write an SQL query that reports all the projects that have the most employees.

The query result format is in the following example:

### Project table:

| project_id | employee_id |
| ---------- | ----------- |
| 1          | 1           |
| 1          | 2           |
| 1          | 3           |
| 2          | 1           |
| 2          | 4           |

### Employee table:

| employee_id | name   | experience_years |
| ----------- | ------ | ---------------- |
| 1           | Khaled | 3                |
| 2           | Ali    | 2                |
| 3           | John   | 1                |
| 4           | Doe    | 2                |

### Result table:

| project_id |
| ---------- |
| 1          |

#### Method 1:

```sql
SELECT P.project_id
FROM PROJECT AS P
LEFT JOIN EMPLOYEE AS E
ON P.employee_id = E.employee_id
GROUP BY P.project_id
HAVING COUNT(P.employee_id) =
    (SELECT MAX(P.employee_count)
        FROM (SELECT project_id, COUNT(employee_id) AS employee_count
                FROM project
                GROUP BY project_id) AS P1
    );
```
