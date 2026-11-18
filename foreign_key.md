

-- 1. Parent Table
CREATE TABLE courses (
    id INT PRIMARY KEY,
    course_name VARCHAR(50)
);

-- 2. Child Table with FOREIGN KEY
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    course_id INT,
    FOREIGN KEY (course_id) REFERENCES courses(id)
);

-- 3. Data Insert - Pehle Parent me
INSERT INTO courses VALUES (1, 'MySQL'), (2, 'Java');

-- Fir Child me
INSERT INTO students VALUES (101, 'Aman', 1);
INSERT INTO students VALUES (102, 'Rahul', 2);

-- Ye FAIL hoga, kyuki course 99 exist nahi karta
-- INSERT INTO students VALUES (103, 'Ravi', 99);

-- 4. JOIN karke dekhna
SELECT students.name, courses.course_name
FROM students
JOIN courses ON students.course_id = courses.id;

-- 5. FOREIGN KEY with ON DELETE CASCADE
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    student_id INT,
    FOREIGN KEY (student_id) REFERENCES students(id)
    ON DELETE CASCADE
    ON UPDATE CASCADE
);

-- 6. Baad me FOREIGN KEY Add karna
-- ALTER TABLE students ADD CONSTRAINT fk_course
-- FOREIGN KEY (course_id) REFERENCES courses(id);