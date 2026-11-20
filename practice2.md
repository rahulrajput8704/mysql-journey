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