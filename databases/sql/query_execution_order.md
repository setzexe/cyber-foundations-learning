# Query Execution Order

With all the clauses and constraints described in the other markdowns, it would be important to note both the order of query structure, and the execution order. They are not the same thing.

## Query Structure

With every applied principle, to make SQL pull the data correctly, this format is followed:

    SELECT DISTINCT column, AGG_FUNC(column)... AS alias
    FROM table
    JOIN table2
        ON table.id = table2.id
    WHERE condition
    GROUP BY column
    HAVING condition
    ORDER BY column ASC/DESC
    LIMIT count OFFSET count;

This is how queries are formatted. SELECT is first, and OFFSET is last. But this is not how the actual process works. SQL itself does not "select" first.

Each query begins with finding the data we actually need in a database, and then filtering that data down into something that can be processed and understood easily by us. 

## Query Execution Order

1. FROM / JOIN

The **FROM** clause (and **JOINS**, as they also look at data *from* a table) are the first clauses to be executed. This tells SQL exactly what data is being worked with.

2. WHERE

Once we have the total working set of data we want to work with, the **WHERE** constraint are applied to each row. If a row does not satisfy the WHERE clause, it is discarded. Only data requested in the **FROM** clause is affected by this (since this is the only required data anyways).

3. GROUP BY

The remaining rows that passed the **WHERE** constraint are then grouped based on common values in the column speciified by **GROUP BY**. This is only really used when there are aggregate functions within the query.

4. HAVING

If the query has a **GROUP BY** clause, then the constraints in the **HAVING** clause are then applied to these rows. Like **WHERE**, rows that do not satisy these requests are discarded.

5. SELECT / aliases

Any expressions within **SELECT** are now finally computed. The alias is handled here too. SQL does not care for aliases much though, as it is more for display / formatting.

6. DISTINCT

After **SELECT**, **DINSTINCT** computes. Any duplicate values in the DISTINCT column will be discarded.

7. ORDER BY 

If an order is specified by the **ORDER BY** clause, the rows are sorted by the data in rather ascending or descending order (depending on what the user queries).

8. LIMIT / OFFSET

The last step of the process is computing the **LIMIT** followed by the **OFFSET** clause. LIMIT limits how many rows we see, with OFFSET offsetting the amount of rows we see.

___

Not every query needs to have every clause you see here. But a reason as to what makes SQL such a standard is the fact that these clauses exist. It allows for ease of use and very efficient ways off pulling data.






