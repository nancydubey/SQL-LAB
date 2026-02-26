# SQL Lab – Experiment 7

## Aim
To perform reporting and grouping operations on EMPLOYEE table.

## Question 1
Compute the number of days remaining in the current year.

### Query
```sql
SELECT TRUNC(TO_DATE('31-12-'||TO_CHAR(SYSDATE,'YYYY'),'DD-MM-YYYY') - SYSDATE)
AS Days_Remaining
FROM DUAL;
```

## Question 2
Find the highest and lowest salaries and the difference between them.

### Query
```sql
SELECT MAX(Sal) AS Highest_Salary,
       MIN(Sal) AS Lowest_Salary,
       (MAX(Sal)-MIN(Sal)) AS Difference
FROM Employee;
```

## Question 3
List employees whose commission is greater than 25% of their salary.

### Query
```sql
SELECT *
FROM Employee
WHERE Comm > (Sal*0.25);
```

## Question 4
Display salary in dollar format.

### Query
```sql
SELECT Ename,
       TO_CHAR(Sal,'$99999.99') AS Salary
FROM Employee;
```

## Question 5
Display job wise salary based on department and total salary.

### Query
```sql
SELECT Job,
       SUM(CASE WHEN Deptno=10 THEN Sal ELSE 0 END) AS Dept10,
       SUM(CASE WHEN Deptno=20 THEN Sal ELSE 0 END) AS Dept20,
       SUM(CASE WHEN Deptno=30 THEN Sal ELSE 0 END) AS Dept30,
       SUM(Sal) AS Total_Salary
FROM Employee
GROUP BY Job;
```

## Question 6
Display total employees hired in each year.

### Query
```sql
SELECT TO_CHAR(Hiredate,'YYYY') AS Year,
       COUNT(*) AS Total
FROM Employee
GROUP BY TO_CHAR(Hiredate,'YYYY');
```

## Question 7
Get the last Sunday of any month.

### Query
```sql
SELECT NEXT_DAY(LAST_DAY(SYSDATE)-7,'SUNDAY')
FROM DUAL;
```

## Question 8
Display department numbers and total employees.

### Query
```sql
SELECT Deptno,
       COUNT(*) AS Total_Employees
FROM Employee
GROUP BY Deptno;
```

## Question 9
Display various jobs and total employees.

### Query
```sql
SELECT Job,
       COUNT(*) AS Total
FROM Employee
GROUP BY Job;
```

## Question 10
Display department numbers and total salary.

### Query
```sql
SELECT Deptno,
       SUM(Sal) AS Total_Salary
FROM Employee
GROUP BY Deptno;
```