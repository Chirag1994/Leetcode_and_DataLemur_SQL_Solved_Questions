## Description

### Write a SQL query to find all duplicate emails in a table named Person.

### Table: Employee

| Id  | Email   |
| --- | ------- |
| 1   | a@b.com |
| 2   | c@d.com |
| 3   | a@b.com |

For example, your query should return the following for the above table:

| Email   |
| ------- |
| a@b.com |

#### Method 1:

```sql
SELECT
    Email
FROM Employee
GROUP BY Email
HAVING COUNT(Email) > 1
```

#### Method 2:

```sql
SELECT
    P.Email
FROM (
    SELECT
        Email,
        COUNT(Email) as Count
    FROM Employee
) AS P
WHERE P.Count >1
```
