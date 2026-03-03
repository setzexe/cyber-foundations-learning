# Schema

When it comes to databases, organization is required. If you had 1000 student AND school files, then proceeded dumped them all in one database, it would just be a mess. It would be super unorganzied meaning you would not be able to access what you want easily.

**Schema** exists to prevent this. Schema works as the blueprint / skeleton of a database. It defines how data is organized, structured, and related. However, the schema does not contain any data itself. It is moreso the layout of how everything works. 

## Core Components 

The main components you want to include in a schema are:

- Tables
    - The main storage containers. These contain the data itself.
- Fields (Columns)
    - Fields, or columns, are the specific types of data you would put in a table. Email, name, order_date, etc. 
- Data Typest
    - Rules on what type of data can go where. **INT** for numbers, **VARCHAR** for text, DATE for dates. A name should only be VARCHAR, and id's should usually just be an INT.
- Relationships
    - How tables connect. The SELECT query uses **JOIN** for this. This is usually done through *Primary Keys* (unique ID) and *Foreign Keys* (linking to another table)
- Constraints
    - Rules enforced by the database itself (Normalization, UNIQUE/NOT NULL on values, etc)

## Why do we use Schema's?

There are three primary reasons that schema's tend to be useful:

- Organization
    - The main one, it keeps data organized. It keeps a logical map of your data so that accessability is easier.
- Accuracy
    - Stops invalid data from being entered. For example, a database with no schema (meaning no constraints) might allow an INT type on a *name* field.
- Security
    - As related to accuracy, this also allows restrictions or constraints to doing certain things. If a field  should not take integers, schema constraints help with this. Thus, any queries that attempt to bypass this should fail. 

## Schema Creation (Simple)

DDL (Data Definition Language) is used to define schemas. DDL is just a subset of SQL. SQL has multiple subsets.

    CREATE TABLE Users (
        user_id INT PRIMARY KEY,
        username VARCHAR(20) NOT NULL,
        email VARCHAR(50) UNIQUE
    )

Users = The table itself.

user_id, username, email = Fields.

NOT NULL, UNIQUE = constraints.