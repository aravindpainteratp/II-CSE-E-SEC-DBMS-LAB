CREATE TABLE EMPLOYEEs (
    EMPLOYEE_ID NUMBER(5) PRIMARY KEY,
    FIRST_NAME VARCHAR2(20),
    LAST_NAME VARCHAR2(20),
    GENDER CHAR(1),
    JOB_ID VARCHAR2(20),
    DEPARTMENT VARCHAR2(20),
    SALARY NUMBER(10,2),
    COMMISSION NUMBER(5),
    HIRE_DATE DATE,
    CITY VARCHAR2(20)
);
![output](<Screenshot (79).png>)

INSERT INTO EMPLOYEE VALUES
(101, 'John', 'Smith', 'M', 'IT_PROG', 'IT', 65000, 5, 
TO_DATE('15-JAN-2020','DD-MON-YYYY'), 'Hyderabad');
![output](<Screenshot (80).png>)

INSERT INTO EMPLOYEE VALUES
(102, 'Anita', 'Sharma', 'F', 'HR_REP', 'HR', 52000, 3, 
TO_DATE('10-JUN-2019','DD-MON-YYYY'), 'Bengaluru');
![output](<Screenshot (81).png>)

INSERT INTO EMPLOYEE VALUES
(103, 'Rahul', 'Kumar', 'M', 'SA_REP', 'Sales', 48000, 8, 
TO_DATE('25-AUG-2021','DD-MON-YYYY'), 'Chennai');

INSERT INTO EMPLOYEE VALUES
(104, 'Priya', 'Reddy', 'F', 'MK_MAN', 'Marketing', 72000, 10, 
TO_DATE('05-MAR-2018','DD-MON-YYYY'), 'Hyderabad');

INSERT INTO EMPLOYEE VALUES
(105, 'David', 'Wilson', 'M', 'FI_ACCOUNT', 'Finance', 58000, NULL, 
TO_DATE('18-DEC-2017','DD-MON-YYYY'), 'Mumbai');

INSERT INTO EMPLOYEE VALUES
(106, 'Sneha', 'Patel', 'F', 'IT_PROG', 'IT', 69000, 6, 
TO_DATE('12-NOV-2022','DD-MON-YYYY'), 'Pune');

INSERT INTO EMPLOYEE VALUES
(107, 'Amit', 'Verma', 'M', 'SA_REP', 'Sales', 45000, 4, 
TO_DATE('20-JUL-2023','DD-MON-YYYY'), 'Delhi');

INSERT INTO EMPLOYEE VALUES
(108, 'Kiran', 'Rao', 'M', 'HR_REP', 'HR', 50000, NULL, 
TO_DATE('09-FEB-2021','DD-MON-YYYY'), 'Hyderabad');

INSERT INTO EMPLOYEE VALUES
(109, 'Lakshmi', 'Nair', 'F', 'IT_PROG', 'IT', 76000, 7, 
TO_DATE('14-SEP-2016','DD-MON-YYYY'), 'Kochi');

INSERT INTO EMPLOYEE VALUES
(110, 'Arjun', 'Singh', 'M', 'MK_MAN', 'Marketing', 68000, 5, 
TO_DATE('30-APR-2019','DD-MON-YYYY'), 'Jaipur');
![output](<Screenshot (82).png>)
![output](<Screenshot (83).png>)
COMMIT;

SELECT * FROM EMPLOYEE;

QUESTION1
SELECT employee_id,
       first_name,
       TO_CHAR(hire_date, 'DD-MON-YYYY') AS hire_date
FROM employee;
![output](<Screenshot (84).png>)
Q2
SELECT employee_id,
       first_name,
       TO_CHAR(salary, 'L9,999,999.00') AS salary
FROM employee;
![output](<Screenshot (85).png>)
Q3
SELECT employee_id,
       first_name,
       TO_NUMBER(salary) + 5000 AS new_salary
