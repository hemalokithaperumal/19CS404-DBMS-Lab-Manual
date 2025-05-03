# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/d2d5144f-21cb-47f8-a790-865613b5d4d9)


```sql
select doctorid,count(appointmentid) as TotalAppointments
from Appointments 
group by doctorid;
```

**Output:**
![image](https://github.com/user-attachments/assets/8da944cb-ca86-44d6-bd0c-7c065b3790be)


**Question 2**
---
![image](https://github.com/user-attachments/assets/d34d3d04-92cc-472f-a035-ef7860f3bfff)


```sql
select doctorid,count(appointmentid) as TotalAppointments
from Appointments 
group by doctorid;
```

**Output:**

![image](https://github.com/user-attachments/assets/8f08a5c5-4dcd-4fe8-9087-3bcb4538ff63)


**Question 3**
---
![image](https://github.com/user-attachments/assets/d789e34a-7914-4d7c-84c3-b04ebc11a29a)


```sql
select doctorid,count(recordid) as TotalRecords
from MedicalRecords 
group by doctorid;
```

**Output:**

![image](https://github.com/user-attachments/assets/2c9b8104-e6eb-49f2-aea8-0a61c956d2e0)


**Question 4**
---
![image](https://github.com/user-attachments/assets/425ab76d-438c-4f46-8add-7fd360bf9643)


```sql
select max(purch_amt)as MAXIMUM from orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/27f3df83-d7ef-48c9-95a0-1d87c33f7caf)


**Question 5**
---
![image](https://github.com/user-attachments/assets/e3bcd3bc-46d7-409f-a884-bc783fc330bc)


```sql
select count(DISTINCT salesman_id) as COUNT from orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/1438e0cb-c8b3-4476-b889-c99e1002d1c5)


**Question 6**
---
![image](https://github.com/user-attachments/assets/d30050ca-d8cd-439d-af4c-f6f25f9494dd)


```sql
select name, length(name) as length from customer order by length(name) desc limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/b4805d2d-3040-45e7-9116-a54d120d5763)


**Question 7**
---
![image](https://github.com/user-attachments/assets/d72669ca-f950-4244-af21-d4e14e39b39f)


```sql
select avg(income) as Average_Salary from employee;
```

**Output:**

![image](https://github.com/user-attachments/assets/44de571e-76ae-46b0-8307-cf0f85872b44)


**Question 8**
---
![image](https://github.com/user-attachments/assets/701bd100-3644-426f-b499-ac3841416cff)


```sql
select age,MIN(income) 
from employee 
group by age 
having MIN(income)<400000;
```

**Output:**

![image](https://github.com/user-attachments/assets/5a28825d-370a-49be-bdd2-06914497c6ac)


**Question 9**
---
![image](https://github.com/user-attachments/assets/a7d61588-54f8-4bef-9740-3e12dbdadf75)


```sql
select address,SUM(salary)
from customer1
group by address 
having SUM(salary)>2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/aa47256b-4185-4918-a6a8-4c230fa72cf5)


**Question 10**
---
![image](https://github.com/user-attachments/assets/81a2398d-2be5-4d5e-854e-0f85ca7923c1)


```sql
select jdate,MAX(workhour)
from employee1
group by jdate 
having MAX(workhour)>12;
```

**Output:**


![image](https://github.com/user-attachments/assets/d83c5036-96c8-4732-9060-f53123160c2e)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
