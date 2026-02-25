# SQL Lab – Experiment 2

## Aim
To perform data retrieval operations using SELECT queries on EMPLOYEE table.

## Question 1
List all distinct jobs in Employee table.

### Query
```sql
SELECT DISTINCT Job
FROM Employee;
```
## Question 2
List all information about employees in Department Number 30.

### Query
```sql
SELECT *
FROM Employee
WHERE Deptno = 30;
```
### Query
```sql
SELECT *
FROM Employee
WHERE Job = 'MANAGER'
AND Deptno <> 30;
```
## Question 4
Find Employees and jobs earning between 1200 and 1400.

### Query
```sql
SELECT Ename, Job
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;
```
## Question 5
List Name and Department Number of employees whose names begin with M.

### Query
```sql
SELECT Ename, Deptno
FROM Employee
WHERE Ename LIKE 'M%';
```
## Question 6
Find all managers not in department 30.

### Query
```sql
SELECT *
FROM Employee
WHERE Job = 'MANAGER'
AND Deptno <> 30;
```
## Question 7
List information about all employees in department 10 who are not managers or clerks.

### Query
```sql
SELECT *
FROM Employee
WHERE Deptno = 10
AND Job NOT IN ('MANAGER','CLERK');
```
## Question 8
Find employees and jobs earning between 1200 and 1400.

### Query
```sql
SELECT Ename, Job
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;
```
## Question 9
List name and department number of employees who are clerks, analysts or salesmen.

### Query
```sql
SELECT Ename, Deptno
FROM Employee
WHERE Job IN ('CLERK','ANALYST','SALESMAN');
```

## Question 10
List name and department number of employees whose names begin with M.

### Query
```sql
SELECT Ename, Deptno
FROM Employee
WHERE Ename LIKE 'M%';
```
