# Query Execution Order

With all the clauses and constraints described in the other markdowns, it would be important to note both the order of query structure, and the execution order. They are not the same thing.

## Query Structure

With every applied principle, to make SQL pull the data correctly, this format is followed:

    SELECT DISTINCT column, AGG_FUNC(column)...
    FROM table
    JOIN table2
        ON table.id = table2.id
    WHERE condition
    GROUP BY column
    HAVING condition
    ORDER BY column ASC/DESC
    LIMIT count OFFSET count;

This is how queries are formatted. SELECT is first, and OFFSET is last. But this is not how the actual process works. SQL itself does not "select" first.

## Query Execution Order