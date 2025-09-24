# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:

<img width="594" height="474" alt="Screenshot 2025-09-24 103759" src="https://github.com/user-attachments/assets/e682e52f-b13d-4d7a-b135-46d8e7646b84" />


### Entities and Attributes

| Entity         | Attributes (PK, FK)                                  | Notes                                 |
| -------------- | ---------------------------------------------------- | ------------------------------------- |
| **Member**     | **Member\_ID (PK)**, Name, MembershipType, StartDate | Each member has unique ID and details |
| **Program**    | **Trainer\_ID (PK)**, Name                           | Program conducted by trainers         |
| **Attendance** | **Attendance\_ID (PK, FK)**                          | Tracks members’ presence in sessions  |
| **Payment**    | **Payment\_ID (PK)**, MembershipFee, SessionFee      | Payment linked to attendance/members  |


### Relationships and Constraints

| Relationship                            | Cardinality                                        | Participation                  | Notes                                                          |
| --------------------------------------- | -------------------------------------------------- | ------------------------------ | -------------------------------------------------------------- |
| **joins** (Member–Program)              | 1\:N (Member to Program), N\:M (Program to Member) | Total participation of Member  | Members can join many programs; programs can have many members |
| **is recorded in** (Attendance–Member)  | 1\:N                                               | Partial participation          | One member can have many attendance records                    |
| **is booked by** (Attendance–Payment)   | 1\:N                                               | Total participation of Payment | Each payment is linked to attendance                           |
| **is tracked for** (Attendance–Payment) | 1\:N                                               | Partial participation          | Payment tracks session fees                                    |
| **conducts** (Program–Trainer)          | 1\:M (Trainer conducts multiple Programs)          | Total participation of Program | Each program must have a trainer                               |


### Assumptions
- Each Member has a unique Member_ID.

- Each Program is conducted by exactly one trainer.

- Attendance is recorded for each session a member attends.


---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
