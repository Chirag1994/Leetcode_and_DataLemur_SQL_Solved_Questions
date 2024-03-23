## Description

Several friends at a cinema ticket office would like to reserve consecutive available seats. Can you help to query all the consecutive available seats order by the seat_id using the following cinema table?

### Table Cinema:

| seat_id | free |
| ------- | ---- |
| 1       | 1    |
| 2       | 0    |
| 3       | 1    |
| 4       | 1    |
| 5       | 1    |

### Your query should return the following result for the sample case above.

| seat_id |
| ------- |
| 3       |
| 4       |
| 5       |

Note:

    - The seat_id is an auto increment int, and free is bool (‘1’ means free, and ‘0’ means occupied.).
    - Consecutive available seats are more than 2(inclusive) seats consecutively available.

Method 1:

```sql
SELECT DISTINCT c1.seat_id
FROM CINEMA AS c1
JOIN CINEMA AS c2
ON (c1.seat_id = c2.seat_id - 1) OR (c1.seat_id = c2.seat_id + 1)
WHERE (c1.free = 1) AND (c2.free = c1.free)
ORDER BY c1.seat_id
```

Method 2:

```sql
SELECT DISTINCT c1.seat_id
FROM CINEMA AS c1
JOIN CINEMA AS c2
ON ABS(c1.seat_id - c2.seat_id) = 1
WHERE (c1.free = 1) AND (c2.free = c1.free)
ORDER BY c1.seat_id
```
