
Date: 10 Nov 2026

-- Table 
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- 1. INSERT - Data daalna
INSERT INTO students (id, name, age) VALUES (1, 'Rahul', 20);

-- Multiple rows 
INSERT INTO students (id, name, age) VALUES
(2, 'Priya', 21),
(3, 'Aman', 19);

SELECT * FROM students;

-- 2. DELETE 
-- Ek specific row hatana
DELETE FROM students WHERE id = 3;


-- Final check
SELECT * FROM students;