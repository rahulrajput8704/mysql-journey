-- Table: employees
CREATE TABLE employees (
  id INT,
  name VARCHAR(50),
  age INT,
  salary INT,
  department VARCHAR(50),
  city VARCHAR(50)
);

INSERT INTO employees VALUES
(1, 'Rahul', 24, 25000, 'IT', 'Delhi'),
(2, 'Priya', 28, 45000, 'HR', 'Mumbai'),
(3, 'Aman', 32, 60000, 'IT', 'Delhi'),
(4, 'Neha', 22, 30000, 'Sales', 'Pune'),
(5, 'Vikash', 35, 80000, 'IT', 'Mumbai');


-- use of and/or/between/order by/limit 