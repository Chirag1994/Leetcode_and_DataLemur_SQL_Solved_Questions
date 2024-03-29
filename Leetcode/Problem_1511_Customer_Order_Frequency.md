## Description

Table: Customers

| Column Name | Type    |
| ----------- | ------- |
| customer_id | int     |
| name        | varchar |
| country     | varchar |

customer_id is the primary key for this table.
This table contains information of the customers in the company.

Table: Product

| Column Name | Type    |
| ----------- | ------- |
| product_id  | int     |
| description | varchar |
| price       | int     |

product_id is the primary key for this table.
This table contains information of the products in the company.
price is the product cost.

Table: Orders

| Column Name | Type |
| ----------- | ---- |
| order_id    | int  |
| customer_id | int  |
| product_id  | int  |
| order_date  | date |
| quantity    | int  |

order_id is the primary key for this table.
This table contains information on customer orders.
customer_id is the id of the customer who bought "quantity" products with id "product_id".
Order_date is the date in format ('YYYY-MM-DD') when the order was shipped.

### Write an SQL query to report the customer_id and customer_name of customers who have spent at least $100 in each month of June and July 2020. Return the result table in any order.

The query result format is in the following example.

Customers table:

| customer_id | name     | country |
| ----------- | -------- | ------- |
| 1           | Winston  | USA     |
| 2           | Jonathan | Peru    |
| 3           | Moustafa | Egypt   |

Product table:

| product_id | description | price |
| ---------- | ----------- | ----- |
| 10         | LC Phone    | 300   |
| 20         | LC T-Shirt  | 10    |
| 30         | LC Book     | 45    |
| 40         | LC Keychain | 2     |

Orders table:

| order_id | customer_id | product_id | order_date | quantity |
| -------- | ----------- | ---------- | ---------- | -------- |
| 1        | 1           | 10         | 2020-06-10 | 1        |
| 2        | 1           | 20         | 2020-07-01 | 1        |
| 3        | 1           | 30         | 2020-07-08 | 2        |
| 4        | 2           | 10         | 2020-06-15 | 2        |
| 5        | 2           | 40         | 2020-07-01 | 10       |
| 6        | 3           | 20         | 2020-06-24 | 2        |
| 7        | 3           | 30         | 2020-06-25 | 2        |
| 9        | 3           | 30         | 2020-05-08 | 3        |

Result table:

| customer_id | name    |
| ----------- | ------- |
| 1           | Winston |

#### Method 1

```sql
SELECT
    Customer_id,
    `Name`
FROM
    (SELECT
        DISTINCT C.Customer_id,
        C.Name,
        SUM(CASE WHEN LEFT(O.Order_date, 7) = '2020-06' THEN P.Price * O.Quantity ELSE 0 END) AS June_Spending,
        SUM(CASE WHEN LEFT(O.Order_date, 7) = '2020-07' THEN P.Price * O.Quantity ELSE 0 END) AS July_Spending
    FROM CUSTOMERS AS C
    JOIN ORDERS AS O
    ON C.Customer_id = O.Customer_id
    JOIN PRODUCT AS P
    ON O.Product_id = P.Product_id
    GROUP BY C.Customer_id
    HAVING June_Spending >= 100 AND July_Spending >= 100
    ) AS TEMP
```
