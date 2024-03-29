## Description

Table: Warehouse

| Column Name | Type    |
| ----------- | ------- |
| name        | varchar |
| product_id  | int     |
| units       | int     |

(name, product_id) is the primary key for this table.
Each row of this table contains the information of the products in each warehouse.

Table: Products

| Column Name  | Type    |
| ------------ | ------- |
| product_id   | int     |
| product_name | varchar |
| Width        | int     |
| Length       | int     |
| Height       | int     |

product_id is the primary key for this table.
Each row of this table contains the information about the product dimensions (Width, Lenght and Height) in feets of each product.

### Write an SQL query to report how much cubic feet of volume does the inventory occupy in each warehouse.

    - warehouse_name
    - volume Return the result table in any order.

The query result format is in the following example.

Warehouse table:

| name     | product_id | units |
| -------- | ---------- | ----- |
| LCHouse1 | 1          | 1     |
| LCHouse1 | 2          | 10    |
| LCHouse1 | 3          | 5     |
| LCHouse2 | 1          | 2     |
| LCHouse2 | 2          | 2     |
| LCHouse3 | 4          | 1     |

Products table:

| product_id | product_name | Width | Length | Height |
| ---------- | ------------ | ----- | ------ | ------ |
| 1          | LC-TV        | 5     | 50     | 40     |
| 2          | LC-KeyChain  | 5     | 5      | 5      |
| 3          | LC-Phone     | 2     | 10     | 10     |
| 4          | LC-T-Shirt   | 4     | 10     | 20     |

Result table:

| warehouse_name | volume |
| -------------- | ------ |
| LCHouse1       | 12250  |
| LCHouse2       | 20250  |
| LCHouse3       | 800    |

#### Method 1:

```sql
SELECT
    w.name AS warehouse_name,
    SUM(w.units * (p.Width * p.Length * p.Height)) AS volume
FROM
    Warehouse w
JOIN
    Products p ON w.product_id = p.product_id
GROUP BY
    w.name;
```
