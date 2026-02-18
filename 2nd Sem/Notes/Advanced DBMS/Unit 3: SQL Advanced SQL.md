# Unit 3: SQL / Advanced SQL (10 Hrs)

---

# 1. General Concepts of SQL

---

## 1.1 What is SQL?

* SQL = Structured Query Language.
* Standard language for relational databases.
* Based on relational algebra & tuple relational calculus.
* Declarative (non-procedural) language → specifies *what*, not *how*.

---

## 1.2 History & Standardization

* Developed by IBM (System R project).
* Standardized by ANSI & ISO.
* Used in:

  * MySQL
  * Oracle Database
  * Microsoft SQL Server
  * PostgreSQL

---

## 1.3 Categories of SQL Commands

### 1. DDL (Data Definition Language)

* CREATE
* ALTER
* DROP
* TRUNCATE

### 2. DML (Data Manipulation Language)

* SELECT
* INSERT
* UPDATE
* DELETE

### 3. DCL (Data Control Language)

* GRANT
* REVOKE

### 4. TCL (Transaction Control Language)

* COMMIT
* ROLLBACK
* SAVEPOINT

---

# 2. Basic Structure of SQL Queries

---

## 2.1 Basic SELECT Structure

```sql
SELECT attribute_list
FROM table_name
WHERE condition
GROUP BY attribute
HAVING condition
ORDER BY attribute;
```

---

## 2.2 Execution Order (Logical Order)

1. FROM
2. WHERE
3. GROUP BY
4. HAVING
5. SELECT
6. ORDER BY

---

## 2.3 Example Schema

STUDENT(SID, Name, Dept, Marks)
COURSE(CID, CourseName, Credits)

---

# 3. Various Examples Related with SQL Queries

---

## 3.1 Selection

```sql
SELECT * FROM STUDENT
WHERE Marks > 80;
```

✔ Retrieves students scoring above 80.

---

## 3.2 Projection

```sql
SELECT Name, Dept FROM STUDENT;
```

✔ Retrieves only specific columns.

---

## 3.3 Aggregation

```sql
SELECT AVG(Marks) FROM STUDENT;
```

Functions:

* COUNT()
* SUM()
* AVG()
* MIN()
* MAX()

---

## 3.4 GROUP BY

```sql
SELECT Dept, AVG(Marks)
FROM STUDENT
GROUP BY Dept;
```

✔ Department-wise average marks.

---

## 3.5 HAVING

```sql
SELECT Dept, AVG(Marks)
FROM STUDENT
GROUP BY Dept
HAVING AVG(Marks) > 70;
```

✔ Filters grouped results.

---

## 3.6 JOIN Operations

### 1. Inner Join

```sql
SELECT S.Name, C.CourseName
FROM STUDENT S
JOIN COURSE C ON S.CID = C.CID;
```

### 2. Left Outer Join

* Includes unmatched rows from left table.

### 3. Right Outer Join

### 4. Full Outer Join

---

## 3.7 Nested Queries (Subqueries)

```sql
SELECT Name
FROM STUDENT
WHERE Marks > (SELECT AVG(Marks) FROM STUDENT);
```

✔ Students scoring above average.

---

## 3.8 Correlated Subquery

```sql
SELECT Name
FROM STUDENT S
WHERE Marks > (
   SELECT AVG(Marks)
   FROM STUDENT
   WHERE Dept = S.Dept
);
```

✔ Students scoring above department average.

---

# 4. SQL Data Types & Schemas

---

## 4.1 Numeric Data Types

* INT
* SMALLINT
* BIGINT
* DECIMAL(p,s)
* FLOAT

---

## 4.2 Character Data Types

* CHAR(n)
* VARCHAR(n)
* TEXT

---

## 4.3 Date & Time Data Types

* DATE
* TIME
* TIMESTAMP
* DATETIME

---

## 4.4 Boolean Data Type

