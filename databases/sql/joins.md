# Joins (and Nulls)

This concepts involves understanding that the real world breaks down data into tables through a process called normalization. For information about NULLs, scroll to the bottom.

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

### Inner Join Example

Table 1: Users

    user_id | username
    1       | alex
    2       | ryan
    3       | connor

Table 2: Logins

    login_id | user_id | login_time
    101      | 1       | 10:00 AM
    102      | 2       | 10:05 AM
    103      | 1       | 11:00 AM

Let's say we only want results where users have actually logged in. Connor should not be on the list.

    SELECT Users.username, logins.login_time
    FROM Users
    INNER JOIN Logins
    ON Users.user_id = Logins.user_id

## Outer Join 

Sometimes, we want to see beyond just what matches in a database. Perhaps we want to see if there is any missing data.

There are three types of outer joins: LEFT, RIGHT, FULL (These are technically labeled LEFT/RIGHT/FULL OUTER JOINS, but you can just label them without OUTER).

### LEFT JOIN (most important)

This reveals everything from your main table. If a corresponding value in the opposite table has no data, it is filled with NULL. 

Table 1: Users

    user_id | username
    1       | alex
    2       | ryan
    3       | connor

Table 2: Logins

    login_id | user_id | login_time
    101      | 1       | 10:00 AM
    102      | 2       | 10:05 AM
    103      | 1       | 11:00 AM

Note that Connor never logs in. Lets do our SQL query.

    SELECT Users.username, logins.login_time
    FROM Users
    LEFT JOIN Logins
    ON Users.user_id = Logins.user_id

Resulting table:

    username | login_time
    alex     | 10:00 AM
    ryan     | 10:05 AM
    connor   | NULL
    alex     | 11:00 AM

Connor appears, despite having no login.

### Right Join

This is the same concept, but Table 2 becomes the main table.

    SELECT Logins.login_id, Users.username, logins.login_time
    FROM Logins
    RIGHT JOIN Users
    ON Logins.user_id = Users.user_id

Result:

    login_id | username   | login_time
    101      | alex       | 10:00 AM
    102      | ryan       | 10:05 AM
    103      | NULL       | 11:00 AM

Note the null. In a real system, this means a non-verified user attempted to log in at 11:00 A.M.

### Full Join

This is just a mix of left and right join.

    SELECT Logins.login_id, Users.username, logins.login_time
    FROM Logins
    FULL JOIN Users
    ON Logins.user_id = Users.user_id

Result:

    login_id | username   | login_time
    101      | alex       | 10:00 AM
    102      | ryan       | 10:05 AM
    103      | NULL       | 11:00 AM
    NULL     | connor     | NULL

Connor is there, but with no login information. Perhaps connor is a test account. That login_id with 103 though would still be a bit of concern.

___

# Nulls

Nulls signify the absence of a value. Not zero, not false. It just means that **there is literally no data in that value.**

User never logs in = login_time will be NULL.
Unknown email = email NULL. 

## SQL Behavior

You can NOT compare NULL like a normal value.

    WHERE login_time = NULL

... would not work. You can't compare with an unknown value.

CORRECT (either one):

    WHERE login_time IS NULL
    WHERE login_TIME IS NOT NULL

NULL also spreads through queries. If you try to do math or operations with a NULL value, the resulting value will just end up being NULL. Seeing this often signals missing relationships or data.

## Cybersecurity Relevance

NULLs can detect suspicious activity in a variety of ways. NULL values, like in the context of login attempts, can show attempts to access something without a proper entry in the system. A NULL user with multiple login attempts could directly mean an authorized user trying to breach.

You will see this alot in:

- Failed logins
- Missing user data
- Unlinked records
- Incomplete logs

NULL often signifies something worth checking out.






