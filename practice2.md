-- Foreign Key + JOIN Practice

CREATE TABLE std3 (
    student_id INT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE fee (
    fee_id INT PRIMARY KEY,
    student_id INT,
    amount INT,
    FOREIGN KEY (student_id) REFERENCES std3(student_id)
);

INSERT INTO std3 VALUES (1, 'Rahul'), (2, 'Priya'), (3, 'amit');
INSERT INTO fee VALUES (101, 1, 5000), (102, 2, 6000);

-- INNER JOIN: Sirf fees wale student
SELECT name, amount FROM std3
INNER JOIN fee ON std3.student_id = fee.student_id;

-- LEFT JOIN: Saare student, fees ho ya na ho
SELECT name, amount FROM std3
LEFT JOIN fee ON std3.student_id = fee.student_id;
-- Output: Rahul-5000, Priya-6000, amit-NULL



21 November 2026--- Day: Foreign Keys Practice

-- 1. CASCADE: Parent delete -> Child auto-delete
CREATE TABLE channel (id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(50));
CREATE TABLE video (
  id INT PRIMARY KEY AUTO_INCREMENT,
  title VARCHAR(100),
  channel_id INT,
  FOREIGN KEY (channel_id) REFERENCES channel(id)
  ON DELETE CASCADE ON UPDATE CASCADE
);

-- 2. SET NULL: Parent delete -> Child bachega, FK NULL ho jayega
CREATE TABLE users (id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(50));
CREATE TABLE post (
  id INT PRIMARY KEY AUTO_INCREMENT,
  caption VARCHAR(100),
  user_id INT,
  FOREIGN KEY (user_id) REFERENCES users(id)
  ON DELETE SET NULL ON UPDATE CASCADE
);

-- 3. RESTRICT: Parent delete nahi hoga jab tak Child hai
CREATE TABLE author (id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(50));
CREATE TABLE book (
  id INT PRIMARY KEY AUTO_INCREMENT,
  title VARCHAR(100),
  author_id INT,
  FOREIGN KEY (author_id) REFERENCES author(id)
  ON DELETE RESTRICT ON UPDATE CASCADE
);


23 November 2026--- Q1 INNER JOIN
SELECT employee.emp_name, department.dept_name
FROM employee
INNER JOIN department ON employee.dept_id = department.dept_id;

-- Q2 LEFT JOIN
SELECT employee.emp_name, department.dept_name
FROM employee
LEFT JOIN department ON employee.dept_id = department.dept_id;

-- Q3 RIGHT JOIN
SELECT employee.emp_name, department.dept_name
FROM employee
RIGHT JOIN department ON employee.dept_id = department.dept_id;

-- Q4 FULL JOIN using UNION
SELECT employee.emp_name, department.dept_name
FROM employee
LEFT JOIN department ON employee.dept_id = department.dept_id
UNION
SELECT employee.emp_name, department.dept_name
FROM employee
RIGHT JOIN department ON employee.dept_id = department.dept_id;


24 November 2026-
# Self Join - Short Notes

## 1. What is Self Join?
Joining a table with itself.
Used when Employee and Manager are in the same table.

We give the same table 2 different names, so MySQL does not get confused.
- `e` = Employee copy
- `m` = Manager copy

## 2. Golden Rules
- Never write a column without alias, it will give an error. Always use `e.` or `m.`
- Order can be changed: `e.manager_id = m.emp_id` = `m.emp_id = e.manager_id`
- Order is always: `JOIN -> ON -> WHERE`
- `WHERE` never comes before `ON`.

## 3. Q1 - Employee + His Manager
```sql
SELECT e.name AS employee, m.name AS manager
FROM employees AS e
LEFT JOIN employees AS m
ON e.manager_id = m.emp_id;