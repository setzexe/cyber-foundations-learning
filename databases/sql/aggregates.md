# Aggregates

Aggregate functions takes multiple rows and compresses them into a single value. If expressions operate at one row at a time, aggregates do many rows at once.

If you wanna summarize a dataset, you would use aggregates. These would with highest bit of data, the average, count, etc.

Let's deploy a very simple table:

    orders
    id | customer | amount
    1  | Ryan     | 2
    2  | Jacob    | 3
    3  | Connor   | 1
    4  | Evin     | 2

## Count(*)

    SELECT COUNT(*) AS total_orders FROM orders;

total_orders results in 4. COUNT(*) counts rows.

**COUNT(*) counts ALL rows. COUNT(column_name) only counts rows where that entry is not NULL.** If there was an extra id above with a NULL customer, and we did COUNT(customer). It would still only show 4.

## SUM

    SELECT SUM(amount) AS total_sales FROM orders;

This adds up all the rows in amount, leading to 8.

## AVG

    SELECT AVG(amount) AS average_orders FROM orders;

This compiles the average amount of orders; 8 / 4 = 2.

## MIN and MAX

    SELECT 
        MIN(amount) AS min_amount,
        MAX(amount) AS max_amount
    FROM orders;

min_amount = 1. max_amount = 3.

___

Notice up to this point that these results typically only aggregates into one row. Perhaps we changed the data in the orders table.

    orders
    id | customer | amount
    1  | Ryan     | 2
    2  | Jacob    | 3
    3  | Ryan     | 1
    4  | Jacob    | 2

Now, we just have two customers, with different values in both rows. If we tried to count the amount of orders placed...

    SELECT COUNT(*) FROM orders;

This just gives 8. But what if we wanna see how much both Ryan and Jacob bought, seperately? That is where GROUP BY comes in.

## GROUP BY

    SELECT COUNT(*) FROM orders
    ORDER BY customer;

You will get a result like:

- Ryan: 3
- Jacob: 5

GROUP BY splits a column into groups (based on that column) before it aggregates the data.

**It is important to know that** when you use GROUP BY, every column in SELECT must either be inside an aggregate function, or be inside the GROUP BY. If you were to do:

    SELECT customer, amount FROM orders
    GROUP BY customer;

SQL does not know which value to display. Jacob could display 3 or 2. Ryan could display 1 or 2. That causes inconsistency.

## Current Format

    SELECT col 
    FROM tables 
    WHERE condition
    GROUP BY col

## Cybersecurity Relevance

In logs, you constantly use aggregates. COUNT for failed logins / requests per user, SUM for data transferred per session, MAX for login time per account, etc.


