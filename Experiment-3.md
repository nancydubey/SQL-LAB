# SQL Lab – Experiment 3
## Aim
To perform data retrieval operations using SELECT queries on EMPLOYEE table using sorting, pattern matching and conditional statements.
## Question 1
List all employees and jobs in Department 30 in descending order by salary.

### Query
```sql
SELECT Ename, Job
FROM Employee
WHERE Deptno = 30
ORDER BY Sal DESC;
```

## Question 2
List job and department number of employees whose names are five letters long, begin with “A” and end with “N”.

### Query
```sql
SELECT Job, Deptno
FROM Employee
WHERE Ename LIKE 'A___N';
```

## Question 3
Display the names of employees whose names start with alphabet S.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Ename LIKE 'S%';
```

## Question 4
Display the names of employees whose names end with alphabet S.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Ename LIKE '%S';
```

## Question 5
Display the names of employees working in department number 10 or 20 or 40
OR employees working as clerks, salesman or analyst.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Deptno IN (10,20,40)
OR Job IN ('CLERK','SALESMAN','ANALYST');
```

## Question 6
Display employee number and names for employees who earn commission.

### Query
```sql
SELECT Empno, Ename
FROM Employee
WHERE Comm IS NOT NULL
AND Comm > 0;
```

## Question 7
Display employee number and total salary for each employee.

### Query
```sql
SELECT Empno, (Sal + NVL(Comm,0)) AS Total_Salary
FROM Employee;
```

## Question 8
Display employee number and annual salary for each employee.

### Query
```sql
SELECT Empno, Sal*12 AS Annual_Salary
FROM Employee;
```

## Question 9
Display the names of all employees working as clerks and drawing a salary more than 3000.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Job = 'CLERK'
AND Sal > 3000;
```

## Question 10
Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3000.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Job IN ('CLERK','SALESMAN','ANALYST')
AND Sal > 3000;
```