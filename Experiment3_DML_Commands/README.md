# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
![image](https://github.com/user-attachments/assets/be4064fd-3acb-47da-a1ef-da682c5a86d6)


```sql
insert into Products (productid,name,category,price,stock)values(101,"Laptop","Electronics",1500,50);
```

**Output:**

![image](https://github.com/user-attachments/assets/8fbe7186-ca0b-428b-b2d9-30ef6aeb983f)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8e092282-a3a9-4d44-8c4e-789f3937523a)

```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (5,'George Clark','Consultant',NULL,NULL);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (7,'Noah Davis','Manager','HR',60000);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values (8,'Ava Miller','Consultant','IT',NULL);

```

**Output:**

![image](https://github.com/user-attachments/assets/a4eb049d-2a52-405a-b008-86ca5440eecf)


**Question 3**
---
![image](https://github.com/user-attachments/assets/d7960d63-28ca-4ca5-9c02-e121446a3ae4)


```sql
UPDATE sales set sell_price=sell_price*1.05 where product_id = 15 and sale_date='2023-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/0d0f83b6-9900-4140-8aa6-9471ab275c2f)


**Question 4**
---
![image](https://github.com/user-attachments/assets/79eee033-2177-4f71-98dd-902f5fd18745)


```sql
update employees set salary=salary+500,email = "updated" 
where job_id ="SA_REP" and commission_pct>0.15;
```

**Output:**

![image](https://github.com/user-attachments/assets/73d0cc87-186d-459a-91bd-24f5a457a79a)


**Question 5**
---
![image](https://github.com/user-attachments/assets/521229f6-dde8-4de7-993d-3eeac1318a7e)


```sql
update purchases set per_unit_price =25,total_price=quantity*25 where
purchase_date ="2022-08-15" and product_id=12;
```

**Output:**

![image](https://github.com/user-attachments/assets/09e93e55-f740-4be5-bc58-5c54d05c5b39)


**Question 6**
---
![image](https://github.com/user-attachments/assets/3d802701-9502-4d94-9eaf-8675a470613f)


```sql
update suppliers set address ='58 Lakeview, Magnolia' where supplier_id =5;
```

**Output:**

![image](https://github.com/user-attachments/assets/89c1a9b4-507b-4148-9c08-891960fb87f0)


**Question 7**
---
![image](https://github.com/user-attachments/assets/7dd373ad-2a84-4de0-beb4-096648b7fd7d)


```sql
select patient_id,first_name,admission_date,discharge_date
from patients where admission_date=discharge_date;

```

**Output:**

![image](https://github.com/user-attachments/assets/a28d4732-a8de-4d8c-a84f-f773b5035a26)


**Question 8**
---
![image](https://github.com/user-attachments/assets/4aab613a-c430-47ae-bde7-52f01a03657a)


```sql
select categoryname, description from categories order by categoryname;
```

**Output:**

![image](https://github.com/user-attachments/assets/38c06f10-0eed-43b6-ad70-b378dd25bcab)


**Question 9**
---
![image](https://github.com/user-attachments/assets/2f4f5afa-92f4-4931-ab1b-ff0e63f1b4ac)


```sql
select customer_id, cust_name, city, grade,salesman_id
from customer where city ='London' and grade >200;
```

**Output:**

![image](https://github.com/user-attachments/assets/5ffc4c29-7ee9-438f-b944-3489e6b468c2)


**Question 10**
---
![image](https://github.com/user-attachments/assets/87cdf942-36ba-464a-b47a-241466850754)


```sql
update products set sell_price =(1.15)*sell_price where quantity <50 and supplier_id=10;
```

**Output:**

![image](https://github.com/user-attachments/assets/e60faea9-99f5-47c1-8010-2987b863160d)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
