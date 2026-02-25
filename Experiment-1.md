# SQL Lab – Experiment 1
## Aim
To create EMPLOYEE and DEPARTMENT tables:
## Question 
Create DEPARTMENT and EMPLOYEE tables .
### Query
```sql
CREATE TABLE DEPARTMENT(
  Deptno NUMBER(2) PRIMARY KEY,
  Dname VARCHAR2(15) NOT NULL
);
CREATE TABLE EMPLOYEE(
  Empno NUMBER(4) PRIMARY KEY,
  Ename VARCHAR2(20) NOT NULL,
  Job VARCHAR2(20),
  Mgr NUMBER(4),
  Hiredate DATE,
  Sal NUMBER(10),
  Comm NUMBER(7),
  Deptno NUMBER(2),
  FOREIGN KEY (Deptno) REFERENCES DEPARTMENT(Deptno)
);
```
## Question 
Insert records into DEPARTMENT table.
### Query
```sql
INSERT INTO DEPARTMENT VALUES(10,'RESEARCH');
INSERT INTO DEPARTMENT VALUES(20,'ACCOUNTING');
INSERT INTO DEPARTMENT VALUES(30,'SALES');
INSERT INTO DEPARTMENT VALUES(40,'OPERATIONS');
```
## Question 
Insert records into EMPLOYEE table.
### Query
```sql
INSERT INTO EMPLOYEE VALUES(7369,'SMITH','CLERK',7902,TO_DATE('17-12-1980','DD-MM-YYYY'),800,NULL,20);
INSERT INTO EMPLOYEE VALUES(7499,'ALLEN','SALESMAN',7698,TO_DATE('20-02-1981','DD-MM-YYYY'),1600,300,30);
INSERT INTO EMPLOYEE VALUES(7521,'WARD','SALESMAN',7698,TO_DATE('22-02-1981','DD-MM-YYYY'),1250,300,30);
INSERT INTO EMPLOYEE VALUES(7566,'JONES','MANAGER',7839,TO_DATE('02-04-1981','DD-MM-YYYY'),2975,NULL,20);
INSERT INTO EMPLOYEE VALUES(7839,'KING','PRESIDENT',NULL,TO_DATE('17-11-1981','DD-MM-YYYY'),5000,NULL,20);
```
## Question 1
Create Employee_master table from Employee table.

### Query
```sql
CREATE TABLE Employee_master AS
SELECT * FROM Employee;
```
## Question 2
Delete records from Employee_master where Deptno = 10.

### Query
```sql
DELETE FROM Employee_master
WHERE Deptno = 10;
```
## Question 3
Update salary by 10% for Deptno = 20 in Employee_master.

### Query
```sql
UPDATE Employee_master
SET Sal = Sal * 1.10
WHERE Deptno = 20;
```
## Question 4
Alter salary column size in Employee_master.

### Query
```sql
ALTER TABLE Employee_master
MODIFY Sal NUMBER(10,2);
```
## Question 5
Drop Employee_master table.

### Query
```sql
DROP TABLE Employee_master;
```