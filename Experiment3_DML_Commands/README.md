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
-- <img width="1210" height="581" alt="image" src="https://github.com/user-attachments/assets/6473a008-b856-4e01-a187-9caf3e5eac3b" />


```sql
-- UPDATE employees
SET salary = 8000
WHERE employee_id = 105
AND salary < 5000;
```

**Output:**

<img width="1217" height="315" alt="image" src="https://github.com/user-attachments/assets/893671d1-d09a-4ec5-8c56-023f09c68354" />


**Question 2**
---
-- <img width="748" height="83" alt="image" src="https://github.com/user-attachments/assets/20d01b25-6b66-4660-9eb7-f3f8c309c921" />


```sql
-- UPDATE customer
SET grade = 5
WHERE city = 'Chennai';
```

**Output:**

<img width="1224" height="536" alt="image" src="https://github.com/user-attachments/assets/cd3032ee-6be6-45fc-be16-3193f646e582" />


**Question 3**
---
-- <img width="882" height="529" alt="image" src="https://github.com/user-attachments/assets/4d73f4bd-ceac-43f6-9f0f-609a415965d1" />


```sql
-- UPDATE products
SET sell_price = sell_price * 1.10
WHERE supplier_id =6;
```

**Output:**

<img width="1218" height="663" alt="image" src="https://github.com/user-attachments/assets/77a6e3a1-1a65-4279-9671-39bd9da0b32f" />


**Question 4**
---
-- <img width="1213" height="770" alt="image" src="https://github.com/user-attachments/assets/c68e8cf3-a2ee-42cb-a28a-6fc8188882b8" />


```sql
-- UPDATE employees
SET first_name = 'John'
WHERE department_id = 80
AND commission_pct < 0.35;
```

**Output:**

![O<img width="1213" height="617" alt="image" src="https://github.com/user-attachments/assets/e98b753e-52fa-4335-bbcd-03a11ddc7e4d" />


**Question 5**
---
-- <img width="918" height="633" alt="image" src="https://github.com/user-attachments/assets/b237cb36-dd1f-47ce-9878-4ea5005c4d90" />


```sql
-- UPDATE employees
SET hire_date = '2024-01-24'
WHERE department_id = 50;
```

**Output:**

<img width="1223" height="353" alt="image" src="https://github.com/user-attachments/assets/eaeaf8df-48e3-42ef-8a9b-410e37b314a8" />

**Question 6**
---
-- <img width="1231" height="488" alt="image" src="https://github.com/user-attachments/assets/37e2134f-03e5-4bbf-bd7f-410020f821d1" />


```sql
-- DELETE FROM customer
WHERE GRADE = 2
AND CUST_NAME LIKE 'M%'
AND PAYMENT_AMT < 3000;
```

**Output:**
<img width="1233" height="491" alt="image" src="https://github.com/user-attachments/assets/7100a7bb-e43b-47c1-8033-41ce404320e7" />


**Question 7**
---
--<img width="866" height="150" alt="image" src="https://github.com/user-attachments/assets/f9a92eb3-72e2-422e-b016-e3ab7118719f" />


```sql
-- DELETE FROM doctors
WHERE doctor_id = 1;
```

**Output:**

<img width="1237" height="328" alt="image" src="https://github.com/user-attachments/assets/cadf412f-6491-4d18-ba14-5170cd11128b" />


**Question 8**
---
--<img width="1222" height="666" alt="image" src="https://github.com/user-attachments/assets/5b5ecad0-e108-4061-aa03-09906f13d089" />


```sql
-- DELETE FROM customer
WHERE GRADE < 2;
```

**Output:**

<img width="743" height="621" alt="image" src="https://github.com/user-attachments/assets/057e4a76-9d71-4c70-8b4c-f6be500817db" />


**Question 9**
---
-- <img width="750" height="545" alt="image" src="https://github.com/user-attachments/assets/abecfcdd-5a35-4090-9208-c8e8b6219543" />


```sql
-- DELETE FROM doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1258" height="473" alt="image" src="https://github.com/user-attachments/assets/668a8153-2fbe-4858-9e39-75109620d7d6" />


**Question 10**
---
-- <img width="1220" height="797" alt="image" src="https://github.com/user-attachments/assets/3116ffaf-3260-442b-b0d2-2d0b0d133a7e" />


```sql
-- DELETE FROM customer
WHERE CUST_CITY <> 'New York'
AND OUTSTANDING_AMT > 5000;
```

**Output:**

<img width="1219" height="662" alt="image" src="https://github.com/user-attachments/assets/3a1d8fc0-f1b9-4f9e-a6d1-6cb79cbccfd6" />

<img width="1436" height="581" alt="image" src="https://github.com/user-attachments/assets/be708513-e5e5-4a06-ab40-82930aa67836" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
