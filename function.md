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