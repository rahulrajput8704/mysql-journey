-- 1. Table Banana
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    department VARCHAR(50),
    salary INT,
    city VARCHAR(50)
);

-- 2. Data Dalna
INSERT INTO employees VALUES
(1, 'Rahul', 'IT', 25000, 'Noida'),
(2, 'Priya', 'HR', 22000, 'Delhi'),
(3, 'Amit', 'IT', 30000, 'Noida'),
(4, 'Sneha', 'Finance', 28000, 'Mumbai'),
(5, 'Vikash', 'HR', 20000, 'Delhi'),
(6, 'Pooja', 'IT', 32000, 'Pune'),
(7, 'Rohan', 'Finance', 18000, 'Noida');

-- 3. DELETE Practice

-- Q1. Delhi me rehne wale saare employees ko delete karo
DELETE FROM employees WHERE city = 'Delhi';

-- Q2. Jiski salary 20000 se kam hai, usko delete karo
DELETE FROM employees WHERE salary < 20000;

-- Q3. IT department me jiska naam 'Amit' hai, usko delete karo
DELETE FROM employees WHERE department = 'IT' AND name = 'Amit';

-- Q4. id = 4 wale employee ko delete karo
DELETE FROM employees WHERE id = 4;

-- Q5. HR department ke saare employees ko delete karo, par sirf woh jinki salary 21000 se kam hai
DELETE FROM employees WHERE department = 'HR' AND salary < 21000;

-- Q6. Noida me rehne wale aur Finance department