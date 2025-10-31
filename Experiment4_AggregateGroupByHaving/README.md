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
<img width="1213" height="576" alt="Screenshot 2025-10-31 105152" src="https://github.com/user-attachments/assets/61218741-0fa9-424e-babb-a1338c6d3918" />


```sql
select Specialty,Gender,COUNT(*) as TotalDoctors
from Doctors
group by Specialty,Gender;
```

**Output:**

<img width="1231" height="693" alt="Screenshot 2025-10-31 105210" src="https://github.com/user-attachments/assets/21b9f9cc-7bb3-4d7c-b833-79033eb39431" />


**Question 2**
---
<img width="1212" height="600" alt="Screenshot 2025-10-31 105550" src="https://github.com/user-attachments/assets/86c8ce4f-592d-4c55-8a5c-2249e832b0c6" />


```sql
select Specialty,COUNT(*) as TotalDocto
from Doctors
group by Specialty;
```

**Output:**
<img width="1216" height="769" alt="Screenshot 2025-10-31 105604" src="https://github.com/user-attachments/assets/51862d95-82db-4ccf-8cdc-ec320b7ba2c1" />


**Question 3**
---
<img width="1220" height="680" alt="Screenshot 2025-10-31 105712" src="https://github.com/user-attachments/assets/536e3749-f703-47d7-b2db-fea36af0e673" />


```sql
select InsuranceCompany,COUNT(*) as TotalExpiredPatients
from Insurance
group by InsuranceCompany;
```

**Output:**
<img width="1224" height="841" alt="Screenshot 2025-10-31 105730" src="https://github.com/user-attachments/assets/a9e1627a-5880-4d4b-aa9f-07b70fd87ad3" />



**Question 4**
---
<img width="1197" height="488" alt="Screenshot 2025-10-31 105905" src="https://github.com/user-attachments/assets/ec09a991-e09b-4d32-bb05-346b8d471f75" />


```sql
select SUM(income) as total_income
from employee
where age >=40;
```

**Output:**
<img width="1222" height="397" alt="Screenshot 2025-10-31 105919" src="https://github.com/user-attachments/assets/eb840090-247a-4bda-bdbf-aee2f21df76b" />



**Question 5**
---
<img width="1181" height="576" alt="Screenshot 2025-10-31 110004" src="https://github.com/user-attachments/assets/75f145ec-19de-4488-a78b-76f033bab6b4" />


```sql
select SUM(inventory) as total_available_amount
from fruits
where price > 0.5;
```

**Output:**
<img width="1212" height="397" alt="Screenshot 2025-10-31 110016" src="https://github.com/user-attachments/assets/a1563907-a9f3-44ea-8bdb-7fd420bd5435" />



**Question 6**
---
<img width="1187" height="522" alt="Screenshot 2025-10-31 110117" src="https://github.com/user-attachments/assets/95730407-4cd9-4737-ad6f-2d614fd0ac6f" />


```sql
select MAX(purch_amt) as MAXIMUM
from orders;
```

**Output:**
<img width="1219" height="392" alt="Screenshot 2025-10-31 110139" src="https://github.com/user-attachments/assets/7006c704-c1d1-41bc-b337-e16b4f1e5e63" />



**Question 7**
---
<img width="1165" height="484" alt="Screenshot 2025-10-31 110306" src="https://github.com/user-attachments/assets/3cda1fa4-2914-48e4-9c35-9f291bbd1b36" />


```sql
select AVG(income) as avg_income
from employee
where name LIKE 'A%';
```

**Output:**
<img width="1224" height="390" alt="Screenshot 2025-10-31 110319" src="https://github.com/user-attachments/assets/a64acd36-5b40-46be-83d4-d2c548114664" />



**Question 8**
---
<img width="1218" height="477" alt="Screenshot 2025-10-31 110420" src="https://github.com/user-attachments/assets/3ca11ad2-a8ff-43ee-bd75-81d7002d0f0a" />


```sql
select (age/5)*5 as age_group,AVG(age) as 'AVG(age)'
from customer1
group by age_group
HAVING AVG(age)<24;
```

**Output:**
<img width="1219" height="388" alt="Screenshot 2025-10-31 110433" src="https://github.com/user-attachments/assets/cf66fa0b-b0e6-4666-a77e-fa989da06625" />



**Question 9**
---
<img width="1212" height="548" alt="Screenshot 2025-10-31 110554" src="https://github.com/user-attachments/assets/96cd902c-3e3d-4434-879d-ae7b894eea75" />


```sql
select category_id,SUM(price * category_id) as Revenue
from products
group by category_id
HAVING SUM(price * category_id) > 25;
```

**Output:**
<img width="1224" height="520" alt="Screenshot 2025-10-31 110606" src="https://github.com/user-attachments/assets/e2b426c4-45ce-4962-b86a-d65a425418d0" />



**Question 10**
---
<img width="1200" height="520" alt="Screenshot 2025-10-31 110659" src="https://github.com/user-attachments/assets/28f0c932-1d57-47b7-a490-45f756b42de3" />


```sql
select jdate,MAX(workhour) as 'MAX(workhour)'
from employee1
group by jdate 
HAVING MAX(workhour)>12;
```

**Output:**
<img width="1224" height="465" alt="Screenshot 2025-10-31 110712" src="https://github.com/user-attachments/assets/eb1dae39-257b-4e37-8fc5-17240643fe38" />

**SEB EXAM**
<img width="1355" height="105" alt="Screenshot 2025-10-31 111022" src="https://github.com/user-attachments/assets/62f5ad19-f86f-4dd7-a376-defa0df4e8d1" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
