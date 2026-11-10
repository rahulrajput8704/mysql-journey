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


10 nov 2026-
-- Day 1: INSERT & DELETE in SQL
-- Date: 10 Nov 2026

-- Create a table (if not already created)
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- 1. INSERT - To add new data
-- Insert a single row
INSERT INTO students (id, name, age) VALUES (1, 'Rahul', 20);

-- Insert multiple rows at once
INSERT INTO students (id, name, age) VALUES
(2, 'Priya', 21),
(3, 'Aman', 19);

-- Check if data is inserted or not
SELECT * FROM students;

-- 2. DELETE - To remove data
-- Delete a specific row (WHERE clause is MUST)
DELETE FROM students WHERE id = 3;

-- Delete based on a condition
DELETE FROM students WHERE age < 20;

-- Delete all data (Table will remain, only data will be deleted) - USE CAREFULLY
-- DELETE FROM students;

-- Final check
SELECT * FROM students;