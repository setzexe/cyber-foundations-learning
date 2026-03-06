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

## Updating Rows

If, for whatever reason, you mean to edit already existing data, the **UPDATE** clause works for this.

The process of updating values / a row is identifying the tables, setting values, then specifying what rows will be updated. For example:

    UPDATE Products
    SET Price = 999.99
    WHERE ProductID = 1;

The MacBook will now be $999.99 according to the database.

You can also update multiple fields / columns at once by seperating them with a column.

    UPDATE Products
    SET Name = "NEW MacBook", Price = 1499.99
    WHERE ProductID = 1;

If the where clause matches more than one row (maybe we did WHERE Category = "Electronics"), the UPDATE query will update ALL rows in that clause. All "Electronics" rows would get this update.

**You must use the WHERE clause if you want to only affect certain rows.** Using the UPDATE query without WHERE applies the update to EVERY SINGLE row in a table.

    UPDATE Products
    SET Price = "99.99";

Now everything in the store is $99.99!

Before running an UPDATE query, it is highly recommended that you do the same query, but with SELECT.

    SELECT * FROM Products WHERE Category = "Electronics"

This shows you have many rows will actually be affected.

## Deleting Rows

Deleting rows in SQL removes unwanted data form database tables using the **DELETE** statement. It is paired with the **WHERE** clause.

    DELETE FROM table
    WHERE condition;

Suppose we have a new table for student information for a school.

    Students
    student_id | student_name | other_columns...

This might have 1800. If you wanted to delete a specific row, possibly because a student graduated or moved (we'll say user 80 in this case) the process would look like this:

    DELETE FROM Students
    WHERE student_id = 80;

Only row 80 will be deleted. You don't have to do this again for every column in that row. Once you have one value, the rest of the row is deleted.

You can also search multiple rows using **in**:

    DELETE FROM Students
    WHERE student_id IN (80, 81, 82);

To delete based on text:

    DELETE FROM Students
    WHERE student_name = 'Ryan';

You can also delete based on numeric conditions.

    DELETE FROM Students
    WHERE student_id < 11 

Students 1-10 will be deleted. 

Much like updating tables, it is recommended to do a SELECT * FROM query before deleting anything. This verifies that you know exactly what you want deleted.

    SELECT * FROM Students WHERE student_id = 80;

**ALWAYS include a where clause** Even if the condition might be silly. If you do not, **ALL data** gets deleted. You could potentially destroy an entire table's data with a simple mistake. **HAVE BACKUPS OF THESE TABLES!!!**

## Trunicate & Drop

It's worth mentioning that there is a specific command for deleting everything intentionally instead of just misusing DELETE:

    TRUNICATE TABLE Students;

This near instantly deletes all data in the table. This is really only what it's used for.

**DROP** does the entire table. Not the data-- the ENTIRE table. 'Students' wouldn't even exist in the database anymore.

If your table works as a foreign key for another table, you CANNOT delete or trunicate the table. It would not allow you.





