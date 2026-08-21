
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
<img width="932" height="643" alt="image" src="https://github.com/user-attachments/assets/c1e73d4b-76c0-4544-9ac5-8a4aca24a784" />


```sql
DELETE FROM Surgeries
WHERE surgery_id=3 or surgeon_id=4
```

**Output:**
<img width="1228" height="797" alt="image" src="https://github.com/user-attachments/assets/cbccf17e-5f1b-4d61-8998-f6313a00c11a" />


**Question 2**
---
<img width="1227" height="677" alt="image" src="https://github.com/user-attachments/assets/7da92e22-e1f6-45c1-b852-96e5efe139bb" />


```sql
DELETE FROM Customer
WHERE GRADE!= 3
```

**Output:**

<img width="832" height="605" alt="image" src="https://github.com/user-attachments/assets/ccbcea96-80c8-43ae-aee0-71a396a93375" />


**Question 3**
---
<img width="807" height="567" alt="image" src="https://github.com/user-attachments/assets/a389cb46-4b34-4118-bf78-d70cc58af16a" />


```sql
DELETE FROM Surgeries
WHERE surgery_id=3
```

**Output:**
<img width="1232" height="468" alt="image" src="https://github.com/user-attachments/assets/cadb8614-120a-471b-81c0-40ad3e824f44" />


**Question 4**
---
<img width="1137" height="482" alt="image" src="https://github.com/user-attachments/assets/37dc8208-f5e8-475b-b4db-8e08c853c09f" />


```sql
SELECT *
FROM EmployeeInfo
WHERE EmpFname NOT IN ('Sanjay','Sonia');
```

**Output:**
<img width="1218" height="377" alt="image" src="https://github.com/user-attachments/assets/697091f5-c338-40d3-8ccf-6e9a8819ab57" />


**Question 5**
---
<img width="1135" height="677" alt="image" src="https://github.com/user-attachments/assets/177f90ce-2322-4bd3-806e-ee828ca29ca3" />


```sql
SELECT name,city
FROM salesman
WHERE city IN ('London','Rome');
```

**Output:**

<img width="757" height="446" alt="image" src="https://github.com/user-attachments/assets/58cf2a68-aa8c-44e0-85d8-d96370e99d4e" />


**Question 6**
---
<img width="1112" height="617" alt="image" src="https://github.com/user-attachments/assets/6a8eb802-cb09-4748-b483-e90c107a6460" />


```sql
SELECT
    product_id,
    original_price,
    discount_percentage,
    (original_price*(1-discount_percentage)) AS discounted_price
FROM Products
WHERE original_price BETWEEN 50 AND 150;
```

**Output:**

<img width="1225" height="385" alt="image" src="https://github.com/user-attachments/assets/cd89f0b9-b199-403a-96f9-3aa8c75befa2" />


**Question 7**
---
<img width="1027" height="322" alt="image" src="https://github.com/user-attachments/assets/2c1e09c8-6500-4174-b893-f7b46897e362" />


```sql
UPDATE Products
SET sell_price=sell_price*1.10
WHERE category='Bakery';
```

**Output:**
<img width="1228" height="520" alt="image" src="https://github.com/user-attachments/assets/a26406dc-ffff-4295-9fdf-07386c54c41e" />


**Question 8**
---
<img width="1212" height="375" alt="image" src="https://github.com/user-attachments/assets/806abd35-e840-436a-8a69-8cbe7932ec76" />


```sql
SELECT 
    product_id,
    original_price,
    discount_percentage,
    original_price*(1-discount_percentage) AS discounted_price
FROM products
WHERE (original_price * (1-discount_percentage)) BETWEEN 100 AND 250;
```

**Output:**

<img width="1243" height="385" alt="image" src="https://github.com/user-attachments/assets/3fc021ab-4399-4141-9367-9509016bc39d" />


**Question 9**
---
<img width="1207" height="570" alt="image" src="https://github.com/user-attachments/assets/b9d58d58-21c7-473a-9d54-db96b111371d" />

```sql
UPDATE Products
SET reorder_lvl = reorder_lvl*0.70
WHERE cost_price > 50 AND quantity <100;
```

**Output:**

<img width="1230" height="532" alt="image" src="https://github.com/user-attachments/assets/8ee8b70a-5b97-494b-9e2d-03f046dd9951" />


**Question 10**
---
<img width="930" height="676" alt="image" src="https://github.com/user-attachments/assets/32cc3a33-6198-44f5-85bc-43d1f8268e56" />


```sql
SELECT *
FROM emp
WHERE hiredate > '2020-01-01';
```

**Output:**

<img width="1237" height="456" alt="image" src="https://github.com/user-attachments/assets/c2c1f2b3-cb06-4f35-bce7-c06287627674" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
