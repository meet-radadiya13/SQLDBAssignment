# SQLDBAssignment

## Creating tables

### Creating Table **EmployeeInfo**
CREATE table EmployeeInfo(<br>
EmpID serial primary key,<br>
EmpFname varchar(20) not null,<br>
EmpLname varchar(20) not null,<br>
Department varchar(10),<br>
Project varchar(10),<br>
Address varchar(50),<br>
DOB date,<br>
Gender varchar(2)	<br>
);<br>

### Inserting data in this table
INSERT INTO EmployeeInfo(EmpFname,EmpLname,Department,Project,Address,DOB,Gender)<br>
VALUES('Sanjay','Mehra','HR','P1','Hyderabad(HYD)','21/12/1976','M'),<br>
('Ananya','Mishra','Admin','P2','Delhi(DEL)','02/05/1968','F'),<br>
('Rohan','Diwan','Account','P3','Mumbai(BOM)','01/01/1980','M'),<br>
('Soniya','Kulkarni','HR','P1','Hyderabad(HYD)','02/05/1992','F'),<br>
('Ankit','Kapoor','Admin','P2','Delhi(DEL)','03/07/1994','M');<br>

#### Output of above table will be
https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-09%2015-18-38.png?csf=1&web=1&e=GpuJyb

### Creating Table **EmployeePosition**
CREATE table EmployeePosition(<br>
EmpID int,<br>
EmpPosition varchar(20),<br>
DateofJoining date,<br>
Salary int,<br>
CONSTRAINT fk_employeeinfo<br>
      FOREIGN KEY(EmpID) <br>
  REFERENCES employeeinfo(EmpID)<br>
);<br>

### Inserting data in this table
INSERT INTO EmployeePosition(EmpPosition,DateofJoining,Salary)<br>
VALUES('Manager','01/05/2022',500000),<br>
('Executive','02/05/2022',75000),<br>
('Manager','01/05/2022',90000),<br>
('Lead','02/05/2022',85000),<br>
('Executive','01/05/2022',300000);<br>

#### Output of above table will be
https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-09%2015-18-55.png?csf=1&web=1&e=sY9VhS

### Question 1
>Write a query to fetch the number of employees working in the department ‘Admin’:<br><br>
>*SELECT COUNT(*) <br>
>FROM employeeinfo<br>
>WHERE department='Admin'*<br>
>* Here COUNT() function is used in SELECT function to return the number of employees working in Admin department.<br>
>* The COUNT() function is an aggregate function that allows you to get the number of rows that match a specific condition of a query.
>#### Output will be
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-06-00.png?csf=1&web=1&e=FmILSc

### Question 2
> Write a query to retrieve the first four characters of  EmpLname from the EmployeeInfo table.<br><br>
>*SELECT LEFT(EmpLname,4)<br>
>FROM employeeinfo;*<br>
>* The PostgreSQL LEFT() function returns the first n characters in the string.<br>
>#### Output will be
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-08-20.png?csf=1&web=1&e=dcOfca

### Question 3
>Write q query to find all the employees whose salary is between 50000 to 100000.<br><br>
>*FROM employeeposition<br>
>WHERE salary>=50000 AND salary<=100000;*<br>
>#### Output will be
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-13-56.png?csf=1&web=1&e=7jJZ48

### Question 4
>Write a query to find the names of employees that begin with ‘S’.<br><br>
>*SELECT * <br>
>FROM employeeinfo<br>
>WHERE empfname LIKE 'S%';*<br>
>* Apart from this if we want to make the search case insensitive, we can use the ILIKE as well.<br>
> #### Output will be
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-14-50.png?csf=1&web=1&e=qBEtGr

### Question 5
>Write a query to fetch top N records order by salary. (ex. top 5 records).<br><br>
>*SELECT * <br>
>FROM employeeposition<br>
>ORDER BY salary DESC <br>
>LIMIT 3;* <br>
>* LIMIT restricts the number of outputs a query returns.<br>  
>* LIMIT is not used as an SQL standard  practice, instead FETCH is used.<br>
> #### Output will be 
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-16-21.png?csf=1&web=1&e=8ef0lt

### Question 6
>Write a query to fetch details of all employees excluding the employees with first names, “Sanjay” and “Sonia” from the EmployeeInfo table.<br><br>
>*SELECT * <br>
>FROM employeeinfo<br>
>WHERE empfname NOT IN('Sanjay','Soniya');*<br><br>
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-20-45.png?csf=1&web=1&e=rIx0Nh

### Question 7
>Write a query to fetch the department-wise count of employees sorted by department’s count in ascending order.<br><br>
>*SELECT department, count(*)<br>
>FROM employeeinfo<br>
>GROUP BY department<br>
>ORDER BY total;*<br><br>
> #### Output will be
> https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-06%2012-30-18.png?csf=1&web=1&e=N14hhm

### Question 8
>Create indexing for any particular field and show the difference in data fetching before and after indexing.<br><br>
>*CREATE INDEX empid ON employeeinfo(empid);*<br><br>
> https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-09%2014-34-24.png?csf=1&web=1&e=xeLym3
>* On examining the results closely, we find that the time cost reduces when we apply index on a particular column.<br>
>##### Before indexing
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-09%2014-33-23.png?csf=1&web=1&e=TLcl1T
>#### After indexing
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/r/personal/meet_r_simformsolutions_com/Documents/Flipkart/Downloads/SQLAssignment/Screenshot%20from%202023-03-09%2014-35-08.png?csf=1&web=1&e=OHh4e2
>* Here we can clearly see that after indexing execution time of same query is reduced  to 0.048 secs from 0.118 secs
>* This can make significant deifferent when handling large amount of data
