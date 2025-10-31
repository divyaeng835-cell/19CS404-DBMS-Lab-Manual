# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--

<img width="1172" height="570" alt="Screenshot 2025-10-31 174132" src="https://github.com/user-attachments/assets/43f6fc4a-328b-4f62-99fd-8d6fcd2febc5" />

```sql
select name,city from customer
where city in (select city from customer
where id in (3,7));
```

**Output:**

<img width="1276" height="543" alt="Screenshot 2025-10-31 174144" src="https://github.com/user-attachments/assets/4ff7c4c3-de3d-4719-b6eb-3d85c06c566b" />


**Question 2**
---

<img width="1241" height="633" alt="Screenshot 2025-10-31 174318" src="https://github.com/user-attachments/assets/feffd8ba-4b1b-41d1-ae9a-91e05fbe160a" />


```sql
select * from CUSTOMERS
where ADDRESS = 'Delhi' and AGE <30
group by ID;
```

**Output:**

<img width="1273" height="446" alt="Screenshot 2025-10-31 174334" src="https://github.com/user-attachments/assets/9acda418-673a-428d-879b-8a1c859863bd" />



**Question 3**
---

<img width="1262" height="642" alt="Screenshot 2025-10-31 174432" src="https://github.com/user-attachments/assets/2916323b-8206-4cfe-b10a-810c8606c2d8" />


```sql
select * from CUSTOMERS
where ADDRESS = 'Delhi';
```

**Output:**

<img width="1276" height="414" alt="Screenshot 2025-10-31 174444" src="https://github.com/user-attachments/assets/7f20f6a6-4dae-462a-bb1f-89cfc2f0cf09" />



**Question 4**
---

<img width="1267" height="764" alt="Screenshot 2025-10-31 174553" src="https://github.com/user-attachments/assets/ac979bd8-628c-4f84-9859-da2a38c14f6c" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id from orders
where salesman_id in (select salesman_id from salesman
where city='London');
```

**Output:**

<img width="1275" height="489" alt="Screenshot 2025-10-31 174607" src="https://github.com/user-attachments/assets/ac927fd1-431e-484d-b03f-83665a3a1ab0" />



**Question 5**
---

<img width="1273" height="752" alt="Screenshot 2025-10-31 175022" src="https://github.com/user-attachments/assets/5aaa5056-62ce-43ae-a595-0231584fd174" />


```sql
select salesman_id,name from salesman
where salesman_id in (select salesman_id from customer
group by salesman_id
having count(customer_id)>1);
```

**Output:**

<img width="1274" height="558" alt="Screenshot 2025-10-31 175036" src="https://github.com/user-attachments/assets/91aa917e-fd9a-475a-b504-44f79c5e0ee1" />


**Question 6**
---

<img width="1277" height="636" alt="Screenshot 2025-10-31 175129" src="https://github.com/user-attachments/assets/ca01ed9c-ef56-4fc4-ae5a-cb15e9cec788" />

```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id from ORDERS
where purch_amt > (select AVG(purch_amt) from ORDERS
where ord_date = '2012-10-10');
```

**Output:**

<img width="1274" height="548" alt="Screenshot 2025-10-31 175141" src="https://github.com/user-attachments/assets/68aa23b2-3f7b-46fa-93bc-65c957a1f21a" />



**Question 7**
---

<img width="1243" height="510" alt="Screenshot 2025-10-31 175233" src="https://github.com/user-attachments/assets/249d594d-a688-4906-8be0-264c63aad453" />


```sql
select * from Medications
where dosage = (select MAX(dosage)from Medications);
```

**Output:**

<img width="1281" height="488" alt="Screenshot 2025-10-31 175245" src="https://github.com/user-attachments/assets/359a20e9-2cae-4060-844f-0716ed29ae70" />


**Question 8**
---

<img width="1246" height="642" alt="Screenshot 2025-10-31 180144" src="https://github.com/user-attachments/assets/1925d805-1f2a-4931-a0ba-704c2ff56560" />


```sql
select * from CUSTOMERS
where SALARY = 1500;
```

**Output:**

<img width="1269" height="424" alt="Screenshot 2025-10-31 180154" src="https://github.com/user-attachments/assets/7a2b5fc2-76bc-467c-a35b-1be382cac1b8" />



**Question 9**
---

<img width="1268" height="639" alt="Screenshot 2025-10-31 180244" src="https://github.com/user-attachments/assets/71dccabd-69cd-4941-bf10-a3de00ff199d" />

```sql
select student_id,student_name,subject,grade from GRADES g
where grade in (select MIN(grade) from GRADES
where subject = g.subject);
```

**Output:**

<img width="1272" height="528" alt="Screenshot 2025-10-31 180258" src="https://github.com/user-attachments/assets/61830bd0-f5d5-41d6-8bb4-6badddc5b5fc" />


**Question 10**
---

<img width="1218" height="771" alt="Screenshot 2025-10-31 180505" src="https://github.com/user-attachments/assets/5da84104-41a0-4d4e-8009-a0034f95a45a" />


```sql
select * from CUSTOMERS
where AGE < 30;
```

**Output:**

<img width="1275" height="665" alt="Screenshot 2025-10-31 180516" src="https://github.com/user-attachments/assets/23fbab36-0742-4673-be0a-bd2a260ba8d0" />

**SEB EXAM**

<img width="1356" height="81" alt="Screenshot 2025-10-31 180642" src="https://github.com/user-attachments/assets/c64afbdf-b823-47f6-9282-d864d83dd934" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
