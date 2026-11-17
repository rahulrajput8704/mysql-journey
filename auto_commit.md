

Example:
SELECT name, IF(marks >= 33, 'Pass', 'Fail') AS result FROM students;

## 1. AUTOCOMMIT
- ON = Har query auto save
- OFF = Khud COMMIT / ROLLBACK karna padega
SET AUTOCOMMIT = 0;

## 2.COMMIT
Change ko permanent save karne ke liye
COMMIT;

## 3. ROLLBACK
Change ko cancel karke pehle wali state pe wapas jane ke liye
ROLLBACK;