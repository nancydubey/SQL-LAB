# SQL Lab – Experiment 4

## Aim
To perform pattern matching, date operations and salary calculations on EMPLOYEE table.

## Question 1
Display the list of employees who have joined before 30th June 1980 or after 31st December 1981.

### Query
```sql
SELECT *
FROM Employee
WHERE Hiredate < TO_DATE('30-06-1980','DD-MM-YYYY')
OR Hiredate > TO_DATE('31-12-1981','DD-MM-YYYY');
```

## Question 2
Display the names of employees whose names have second alphabet A in their names.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Ename LIKE '_A%';
```

## Question 3
Display the names of employees whose name is exactly five characters in length.

### Query
```sql
SELECT Ename
FROM Employee
WHERE LENGTH(Ename) = 5;
```

## Question 4
Display the names of employees whose names have second alphabet A in their names.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Ename LIKE '_A%';
```

## Question 5
Display the names of employees who are not working as salesman, clerk or analyst.

### Query
```sql
SELECT Ename
FROM Employee
WHERE Job NOT IN ('SALESMAN','CLERK','ANALYST');
```

## Question 6
Display the name of the employee along with their annual salary. The highest salary should appear first.

### Query
```sql
SELECT Ename, Sal*12 AS Annual_Salary
FROM Employee
ORDER BY Sal DESC;
```

## Question 7
Display name, sal, hra, pf, da, totalsal for each employee.

### Query
```sql
SELECT Ename,
       Sal,
       Sal*0.15 AS HRA,
       Sal*0.10 AS DA,
       Sal*0.05 AS PF,
       (Sal + (Sal*0.15) + (Sal*0.10) - (Sal*0.05)) AS TotalSal
FROM Employee
ORDER BY TotalSal;
```

## Question 8
Update the salary of each employee by 10% increment who are not eligible for commission.

### Query
```sql
UPDATE Employee
SET Sal = Sal * 1.10
WHERE Comm IS NULL;
```

## Question 9
Display those employees whose salary is more than 3000 after giving 20% increment.

### Query
```sql
SELECT Ename, Sal*1.20 AS Increased_Salary
FROM Employee
WHERE (Sal*1.20) > 3000;
```

## Question 10
Display those employees whose salary contains at least 3 digits.

### Query
```sql
SELECT Ename, Sal
FROM Employee
WHERE LENGTH(TRIM(TO_CHAR(Sal))) >= 3;
```