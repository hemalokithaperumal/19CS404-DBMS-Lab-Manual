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

![image](https://github.com/user-attachments/assets/69aee919-ae1b-4517-aa41-0645ebfad37f)


```sql

ALTER TABLE student_details
ADD column Date_of_birth Date;
```

**Output:**

![image](https://github.com/user-attachments/assets/fd563764-f1eb-4b2f-b85f-727567f6553c)


**Question 2**
---
![image](https://github.com/user-attachments/assets/3e827fe4-d421-4143-ad01-71f1879e9446)


```sql

create table Department(
    DepartmentID integer PRIMARY KEY,DepartmentName TEXT UNIQUE NOT NULL,
    Location text );

```

**Output:**

![image](https://github.com/user-attachments/assets/353aeedd-2f12-4966-8289-a567b4d73a0e)

**Question 3**
---
![image](https://github.com/user-attachments/assets/8ade919b-d006-4327-a1af-587f43724c60)


```sql
insert into Products (productid,name,category,price,stock)values(101,"Laptop","Electronics",1500,50);
```

**Output:**

![image](https://github.com/user-attachments/assets/8f21e17e-9481-4d73-a9cc-ade194e59b4e)


**Question 4**
---
![image](https://github.com/user-attachments/assets/509cd237-f098-44bd-9936-83ac64c75e69)


```sql
create table item(item_id text primary key,item_desc text not null,rate integer not null,icom_id text(4),
foreign key (icom_id)references company(com_id) on update cascade on delete cascade);
```

**Output:**

![image](https://github.com/user-attachments/assets/74afbc96-32a1-42c3-b1b0-f73e1cc2de95)


**Question 5**
---
![image](https://github.com/user-attachments/assets/c902c84a-7bd1-40ff-8a91-c5c79c120855)


```sql
create table item(item_id text primary key,item_desc text not null,rate integer not null,icom_id text(4),
foreign key (icom_id)references company(com_id) on update set null on delete set null);
```

**Output:**

![image](https://github.com/user-attachments/assets/b5dd596e-0b53-4750-b96e-1dfa77900ba3)


**Question 6**
---
![image](https://github.com/user-attachments/assets/f664252b-c79c-4634-8f6d-ffb3f5bbc09a)


```sql
CREATE TABLE Attendance(
AttendanceID  INTEGER  primary key,
EmployeeID INTEGER , 
AttendanceDate  DATE,
Status  TEXT check (status in( 'Present', 'Absent', 'Leave')),
foreign key (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/f7b81e38-2f54-4fc2-bfa8-38f8e72eff1e)


**Question 7**
---
![image](https://github.com/user-attachments/assets/36547c0d-7148-469a-8ecd-1327fcc2cdfe)


```sql
ALTER TABLE Companies 
ADD COLUMN designation varchar(50);
ALTER TABLE Companies 
ADD COLUMN net_salary number;
```

**Output:**

![image](https://github.com/user-attachments/assets/93198260-b730-470d-8e01-a3bc5eaa1645)


**Question 8**
---
![image](https://github.com/user-attachments/assets/3f2faa21-3788-467e-97de-5c12d1dde2de)


```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (5,'George Clark','Consultant',NULL,NULL);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (7,'Noah Davis','Manager','HR',60000);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (8,'Ava Miller','Consultant','IT',NULL);


```

**Output:**

![image](https://github.com/user-attachments/assets/b34081da-7b89-4457-9100-6c7d36fc0b3e)


**Question 9**
---
![image](https://github.com/user-attachments/assets/6f4a3701-6f54-41ae-984b-ff97650a1bae)


```sql
create table orders (OrderID INTEGER,OrderDate TEXT,CustomerID INTEGER);
```

**Output:**

![image](https://github.com/user-attachments/assets/7e45f4a7-2e49-4e4a-8d4a-ec1d3f278524)


**Question 10**
---
![image](https://github.com/user-attachments/assets/44db2e83-e359-4c2e-a28c-eaf530d84b46)


```sql
insert into customers
select CustomerID, Name, Address, Email
from Old_customers
```

**Output:**

![Uploading image.png…]()



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
