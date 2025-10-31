# Experiment 6: Joins

## AIM 
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1262" height="851" alt="Screenshot 2025-10-31 191218" src="https://github.com/user-attachments/assets/b994c9d9-a16a-48c7-b276-8ef9d94705eb" />


```sql
select c.cust_name,c.city,c.grade,s.name AS "Salesman",s.city
from customer c
join salesman s on c.salesman_id=s.salesman_id
order by c.customer_id ASC;
```

**Output:**
<img width="1271" height="845" alt="Screenshot 2025-10-31 191236" src="https://github.com/user-attachments/assets/4cb1a8ec-102c-45ac-a005-24d347882ae7" />



**Question 2**
---
<img width="1245" height="373" alt="Screenshot 2025-10-31 191400" src="https://github.com/user-attachments/assets/3478aa2b-6dc9-47e9-8dd8-8015b9ebc51c" />


```sql
select s.*
from salesman s
left join customer c on s.salesman_id = c.salesman_id
where c.cust_name = 'Fabian Johns';
```

**Output:**

<img width="1273" height="508" alt="Screenshot 2025-10-31 191411" src="https://github.com/user-attachments/assets/9d7ea77f-e317-4698-80c9-eec9d4fe5fc7" />


**Question 3**
---
<img width="1276" height="852" alt="Screenshot 2025-10-31 191513" src="https://github.com/user-attachments/assets/e0b7fb85-5527-45d2-9294-13fdfebb5b5d" />

```sql
select c.cust_name as "Customer Name",c.city,s.name as "Salesman",s.commission
from customer c
join salesman s on c.salesman_id=s.salesman_id
where s.commission > 0.12;
```

**Output:**
<img width="1282" height="845" alt="Screenshot 2025-10-31 191533" src="https://github.com/user-attachments/assets/a0adc101-8970-4c98-be7b-16ca72b0b0a7" />



**Question 4**
---
<img width="1246" height="771" alt="Screenshot 2025-10-31 191704" src="https://github.com/user-attachments/assets/1de1c6ec-cea2-4dfc-b1b7-df71c29a952e" />


```sql
select p.first_name as "patient_name",t.test_name
from patients p
inner join test_results t on p.patient_id=t.patient_id

```

**Output:**
<img width="1273" height="626" alt="Screenshot 2025-10-31 191716" src="https://github.com/user-attachments/assets/a72142b0-d7ea-4d21-ba78-ffea7374e5ed" />



**Question 5**
---
<img width="1273" height="866" alt="Screenshot 2025-10-31 191820" src="https://github.com/user-attachments/assets/1d8c4105-72f8-41d8-ae64-f92bcabac173" />


```sql
select o.ord_no,o.purch_amt,c.cust_name,c.city
from orders o
inner join customer c on c.customer_id=o.customer_id
where o.purch_amt between 500 and 2000;
```

**Output:**
<img width="1275" height="585" alt="Screenshot 2025-10-31 191831" src="https://github.com/user-attachments/assets/e7680ef7-40d6-4d8a-a300-549f61d33235" />



**Question 6**
---
<img width="1248" height="390" alt="Screenshot 2025-10-31 191923" src="https://github.com/user-attachments/assets/ff37606b-657e-4269-a1e8-57c332793c7f" />


```sql
select s.name
from salesman s
left join customer c on s.salesman_id=c.salesman_id
where c.city='London';
```

**Output:**

<img width="1273" height="559" alt="Screenshot 2025-10-31 191935" src="https://github.com/user-attachments/assets/2d3dbc2c-8147-4d42-911d-2c829d17d876" />


**Question 7**
---
<img width="1267" height="826" alt="Screenshot 2025-10-31 192125" src="https://github.com/user-attachments/assets/bdb9fafa-ba7c-45da-bb30-35cd147dabbb" />

```sql
select p.first_name, s.*
from patients p
inner join surgeries s on p.patient_id=s.patient_id
where p.discharge_date between '2024-03-01' and '2024-03-31'
and not (p.admission_date between '2024-03-01' and '2024-03-31');
```

**Output:**
<img width="1277" height="501" alt="Screenshot 2025-10-31 192137" src="https://github.com/user-attachments/assets/b35724a1-0302-4f98-babc-d81542f81893" />



**Question 8**
---
<img width="1262" height="779" alt="Screenshot 2025-10-31 192240" src="https://github.com/user-attachments/assets/575e205e-e7b5-4a81-991f-bf60ed8b0ff5" />


```sql
select p.first_name as "patient_name",d.first_name as "doctor_name"
from patients p
inner join doctors d on p.doctor_id=d.doctor_id
where p.discharge_date is null;
```

**Output:**
<img width="1277" height="558" alt="Screenshot 2025-10-31 192251" src="https://github.com/user-attachments/assets/e526401c-5ddf-4ef7-969e-9b0ed67221b4" />



**Question 9**
---
<img width="1237" height="859" alt="Screenshot 2025-10-31 192409" src="https://github.com/user-attachments/assets/a55323ff-76b0-434b-8fc3-a4adf07d0abb" />


```sql
select c.cust_name as "Customer Name",c.city,s.name as "Salesman",s.city,s.commission
from customer c
join salesman s on c.salesman_id=s.salesman_id
where s.city<> c.city and s.commission > 0.12;
```

**Output:**
<img width="1274" height="721" alt="Screenshot 2025-10-31 192424" src="https://github.com/user-attachments/assets/58c14d7c-d83d-4b20-8c79-c009170cf614" />



**Question 10**
---
<img width="1262" height="853" alt="Screenshot 2025-10-31 192531" src="https://github.com/user-attachments/assets/dfa21c24-7cba-4b15-9e53-c31bd5c210b3" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as "Order Amount",s.name,s.commission
from customer c
left join orders o on c.customer_id=o.customer_id
left join salesman s on c.salesman_id=s.salesman_id;
```

**Output:**
<img width="1279" height="860" alt="Screenshot 2025-10-31 192547" src="https://github.com/user-attachments/assets/27b4e613-1738-4af8-8f09-834cdb764033" />

**SEB EXAM**



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
