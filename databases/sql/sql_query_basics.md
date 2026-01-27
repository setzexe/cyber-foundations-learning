# SQL Query Basics

Queries are requests we make via SQL. They declare what data we are looking for and where to find it, with the optionality of transforming data before it is returned. Queries follow a specific syntax, much like how most programming language have a specific syntax.

## SELECT

SELECT is used to select what data we want to find. A simple query would look something like:

    SELECT column FROM table;

This just selects the column row from a table.

Suppose, from the same table, we wanted to pull all available rows of information. We would do:

    SELECT * FROM table;

"*" here means "every". So this is asking for all the rows from table.

## Constraints

In many situations, searching up all the data for a table would be inconvenient as there might be mounds of data to show. To filter out unwanted data, we use the **WHERE** clause to determine what data should be displayed. If more than one filter is need, you can use AND/OR. 

    SELECT * FROM cars 
    WHERE brand = "BMW" 
    AND year > 2008

This would only displays BMW's older than 2008.

### Comparison Operators

When it comes to comparing data, the following comparison operators work:

">=", ">", "<" "<=", "!=", and "=".

### BETWEEN ... AND ....

For checking between areas of data, BETWEEN ... AND ... / NOT BETWEEN ... AND ... is what would be used.

    ... col_name BETWEEN 2 AND 10

This displays rows only where col_name is between 2 and 10.

### IN (...) / NOT IN (...)

IN (...) is the constraint / filter that is used to check for data within a certain group. For data that is not in a certain group, NOT IN (...) is what is used.

    SELECT * FROM table WHERE rank IN (1, 2, 3);

This selects rows from the table where the data rank is 1, 2, or 3.

