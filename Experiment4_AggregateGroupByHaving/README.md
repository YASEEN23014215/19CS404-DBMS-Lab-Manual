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
-- <img width="1191" height="635" alt="image" src="https://github.com/user-attachments/assets/954f7ca6-510f-4fe7-bab1-df0def454c29" />


```sql
-- SELECT PatientID, COUNT(*) AS TotalMedications
FROM Prescriptions
GROUP BY PatientID;
```

**Output:**

<img width="1167" height="820" alt="image" src="https://github.com/user-attachments/assets/e61e7719-8c41-41a7-b930-73ecdf697c9e" />


**Question 2**
---
-- <img width="1194" height="470" alt="image" src="https://github.com/user-attachments/assets/53061996-5b90-46d8-a06b-7e1ec019049a" />


```sql
-- SELECT strftime('%Y-%m', created_date) AS Month, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY strftime('%Y-%m', created_date);

```

**Output:**

<img width="1221" height="728" alt="image" src="https://github.com/user-attachments/assets/35395542-f18a-421c-ad39-07ae8aaadd30" />


**Question 3**
---
-- <img width="1152" height="446" alt="image" src="https://github.com/user-attachments/assets/391ef3e5-91d4-4c1f-90bc-07170dec6a73" />


```sql
-- SELECT Gender, COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="1075" height="424" alt="image" src="https://github.com/user-attachments/assets/542ed005-70d8-488d-8701-375f41021b41" />


**Question 4**
---
-- <img width="1071" height="461" alt="image" src="https://github.com/user-attachments/assets/34a23d21-1871-466e-a904-4c82fad72dad" />


```sql
--SELECT name, email, LENGTH(email) AS min_email_length
FROM customer
WHERE LENGTH(email) = (SELECT MIN(LENGTH(email)) FROM customer)
ORDER BY id
LIMIT 1;
```

**Output:**
<img width="1163" height="373" alt="image" src="https://github.com/user-attachments/assets/55f4caa3-e2a0-4427-ae1c-1e144bce0402" />


**Question 5**
---
-- <img width="1186" height="548" alt="image" src="https://github.com/user-attachments/assets/8beb3088-5a8a-460c-a954-84051c0ee8dd" />


```sql
-- SELECT SUM(inventory) AS total_available_amount
FROM fruits
WHERE price > 0.5;
```

**Output:**

<img width="958" height="386" alt="image" src="https://github.com/user-attachments/assets/467749ae-9f60-4ec6-8f74-e428cc13f18d" />

**Question 6**
---
-- <img width="985" height="498" alt="image" src="https://github.com/user-attachments/assets/9c1c5fc6-05fc-4599-883d-22bf10304713" />



```sql
-- SELECT name AS Employee_Name, age AS Age
FROM employee
ORDER BY age ASC, id ASC
LIMIT 1;
```

**Output:**

<img width="834" height="376" alt="image" src="https://github.com/user-attachments/assets/9eba2bb0-48c9-448c-95bf-495be99bbd36" />


**Question 7**
---
--<img width="1195" height="473" alt="image" src="https://github.com/user-attachments/assets/a61b9100-5484-4809-9629-f9941cc1da6c" />


```sql
-- SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**

<img width="677" height="391" alt="image" src="https://github.com/user-attachments/assets/8d3161b0-2f6f-4e5c-9a1f-987d9382502c" />


**Question 8**
---
-- <img width="1284" height="482" alt="image" src="https://github.com/user-attachments/assets/c8b01ef8-2aeb-4dc6-a74a-7a1490014f3f" />


```sql
-- SELECT category_id, SUM(price) AS Total_Cost
FROM products
GROUP BY category_id
HAVING SUM(price) > 50;

```

**Output:**

<img width="963" height="403" alt="image" src="https://github.com/user-attachments/assets/83293cd6-8b2f-4f14-96e0-b1f6d77375aa" />


**Question 9**
---
-- <img width="1220" height="470" alt="image" src="https://github.com/user-attachments/assets/ac27ab22-5252-43c1-a03d-99c8289dbf40" />


```sql
-- SELECT category_id, MIN(price) AS Price
FROM products
GROUP BY category_id
HAVING MIN(price) < 10;
```

**Output:**

<img width="796" height="427" alt="image" src="https://github.com/user-attachments/assets/02d62af5-1bbe-47fd-a68e-03b56f4ffe44" />


**Question 10**
---
-- <img width="1185" height="501" alt="image" src="https://github.com/user-attachments/assets/a8e55c37-efeb-4e1b-b823-498060d379ea" />


```sql
-- SELECT address, SUM(salary)
FROM customer1
GROUP BY address
HAVING SUM(salary) > 2000
ORDER BY address;
```

**Output:**

<img width="814" height="551" alt="image" src="https://github.com/user-attachments/assets/b451b346-3bca-4539-8ae7-969be3f61d6d" />

<img width="1521" height="782" alt="image" src="https://github.com/user-attachments/assets/1e6b7a66-3dff-455a-b835-6953c49b6294" />




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
