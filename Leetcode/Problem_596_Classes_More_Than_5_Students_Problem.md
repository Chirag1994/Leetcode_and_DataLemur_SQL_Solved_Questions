## Description

### There is a table courses with columns: student and class. Please list out all classes which have more than or equal to 5 students.

### For example, the table:

| student | class    |
| ------- | -------- |
| A       | Math     |
| B       | English  |
| C       | Math     |
| D       | Biology  |
| E       | Math     |
| F       | Computer |
| G       | Math     |
| H       | Math     |
| I       | Math     |

Output should be

| Class |
| ----- |
| Math  |

#### Method 1:

```sql
SELECT Class
FROM Courses
GROUP BY Class
HAVING COUNT(DISTINCT Student) >= 5;
```
