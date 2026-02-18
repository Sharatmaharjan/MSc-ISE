# Unit 2: Relational Algebra (10 Hrs)

---

# 1. Basic Concepts of Relational Algebra

---

## 1.1 Relational Model

* Proposed by **E.F. Codd (1970)**.
* Based on **mathematical set theory** and **predicate logic**.
* Data is stored in the form of **relations (tables)**.

---

## 1.2 Important Terminologies

### 1. Relation

* A table with rows and columns.
* Example: STUDENT(SID, Name, Address)

### 2. Tuple

* A row in a relation.
* Example: (101, “Sharat”, “Biratnagar”)

### 3. Attribute

* Column of a table.
* Example: SID, Name

### 4. Domain

* Set of possible values for an attribute.
* Example: Age → Integer (0–120)

### 5. Degree

* Number of attributes in a relation.

### 6. Cardinality

* Number of tuples in a relation.

---

## 1.3 Properties of Relations

* No duplicate tuples
* Order of rows does not matter
* Order of columns does not matter
* Atomic values (1NF)

---

## 1.4 Relational Algebra

### Definition:

* Procedural query language.
* Specifies **what to do and how to do it**.
* Input → Relation
* Output → Relation

### Used in:

* Query optimization
* Internal DBMS processing

---

# 2. DDL & DML

---

## 2.1 DDL (Data Definition Language)

### Purpose:

* Defines structure/schema of database.

### Commands:

* CREATE
* ALTER
* DROP
* TRUNCATE

### Example:

```sql
CREATE TABLE Student(
   SID INT PRIMARY KEY,
   Name VARCHAR(50),
   Address VARCHAR(100)
);
```

### Advantages:

* Schema control
* Structural integrity

### Disadvantages:

* Structural changes may affect applications

---

## 2.2 DML (Data Manipulation Language)

### Purpose:

* Manipulates data inside tables.

### Commands:

* SELECT
* INSERT
* UPDATE
* DELETE

### Example:

```sql
INSERT INTO Student VALUES(101,'Sharat','Biratnagar');
```

### Advantage:

* Flexible data handling

---

# 3. Structure of Relational Databases

---

## 3.1 Schema vs Instance

### Schema:

* Logical design of database.
* Fixed structure.

### Instance:

* Snapshot of database at a particular time.
* Changes frequently.

---

## 3.2 Keys in Relational Model

### 1. Super Key

* Set of attributes uniquely identifying tuples.

### 2. Candidate Key

* Minimal super key.

### 3. Primary Key

* Selected candidate key.

### 4. Foreign Key

* Attribute referencing primary key of another relation.

---

## 3.3 Example

STUDENT(SID, Name, CID)
COURSE(CID, CourseName)

* SID → Primary Key
* CID in STUDENT → Foreign Key

---

# 4. Fundamental Relational Algebra Operations

---

## 4.1 Selection (σ)

### Purpose:

* Select rows based on condition.

### Syntax:

σ condition (Relation)

### Example:

σ Salary > 50000 (EMPLOYEE)

### Real-world:

* Find employees earning more than 50k.

---

## 4.2 Projection (π)

### Purpose:

* Select specific columns.

### Syntax:

π attribute-list (Relation)

### Example:

π Name, Salary (EMPLOYEE)

### Note:

* Removes duplicate tuples.

---

## 4.3 Union (∪)

### Conditions:

* Same number of attributes.
* Compatible domains.

### Example:

EMPLOYEE ∪ MANAGER

---

## 4.4 Set Difference (−)

* Returns tuples present in first relation but not in second.

Example:
EMPLOYEE − RETIRED_EMPLOYEE

---

## 4.5 Cartesian Product (×)

* Combines all tuples of two relations.
* Produces m × n tuples.

Example:
STUDENT × COURSE

---

## 4.6 Rename (ρ)

* Renames relation or attributes.

Example:
ρ S(SID, SName)(STUDENT)

---

# 5. Additional Relational Algebra Operations

---

## 5.1 Intersection (∩)

* Common tuples in both relations.

---

## 5.2 Natural Join (⨝)

* Combines relations based on common attribute.
* Removes duplicate columns.

Example:
STUDENT ⨝ COURSE

---

## 5.3 Theta Join (⨝θ)

* Join using condition (>, <, =)

Example:
EMPLOYEE ⨝ Salary>50000 DEPARTMENT

---

## 5.4 Division (÷)

### Used for:

* Queries involving “for all”.

Example:
Find students who enrolled in all courses.

---

# 6. Extended Relational Algebra Operations

---

## 6.1 Aggregation (γ)

* COUNT
* SUM
* AVG
* MAX
* MIN

Example:
γ COUNT(SID)(STUDENT)

---

## 6.2 Grouping

Example:
γ DeptName, AVG(Salary)(EMPLOYEE)

---

## 6.3 Outer Join

### Types:

* Left Outer Join
* Right Outer Join
* Full Outer Join

### Purpose:

* Includes unmatched tuples.

---

## 6.4 Assignment Operator (←)

Example:
Temp ← σ Salary>50000 (EMPLOYEE)

---

# 7. Null Values

---

## 7.1 Meaning of NULL

* Unknown value
* Missing value
* Not applicable

---

## 7.2 Properties of NULL

* NULL ≠ 0
* NULL ≠ ''
* Any arithmetic with NULL → NULL

---

## 7.3 Problems with NULL

* Comparison issues
* Aggregation ambiguity
* Three-valued logic (True, False, Unknown)

---

## 7.4 Handling NULL

* IS NULL
* IS NOT NULL
* COALESCE function

---

# 8. Modification of the Database

---

## 8.1 Insertion

Syntax:
Relation ← Relation ∪ NewTuple

Example:
Insert new student record.

---

## 8.2 Deletion

Syntax:
Relation ← Relation − σ condition (Relation)

Example:
Delete students with SID=101

---

## 8.3 Update

* Combination of deletion and insertion.

Example:
Update Salary:

1. Delete old tuple
2. Insert new modified tuple

---

# Advantages of Relational Algebra

* Formal mathematical foundation
* Basis for SQL
* Useful in query optimization
* Closed system (input & output both relations)

---

# Disadvantages

* Procedural (less user-friendly)
* Not directly used by end users
* Complex for large queries

---

# Important Exam-Oriented Questions

1. Define relational algebra with example.
2. Explain fundamental operations with examples.
3. Differentiate Selection and Projection.
4. Explain Join types with examples.
5. Explain Division operator.
6. Write relational algebra for:

   * Students enrolled in all courses.
   * Employees with salary > 50000.
7. Discuss NULL values and three-valued logic.
8. Explain modification operations in relational algebra.

---

