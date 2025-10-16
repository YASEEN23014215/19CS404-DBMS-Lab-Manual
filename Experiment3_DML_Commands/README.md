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
-- 

```sql
-- UPDATE employees
SET salary = 8000
WHERE employee_id = 105
AND salary < 5000;
```

**Output:**

<img width="1205" height="299" alt="image" src="https://github.com/user-attachments/assets/eab7d9f4-f543-4664-bad7-b5468a60ad10" />


**Question 2**
---
-- <img width="702" height="80" alt="image" src="https://github.com/user-attachments/assets/e06a8630-9aa9-4db2-a07d-902e815a0b03" />


```sql
-- UPDATE customer
SET grade = 5
WHERE city = 'Chennai';
```

**Output:**
<img width="1210" height="542" alt="image" src="https://github.com/user-attachments/assets/7cdcfa0b-a433-46f9-afb4-c2e0a39ba2f1" />


**Question 3**
---
--<img width="890" height="527" alt="image" src="https://github.com/user-attachments/assets/b4962784-899a-425f-99da-877ee4ab82a2" />


```sql
-- UPDATE products
SET sell_price = sell_price * 1.10
WHERE supplier_id =6;
```

**Output:**

<img width="1215" height="653" alt="image" src="https://github.com/user-attachments/assets/2324a0af-1aa3-45e6-a196-a0c434840928" />


**Question 4**
---
<img width="1235" height="758" alt="image" src="https://github.com/user-attachments/assets/eba7d3e8-7e13-4d7a-8767-c86ada88fe3e" />


```sql
--UPDATE employees
SET first_name = 'John'
WHERE department_id = 80
AND commission_pct < 0.35;
```

**Output:**

<img width="1233" height="607" alt="image" src="https://github.com/user-attachments/assets/59eae7cd-094c-4aba-ac08-19389927e875" />


**Question 5**
---
-- <img width="956" height="637" alt="image" src="https://github.com/user-attachments/assets/d33224cf-0756-497e-a9ef-3962cafffc4f" />


```sql
-- UPDATE employees
SET hire_date = '2024-01-24'
WHERE department_id = 50;
```

**Output:**

<img width="1244" height="360" alt="image" src="https://github.com/user-attachments/assets/27887db5-21ec-415c-998b-f917fc6df8db" />


**Question 6**
---
-- <img width="1225" height="496" alt="image" src="https://github.com/user-attachments/assets/c36a40bc-0d58-4227-9b83-c1a0150b178f" />


```sql
-- DELETE FROM customer
WHERE GRADE = 2
AND CUST_NAME LIKE 'M%'
AND PAYMENT_AMT < 3000;
```

**Output:**
<img width="1232" height="468" alt="image" src="https://github.com/user-attachments/assets/0bb8e508-e537-489a-bb49-51be27477170" />


**Question 7**
---
-- <img width="1071" height="143" alt="image" src="https://github.com/user-attachments/assets/aba5d9b4-7146-479f-93d3-91f4e8012668" />


```sql
--DELETE FROM doctors
WHERE doctor_id = 1;
```

**Output:**

<img width="1217" height="335" alt="image" src="https://github.com/user-attachments/assets/28329830-c6a8-49f5-9464-f83dbf769248" />


**Question 8**
---
-- <img width="1218" height="675" alt="image" src="https://github.com/user-attachments/assets/621356cb-0453-4728-ae57-8f168d0897ba" />


```sql
--DELETE FROM customer
WHERE GRADE < 2;
```

**Output:**

<img width="799" height="632" alt="image" src="https://github.com/user-attachments/assets/a98ca655-a4ee-46b6-b89c-3ac25813f3f6" />


**Question 9**
---
-- <img width="798" height="537" alt="image" src="https://github.com/user-attachments/assets/1741cb79-89f6-44a3-88ad-68f120d1b2f3" />


```sql
-- DELETE FROM doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1247" height="781" alt="image" src="https://github.com/user-attachments/assets/0efff0b5-ac78-4e83-87af-dc4cfd229c94" />


**Question 10**
---
-- <img width="1219" height="508" alt="image" src="https://github.com/user-attachments/assets/98628bba-d0d0-40d3-aad0-efc06b593e9e" />


```sql
-- DELETE FROM customer
WHERE CUST_CITY <> 'New York'
AND OUTSTANDING_AMT > 5000;
```
**Output:**

<img width="1218" height="669" alt="image" src="https://github.com/user-attachments/assets/ef2be6fd-701c-410e-bc95-85d4f892c094" />

<img width="1457" height="584" alt="image" src="https://github.com/user-attachments/assets/260616ee-3690-4782-93e6-0625748b01c8" />



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
