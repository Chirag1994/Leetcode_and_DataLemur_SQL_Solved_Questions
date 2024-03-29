## Description

Table: Accounts

| Column Name | Type |
| ----------- | ---- |
| account_id  | int  |
| max_income  | int  |

account_id is the primary key for this table.
Each row contains information about the maximum monthly income for one bank account.

Table: Transactions

| Column Name    | Type     |
| -------------- | -------- |
| transaction_id | int      |
| account_id     | int      |
| type           | ENUM     |
| amount         | int      |
| day            | datetime |

transaction_id is the primary key for this table.
Each row contains information about one transaction.
type is ENUM ('Creditor','Debtor') where 'Creditor' means the user deposited money into their account and 'Debtor' means the user withdrew money from their account.
amount is the amount of money depositied/withdrawn during the transaction.

### Write an SQL query to report the IDs of all suspicious bank accounts. A bank account is suspicious if the total income exceeds the max_income for this account for two or more consecutive months. The total income of an account in some month is the sum of all its deposits in that month (i.e., transactions of the type ‘Creditor’). Return the result table in ascending order by transaction_id.

The query result format is in the following example:

Accounts table:

| account_id | max_income |
| ---------- | ---------- |
| 3          | 21000      |
| 4          | 10400      |

Transactions table:

| transaction_id | account_id | type     | amount | day                 |
| -------------- | ---------- | -------- | ------ | ------------------- |
| 2              | 3          | Creditor | 107100 | 2021-06-02 11:38:14 |
| 4              | 4          | Creditor | 10400  | 2021-06-20 12:39:18 |
| 11             | 4          | Debtor   | 58800  | 2021-07-23 12:41:55 |
| 1              | 4          | Creditor | 49300  | 2021-05-03 16:11:04 |
| 15             | 3          | Debtor   | 75500  | 2021-05-23 14:40:20 |
| 10             | 3          | Creditor | 102100 | 2021-06-15 10:37:16 |
| 14             | 4          | Creditor | 56300  | 2021-07-21 12:12:25 |
| 19             | 4          | Debtor   | 101100 | 2021-05-09 15:21:49 |
| 8              | 3          | Creditor | 64900  | 2021-07-26 15:09:56 |
| 7              | 3          | Creditor | 90900  | 2021-06-14 11:23:07 |

Result table:

| account_id |
| ---------- |
| 3          |

#### Method 1:

```sql

```
