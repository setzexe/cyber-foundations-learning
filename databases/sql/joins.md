# Joins

This concepts involves understanding that the real world breaks down data into tables through a process called normalization. 

Tables that share information about a single entity need a certain indentifier that let's each table know its referring to that thing alone. This is called a *primary key*. This is a unique identifier for a specific identity. This is often just an incremented number from the previous ID, but it can be anything. Strings, hashes, etc. 

The actual method of combining the tables and checking data is the JOIN clause.

## Inner Join

Inner Join is one of the Join clauses that we can use. ON is used with INNER JOIN.

Format so far (Now include INNER JOIN):

    SELECT column, column2 FROM table
    INNER JOIN another_table
        ON table.id = another_table.id
    WHERE conditions
    ORDER BY column, ... ASC/DESC
    LIMIT num_limit OFFSET num_offset

The clauses below inner join only apply once data regarding that join has been found. The table checks for matching data (via ON) and returns rows showing the maching data.

You could technically just use JOIN for these, but by definition this is an inner join.

## Outer Join 
