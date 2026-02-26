# SQL Lab – Experiment 6

## Aim
To perform operations using decode, date and time functions.

## Question 1
Display empno, ename and department name using decode function.

### Query
```sql
SELECT Empno,
       Ename,
       DECODE(Deptno,
              10,'RESEARCH',
              20,'ACCOUNTING',
              30,'SALES',
              40,'OPERATIONS') AS Dept_Name
FROM Employee;
```

## Question 2
Display your age in days.

### Query
```sql
SELECT TRUNC(SYSDATE - TO_DATE('01-01-2000','DD-MM-YYYY')) AS Age_In_Days
FROM DUAL;
```

## Question 3
Display your age in months.

### Query
```sql
SELECT TRUNC(MONTHS_BETWEEN(SYSDATE, TO_DATE('01-01-2000','DD-MM-YYYY'))) AS Age_In_Months
FROM DUAL;
```

## Question 4
Display the current date in given format.

### Query
```sql
SELECT TO_CHAR(SYSDATE,'DDth Month Day YYYY') FROM DUAL;
```

## Question 5
Display joining date of Scott in words.

### Query
```sql
SELECT Ename,
       TO_CHAR(Hiredate,'Day DDth Month YYYY')
FROM Employee
WHERE Ename='SCOTT';
```

## Question 6
Find the nearest Saturday after current date.

### Query
```sql
SELECT NEXT_DAY(SYSDATE,'SATURDAY') FROM DUAL;
```

## Question 7
Display current time.

### Query
```sql
SELECT TO_CHAR(SYSDATE,'HH:MI:SS AM') FROM DUAL;
```

## Question 8
Display the date three months before current date.

### Query
```sql
SELECT ADD_MONTHS(SYSDATE,-3) FROM DUAL;
```

## Question 9
Display employees who joined in December.

### Query
```sql
SELECT *
FROM Employee
WHERE TO_CHAR(Hiredate,'MON')='DEC';
```

## Question 10
Display employees whose 10% of salary equals year of joining.

### Query
```sql
SELECT *
FROM Employee
WHERE (Sal*0.10)=TO_NUMBER(TO_CHAR(Hiredate,'YYYY'));
```

## Question 11
Display employees who joined before 15th of month.

### Query
```sql
SELECT *
FROM Employee
WHERE TO_CHAR(Hiredate,'DD')<15;
```

## Question 12
Display employees whose joining date is available in deptno.

### Query
```sql
SELECT *
FROM Employee
WHERE TO_CHAR(Hiredate,'DD')=Deptno;
```