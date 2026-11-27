## SQL Views - Practice
A View is a virtual table created from a SELECT query, it stores no data itself.
Today I created views like it_team, high_salary, delhi_employees, pending_orders.
Practiced JOIN views like emp_orders with WHERE conditions to filter data.

## SQL Views - Practice Notes

1. Simple View: it_team - IT department ke employees
2. Condition View: high_salary - Salary > 50000 wale employees
3. SELECT * View: delhi_employees - Delhi ke employees
4. Other Table View: pending_orders - Pending status wale orders
5. JOIN View: emp_orders - employees2 + orders JOIN
6. JOIN + WHERE View: kasganj_orders - Kasganj + Cancelled nahi
7. JOIN + WHERE View: high_value_orders - Delivered + Amount > 10000

Learned: CREATE VIEW, DROP VIEW, JOIN + WHERE in View.



27 November 2026

-- Tables
DROP TABLE IF EXISTS orders;
DROP TABLE IF EXISTS employees2;

CREATE TABLE employees2 (
    emp_id INT PRIMARY KEY,
    name VARCHAR(50),
    city VARCHAR(50),
    department VARCHAR(50),
    salary INT
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    emp_id INT,
    product VARCHAR(50),
    amount INT,
    status VARCHAR(20),
    FOREIGN KEY (emp_id) REFERENCES employees2(emp_id)
);

-- Data
INSERT INTO employees2 VALUES
(1, 'Arjun', 'Noida', 'IT', 75000),
(2, 'Sneha', 'Lucknow', 'HR', 32000),
(3, 'Vikash', 'Noida', 'Finance', 38000),
(4, 'Anjali', 'Agra', 'IT', 48000),
(5, 'Karan', 'Greater Noida', 'Sales', 29000),
(6, 'Pooja', 'Noida', 'HR', 52000);

INSERT INTO orders VALUES
(201, 1, 'Gaming Laptop', 85000, 'Delivered'),
(202, 2, 'Printer', 16000, 'Pending'),
(203, 3, 'Monitor', 22000, 'Pending'),
(204, 4, 'Keyboard', 3000, 'Delivered'),
(205, 5, 'Office