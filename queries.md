-- SQL: ALTER TABLE & DELETE TABLE

-- 1. Create Table
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- 2. ALTER TABLE : Modify the Table Structure

-- Add a new column
ALTER TABLE students ADD email VARCHAR(100);

-- Change data type of a column
ALTER TABLE students MODIFY age BIGINT;

-- Rename a column
ALTER TABLE students RENAME COLUMN email TO student_email;

-- Delete a column
ALTER TABLE students DROP COLUMN student_email;

-- 3. Delete Data (Table will remain)

-- Delete a single row
DELETE FROM students WHERE id = 1;

-- Delete all data
-- DELETE FROM students;

-- 4. Delete the Entire Table

DROP TABLE students;


