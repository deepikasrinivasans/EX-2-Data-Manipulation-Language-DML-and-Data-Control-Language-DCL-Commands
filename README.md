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
![DBMS1](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/1c122311-48c5-4a4c-98e5-3b657c7006ec)
### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![DBMS2](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/cf1404ff-38bf-42d8-bd03-05a688896545)
### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![DBMS3](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/4de91826-5bad-438f-8853-6edec6ba9eaa)
### Q4)	List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![DBMS4](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/d3badd6f-f9ac-474d-b83e-ff85cb6e3b23)
### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![DBMS5](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/5bf9fdc8-cefc-4176-8015-e9fd857ca69a)
### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![DBMS6](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/098af376-c7c2-449a-af61-3bfa461d756a)
### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![DBMS7](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/629c0008-7b28-44bd-b054-5e9b5280c75a)
### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![DBMS8](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/ab85905d-f70b-413a-99a3-442f19d47a7b)
### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![DBMS9](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/056e35ea-8b98-4ff7-a1f2-5191122ba1eb)
### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:

![DBMS10](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/82067a18-6846-44bc-ab5e-b0d2ec94a33a)
### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![DBMS11](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/f640d484-7cf4-4dd1-bafb-7173cb5260cf)
### Q12) Find number of rows in the table EMP
### QUERY:
```
 select count(*) from manager;
```
### OUTPUT:

![DBMS12](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/2c33ffe9-516a-4729-8364-9da288e28cf5)
### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
### MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![DBMS13](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/dabb7236-13e3-425e-838d-411d480561f1)
### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![DBMSMIN](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/cfa7ccbf-99fe-4700-9b72-5d284c4ed856)

### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![DBMSAVG](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/a5f3290d-14c4-4036-8795-f5d172254a01)
### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![DBMS14](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/1914c2ae-08fa-479d-add7-ec0d17268f91)
## Result:
 To create a manager database and execute DML queries using SQL is executed successfully.