* BOOLEAN / BIT

---

## 4.5 BLOB Data Type

* Used for:

  * Images
  * Videos
  * Binary data

---

## 4.6 Schema

### Definition:

* Logical container of database objects.

### Example:

```sql
CREATE SCHEMA University;
```

### Advantages:

* Logical grouping
* Security control
* Name conflict avoidance

---

# 5. Integrity Constraints

---

## 5.1 Domain Constraint

* Restricts data type.
* Example:
  Marks INT CHECK (Marks BETWEEN 0 AND 100)

---

## 5.2 Entity Integrity

* Primary key cannot be NULL.

---

## 5.3 Referential Integrity

* Foreign key must match primary key of referenced table.

```sql
FOREIGN KEY (CID) REFERENCES COURSE(CID)
```

---

## 5.4 Key Constraints

* PRIMARY KEY
* UNIQUE

---

## 5.5 Check Constraint

```sql
CHECK (Salary > 0)
```

---

## 5.6 NOT NULL Constraint

```sql
Name VARCHAR(50) NOT NULL
```

---

## 5.7 DEFAULT Constraint

```sql
Dept VARCHAR(20) DEFAULT 'ISE'
```

---

## 5.8 Advantages of Constraints

* Maintains consistency
* Prevents invalid data
* Improves data quality

---

# 6. Advanced SQL Features

---

## 6.1 Views

### Definition:

* Virtual table.

```sql
CREATE VIEW TopStudents AS
SELECT Name, Marks
FROM STUDENT
WHERE Marks > 80;
```

### Advantages:

* Security
* Simplifies complex queries

### Disadvantages:

* Performance overhead

---

## 6.2 Indexes

```sql
CREATE INDEX idx_name ON STUDENT(Name);
```

### Advantages:

* Faster search
* Optimized query performance

### Disadvantages:

* Extra storage
* Slower insert/update

---

## 6.3 Triggers

### Definition:

* Automatic procedure executed on event.

```sql
CREATE TRIGGER UpdateAudit
AFTER UPDATE ON STUDENT
FOR EACH ROW
INSERT INTO AUDIT VALUES(...);
```

### Uses:

* Auditing
* Logging
* Enforcing business rules

---

## 6.4 Stored Procedures

```sql
CREATE PROCEDURE GetStudents()
BEGIN
   SELECT * FROM STUDENT;
END;
```

### Advantages:

* Code reuse
* Improved performance
* Security

---

## 6.5 Functions

* Returns a value.
* Used in queries.

---

## 6.6 Transactions

### ACID Properties:

* Atomicity
* Consistency
* Isolation
* Durability

Example:

```sql
BEGIN;
UPDATE Account SET Balance=Balance-500 WHERE ID=1;
COMMIT;
```

---

## 6.7 Window Functions (Modern SQL)

```sql
SELECT Name, 
       RANK() OVER (ORDER BY Marks DESC)
FROM STUDENT;
```

✔ Used for ranking, running totals.

---

## 6.8 Common Table Expression (CTE)

```sql
WITH HighMarks AS (
   SELECT * FROM STUDENT WHERE Marks > 80
)
SELECT * FROM HighMarks;
```

---

# Advantages of SQL

* Standardized language
* Easy to learn
* Powerful querying
* Data integrity enforcement
* Scalable

---

# Disadvantages of SQL

* Complex queries may be slow
* Vendor-specific extensions
* Limited for unstructured data

---

# Important Exam-Oriented Questions

1. Explain basic structure of SQL query.
2. Write SQL queries for:

   * Students scoring above average.
   * Department-wise average marks.
3. Explain integrity constraints with examples.
4. Explain JOIN types with example.
5. Explain views and indexes.
6. What are stored procedures and triggers?
7. Explain ACID properties.
8. Differentiate WHERE and HAVING.
9. Explain correlated subquery.
10. Discuss advanced SQL features.

---
