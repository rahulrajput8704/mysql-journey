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