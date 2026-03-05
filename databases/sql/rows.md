# Rows

In SQL and Databases, a row represents a **complete record / entry within a table**. One row would be one table entry. If it was a table based on store customers, you would find only one row for each customer, with the respective customers information. These provide the structure of information, and what appears in a row's cells depens on what Fields exist.

This markdown works with how we manipulate / work with rows.

## Inserting Rows

We insert rows to actually add data onto a table. Suppose we had a table for products with three fields:

    Products
    ProductID | ProductName | Price

This means that to create an entry, we need to satisfy these fields to create a row. Do note that, whatever fields you need to enter a value for, depends on what that tables constraints are. If a field is NOT NULL, a value is mandatory. If NULL, it can stay empty. The process, with SQL, goes like this:

    INSERT INTO Products (ProductID, ProductName, Price)
    VALUES (1, "MacBook", 1199.99);

If you're going to insert data into EVERY field (in the order they were created), it is fine to omit the columns and just put "INSERT INTO Products" for the first line.

You can also insert multiple rows at once. The column omitting rule still applies.

    INSERT INTO Products
    VALUES
        (1, "MacBook", 1199.99),
        (2, "iPad", 999.99),
        (3, "Airpods Gen 2", 199.99);

    



