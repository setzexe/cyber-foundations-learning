# Expressions 

Expressions (and Aliases) are a foundation concept in how you actually get data. Imagine you want to manipulate your data before you actually display it. This does not mean "display data at a certain data", this means arithmetics too. Expressions help with that.

## Expression Clauses

You use these to work with the data before actually returning it. If you want to change how the data looks but not actually change the data itself, expressions are handy here.

### SELECT With Expresions

    SELECT inch_amount / 12.0 AS feet_amount
    FROM sizechart;

If sizechart had three rows with 48, 60, and 72 respectively, then the result (which would be labeled as inches_amount) gets displayed as 4, 5, and 6. This is just simple arithmetic work.

Note that if your're using division, try to use floating point division (2.0, 3.0, not 2 or 3). Some systems use integer division by default. 5 / 2 would give 2, which is not ideal. 5 / 2.0 fixes that.

### Expressions in WHERE

The WHERE clause is used to check data and only display data that matches certain conditions.

    ... WHERE sum > 24;

Perhaps we want to mess with the sum before we actually check the data. Yes, we could do that with SELECT. But WHERE also allows use of functions. We will not do that here, but it is important to know.

    ... WHERE sum * 3.0 > 24;

The data itself won't change, but now anything in the data above 8 will be shown too, as opposed to just everything above 24.

## Functions

Functions exist within databases to do a variety of tasks. You can find functions for strings, date, and arithmetics on your database's respective document (not all database companies, like MySQL or Oracle, follow the same functions).

    SELECT ... AS... FROM ...
    WHERE ABS(distance) > 8.00;

ABS(variable) just gets the absolute value of a variable so it is not negative. In the query above, we only pull results that are more than 8.00.

## Alliases

Let's go back to the query we did in the SELECT portion.

    SELECT inch_amount / 12.0 AS feet_amount
    FROM sizechart

"AS half_particle_speed" is an alias. It is simply a temporary name. Let's say you wanted to multiply the data of rows *rows* & *cols*. If you did...

    SELECT rows * cols FROM table;

The resulting table would be labeled "rows * cols". Does not look very nice. With an alias, we can make it make more sense.

    SELECT rows * cols AS total 
    FROM table;

Now, "rows * cols" will be labeled as "total". It is worth noting that you often do not need to use AS. You can just go:

    SELECt (rows * cols) total
    FROM table;

That being said, using AS is standard practice and is recommended.

### Alliasing Tables

You can also alias tables:

    SELECT column AS better_column_name
    FROM very_long_table_name AS table1
    INNER JOIN table_sales
    ON table1.id = table_sales.id;

Same with variables, you would do this for clarity or simplication. Some table names might make no sense or be way too long.

Aliases also make it easier when connecting tables. If both tables have a primary key called *id*, just doing "id = id" would be faulty. Having an alias in front of it, like "table.id, a.id" shows much more clarity. 

## Combining Expressions 

Expessions include:

-   Arithmetic (-, /, *, +)
-   Mathematical / String functions
-   Date functions
-   Logical expressions

You can use multiple to display multiple results.

    SELECT price * quantity AS total_value,
        ROUND(price * 0.07, 2) AS tax
    FROM orders;

The shows the total_value of the items in the table + the tax.
