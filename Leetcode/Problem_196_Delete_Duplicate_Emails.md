## Description

### Write a SQL query to delete all duplicate email entries in a table named Person, keeping only unique emails based on its smallest Id.

### Table: Customers.

| Id  | Email            |
| --- | ---------------- |
| 1   | john@example.com |
| 2   | bob@example.com  |
| 3   | john@example.com |

Id is the primary key column for this table.

For example, after running your query, the above Person table should have the following rows:

| Id  | Email            |
| --- | ---------------- |
| 1   | john@example.com |
| 2   | bob@example.com  |

#### Method 1:

```sql
DELETE P1
FROM Person AS P1, Person AS P2
WHERE P1.Email = P2.Email and P1.Id > P2.Id
```

#### Method 2:

```sql
DELETE p1
FROM Person p1
JOIN (
    SELECT MIN(Id) AS MinId, Email
    FROM Person
    GROUP BY Email
) p2 ON p1.Id > p2.MinId AND p1.Email = p2.Email;
```
