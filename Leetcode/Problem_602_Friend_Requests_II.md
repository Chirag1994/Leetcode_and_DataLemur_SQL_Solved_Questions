## Description

In social network like Facebook or Twitter, people send friend requests and accept others’ requests as well.

Table: Request_accepted

| requester_id | accepter_id | accept_date |
| ------------ | ----------- | ----------- |
| 1            | 2           | 2016_06-03  |
| 1            | 3           | 2016-06-08  |
| 2            | 3           | 2016-06-08  |
| 3            | 4           | 2016-06-09  |

This table holds the data of friend acceptance, while requester_id and accepter_id both are the id of a person.

### Write a query to find the the people who has most friends and the most friends number under the following rules:

    - It is guaranteed there is only 1 people having the most friends.
    - The friend request could only been accepted once, which mean there is no multiple records with the same requester_id and accepter_id value.

For the sample data above, the result is:

| id  | num |
| --- | --- |
| 3   | 3   |

#### Method 1:

```sql

```
