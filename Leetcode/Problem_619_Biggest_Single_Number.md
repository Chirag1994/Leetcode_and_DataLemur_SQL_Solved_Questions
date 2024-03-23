## Description

### Table my_numbers contains many numbers in column num including duplicated ones. Can you write a SQL query to find the biggest number, which only appears once.

### Table my_numbers:

| num |
| --- |
| 8   |
| 8   |
| 3   |
| 3   |
| 1   |
| 4   |
| 5   |
| 6   |

### For the sample data above, your query should return the following result:

| num |
| --- |
| 6   |

Note: If there is no such number, just output null.

```sql
SELECT
num
FROM MY_NUMBERS
GROUP BY NUMS
HAVING COUNT(nums) = 1
ORDER BY nums DESC
LIMIT 1;
```
