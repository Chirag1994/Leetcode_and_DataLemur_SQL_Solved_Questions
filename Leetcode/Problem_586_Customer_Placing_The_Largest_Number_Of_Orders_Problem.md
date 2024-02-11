## Description

### Query the customer_number from the orders table for the customer who has placed the largest number of orders. It is guaranteed that exactly one customer will have placed more orders than any other customer.

The orders table is defined as follows:

| Column            | Type      |
| ----------------- | --------- |
| order_number (PK) | int       |
| customer_number   | int       |
| order_date        | date      |
| required_date     | date      |
| shipped_date      | date      |
| status            | char(15)  |
| comment           | char(200) |

### Sample Input.

| order_number | customer_number | order_date | required_date | shipped_date | status | comment |
| ------------ | --------------- | ---------- | ------------- | ------------ | ------ | ------- |
| 1            | 1               | 2017-04-09 | 2017-04-13    | 2017-04-12   | Closed |         |
| 2            | 2               | 2017-04-15 | 2017-04-20    | 2017-04-18   | Closed |         |
| 3            | 3               | 2017-04-16 | 2017-04-25    | 2017-04-20   | Closed |         |
| 4            | 3               | 2017-04-18 | 2017-04-28    | 2017-04-25   | Closed |         |

### Sample Output.

| customer_number |
| --------------- |
| 3               |

#### Method 1:

```sql
SELECT
    O.Customer_Number
FROM Orders AS O
GROUP BY O.Customer_Number
HAVING COUNT(O.Order_Number) = (
    SELECT MAX(O.Order_Count)
) FROM
(SELECT
    COUNT(O1.Order_Number) AS Order_Count
FROM Orders AS O1
GROUP BY O1.Customer_Number) AS O_;
```

#### Method 2:

```sql
SELECT
    Customer_Number
FROM (SELECT
        Customer_Number, COUNT(Order_Number) AS Order_Count
      FROM Orders GROUP BY Customer_Number) AS A
ORDER BY Order_Count DESC
LIMIT 1;
```
