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
-- <img width="1428" height="788" alt="image" src="https://github.com/user-attachments/assets/c2fc2aac-18e4-4d7d-ba07-5cd75b8f7e7f" />


```sql
-- SELECT p.*
FROM patients p
INNER JOIN doctors d 
    ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John'
  AND d.last_name = 'Smith';

```

**Output:**

<img width="1258" height="429" alt="image" src="https://github.com/user-attachments/assets/f2f798a7-98a6-42a2-a68e-24801d04cb0c" />


**Question 2**
---
-- <img width="1292" height="880" alt="image" src="https://github.com/user-attachments/assets/c9c9e233-f26e-4bb9-bb4c-7468359865ed" />


```sql
-- SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name AS "Salesman",
    s.city
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;

```

**Output:**

<img width="1261" height="902" alt="image" src="https://github.com/user-attachments/assets/29d35f04-9859-4eb3-9d92-f6b953833bad" />


**Question 3**
---
-- <img width="1250" height="389" alt="image" src="https://github.com/user-attachments/assets/682cbb7f-209c-4c60-8a0b-7af0e958d935" />


```sql
-- SELECT 
    c.*
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id
WHERE 
    o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

```

**Output:**

<img width="1270" height="529" alt="image" src="https://github.com/user-attachments/assets/6c091fae-b087-4ad6-98de-16cdab1487a4" />


**Question 4**
---
-- <img width="1275" height="718" alt="image" src="https://github.com/user-attachments/assets/24375887-3e7b-427b-8135-4406a853d5d1" />


```sql
-- SELECT 
    p.date_of_birth,
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a
ON 
    p.patient_id = a.patient_id
WHERE 
    p.first_name = 'Alice';

```

**Output:**

<img width="1269" height="426" alt="image" src="https://github.com/user-attachments/assets/282bcc30-7e47-4e7b-b3ab-96b70af1ed46" />


**Question 5**
---
-- <img width="1291" height="905" alt="image" src="https://github.com/user-attachments/assets/b34f8679-bb82-42e2-8c8b-6320065d5c17" />


```sql
-- SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id
ORDER BY 
    o.ord_date ASC;

```

**Output:**
<img width="1277" height="891" alt="image" src="https://github.com/user-attachments/assets/e8eeb56f-15dc-4324-9034-8a95848c527a" />


**Question 6**
---
-- <img width="1270" height="391" alt="image" src="https://github.com/user-attachments/assets/0983ed12-41ad-4e53-abda-e18183cdaf44" />


```sql
-- SELECT 
    c.cust_name
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id
WHERE 
    o.purch_amt < 100;

```

**Output:**

<img width="650" height="476" alt="image" src="https://github.com/user-attachments/assets/1815673d-0db0-4d27-b09e-4624b433a3b4" />


**Question 7**
---
-- <img width="1259" height="900" alt="image" src="https://github.com/user-attachments/assets/d2916d67-dfc4-4c5b-8b71-e1ca738ce6ae" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name AS,
    c.city AS "Customer_City",
    c.grade,
    s.name AS "Salesman name",
    s.city AS "Salesman city",
    s.commission
FROM 
    orders o
INNER JOIN 
    customer c 
    ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s 
    ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1274" height="723" alt="image" src="https://github.com/user-attachments/assets/c818e2b3-2536-4c79-a359-249c652fb4ad" />


**Question 8**
---
-- <img width="1086" height="809" alt="image" src="https://github.com/user-attachments/assets/a8d373a0-8359-4206-ae07-7912bcbdaad9" />


```sql
--SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission AS "commission"
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.city <> s.city
    AND s.commission > 0.12;

```

**Output:**
<img width="1275" height="643" alt="image" src="https://github.com/user-attachments/assets/a7cef4ba-139c-4568-8d21-ed1cb0720ee0" />


**Question 9**
---
-- <img width="1264" height="725" alt="image" src="https://github.com/user-attachments/assets/b13fbb49-0a77-4604-a147-a049ec722a5a" />


```sql
-- SELECT 
    p.first_name AS patient_name,
    t.test_name
FROM 
    patients p
INNER JOIN 
    test_results t
ON 
    p.patient_id = t.patient_id;

```

**Output:**

<img width="837" height="546" alt="image" src="https://github.com/user-attachments/assets/48c36526-310d-47cc-a585-f346d1385ce7" />


**Question 10**
---
-- <img width="991" height="884" alt="image" src="https://github.com/user-attachments/assets/5cfd6436-46fc-4d51-b0ef-0075f2c3b3bf" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
INNER JOIN 
    customer c
ON 
    o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

<img width="1260" height="492" alt="image" src="https://github.com/user-attachments/assets/c0f45ab7-309d-49a0-b338-b068b412a5d8" />
<img width="1492" height="737" alt="image" src="https://github.com/user-attachments/assets/6e198a9d-3cfc-4f93-842a-b7bc8c759a51" />




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