FROM employee;
![output ](<Screenshot (86).png>)
Q4
SELECT *
FROM employee
WHERE hire_date > TO_DATE('01-JAN-2020', 'DD-MON-YYYY');
![output](<Screenshot (87).png>)
Q5
SELECT employee_id,
       first_name || ' ' || last_name AS full_name
FROM employee;
![output](<Screenshot (88).png>)
Q6
SELECT employee_id,
       CONCAT(CONCAT(first_name, ' '), last_name) AS full_name
FROM employee;
![output](<Screenshot (89).png>)
Q7
SELECT first_name,
       LPAD(first_name, 10, '*') AS padded_name
FROM employee;

![output](<Screenshot (90).png>)
Q8
SELECT first_name,
       RPAD(first_name, 10, '*') AS padded_name
FROM employee;
![output](<Screenshot (91).png>)
Q9
SELECT LTRIM(first_name) AS trimmed_name
FROM employee;

Q10
SELECT RTRIM(first_name) AS trimmed_name
FROM employee;

Q11
SELECT LOWER(first_name) AS first_name
FROM employee;

Q13
SELECT INITCAP(first_name) AS first_name
FROM employee;
Q14
SELECT first_name,
       LENGTH(first_name) AS name_length
FROM employee;

Q15
SELECT first_name,
       SUBSTR(first_name, 1, 3) AS first_three_chars
FROM employee;
Q16
SELECT first_name,
       INSTR(LOWER(first_name), 'a') AS position_of_a
FROM employee;

Q17
SELECT employee_id,
       first_name,
       last_name,
       hire_date,
       salary,
       SYSDATE AS current_date
FROM employee;
Q18
SELECT employee_id,
       first_name,
       hire_date,
       NEXT_DAY(hire_date, 'MONDAY') AS next_monday
FROM employee;
Q19
SELECT employee_id,
       first_name,
       hire_date,
       ADD_MONTHS(hire_date, 6) AS date_after_six_months
FROM employee;
Q20
FROM employee;
SELECT * FROM EMPLOYEE;
SELECT employee_id,
       first_name,
       hire_date,
       MONTHS_BETWEEN(SYSDATE, hire_date) AS months_worked
       first_name,
       hire_date,
SELECT employee_id,
       LAST_DAY(hire_date) AS last_day_of_month
FROM employee;

SELECT * FROM EMPLOYEE;

Q1
CREATE VIEW EMP_VIEW AS
SELECT *
FROM EMPLOYEE;

<img width="1920" height="1080" alt="Screenshot (105)" src="https://github.com/user-attachments/assets/c59de322-8c44-4f10-8e1c-d5002034d826" />

Q2
CREATE VIEW EMP_BASIC AS
SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME, DEPARTMENT, SALARY
FROM EMPLOYEE;

<img width="1920" height="1080" alt="Screenshot (106)" src="https://github.com/user-attachments/assets/de8e072c-0cc2-4f30-8e9f-ec3364f1f515" />

Q3
SELECT *
FROM EMP_VIEW;
<img width="1920" height="1080" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/ac492804-7d82-4f19-9de7-d87e0cc0231f" />

Q4
CREATE VIEW IT_EMPLOYEES AS
SELECT *
FROM EMPLOYEE
WHERE DEPARTMENT = 'IT';
<img width="1920" height="1080" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/bb6d0316-a0ea-43e7-b42e-624433f14fdd" />

Q5
CREATE VIEW HIGH_SALARY AS
SELECT *
FROM EMPLOYEE
WHERE SALARY > 60000;
<img width="1920" height="1080" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/4b392ec4-2b95-445d-8dc0-fd909a95de53" />

Q6
CREATE VIEW HYDERABAD_EMP AS
SELECT *
FROM EMPLOYEE
WHERE CITY = 'Hyderabad';
<img width="1920" height="1080" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/d0755229-b2a4-49ee-948d-86f5f122e991" />

Q7
CREATE VIEW FEMALE_EMP AS
SELECT *
FROM EMPLOYEE
WHERE GENDER = 'Female';
<img width="1920" height="1080" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/c9f775a5-ab62-4a28-a581-241164206499" />

