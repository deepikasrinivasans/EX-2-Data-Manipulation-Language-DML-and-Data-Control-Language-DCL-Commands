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
![OUTLET1](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/ee495809-c192-4c08-bdad-0098562ac710)
### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![OUTLET2](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/cb0e99ff-d52e-4bf8-a7d2-f493b73e9fdc)
### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![OUTLET3](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/43979354-197f-43f6-8f2f-d7164b6d0595)
### Q4)	List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![OUTLET4](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/26c4f673-423d-427f-8aa4-60a043030cc5)
### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![OUTLET5](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/70a09365-727d-4915-9aec-50fbfb164437)
### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![OUTLET6](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/8e0687f5-6747-4f53-a2b0-2fa2a82e3e70)
### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![OUTLET7](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/611a3ebf-b8ae-4ef8-ad17-10514919ca94)
### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![OUTLET8](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/b966078c-34d3-49f9-8da3-b52a20a66039)
### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![OUTLET9](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/c6ba3386-60da-4be4-bc19-976a2fdf9f0e)
### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![OUTLET10](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/7fe9512b-c6f4-4afd-a4b1-9d0417bd117c)
### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![OUTLET11](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/a95127ca-bcd2-4d04-840a-1ad76b1e0788)
### Q12) Find number of rows in the table EMP
### QUERY:
```
 select count(*) from manager;
```
### OUTPUT:
![OUTLET12](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/dcbda41f-3425-4050-a460-a619d87b1a55)
### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
### MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![OUTLET13](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/6c5395c7-a61d-44c7-ade7-5ce97eda61ca)
### MINIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![OUTLETMIN](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/65f98c7b-5ae1-4bb8-8ba8-67923464586a)
#### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![OUTLETAVG](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/de341716-6590-4732-a8b6-51e794140bf1)
### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![OUTLET14](https://github.com/deepikasrinivasans/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393935/974171e5-bf71-4c02-afd2-f158081eb8d8)
### RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.

