# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- <img width="1225" height="314" alt="image" src="https://github.com/user-attachments/assets/43edf504-a3ec-484e-a476-6b6b77f8659b" />


```sql
-- CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1193" height="275" alt="image" src="https://github.com/user-attachments/assets/556f3e4d-8418-47ae-9d6e-1a9e5f3d67fb" />


**Question 2**
---
-- <img width="1082" height="246" alt="image" src="https://github.com/user-attachments/assets/f301387c-cc5d-4a15-9932-068d013cc90c" />


```sql
-- INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (201, 'David Lee', 'M', 'Physics', 92);
```

**Output:**

<img width="1234" height="303" alt="image" src="https://github.com/user-attachments/assets/36a1715f-d216-4171-b3ff-daf9bafb8fc6" />


**Question 3**
---
-- <img width="882" height="445" alt="image" src="https://github.com/user-attachments/assets/516b46e5-4ed8-4b47-8d7b-d3cc4dbf428c" />


```sql
-- INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES
(202, 'Ella King', 'F', 'Chemistry', 87),
(203, 'James Bond', 'M', 'Literature', 78);
```

**Output:**

<img width="1204" height="330" alt="image" src="https://github.com/user-attachments/assets/a929924a-72c1-42b5-9bdf-6736dfd9aabe" />


**Question 4**
---
-- <img width="770" height="339" alt="image" src="https://github.com/user-attachments/assets/5bf39246-3196-42ba-9641-c08c71824c96" />


```sql
-- CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INTEGER CHECK (Stock >= 0)
);
```

**Output:**

<img width="1214" height="357" alt="image" src="https://github.com/user-attachments/assets/be9f4019-fb67-4319-b2a8-2f585716806c" />


**Question 5**
---
-- <img width="967" height="277" alt="image" src="https://github.com/user-attachments/assets/a6d368dd-abfc-4260-af15-9a5cf6b77a32" />


```sql
-- ALTER TABLE employee
ADD COLUMN designation varchar(50);

```

**Output:**

<img width="1221" height="371" alt="image" src="https://github.com/user-attachments/assets/8a90bc78-e5cd-4d3e-af90-b428c354772b" />


**Question 6**
---
--<img width="1218" height="498" alt="image" src="https://github.com/user-attachments/assets/0b3b59f9-0f59-4708-adf1-aa9072e846b1" />


```sql
-- ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;
```

**Output:**

<img width="1221" height="449" alt="image" src="https://github.com/user-attachments/assets/da16b08b-24f3-4d5b-af5d-c2fb7d53a711" />


**Question 7**
---
-- <img width="962" height="379" alt="image" src="https://github.com/user-attachments/assets/a4445fb6-fc9e-4a80-9cfb-ad936951871b" />


```sql
-- CREATE TABLE Events (
    EventID INTEGER,
    EventName TEXT,
    EventDate DATE
);
```

**Output:**

<img width="1221" height="443" alt="image" src="https://github.com/user-attachments/assets/e221ec25-876b-4ee4-a8c4-5a71b9ac3c93" />


**Question 8**
---
-- <img width="1214" height="408" alt="image" src="https://github.com/user-attachments/assets/d26f86ed-f165-4293-bfc6-6214918ffab0" />


```sql
-- CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT UNIQUE NOT NULL,
    Price REAL CHECK (Price > 0),
    StockQuantity INTEGER CHECK (StockQuantity >= 0)
);
```

**Output:**

<img width="1213" height="355" alt="image" src="https://github.com/user-attachments/assets/1fa6972e-7358-4754-adf7-63f2daf6f891" />


**Question 9**
---
-- <img width="694" height="190" alt="image" src="https://github.com/user-attachments/assets/4db91bfe-3d94-4765-bfac-ffd883f712df" />


```sql
-- CREATE TABLE Invoices (
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    Amount REAL CHECK (Amount > 0),
    DueDate DATE CHECK (DueDate > InvoiceDate),
    OrderID INTEGER,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

<img width="1220" height="350" alt="image" src="https://github.com/user-attachments/assets/e8f16146-4982-411a-92e3-eee826833981" />


**Question 10**
---
--<img width="1005" height="339" alt="image" src="https://github.com/user-attachments/assets/6d6134c4-9bb7-4cc3-883f-481ad87024ef" />


```sql
-- Insert all books from Out_of_print_books into Books
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```

**Output:**

<img width="1217" height="730" alt="image" src="https://github.com/user-attachments/assets/a760986e-40a0-46c6-95e9-c35a57dabdb4" />


<img width="1522" height="653" alt="image" src="https://github.com/user-attachments/assets/7305a552-c651-45fe-b91d-82986604ee64" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
