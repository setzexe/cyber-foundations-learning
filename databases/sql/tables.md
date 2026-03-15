# Tables

Tables are the fundamental part of databases that actual store data. They consist of rows and columns and store data based on constraints. Everyday systems heavily rely on these tables. The passwords you have on websites exist within a table. Very similar to a spreadsheet.

The structure of a table is defined by it's **schema**. Each column has a name, a data type that's allowed, an optional constraint, and an optional default value. This structure ensures tables have variety and are not just clumps of data.

## Table Creation Example

Below would be the creation of a table for **students** in a school system:

    CREATE TABLE Students (
        StudentID INT PRIMARY KEY,
        First_Name VARCHAR(100),
        Last_Name VARCHAR(100),
        Grade INT,
        GPA DECIMAL(3, 2),
        Enrolled DATE
    );

The table holds 6 columns, with StudentID being the primary key. Among these 6 columns, there are:
- 4 different data types
    - INT
    - VARCHAR(100) 
    - DECIMAL(3, 2)
    - DATE
- 1 constraint
    - PRIMARY KEY

More information on these will be below. But generally, this table creates rows of data containing grade/gpa, name, and enrollment date. A unique integer is used as the identifier for each student.

## Adding Columns

You need to specify the datatype and the (optional) constraint when adding a column. The syntax is simular to creating rows.

    ALTER TABLE table
    ADD column DataType OptionalConstraint
        DEFAULT DefaultValue

## Removing Columns

This feature is very straight forward.

    ALTER TABLE table
    DROP column

**Do note that some databases do not do this, like SQLlite.** You would have to just make a new table.

## Renaming Tables

This is also very straight forward.

    ALTER TABLE table
    RENAME TO NewTable

## Dropping Tables

**DELETE** was mentioned before, which removes a tables schema from a database entirely. But this might not delete data or metadata. This is where **DROP TABLE IF EXISTS** comes in.

    DROP TABLE IF EXISTS table;

Much like **DELETE**'s and whatnot, a table won't be deleted if that table serves as a primary key to other tables.