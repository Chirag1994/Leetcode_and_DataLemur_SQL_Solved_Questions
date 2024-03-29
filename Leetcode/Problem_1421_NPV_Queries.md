## Description

Table: NPV

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| year        | int  |
| npv         | int  |

(id, year) is the primary key of this table.
The table has information about the id and the year of each inventory and the corresponding net present value.

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| year        | int  |

(id, year) is the primary key of this table.
The table has information about the id and the year of each inventory query.

### Write an SQL query to find the npv of all each query of queries table. Return the result table in any order.

The query result format is in the following example:

NPV table:

| id  | year | npv |
| --- | ---- | --- |
| 1   | 2018 | 100 |
| 7   | 2020 | 30  |
| 13  | 2019 | 40  |
| 1   | 2019 | 113 |
| 2   | 2008 | 121 |
| 3   | 2009 | 12  |
| 11  | 2020 | 99  |
| 7   | 2019 | 0   |

Queries table:

| id  | year |
| --- | ---- |
| 1   | 2019 |
| 2   | 2008 |
| 3   | 2009 |
| 7   | 2018 |
| 7   | 2019 |
| 7   | 2020 |
| 13  | 2019 |

Result table:

| id  | year | npv |
| --- | ---- | --- |
| 1   | 2019 | 113 |
| 2   | 2008 | 121 |
| 3   | 2009 | 12  |
| 7   | 2018 | 0   |
| 7   | 2019 | 0   |
| 7   | 2020 | 30  |
| 13  | 2019 | 40  |

#### Method 1:

```sql

```
