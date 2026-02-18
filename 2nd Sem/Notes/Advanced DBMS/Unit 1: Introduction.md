# Unit 1: Introduction (Advanced DBMS) – 5 Hrs

---

## 1. Introducing the Course (Advanced DBMS)

### 1.1 What is Advanced DBMS?

* Study of **advanced database concepts** beyond basic CRUD operations.
* Focuses on:

  * Database architecture
  * Query processing & optimization
  * Transaction management
  * Concurrency control
  * Recovery techniques
  * Distributed and NoSQL databases
  * Big Data storage systems

### 1.2 Objectives of Advanced DBMS

* Understand internal working of DBMS.
* Design scalable, secure, and high-performance database systems.
* Analyze query optimization strategies.
* Handle distributed and large-scale data systems.
* Integrate modern technologies like cloud databases and NoSQL.

### 1.3 Real-World Applications

* Banking systems (transaction processing)
* E-commerce (Amazon-like systems)
* Social Media platforms
* Healthcare management systems
* Big Data analytics systems

---

# 2. Concepts of Data, Database and DBMS

---

## 2.1 Data

### Definition:

* Raw facts and figures without context.

### Examples:

* 101
* “Sharat”
* 50000
* 2026-02-18

### Types of Data:

* Structured (tables)
* Semi-structured (JSON, XML)
* Unstructured (videos, images, emails)

### Real-World Example:

* Student marks stored in Excel sheet.

---

## 2.2 Information

* Processed and meaningful data.
* Example:

  * Data: 85
  * Information: “Student scored 85 marks in DBMS”

---

## 2.3 Database

### Definition:

* Organized collection of related data stored electronically.

### Characteristics:

* Integrated
* Shared
* Persistent
* Structured

### Example:

* University database containing:

  * Students
  * Courses
  * Faculty
  * Results

### Advantages:

* Data consistency
* Centralized control
* Easy retrieval

### Disadvantages:

* Requires maintenance
* Security risks if poorly managed

---

## 2.4 DBMS (Database Management System)

### Definition:

* Software that manages databases and provides interface between user and database.

### Examples:

* MySQL
* Oracle Database
* Microsoft SQL Server
* MongoDB

### Functions of DBMS:

* Data storage
* Data retrieval
* Security management
* Backup & recovery
* Concurrency control
* Transaction management

### Real-World Example:

* ATM system uses DBMS to:

  * Check balance
  * Deduct money
  * Record transaction

---

# 3. Levels of Abstraction in DBMS

DBMS hides complexity using **three-level architecture**.

---

## 3.1 Physical Level (Internal Level)

### Description:

* Lowest level.
* Describes how data is stored physically.

### Includes:

* File structure
* Indexing
* Storage blocks
* Compression techniques

### Example:

* Data stored in B+ Trees
* Data stored in SSD blocks

### Advantage:

* Optimized performance

### Disadvantage:

* Complex for users to understand

---

## 3.2 Logical Level (Conceptual Level)

### Description:

* Describes what data is stored and relationships.

### Includes:

* Tables
* Attributes
* Constraints
* Relationships

### Example:

Student (SID, Name, Address)
Course (CID, CourseName)

### Advantage:

* Easy database design
* Data independence

---

## 3.3 View Level (External Level)

### Description:

* Highest level.
* User-specific view of database.

### Example:

* Teacher sees marks.
* Student sees only own result.

### Advantage:

* Security
* Data hiding

---

## 3.4 Data Independence

### 1. Physical Data Independence

* Changes in physical storage do not affect logical schema.

### 2. Logical Data Independence

* Changes in logical schema do not affect external views.

### Importance:

* Reduces system maintenance cost.

---

# 4. Increasing Trends of Storage Space Required

---

## 4.1 Reasons for Rapid Storage Growth

* Explosion of Internet data
* Social media content
* IoT devices
* Cloud computing
* Big Data analytics
* AI/ML datasets

---

## 4.2 Real-World Examples

* Social media:

  * Facebook stores billions of photos.
* Video streaming:

  * YouTube uploads millions of hours of video daily.
* E-commerce:

  * Amazon stores product data, transactions, logs.

---

## 4.3 Types of Modern Data Growth

* Structured data (RDBMS)
* Semi-structured data (JSON APIs)
* Unstructured data (Images, Audio, Video)
* Log files
* Sensor data

---

## 4.4 Challenges Due to Large Storage

* Data redundancy
* Data inconsistency
* High maintenance cost
* Performance degradation
* Security risk

---

## 4.5 Technologies Handling Large Storage

* Cloud storage
* Distributed databases
* NoSQL databases
* Data warehouses
* Hadoop ecosystem

---

# 5. Need of Having DBMS

---

## 5.1 Problems with File-Based System

1. Data Redundancy
2. Data Inconsistency
3. Data Isolation
4. Security Problems
5. Integrity Issues
6. Difficult Backup & Recovery
7. Concurrent Access Issues

---

## 5.2 Why DBMS is Needed?

### 1. Data Redundancy Control

* Centralized storage reduces duplication.

### 2. Data Consistency

* Single version of truth.

### 3. Data Sharing

* Multiple users access same database.

### 4. Security

* Role-based access control.

### 5. Integrity Constraints

* Primary Key
* Foreign Key
* Check constraints

### 6. Concurrency Control

* Handles multiple transactions simultaneously.

### 7. Backup & Recovery

* Crash recovery mechanisms.

---

## 5.3 Real-World Example (Banking System)

Without DBMS:

* Duplicate account data
* Inconsistent balance

With DBMS:

* ACID properties maintained
* Transaction rollback possible

---

## 5.4 Advantages of DBMS

* Reduced redundancy
* Improved consistency
* Better security
* Efficient data retrieval
* Multi-user support
* Scalability

---

## 5.5 Disadvantages of DBMS

* High initial cost
* Complex system
* Requires skilled DBA
* System failure affects all users

---

# Important Exam-Oriented Points

✔ Define Data, Database, DBMS (2–4 marks)
✔ Explain three-level architecture with diagram (5 marks)
✔ Differentiate File System vs DBMS (4–6 marks)
✔ Explain need of DBMS with example (5 marks)
✔ Discuss data independence (4 marks)
✔ Explain causes of increasing storage demand (5 marks)

---


