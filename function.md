-- MySQL Aggregate Functions
-- Date: 15 Nov 2026

-- 1. COUNT() - Total rows count karta hai
SELECT COUNT(*) AS total_students FROM students;
SELECT COUNT(name) FROM students;

-- 2. MIN() and MAX() - Sabse chota aur sabse bada value
SELECT MIN(marks) AS lowest_marks FROM students;
SELECT MAX(marks) AS highest_marks FROM students;

-- 3. SUM() - Total sum nikalta hai
SELECT SUM(marks) AS total_marks FROM students;
SELECT SUM(price) AS total_price FROM products;

4.SELECT MOD(10, 3);
-- Output: 1

SELECT MOD(15, 4);
-- Output: 3

SELECT * FROM students WHERE MOD(id, 2) = 0;

5.SELECT CONCAT('Hello', ' ', 'Bhai');
-- Output: Hello Bhai

SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM students;


 6.LENGTH()

```sql
SELECT LENGTH('Hello');
-- Output: 5

SELECT name, LENGTH(name) FROM students;

7.SELECT AVG(marks) FROM students;
-- Output: saare students ke marks ka average

SELECT AVG(salary) FROM employees;