

-- Sample Table
CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    age INT,
    city VARCHAR(50)
);

INSERT INTO students VALUES
(1, 'Rahul', 20, 'Ghaziabad'),
(2, 'Priya', 22, 'Delhi'),
(3, 'Aman', 19, 'Noida'),
(4, 'Sana', 25, 'Ghaziabad');

-- 1. WHERE Clause - Used to filter records
SELECT * FROM students WHERE city = 'Ghaziabad';
SELECT * FROM students WHERE age > 20;

-- 2. AND Operator - Both conditions must be true
SELECT * FROM students WHERE city = 'Ghaziabad' AND age > 20;

-- 3. OR Operator - Any one condition can be true
SELECT * FROM students WHERE city = 'Delhi' OR city = 'Noida';

-- 4. AND + OR Combined
SELECT * FROM students WHERE (city = 'Ghaziabad' OR city = 'Delhi') AND age >= 20;

-- 5. BETWEEN Operator - Value within a range (inclusive)
SELECT * FROM students WHERE age BETWEEN 20 AND 25;
-- Same as: age >= 20 AND age <= 25
