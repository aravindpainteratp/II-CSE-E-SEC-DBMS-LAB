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
![output](Screenshot (79).png)

INSERT INTO EMPLOYEE VALUES
(101, 'John', 'Smith', 'M', 'IT_PROG', 'IT', 65000, 5, 
TO_DATE('15-JAN-2020','DD-MON-YYYY'), 'Hyderabad');
![output](Screenshot (80).png)

INSERT INTO EMPLOYEE VALUES
(102, 'Anita', 'Sharma', 'F', 'HR_REP', 'HR', 52000, 3, 
TO_DATE('10-JUN-2019','DD-MON-YYYY'), 'Bengaluru');
![output](Screenshot (81).png)

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
![output](Screenshot (82).png)
![output](Screenshot (83).png)
COMMIT;

SELECT * FROM EMPLOYEE;

QUESTION1
SELECT employee_id,
       first_name,
       TO_CHAR(hire_date, 'DD-MON-YYYY') AS hire_date
FROM employee;
![output](Screenshot (84).png)
Q2
SELECT employee_id,
       first_name,
       TO_CHAR(salary, 'L9,999,999.00') AS salary
FROM employee;
![output](Screenshot (85).png)
Q3
SELECT employee_id,
       first_name,
       TO_NUMBER(salary) + 5000 AS new_salary
FROM employee;
![output (Screenshot (86).png)
Q4
SELECT *
FROM employee
WHERE hire_date > TO_DATE('01-JAN-2020', 'DD-MON-YYYY');
![output](Screenshot (87).png)
Q5
SELECT employee_id,
       first_name || ' ' || last_name AS full_name
FROM employee;
![output](Screenshot (88).png)
Q6
SELECT employee_id,
       CONCAT(CONCAT(first_name, ' '), last_name) AS full_name
FROM employee;
![output](Screenshot (89).png)
Q7
SELECT first_name,
       LPAD(first_name, 10, '*') AS padded_name
FROM employee;
![output](Screenshot (90).png)
Q8
SELECT first_name,
       RPAD(first_name, 10, '*') AS padded_name
FROM employee;
![output](Screenshot (91).png)
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
