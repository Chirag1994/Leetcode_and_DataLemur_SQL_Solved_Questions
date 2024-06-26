## Description

Table: Product

| Column Name | Type    |
| ----------- | ------- |
| product_id  | int     |
| name        | varchar |

product_id is the primary key for this table.
This table contains the ID and the name of the product. The name consists of only lowercase English letters. No two products have the same name.

Table: Invoice

| Column Name | Type |
| ----------- | ---- |
| invoice_id  | int  |
| product_id  | int  |
| rest        | int  |
| paid        | int  |
| canceled    | int  |
| refunded    | int  |

invoice_id is the primary key for this table and the id of this invoice.
product_id is the id of the product for this invoice.
rest is the amount left to pay for this invoice.
paid is the amount paid for this invoice.
canceled is the amount canceled for this invoice.
refunded is the amount refunded for this invoice.

### Write an SQL query that will, for all products, return each product name with total amount due, paid, canceled, and refunded across all invoices. Return the result table ordered by product_name.

The query result format is in the following example:

Product table:

| product_id | name  |
| ---------- | ----- |
| 0          | ham   |
| 1          | bacon |

Invoice table:

| invoice_id | product_id | rest | paid | canceled | refunded |
| ---------- | ---------- | ---- | ---- | -------- | -------- |
| 23         | 0          | 2    | 0    | 5        | 0        |
| 12         | 0          | 0    | 4    | 0        | 3        |
| 1          | 1          | 1    | 1    | 0        | 1        |
| 2          | 1          | 1    | 0    | 1        | 1        |
| 3          | 1          | 0    | 1    | 1        | 1        |
| 4          | 1          | 1    | 1    | 1        | 0        |

Result table:

| name  | rest | paid | canceled | refunded |
| ----- | ---- | ---- | -------- | -------- |
| bacon | 3    | 3    | 3        | 3        |
| ham   | 2    | 4    | 5        | 3        |

#### Method 1:

```sql
SELECT
    P.product_name,
    SUM(I.rest) AS rest,
    SUM(I.paid) AS paid,
    SUM(I.canceled) AS canceled,
    SUM(I.refunded) AS refunded
FROM PRODUCT AS P JOIN INVOICE AS I
ON P.product_id = I.product_id
GROUP BY P.product_name
ORDER BY P.product_name;
```
