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
-- <img width="1262" height="800" alt="image" src="https://github.com/user-attachments/assets/07c05141-5eb5-4cd1-adbd-d0ef26430b3a" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.customer_id,
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';

```

**Output:**

<img width="1263" height="561" alt="image" src="https://github.com/user-attachments/assets/3cef3c2d-f59c-4e1f-a4cb-2b15fb933c6c" />


**Question 2**
---
-- <img width="1103" height="679" alt="image" src="https://github.com/user-attachments/assets/1695a4df-79bb-43cc-a795-25af63f5939e" />


```sql
-- SELECT DISTINCT s.commission
FROM salesman s
JOIN customer c
  ON s.salesman_id = c.salesman_id
WHERE c.city = 'Paris';

```

**Output:**

<img width="567" height="445" alt="image" src="https://github.com/user-attachments/assets/1dc47ddf-2bdd-4e90-bc35-a18147270350" />


**Question 3**
---
-- <img width="1227" height="617" alt="image" src="https://github.com/user-attachments/assets/c8138028-498d-400e-b939-7be66168b5e4" />


```sql
-- SELECT 
    ord_no,
    purch_amt,
    ord_date,
    customer_id,
    salesman_id
FROM 
    orders
WHERE 
    purch_amt > (
        SELECT 
            AVG(purch_amt)
        FROM 
            orders
        WHERE 
            ord_date = '2012-10-10'
    );

```

**Output:**

<img width="1272" height="531" alt="image" src="https://github.com/user-attachments/assets/3062c87d-9c1d-4cc8-b8ce-c2f9f8a5ac53" />


**Question 4**
---
-- <img width="1098" height="623" alt="image" src="https://github.com/user-attachments/assets/938438e7-2e2c-4374-919e-819dcc4145c9" />


```sql
-- SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi'
  AND AGE < 30
ORDER BY ID;

```

**Output:**

<img width="1276" height="437" alt="image" src="https://github.com/user-attachments/assets/60783a91-39d5-4374-8413-d77ac09d73af" />


**Question 5**
---
-- <img width="1153" height="540" alt="image" src="https://github.com/user-attachments/assets/4c457dac-8557-4cf2-9ac7-16c6554ae35f" />


```sql
-- SELECT name, city
FROM customer
WHERE city IN (
    SELECT city 
    FROM customer 
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="827" height="535" alt="image" src="https://github.com/user-attachments/assets/c3388f08-b4b2-4bd2-8ab7-60d7112a81fa" />


**Question 6**
---
-- <img width="1242" height="816" alt="image" src="https://github.com/user-attachments/assets/78ddf14a-9d2b-42b6-9c9e-60d618519ea4" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.commission = (
        SELECT MAX(commission)
        FROM salesman
    );

```

**Output:**

<img width="1066" height="547" alt="image" src="https://github.com/user-attachments/assets/a1c0afbc-f066-45b9-aa91-e52f80220292" />


**Question 7**
---
-- <img width="1248" height="648" alt="image" src="https://github.com/user-attachments/assets/55e722ef-8476-4883-9b56-3c84a797f9af" />


```sql
-- SELECT 
    student_name,
    grade
FROM 
    grades g
WHERE 
    grade = (
        SELECT 
            MAX(grade)
        FROM 
            grades
        WHERE 
            subject = g.subject
    );

```

**Output:**

<img width="878" height="511" alt="image" src="https://github.com/user-attachments/assets/0b42bd13-01ed-433c-86c6-b037a1044a56" />


**Question 8**
---
-- <img width="1214" height="743" alt="image" src="https://github.com/user-attachments/assets/b3b9a930-99f0-47de-a84e-4e5894b5edc4" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.customer_id,
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.name = 'Paul Adam';

```

**Output:**

<img width="1265" height="462" alt="image" src="https://github.com/user-attachments/assets/0157f5dd-19a9-476a-9a24-2bfe9e94ba49" />


**Question 9**
---
-- <img width="1240" height="622" alt="image" src="https://github.com/user-attachments/assets/cbc7cf65-4b11-4a43-9370-8822d8d35e79" />


```sql
-- SELECT *
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

<img width="1268" height="530" alt="image" src="https://github.com/user-attachments/assets/b31e6199-6d31-4a46-9be8-224194872aba" />


**Question 10**
---
-- <img width="1268" height="530" alt="image" src="https://github.com/user-attachments/assets/1d8e80c2-54c3-4063-94f9-150c2367d32e" />


```sql
-- SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.customer_id,
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'London';

```

**Output:**

<img width="1268" height="483" alt="image" src="https://github.com/user-attachments/assets/01030b37-5302-4b5c-a98d-7cb99da15da0" />
<img width="1504" height="754" alt="image" src="https://github.com/user-attachments/assets/94398efc-0eaa-474e-ad45-1c4e1a1d34f7" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
