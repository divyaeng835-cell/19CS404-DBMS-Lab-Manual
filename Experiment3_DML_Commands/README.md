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
<img width="1220" height="637" alt="Screenshot 2025-10-15 102021" src="https://github.com/user-attachments/assets/7078a365-d1a9-4e6b-b929-ac1198b7b842" />


```sql
update Employees
set salary=8000
where employee_id = 105 and salary<5000;
```

**Output:**
<img width="1214" height="318" alt="Screenshot 2025-10-15 102046" src="https://github.com/user-attachments/assets/53f77783-83c7-4591-a379-c1a82ce6f5d9" />

**Question 2**
---
<img width="1234" height="624" alt="Screenshot 2025-10-15 102335" src="https://github.com/user-attachments/assets/ca33ac9f-28d7-45af-9731-b6aa3985d23d" />

```sql
update PRODUCTS
set reorder_lvl=reorder_lvl*0.7
where product_name LIKE '%cream%' and quantity > reorder_lvl;
```

**Output:**
<img width="1216" height="589" alt="Screenshot 2025-10-15 102355" src="https://github.com/user-attachments/assets/d993b3f3-4ba1-4a22-ad54-e4fa375e41b2" />

**Question 3**
---
<img width="1192" height="675" alt="Screenshot 2025-10-15 102541" src="https://github.com/user-attachments/assets/76fd62e9-c73e-427b-b249-a49e2aad1858" />

```sql
update Employees
set email='Unavailable';
```

**Output:**
<img width="1227" height="537" alt="Screenshot 2025-10-15 102556" src="https://github.com/user-attachments/assets/1c9be4b3-43bc-4792-aecd-3b1b2d0ac13b" />

**Question 4**
---
<img width="1098" height="300" alt="Screenshot 2025-10-15 102709" src="https://github.com/user-attachments/assets/70a73cce-7869-485a-8fb0-66b6b6bb4c96" />


```sql
update sales
set sell_price=sell_price*1.05
where product_id=15 and sale_date='2023-01-31';
```

**Output:**
<img width="1228" height="535" alt="Screenshot 2025-10-15 102720" src="https://github.com/user-attachments/assets/7c5e8602-9dcc-4c6e-8363-ac8647925375" />

**Question 5**
---
<img width="1119" height="551" alt="Screenshot 2025-10-15 102839" src="https://github.com/user-attachments/assets/dd6d1fcc-3309-4d59-8f81-fcb8af73f9f2" />


```sql
update PRODUCTS
set reorder_lvl=40
where category='Grocery';
```

**Output:**
<img width="1222" height="478" alt="Screenshot 2025-10-15 102854" src="https://github.com/user-attachments/assets/a95f8da0-f64e-4004-adb6-9b5e2c314d2e" />


**Question 6**
---
<img width="1235" height="502" alt="Screenshot 2025-10-15 103303" src="https://github.com/user-attachments/assets/d413d0a4-4832-40d2-b706-bae8d8026c4d" />

```sql
delete from Customer
where CUST_COUNTRY NOT IN ('India','USA');
```

**Output:**
<img width="1219" height="622" alt="Screenshot 2025-10-15 103319" src="https://github.com/user-attachments/assets/6eb6858c-46d8-4576-8263-a4b1316f4dbd" />

**Question 7**
---
<img width="1228" height="731" alt="Screenshot 2025-10-15 103443" src="https://github.com/user-attachments/assets/dc45b60e-4b52-458f-b56e-7aed2e473d91" />

```sql
delete from Customer
where CUST_CITY LIKE 'L%';
```

**Output:**
<img width="1206" height="834" alt="Screenshot 2025-10-15 103518" src="https://github.com/user-attachments/assets/52e4ab1c-807f-446a-beab-e631360a5a87" />

**Question 8**
---
<img width="1219" height="509" alt="Screenshot 2025-10-15 103639" src="https://github.com/user-attachments/assets/0945df49-ac89-43d7-971f-0e308314204f" />

```sql
delete from Customer
where GRADE=2 and CUST_NAME LIKE 'M%' and PAYMENT_AMT < 3000;
```

**Output:**
<img width="1213" height="482" alt="Screenshot 2025-10-15 103656" src="https://github.com/user-attachments/assets/2894f928-05bb-4204-814e-d1c9f284a429" />

**Question 9**
---
<img width="1228" height="549" alt="Screenshot 2025-10-15 103818" src="https://github.com/user-attachments/assets/d1c651b3-79e8-40a5-b4c2-22bd293fdd26" />

```sql
delete from Doctors
where specialization IN ('Pediatrics','Cardiology') and last_name = 'Brown';
```

**Output:**
<img width="1219" height="827" alt="Screenshot 2025-10-15 103843" src="https://github.com/user-attachments/assets/1a800666-f761-41aa-9dbd-2ef93c75fd36" />

**Question 10**
---
<img width="1223" height="520" alt="Screenshot 2025-10-15 104028" src="https://github.com/user-attachments/assets/8fb218b1-5c3f-436c-93a0-0b6f983b75aa" />

```sql
delete from Customer
where (GRADE>2 and PAYMENT_AMT < (SELECT AVG(PAYMENT_AMT)from Customer)) or OUTSTANDING_AMT>8000;
```

**Output:**
<img width="1223" height="752" alt="Screenshot 2025-10-15 104121" src="https://github.com/user-attachments/assets/25b706c0-78e8-4ca4-a803-e5bc76970f1b" />

**SEB EXAM**

<img width="1354" height="78" alt="Screenshot 2025-10-15 104907" src="https://github.com/user-attachments/assets/51269097-bc66-455b-a288-d96c12161f60" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
