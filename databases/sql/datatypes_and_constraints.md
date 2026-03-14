# Data Types

**Constraints section below this section**

Data can be represented in a multitude of ways. Numerics, letters, date, etc. Different tables and columns will use and handle different data types naturally. Below demonstrates the different data types/

### Numbers

**INT**: Whole number. No decimals.

**BOOLEAN**: True/False.

    age INT,
    enrolled BOOLEAN

### Decimals

**FLOAT** / **DOUBLE**: Numbers with decimals (4.5, 99.99, 100.99182382)

**DECIMAL(T, D)**: Number with a set decimal. T represents how many total digits. D represents how many will be behind the decimal. 

    income FLOAT,
    gpa DECIMAL(3, 2)

gpa would be 0.00 - 9.99.

### Text / Words

**CHAR(n)**: Fixed text length. CHAR(2) = the inserted data MUST be 2 letters.

**VARCHAR(n)**: Variable text length. (n) is a max letters. If VARCHAR(20), the data can be 1-20 letters long but none more.

**TEXT**: No limit. Used for long paragraphs.

    age CHAR(2),
    username VARCHAR(50),
    description TEXT

### Time & Dates

**DATE**: Just the day (YYYY-MM-DD).

**DATETIME**: The day + the exact time down to the second.

    creation_date DATE,
    last_updated DATETIME

### BLOB

**BLOB**: Binary Large Object. This is the actual file data, like image or video data itself. Not something used for like typical "data".

    image_file BLOB

___

# Constraints

Constraints prevent people from putting in random / copied values into a database. These are added next to datatypes when defining a table and its columns.

### PRIMARY KEY

    student_id INT PRIMARY KEY

PRIMARY KEY uniquely identifies every single row. It can **NOT** be empty and can **NOT** be a duplicate. Every table should have one.

Making it a PRIMARY KEY automatically makes the value NOT NULL and UNIQUE (more on that down below).

### AUTOINCREMENT

    student_id INT PRIMARY KEY AUTOINCREMENT

Simply adds from the last number. If the last student had an id of 1, this new student will have an id of 2. It will not be needed to be added manually.

### DEFAULT

    status TEXT DEFAULT 'active'

This autofills a value if a value is not provided.

### UNIQUE

    email TEXT UNIQUE

Ensures no two rows have the same value. You can have multiple unique columns.

### NOT NULL

    username TEXT NOT NULL

NOT NULL makes a column mandatory. The database throws an error if you try to insert null data.

### CHECK (expression)

**This is relevant in general security**. 

    age INT CHECK (age >= 13) # This prevents kids under 13 from signing up to a surface.

This checks the data of a specific condition before letting it be inserted.

## FOREIGN KEY

    FOREIGN KEY (user_id) REFERENCES users(id)

Links a column in one table to the primary key of another table.
