# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);

```

### OUTPUT:
![Q1](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/1d66948b-7919-4849-81d5-c2a58efa216c)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![Q2](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/70f3423a-36d3-485a-b4b6-f56fcccb2236)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![Q3](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/5e34fa0e-672f-4860-ab8d-d6430226f451)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```

### OUTPUT:

![Q4](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/1d15721d-77df-4a22-9ecc-5e9ead999a60)

### Q5)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![Q5](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/db21a708-0df8-451e-abe2-abd3c132c438)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![Q6](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/ff826474-3a2d-4ece-9176-10d3efd5f6c1)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![Q7](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/25d6e637-c8e0-4d32-bd28-cb0e9f165e2e)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![Q8](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/d867d163-6acd-46a9-a509-3ae70ab45287)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![Q9](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/e43e7182-4761-4e64-b432-0ae4ed69e8b4)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![Q10](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/29a7a7f2-b4e4-4d0c-a4d4-9b40d28953eb)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![Q11](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/5c3e9892-e46f-40df-a083-040ae71c6ad3)

### Q12) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```

### OUTPUT:
![Q12](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/7cf2d54d-b57a-44f4-a4c1-49c8fed11b79)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```
select max(salary) from manager;
```

### OUTPUT:
![Q13 1](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/753cec17-4df0-4ef1-a2aa-0ba6ae919bd3)

### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![Q13 2](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/35ae26d9-02fb-4f68-bb94-dbae7e3be808)

### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![Q13 3](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/284e827c-536f-4d74-998b-5e895f73030c)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![Q14](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/df54174f-6bf2-4813-b72a-f350a2ca8b63)

## Result:
 To create a manager database and execute DML queries using SQL is executed successfully.
