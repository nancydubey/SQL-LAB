# SQL Lab – Experiment 5

## Aim
To perform aggregate and string function operations on EMPLOYEE table.

## Question 1
Display the total number of employees working in the company.

### Query
```sql
SELECT COUNT(*) FROM Employee;
```

## Question 2
Display the total salary being paid to all employees.

### Query
```sql
SELECT SUM(Sal) FROM Employee;
```

## Question 3
Display the maximum salary from Employee table.

### Query
```sql
SELECT MAX(Sal) FROM Employee;
```

## Question 4
Display the minimum salary from Employee table.

### Query
```sql
SELECT MIN(Sal) FROM Employee;
```

## Question 5
Display the average salary from Employee table.

### Query
```sql
SELECT AVG(Sal) FROM Employee;
```

## Question 6
Display the maximum salary being paid to clerk.

### Query
```sql
SELECT MAX(Sal)
FROM Employee
WHERE Job='CLERK';
```

## Question 7
Display the maximum salary being paid in Deptno 20.

### Query
```sql
SELECT MAX(Sal)
FROM Employee
WHERE Deptno=20;
```

## Question 8
Display the minimum salary paid to any salesman.

### Query
```sql
SELECT MIN(Sal)
FROM Employee
WHERE Job='SALESMAN';
```

## Question 9
Display the average salary drawn by managers.

### Query
```sql
SELECT AVG(Sal)
FROM Employee
WHERE Job='MANAGER';
```

## Question 10
Display the total salary drawn by analyst working in Deptno 40.

### Query
```sql
SELECT SUM(Sal)
FROM Employee
WHERE Job='ANALYST' AND Deptno=40;
```

## Question 11
Display the names of the employee in uppercase.

### Query
```sql
SELECT UPPER(Ename) FROM Employee;
```

## Question 12
Display the names of the employee in lowercase.

### Query
```sql
SELECT LOWER(Ename) FROM Employee;
```

## Question 13
Display the names of the employee in proper case.

### Query
```sql
SELECT INITCAP(Ename) FROM Employee;
```

## Question 14
Display the length of your name using appropriate function.

### Query
```sql
SELECT LENGTH('NANCY') FROM DUAL;
```

## Question 15
Display the length of all employee names.

### Query
```sql
SELECT Ename, LENGTH(Ename) FROM Employee;
```