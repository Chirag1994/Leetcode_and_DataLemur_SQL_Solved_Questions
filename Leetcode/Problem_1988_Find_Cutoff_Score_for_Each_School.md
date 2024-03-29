## Description

Table: Schools

| Column Name | Type |
| ----------- | ---- |
| school_id   | int  |
| capacity    | int  |

school_id is the primary key for this table.
This table contains information about the capacity of some schools. The capacity is the maximum number of students the school can accept.

Table: Exam

| Column Name   | Type |
| ------------- | ---- |
| score         | int  |
| student_count | int  |

score is the primary key for this table.
Each row in this table indicates that there are student_count students that got at least score points in the exam.

The data in this table will be logically correct, meaning a row recording a higher score will have the same or smaller student_count compared to a row recording a lower score. More formally, for every two rows i and j in the table, if scorei > scorej then student_counti <= student_countj.

Every year, each school announces a minimum score requirement that a student needs to apply to it. The school chooses the minimum score requirement based on the exam results of all the students:

They want to ensure that even if every student meeting the requirement applies, the school can accept everyone.

They also want to maximize the possible number of students that can apply.
They must use a score that is in the Exam table.

### Write an SQL query to report the minimum score requirement for each school. If there are multiple score values satisfying the above conditions, choose the smallest one. If the input data is not enough to determine the score, report -1. Return the result table in any order.

The query result format is in the following example.

Example 1:

Schools table:

| school_id | capacity |
| --------- | -------- |
| 11        | 151      |
| 5         | 48       |
| 9         | 9        |
| 10        | 99       |

Exam table:

| score | student_count |
| ----- | ------------- |
| 975   | 10            |
| 966   | 60            |
| 844   | 76            |
| 749   | 76            |
| 744   | 100           |

Output:

| school_id | score |
| --------- | ----- |
| 5         | 975   |
| 9         | -1    |
| 10        | 749   |
| 11        | 744   |

#### Method 1:

```sql

```
