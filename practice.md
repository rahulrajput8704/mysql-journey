-- Day: Foreign Key + JOIN Practice

-- 1. FOREIGN KEY - ON DELETE CASCADE
CREATE TABLE countries (code INT PRIMARY KEY, name VARCHAR(20));
CREATE TABLE cities (id INT PRIMARY KEY, name VARCHAR(20), country_code INT,
FOREIGN KEY (country_code) REFERENCES countries(code) ON DELETE CASCADE);
-- Country delete hote hi uski cities bhi auto delete

-- 2. FOREIGN KEY - ON DELETE SET NULL
CREATE TABLE departments (id INT PRIMARY KEY, name VARCHAR(20));
CREATE TABLE employees (id INT PRIMARY KEY, name VARCHAR(20), dept_id INT,
FOREIGN KEY (dept_id) REFERENCES departments(id) ON DELETE SET NULL);
-- Dept delete hone par employee rahega, dept_id NULL ho jayega

-- 3. FOREIGN KEY - ON DELETE RESTRICT
CREATE TABLE authors (id INT PRIMARY KEY, name VARCHAR(20));
CREATE TABLE books (id INT PRIMARY KEY, title VARCHAR(20), author_id INT,
FOREIGN KEY (author_id) REFERENCES authors(id) ON DELETE RESTRICT);
-- Jab tak books hain, author delete nahi hoga

-- 4. FOREIGN KEY - ON UPDATE CASCADE
-- countries me code 91 -> 99 kiya toh cities me bhi auto 99 ho gaya

-- 5. JOINS
CREATE TABLE users (id INT, name VARCHAR(20));
CREATE TABLE orders (id INT, user_id INT, item VARCHAR(20));
INSERT INTO users VALUES (1,'Rahul'), (2,'Amit'), (3,'Priya');
INSERT INTO orders VALUES (1,1,'Laptop'), (2,1,'Mouse'), (3,2,'Phone');

-- INNER JOIN: Sirf wo jinhone order kiya (Rahul, Amit)
SELECT * FROM users INNER JOIN orders ON users.id = orders.user_id;

-- LEFT JOIN: Saare users, Priya ke aage NULL
SELECT * FROM users LEFT JOIN orders ON users.id = orders.user_id;

-- RIGHT JOIN: Saare orders, Priya nahi aayegi
SELECT * FROM users RIGHT JOIN orders ON users.id = orders.user_id;

-- Jin users ne koi order nahi kiya (Priya)
SELECT * FROM users LEFT JOIN orders ON users.id = orders.user_id WHERE orders.id IS NULL;