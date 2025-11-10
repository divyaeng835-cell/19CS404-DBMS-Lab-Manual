# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.

## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql 
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
### SQL Code:
```sql
DECLARE
    num1 NUMBER := 45;
    num2 NUMBER := 80;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```
**Expected Output:**  
Greater number is: 80

<img width="760" height="281" alt="Screenshot 2025-11-10 133233" src="https://github.com/user-attachments/assets/81b948f8-142e-4f59-9a6e-ca853a9ca2d0" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
### SQL Code:
```sql
DECLARE
    n NUMBER := 10;
    sum NUMBER := 0;
    i NUMBER := 1;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
**Expected Output:**  
Sum of first 10 natural numbers is: 55
<img width="758" height="272" alt="Screenshot 2025-11-10 133311" src="https://github.com/user-attachments/assets/03f1a934-8a66-4b0a-b9fb-9055ba2b007e" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
### SQL Code:
```sql
DECLARE
    n NUMBER := 7;       
    a NUMBER := 0;      
    b NUMBER := 1;       
    c NUMBER;            
    i NUMBER := 3;       
BEGIN
    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT('Fibonacci sequence: ' || a || ', ' || b);
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT(', ' || c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.NEW_LINE;  
END;
/
```
**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
<img width="762" height="302" alt="Screenshot 2025-11-10 133520" src="https://github.com/user-attachments/assets/51aed363-23e8-433c-a1fe-36b9069a42dd" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
### SQL Code:
```sql
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    rem NUMBER;
    temp NUMBER;
BEGIN
    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    temp := n;
    WHILE temp > 0 LOOP
        rem := MOD(temp, 10);            
        rev := (rev * 10) + rem;    
        temp := FLOOR(temp / 10);       
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
```
**Expected Output:**  
n = 1535  
Reversed number is 5351

<img width="761" height="296" alt="Screenshot 2025-11-10 133834" src="https://github.com/user-attachments/assets/c71be0ac-c6fe-4606-8d7e-f689df63cbc0" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
### SQL Code:
```sql
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    IF (a > b) AND (a > c) THEN
        largest := a;
    ELSIF (b > a) AND (b > c) THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
    DBMS_OUTPUT.PUT_LINE('Largest of three numbers is ' || largest);
END;
/
```
**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

<img width="762" height="272" alt="Screenshot 2025-11-10 133902" src="https://github.com/user-attachments/assets/7f065ea6-1831-4016-a141-bcefb084044c" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.


