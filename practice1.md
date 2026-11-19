-- CREATE TABLE
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    city VARCHAR(50),
    age INT,
    marks INT
);

-- INSERT Practice
INSERT INTO students(id, name, city, age, marks) VALUES(1, 'Rahul', 'Delhi', 20, 85);
INSERT INTO students(id, name, city, age, marks) VALUES(2, 'Priya', 'Mumbai', 22, 90), (3, 'Aman', 'Delhi', 19, 75), (4, 'Sana', 'Jaipur', 21, 88);
INSERT INTO students(id, name) VALUES(5, 'Vikash');
INSERT INTO students(name, id, city, age, marks) VALUES('Neha', 6, 'Noida', 23, 92);

-- UPDATE Practice
UPDATE students SET marks = 95 WHERE id = 1;
UPDATE students SET marks = marks + 5 WHERE city = 'Delhi';
UPDATE students SET city = 'Pune', age = 20 WHERE id = 3;
UPDATE students SET city = 'Kanpur' WHERE marks < 80;
UPDATE students SET age = age + 1;
UPDATE students SET name = 'Priya Sharma' WHERE id = 2 AND marks > 85;




# SQL Practice -  | ORDER BY + GROUP BY

## Table: std2
| name | course | marks |
| :--- | :--- | :--- |
| Aman | Java | 85 |
| Rahul | Java | 78 |
| Anjali | Java | 95 |
| Priya | Python | 92 |
| Vikash | Python | 65 |
| Sneha | SQL | 88 |

## Queries
-- Q7. Har course me kitne students hai?
select course, count(*) from std2 group by course;
-- Result: Java - 3, Python - 2, SQL - 1

-- Q8. Har course ka average marks
select course, avg(marks) as average from std2 group by course;
-- Result: Java - 86, Python - 78.5, SQL - 88

-- Q9. Sirf Java walo ka average
select avg(marks) as java_average from std2 where course = 'Java';
-- Result: 86.0000

-- Q10. Sabse zyada marks wala student
select name, marks from std2 order by marks desc limit 1;
-- Result: Anjali - 95

-- Q11. Pehle course A-Z, fir usi course me marks zyada se kam
select name, course, marks from std2 order by course asc, marks desc;

## Key Learnings
-- 1. ASC = A-Z / Chhota se Bada (Default), DESC = Z-A / Bada se Chhota
-- 2.