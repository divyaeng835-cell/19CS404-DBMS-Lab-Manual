# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY
### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1213" height="437" alt="Screenshot 2025-09-29 133611" src="https://github.com/user-attachments/assets/e5f06565-b4c9-4c61-912f-97c472913be2" />


```sql

contact_id  INTEGER  primary key,
first_name  TEXT  not NULL,
last_name  TEXT  not NULL,
email  TEXT,
phone  TEXT  not NULL check(length(phone)>=10)
);
```

**Output:**
<img width="1214" height="419" alt="Screenshot 2025-09-29 133720" src="https://github.com/user-attachments/assets/d12f1a66-6980-45ac-9e7e-333bc4d2b271" />



**Question 2**
---
-- <img width="912" height="365" alt="Screenshot 2025-09-29 134039" src="https://github.com/user-attachments/assets/b5e93b23-1ad2-4acc-b6da-b7af47835dee" />

```sql
insert into Employee(EmployeeID, Name, Department, Salary)
select EmployeeID, Name, Department, Salary 
from  Former_employees 
```

**Output:**
<img width="1210" height="366" alt="Screenshot 2025-09-29 134055" src="https://github.com/user-attachments/assets/78bb1fcf-a1b8-42a2-8f98-985b89504627" />


**Question 3**
---
<img width="1216" height="276" alt="Screenshot 2025-09-29 134402" src="https://github.com/user-attachments/assets/526ff086-df87-4a51-951a-19bb257d7c87" />


```sql
create table jobs(
job_id integer,
job_title default '',
min_salary default 8000,
max_salary default null
);
```

**Output:**
<img width="1217" height="398" alt="Screenshot 2025-09-29 134424" src="https://github.com/user-attachments/assets/fc9da838-1d6f-4b81-a429-504bf870f446" />


**Question 4**
---
<img width="1212" height="606" alt="Screenshot 2025-09-29 134912" src="https://github.com/user-attachments/assets/1bc828b7-5cc7-4a0b-a55a-98a31dcc04d5" />


```sql
alter table Student_details
add mobilenumber number
```

**Output:**
<img width="1220" height="425" alt="Screenshot 2025-09-29 134933" src="https://github.com/user-attachments/assets/52e9c7b9-32d1-4015-a237-645e707b7c09" />

**Question 5**
---
<img width="1206" height="445" alt="Screenshot 2025-09-29 135244" src="https://github.com/user-attachments/assets/f60575e1-a030-4b88-a22a-e6b950138fa2" />

```sql
create table Employees(
EmployeeID  integer primary key,
FirstName varchar(50) NOT NULL,
LastName  varchar(50) NOT NULL,
Email  varchar(100) unique,
Salary decimal(10,2) check(Salary>0),
DepartmentID integer,
foreign key (DepartmentID) references Departments(DepartmentID)
);
```

**Output:**
<img width="1203" height="485" alt="Screenshot 2025-09-29 135317" src="https://github.com/user-attachments/assets/f1bd22f7-0a3c-43bf-933c-27bd4bda6445" />


**Question 6**
---
<img width="1110" height="454" alt="Screenshot 2025-09-29 135551" src="https://github.com/user-attachments/assets/260bcc87-5a74-45f8-96eb-048a8b6a47b3" />

```sql
create table Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT 
);
```

**Output:**
<img width="1201" height="465" alt="Screenshot 2025-09-29 135615" src="https://github.com/user-attachments/assets/76a42be4-bb9b-41a2-a67f-b557ee343e8a" />

**Question 7**
---
<img width="1187" height="462" alt="Screenshot 2025-09-29 135907" src="https://github.com/user-attachments/assets/19bb88a9-48f2-4929-8bd2-d5b840dcd8dc" />

```sql
alter table Companies
rename column name to first_name;
alter table Companies 
add mobilenumber number;
alter table Companies 
add DOB Date;
alter table Companies 
add State varchar(30);
```

**Output:**
<img width="1202" height="479" alt="Screenshot 2025-09-29 135926" src="https://github.com/user-attachments/assets/7df81e16-9076-42a3-a054-1602030ef263" />


**Question 8**
---

<img width="1089" height="406" alt="Screenshot 2025-09-29 140050" src="https://github.com/user-attachments/assets/f53f0004-ee82-4f78-b538-6c252a8260e6" />


```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values(2,'John Smith','Developer','IT',75000),(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1213" height="430" alt="Screenshot 2025-09-29 140107" src="https://github.com/user-attachments/assets/76a50d3d-d87a-4c68-90bb-89421a77bc72" />


**Question 9**
---

<img width="1211" height="447" alt="Screenshot 2025-09-29 140257" src="https://github.com/user-attachments/assets/ffe89079-47f3-4462-a17b-7a2ebbbb7fa2" />

```sql
create table Invoices(
InvoiceID  INTEGER  primary key,
InvoiceDate DATE,
Amount  REAL check(Amount>0),
DueDate DATE check(DueDate>InvoiceDate),
OrderID  INTEGER,
foreign key (OrderID) references Orders(OrderID)
);
```

**Output:**

<img width="1208" height="351" alt="Screenshot 2025-09-29 140315" src="https://github.com/user-attachments/assets/b4913b9d-ed8b-44cf-91d0-02ab05ed772c" />

**Question 10**
---

<img width="1066" height="491" alt="Screenshot 2025-09-29 140559" src="https://github.com/user-attachments/assets/d5809a20-4e95-4902-8934-49050686b47d" />

```sql
insert into Student_details(RollNo,Name,Gender)
values(204,'Samuel Black','M');
```

**Output:**

<img width="1216" height="384" alt="Screenshot 2025-09-29 140639" src="https://github.com/user-attachments/assets/6e5d1c78-2a24-4c90-af2b-fe762bbe410f" />

**SEB Exam**
---
<img width="1286" height="75" alt="Screenshot 2025-09-29 142630" src="https://github.com/user-attachments/assets/3340eccc-0d6a-43e1-8a8f-d7a7dfd4db36" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
