# Database Normalization 

In databases, normalization is the process of organizing data to reduce duplicate data and prevent errors. Instead of having all forms of data into one table, you split the data into logical tables and connect them with keys + joins. 

While this does require more tables, the benefits are far more. More security, better authentication, less redundancy, cleaner structure, etc. 

## Forms 

The process of normalization is broken down into "normal forms". These are table forms (1NF, 2NF, 3NF) that follow certain procedures and protocols.

### 1NF (1st Normal Form)

Each cell must contain a single atomic value. No repeating groups. 

    user_id | emails
    1       | a@gmail.com, b@gmail.com

The scenario above is not ideal and is not 1NF. Below is good.

    user_id | emails
    1       | a@gmail.com
    1       | b@gmail.com

### 2NF (2nd Normal Form) 

The table must be 2NF & must not have partial dependencies. For instance, lets say an Order table requires OrderID & ProductID as the key. Product name is in the table, but this does not make full sense because that would only rely on ProductID.

You would fix this by moving ProductName to its own seperate Product table.

### 3NF (3rd Normal Form) 

The table must be 2NF & have every column *only* depend on the primary key. Every piece of info in that table must describe the ID of the table, nothing else. 

    Student_ID | Student_Name | Club_Name | Club_Leader | Leader_Email

Imagine having rows like this. This is before 3NF. If a club leader changes his email once, suddenly every student in that club needs to have their information redone. If someone pulls up an older students info and the leader email is wrong, that is dangerous.

To fix this, we create different tables for students and clubs and link them whenever needed.

Students:

    Student_ID | Student_Name | Club_Name

Clubs:

    Club_Name | Club_Leader | Leader_Email

Now, there would be a lot less updating if the email were changed. But if the club name were changed, you would have to fix it for every student as well.

**Realistically, real systems rely on ID's that don't change as opposed to name systems.** Real 3NF systems will look more like this:

Students:

    Student_ID | Student_Name | Club_ID

Clubs:

    Club_ID | Club_Name | Club_Leader | Leader_Email


This is how it is with most systems. **3NF is the industry standard for databases.** You will work with this one the most.

___

## Cybersecurity Relevance

The form of database tables matter more beyond just ease of use and organization. 

### Exploitable Data

Badly structured databases can hold duplicate or old data. If a user exists in a log twice with a new and old password, anyone can access that account with either password. 

### Authentication Flow

Normalized database structure ensures proper tables for different tasks. Roles have proper info, users have proper info, etc. Having simple tables that directly work with each other helps alot in authentication and logging. 

### Prevents injection damage spreading

If all forms of data was in one massive table, everything would be exposed. By having seperate tasks in seperate tables, this lowers the surface of exposure. 