Q8
CREATE VIEW RECENT_EMPLOYEES AS
SELECT *
FROM EMPLOYEE
WHERE HIRE_DATE >= TO_DATE('01-JAN-2020','DD-MON-YYYY');
<img width="1920" height="1080" alt="Screenshot (112)" src="https://github.com/user-attachments/assets/447b8789-32c6-4f34-81c0-50c0da727f4c" />

Q9
SELECT EMPLOYEE_ID, FIRST_NAME, SALARY
FROM HIGH_SALARY;
<img width="1920" height="1080" alt="Screenshot (113)" src="https://github.com/user-attachments/assets/5626dcf1-0c77-4087-b667-57aa1025c52c" />

Q10
CREATE OR REPLACE VIEW EMP_BASIC AS
SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME,
       DEPARTMENT, SALARY, CITY
FROM EMPLOYEE;
<img width="1920" height="1080" alt="Screenshot (114)" src="https://github.com/user-attachments/assets/c138757c-725f-49ed-878e-4e630ffe4d47" />

Q11
CREATE VIEW EMP_SALARY_VIEW AS
SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME, SALARY
FROM EMPLOYEE
WITH READ ONLY;

Q12
CREATE VIEW SALES_EMP AS
SELECT *
FROM EMPLOYEE
WHERE DEPARTMENT = 'Sales'
WITH CHECK OPTION;
<img width="1920" height="1080" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/c197d241-86b2-4884-8a12-c5e6bfb0099a" />

Q13
UPDATE EMP_BASIC
SET SALARY = 75000
WHERE EMPLOYEE_ID = 101;

COMMIT;
<img width="1920" height="1080" alt="Screenshot (116)" src="https://github.com/user-attachments/assets/9a6ff176-f99f-44ba-8c93-485e242a6f7f" />

Q14
DELETE FROM EMP_VIEW
WHERE EMPLOYEE_ID = 107;

COMMIT;
<img width="1920" height="1080" alt="Screenshot (117)" src="https://github.com/user-attachments/assets/1b737005-63c4-4e7f-b260-b1a2023e85a1" />

Q15
INSERT INTO EMP_BASIC
VALUES (111, 'Ravi', 'Kumar', 'IT', 50000, 'Hyderabad');

COMMIT;
<img width="1920" height="1080" alt="Screenshot (118)" src="https://github.com/user-attachments/assets/116a1cb9-3819-4eb9-95be-e34071243aed" />

Q16
DESC EMP_BASIC;

Q17
SELECT *
FROM IT_EMPLOYEES;
<img width="1920" height="1080" alt="Screenshot (119)" src="https://github.com/user-attachments/assets/be6135b3-ebc5-4a6e-8152-3c3bec0b9ecb" />

Q18
SELECT *
FROM HIGH_SALARY
<img width="1920" height="1080" alt="Screenshot (120)" src="https://github.com/user-attachments/assets/c767e149-253d-499b-835f-ab805ea15882" />


Q19
SELECT *
FROM FEMALE_EMP;

Q20
SELECT FIRST_NAME, SALARY
FROM HYDERABAD_EMP;

Q21
DROP VIEW EMP_VIEW;

Q22
DROP VIEW HIGH_SALARY;

Q23
DROP VIEW EMP_BASIC;

Q24
CREATE VIEW HR_EMPLOYEES AS
SELECT *
FROM EMPLOYEE
WHERE DEPARTMENT = 'HR';

Q25
CREATE VIEW MARKETING_EMP AS
SELECT EMPLOYEE_ID, FIRST_NAME, DEPARTMENT, SALARY
FROM EMPLOYEE
WHERE DEPARTMENT = 'Marketing';

Q26
CREATE VIEW TOP_EARNERS AS
SELECT *
FROM EMPLOYEE
WHERE SALARY > 70000;

Q27
CREATE VIEW EMP_CITY AS
SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME, CITY
FROM EMPLOYEE;

