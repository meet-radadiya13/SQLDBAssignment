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
![EmployeeInfo table](https://user-images.githubusercontent.com/125358696/224024735-87a3cfdd-7b0c-465f-89b1-f3877b3ed714.png)

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

#### Output of above table will be
![Employee Position Table]()


