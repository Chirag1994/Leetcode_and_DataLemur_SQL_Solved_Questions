## Description

### Table: Person

| Column Name | Type    |
| ----------- | ------- |
| PersonId    | int     |
| FirstName   | varchar |
| LastName    | varchar |

PersonId is the primary key column for this table.

### Table: Address

| Column Name | Type    |
| ----------- | ------- |
| AddressId   | int     |
| PersonId    | int     |
| City        | varchar |
| State       | varchar |

AddressId is the primary key column for this table.

### Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people:

    - FirstName, LastName, City, State

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
