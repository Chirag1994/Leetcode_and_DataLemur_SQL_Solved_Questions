## Description

Table: Products

+-------------+---------+-------+
| Column Name | Type | |
+-------------+---------+-------+
| product_id | int | |
| store | enum | |
| price | int | |
+-------------+---------+-------+

(product_id,store) is the primary key for this table.
store is an ENUM of type ('store1', 'store2', 'store3') where each represents the store this product is available at.
price is the price of the product at this store.

### Write an SQL query to find the price of each product in each store. Return the result table in any order.

The query result format is in the following example:

+-------------+--------+--------+--------+
| product_id | store1 | store2 | store3 |
+-------------+--------+--------+--------+
| 0 | 95 | 100 | 105 |
| 1 | 70 | null | 80 |
+-------------+--------+--------+--------+

#### Method 1:

```sql

```
