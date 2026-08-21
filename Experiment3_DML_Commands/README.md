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
<img width="862" height="366" alt="image" src="https://github.com/user-attachments/assets/4d479d8c-0dff-4538-8fe4-989453ed84bc" />


```sql
INSERT INTO
Customers(CustomerID,Name,Address,Email)
SELECT
CustomerID,Name,Address,Email
FROM Old_Customers;
```

**Output:**
<img width="1217" height="372" alt="image" src="https://github.com/user-attachments/assets/9a766c5c-fc6e-4b00-914f-7fce3cccae96" />


**Question 2**
---
<img width="1072" height="470" alt="image" src="https://github.com/user-attachments/assets/975095d3-a1d1-46f7-b59e-7e65f902e431" />


```sql
CREATE TABLE Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME
);
```

**Output:**
<img width="1232" height="497" alt="image" src="https://github.com/user-attachments/assets/6e852b9b-c666-494b-abf5-7b609e4b48f3" />


**Question 3**
---
<img width="1230" height="362" alt="image" src="https://github.com/user-attachments/assets/86d2b923-a534-47e6-8c7a-b765d7e5c390" />


```sql
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**
<img width="1230" height="363" alt="image" src="https://github.com/user-attachments/assets/d0b36027-376e-4329-b292-0685fa6a0db2" />


**Question 4**
---
<img width="912" height="492" alt="image" src="https://github.com/user-attachments/assets/611c4b01-e876-4d9b-93e7-cab94b6cc211" />


```sql
INSERT INTO Student_details
SELECT *
FROM Archived_Students
```

**Output:**

<img width="1225" height="361" alt="image" src="https://github.com/user-attachments/assets/4a351eeb-8f80-44d2-b739-d6f4daf478ff" />


**Question 5**
---
<img width="1162" height="403" alt="image" src="https://github.com/user-attachments/assets/67f1ac13-ca53-4752-9761-2f5b01dd45b9" />


```sql
ALTER TABLE Student_details
ADD Column ParentsNumber number;
ALTER TABLE Student_details
ADD Column Adhar_Number number;
```

**Output:**

<img width="1212" height="453" alt="image" src="https://github.com/user-attachments/assets/4b806173-45d8-4a72-b4da-97f6d4e7a869" />

**Question 6**
---
<img width="782" height="358" alt="image" src="https://github.com/user-attachments/assets/92b70870-0325-4f1e-b886-bd6711703ee5" />


```sql
CREATE TABLE Products(
ProductID PRIMARY KEY,
ProductName NOT NULL,
Price REAL CHECK (Price>0),
Stock INTEGER CHECK(Stock>=0)
);
```

**Output:**

<img width="1232" height="370" alt="image" src="https://github.com/user-attachments/assets/163f7188-1d61-448a-aa1b-41458ae44b37" />


**Question 7**
---
<img width="1232" height="431" alt="image" src="https://github.com/user-attachments/assets/6e153d54-9470-47da-99ab-461a4cc7a8b8" />

```sql
CREATE TABLE Attendance(
AttendanceID INTEGER,
EmployeeID INTEGER,
AttendanceDate DATE,
Status TEXT CHECK(Status IN('Present','Absent','Leave')),
FOREIGN KEY (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**

<img width="1221" height="357" alt="image" src="https://github.com/user-attachments/assets/7a34f073-63f7-4cd3-a1db-9ca0e80d4398" />


**Question 8**
---
<img width="1057" height="592" alt="image" src="https://github.com/user-attachments/assets/1dabf5b2-0a59-4d92-9d9d-2a96cccac2a6" />


```sql
ALTER TABLE Student_details
ADD Column Mobilenumber number;
```

**Output:**
<img width="1232" height="447" alt="image" src="https://github.com/user-attachments/assets/c198c52b-938e-47f8-82d2-95e6690cba41" />


**Question 9**
---
<img width="1225" height="447" alt="image" src="https://github.com/user-attachments/assets/f660f41d-b116-43c5-b467-c1941571cc4c" />


```sql
CREATE TABLE Employees(
EmployeeID INT PRIMARY KEY,
FirstName NOT NULL,
LastName NOT NULL,
Email UNIQUE,
Salary CHECK(Salary>0),
DepartmentID INT,
FOREIGN KEY (DEPARTMENTID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1231" height="507" alt="image" src="https://github.com/user-attachments/assets/684a59ab-4133-48ce-87ad-817fae45a63a" />


**Question 10**
---
<img width="1127" height="267" alt="image" src="https://github.com/user-attachments/assets/06ac5ec0-c5b3-4750-86bb-29f21a30b653" />


```sql
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES ('101','Laptop','Electronics',1500,50);
```

**Output:**

<img width="1232" height="332" alt="image" src="https://github.com/user-attachments/assets/cfec7ad4-078b-4717-aee7-c068824393a1" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
