# 2082

### 1. Explain the purpose of using database system over traditional file system. Briefly elaborate the properties of a database transaction. Explain backup and recovery process in database system.

This answer covers the three key parts of the question, structured for clarity and exam marks.

#### A. Purpose of Database System Over Traditional File System

The following points highlight the fundamental advantages of a Database Management System (DBMS) over the older, file-based approach .

- **Data Storage and Structure:**
    - **File System:** Data is stored in disparate files, often in proprietary formats specific to each application (e.g., a text file for students, a separate Excel file for courses). This leads to data fragmentation and lack of a unified view .
    - **Database System:** Data is stored in a **single, central repository** with a clearly defined structure (tables, rows, columns). This centralization is managed by the DBMS, providing a unified and organized view of all enterprise data .
    - **Real-World Example:** A university store's student personal details in a file and their course registrations in another. A DBMS would combine these into related tables, making it easy to find which courses a specific student is taking.

- **Data Redundancy and Inconsistency:**
    - **File System:** High **data redundancy**, as the same information (e.g., a student's name and address) might be duplicated across multiple files for different applications. This leads to **data inconsistency**, where the same data point has different values in different files .
    - **Database System:** Redundancy is **controlled and minimized**. Data is stored in a single place (e.g., student details once in a "Student" table) and referenced by other parts of the system, ensuring consistency .
    - **Real-World Example:** A student changes their phone number. In a file system, it must be updated in the library file, sports file, and hostel file. In a DBMS, it's updated just once in the central student record.

- **Data Access and Querying:**
    - **File System:** Data retrieval is cumbersome. It often requires writing new programs or complex scripts to search for specific information or generate reports .
    - **Database System:** Provides a powerful **query language (SQL)** . Users can ask complex questions (e.g., "Find the names of all students enrolled in 'Database' who scored above 80%") easily and get answers quickly, without needing to write new programs .
    - **Advantage:** **Ad-hoc queries** are possible, allowing users to get answers to unplanned questions instantly.

- **Concurrency Control:**
    - **File System:** If two people try to book the last seat on a flight simultaneously by editing the same file, one person's update can be lost or the file can become corrupted. It lacks robust **concurrency control** .
    - **Database System:** The DBMS manages concurrent access, ensuring data integrity through **transactions and locking mechanisms**. It guarantees that concurrent operations produce correct results, much like a modern ticket booking system .
    - **Advantage:** Enables **multi-user support** without data corruption.

- **Security and Integrity:**
    - **File System:** Security is typically at the file level (e.g., read/write permissions for the whole file). It's difficult to restrict access to specific data within a file. Data integrity rules (e.g., age must be >0) must be enforced by the application code .
    - **Database System:** Offers **fine-grained security** (e.g., allow a user to see names but not salaries). It enforces **integrity constraints** (like Primary Key, Foreign Key, CHECK constraints) at the database level, ensuring data accuracy regardless of the application accessing it .
    - **Advantage:** Centralized control over data quality and access.

| **Feature** | **Traditional File System** | **Database System** |
| :--- | :--- | :--- |
| **Data Storage** | Disparate files, often duplicated. | Centralized repository with minimal redundancy. |
| **Data Consistency** | High risk of inconsistency due to redundancy. | High consistency due to controlled redundancy. |
| **Data Access** | Difficult, requires programming for specific tasks. | Flexible, powerful query language (SQL) for ad-hoc queries. |
| **Concurrency** | Poor, leads to data corruption. | Excellent, with ACID transactions for safe concurrent access. |
| **Security** | Coarse-grained (file-level). | Fine-grained (user/role-level on tables/rows). |

#### B. Properties of a Database Transaction (ACID)

A transaction is a logical unit of work (one or more SQL operations) that must be executed atomically. The properties it must hold are known as ACID .

- **1. Atomicity:**
    - **Definition:** The transaction is treated as a single, indivisible unit. It either **executes completely or not at all** (all-or-nothing) .
    - **Real-World Example:** A fund transfer from Account A to Account B involves two steps: (1) Debit $100 from A, and (2) Credit $100 to B. Atomicity ensures that if the system crashes after step 1, the entire transaction is rolled back, and the $100 is not deducted from A without being added to B.
    - **Mechanism:** Implemented via a **rollback log** (or undo log). The DBMS keeps a record of the original values. If the transaction fails, it uses this log to restore the original state.

- **2. Consistency:**
    - **Definition:** A transaction brings the database from one **valid state to another**, preserving all defined integrity rules (constraints, triggers, etc.) .
    - **Real-World Example:** A database rule says "sum of credits and debits must always be zero." A transfer transaction, whether successful or not, must leave the database satisfying this rule. If an error would violate the rule, the transaction is aborted.
    - **Key Point:** Consistency is closely tied to **atomicity** and the enforcement of database rules.

- **3. Isolation:**
    - **Definition:** Concurrent execution of transactions results in a system state that is equivalent to the state that would be achieved had the transactions been executed **serially** (one after another). Intermediate states of a transaction are not visible to other transactions .
    - **Real-World Example:** Two transactions, T1 (generating a total sales report) and T2 (adding a new sale), run concurrently. Isolation ensures that T1 sees a consistent snapshot of the data, either including all of T2's changes or none of them. It won't see a half-finished state of T2.
    - **Mechanism:** Implemented through a **concurrency control system** (e.g., locks or multiversion concurrency control).

- **4. Durability:**
    - **Definition:** Once a transaction commits (successfully completes), its changes are **permanent** and must survive even a subsequent system crash or power failure .
    - **Real-World Example:** After you successfully book a flight ticket online and see the confirmation, your seat is booked permanently. Even if the airline's system crashes a second later, your booking is not lost.
    - **Mechanism:** Implemented by writing all changes to a persistent storage medium, typically using a **write-ahead log (WAL)** , before the transaction is considered committed.

#### C. Backup and Recovery Process

Backup and Recovery is the process of protecting a database against data loss and restoring it to a consistent state after a failure .

- **Types of Backups:**
    - **Physical Backup:** A copy of the actual physical files used by the database (data files, log files, control files).
        - **Full Backup:** A complete copy of the entire database at a point in time .
        - **Incremental Backup:** Copies only the data that has changed since the last backup (full or incremental). This is faster and saves storage.
    - **Logical Backup:** Exporting database schema and data into a file (e.g., SQL dump) using a utility like `mysqldump`.

- **Types of Failures:**
    - **Transaction Failure:** Failure due to logical errors, deadlocks, or system errors within a transaction. Handled automatically by transaction rollback (atomicity).
    - **System Crash:** Power outage, OS crash, etc., causing the database to stop. Recovery happens upon restart using logs.
    - **Media Failure/Disk Failure:** Physical damage to the hard disk where the database is stored. This is the most severe and requires restoring from a backup.

- **The Recovery Process:**
    The standard recovery process after a media failure involves two main phases: **Restore** and **Recovery** .

    - **Step 1: RESTORE:**
        - The DBA retrieves the most recent **full backup** of the database from offline storage (tape, cloud, etc.) and copies the data files back to the database server's disk.
        - If any incremental backups were taken after the full backup, they are also restored in sequence.

    - **Step 2: RECOVERY (Rollforward):**
        - After restoring the backups, the database is likely not up-to-date, as all transactions that occurred after the last backup are missing.
        - The DBMS then applies the **transaction logs** (or redo logs) that were backed up (or still available on disk). These logs contain a record of every committed transaction.
        - The system **replays (redoes)** all the committed transactions from the logs, bringing the database forward in time to the exact state it was in just before the failure.
        - Any uncommitted transactions that were in progress at the time of the failure are rolled back (undone) to ensure consistency .

    - **Point-in-Time Recovery (PITR):**
        - This is a more advanced form of recovery. Instead of recovering to the latest possible state, the DBA can recover the database to a specific moment in time (e.g., "just before 10:23 AM, when an erroneous `DROP TABLE` command was issued") .
        - **Process:** Restore a full backup taken before the target time, and then selectively apply the transaction logs only up to, but not including, the erroneous command. This is crucial for recovering from logical errors.

- **Example Scenario:**
    1.  **Friday, 10 PM:** Full database backup is taken.
    2.  **Saturday, all day:** Many transactions occur and are recorded in the transaction log.
    3.  **Sunday, 2 AM:** The database disk crashes.
    4.  **Recovery:**
        - The DBA **restores** the Friday night full backup.
        - The DBA applies all the **transaction logs** from Saturday. This "replays" all of Saturday's transactions, recovering all the work up to the moment of the crash on Sunday.
        - The database is now fully operational and consistent as of Sunday, 2 AM. Only the data in memory at the time of the crash is lost .

---

### 4. What do you mean by normalization? With an example discuss how a database can be normalized in first normal, second normal, third normal and BCNF form.

#### A. Definition of Normalization

- **Normalization** is a systematic process of organizing data in a database to **reduce redundancy** and **avoid anomalies** (insert, update, delete anomalies) .
- It involves decomposing larger, unnormalized tables into smaller, well-structured tables and defining relationships between them .
- The process is guided by **normal forms** (1NF, 2NF, 3NF, BCNF, etc.), each with specific rules to achieve a higher level of data integrity .

**Advantages:**
- Eliminates duplicate data, saving storage .
- Ensures data consistency and integrity .
- Makes the database more flexible for future changes .
- Simplifies query writing and maintenance .

**Disadvantages:**
- Can lead to a higher number of tables, requiring more joins in queries (performance trade-off) .
- Over-normalization may complicate application logic .

#### B. Example: Unnormalized Table (Before Normalization)

Consider a table that stores information about students and the courses they enroll in:

**Student_Course (Unnormalized)**

| Student_ID | Student_Name | Course_ID | Course_Name   | Instructor | Instructor_Office |
|------------|--------------|-----------|---------------|------------|-------------------|
| S101       | Alice        | C01       | Database      | Dr. Smith  | B202              |
| S101       | Alice        | C02       | Networks      | Dr. Jones  | B205              |
| S102       | Bob          | C01       | Database      | Dr. Smith  | B202              |
| S103       | Charlie      | C03       | AI            | Dr. Brown  | B210              |

**Problems (Anomalies):**
- **Redundancy:** Student name repeated for each course, instructor details repeated.
- **Update Anomaly:** If Dr. Smith changes office, we must update multiple rows.
- **Insert Anomaly:** Cannot add a new course (e.g., C04) until a student enrolls in it.
- **Delete Anomaly:** Deleting the last student from a course removes course information.

#### C. Normalization Steps

**Step 1: First Normal Form (1NF)**

**Rule:** 
- Table must have a **primary key**.
- All attributes must be **atomic** (no repeating groups or multi-valued attributes).

**Apply to our table:**
- The original table already has atomic values, but it has a composite primary key (Student_ID + Course_ID) to uniquely identify each row.

**Resulting 1NF Table:**

| Student_ID | Student_Name | Course_ID | Course_Name | Instructor | Instructor_Office |
|------------|--------------|-----------|-------------|------------|-------------------|
| S101       | Alice        | C01       | Database    | Dr. Smith  | B202              |
| S101       | Alice        | C02       | Networks    | Dr. Jones  | B205              |
| S102       | Bob          | C01       | Database    | Dr. Smith  | B202              |
| S103       | Charlie      | C03       | AI          | Dr. Brown  | B210              |

**Still has redundancy and anomalies.**

---

**Step 2: Second Normal Form (2NF)**

**Rule:** 
- Must be in 1NF.
- Remove **partial dependencies**: every non-key attribute must be fully functionally dependent on the **entire primary key** (not just part of it).

**Analysis of our table:**
- Primary Key: (Student_ID, Course_ID)
- Non-key attributes: Student_Name, Course_Name, Instructor, Instructor_Office.

Check dependencies:
- **Student_Name** depends only on Student_ID (partial dependency).
- **Course_Name, Instructor, Instructor_Office** depend only on Course_ID (partial dependency).

**Solution:** Decompose into three tables to remove partial dependencies.

**Resulting 2NF Tables:**

1. **Student** table:
   - Student_ID (PK), Student_Name

| Student_ID | Student_Name |
|------------|--------------|
| S101       | Alice        |
| S102       | Bob          |
| S103       | Charlie      |

2. **Course** table:
   - Course_ID (PK), Course_Name, Instructor, Instructor_Office

| Course_ID | Course_Name | Instructor | Instructor_Office |
|-----------|-------------|------------|-------------------|
| C01       | Database    | Dr. Smith  | B202              |
| C02       | Networks    | Dr. Jones  | B205              |
| C03       | AI          | Dr. Brown  | B210              |

3. **Enrollment** table (junction table):
   - (Student_ID, Course_ID) as composite PK

| Student_ID | Course_ID |
|------------|-----------|
| S101       | C01       |
| S101       | C02       |
| S102       | C01       |
| S103       | C03       |

**Now:**
- No more partial dependencies.
- Student names are stored only once, course details only once.
- Update anomaly reduced: Changing Dr. Smith's office updates only one row in Course table.

---

**Step 3: Third Normal Form (3NF)**

**Rule:** 
- Must be in 2NF.
- Remove **transitive dependencies**: no non-key attribute should depend on another non-key attribute.

**Analysis of current tables:**
- In the **Course** table: 
  - Course_ID → Instructor → Instructor_Office.
  - Here, Instructor_Office is transitively dependent on Course_ID via Instructor. This is a **transitive dependency**.

**Solution:** Decompose the Course table further.

**Resulting 3NF Tables:**

1. **Course** table (updated):
   - Course_ID (PK), Course_Name, Instructor_ID (foreign key to Instructor table)

| Course_ID | Course_Name | Instructor_ID |
|-----------|-------------|---------------|
| C01       | Database    | I01           |
| C02       | Networks    | I02           |
| C03       | AI          | I03           |

2. **Instructor** table:
   - Instructor_ID (PK), Instructor_Name, Instructor_Office

| Instructor_ID | Instructor_Name | Instructor_Office |
|---------------|-----------------|-------------------|
| I01           | Dr. Smith       | B202              |
| I02           | Dr. Jones       | B205              |
| I03           | Dr. Brown       | B210              |

**Now:**
- No transitive dependencies. Instructor details are stored independently.
- Changing an instructor's office affects only one row.
- Avoids repeating instructor details for multiple courses they teach.

---

**Step 4: Boyce-Codd Normal Form (BCNF)**

**Rule:** 
- A stronger version of 3NF.
- For every **non-trivial functional dependency** X → Y, X must be a **superkey**.

**When is 3NF not BCNF?**
- 3NF allows dependencies where the left-hand side is not a superkey if the right-hand side is a prime attribute (part of a candidate key). BCNF eliminates this.

**Example to illustrate:**
Suppose we have a table **Teaches** with:
- (Student_ID, Course_ID) as PK
- Instructor_ID (each course has one instructor, but an instructor can teach multiple courses; a student can take a course from only one instructor? Actually we need a scenario.)

Consider a scenario: A student takes a course from a specific instructor. The combination (Student_ID, Course_ID) is unique. But an instructor teaches only one course (say). This is contrived.

Better example: **Assessment** table:

| Student_ID | Course_ID | Instructor_ID | Grade |
|------------|-----------|---------------|-------|
| S1         | C1        | I1            | A     |
| S2         | C1        | I1            | B     |
| S1         | C2        | I2            | A     |

Assume: Each course has exactly one instructor (Course_ID → Instructor_ID). This is a functional dependency where Course_ID is not a superkey (since PK is Student_ID + Course_ID). This violates BCNF because the determinant (Course_ID) is not a superkey.

**Solution:** Decompose into:

1. **Course_Instructor**: (Course_ID (PK), Instructor_ID)
2. **Enrollment_Grade**: (Student_ID, Course_ID (FK), Grade)

**Now BCNF satisfied.**

**In our 3NF example**, the Course table had (Course_ID → Instructor_ID). Is Course_ID a superkey? Yes, because it's the primary key of that table. So our design is already in BCNF. The transitive dependency we removed earlier (Instructor → Office) was already handled.

Thus, our final normalized schema (in BCNF) is:
- **Student** (Student_ID, Student_Name)
- **Instructor** (Instructor_ID, Instructor_Name, Instructor_Office)
- **Course** (Course_ID, Course_Name, Instructor_ID)
- **Enrollment** (Student_ID, Course_ID)

---

### 5. Consider the following supplier database... Construct the following relational algebra queries...

#### A. Implement Data Definition Language (DDL) of the given relation

The DDL statements to create the three tables (Supplier, Supplies, Parts) in SQL:

```sql
-- Create Supplier table
CREATE TABLE Supplier (
    supplier_id INT PRIMARY KEY,
    supplier_name VARCHAR(100) NOT NULL,
    city VARCHAR(50)
);

-- Create Parts table
CREATE TABLE Parts (
    part_id INT PRIMARY KEY,
    part_name VARCHAR(100) NOT NULL,
    color VARCHAR(30),
    weight DECIMAL(10,2)  -- assuming weight in kg or appropriate unit
);

-- Create Supplies table (junction table with composite primary key and foreign keys)
CREATE TABLE Supplies (
    supplier_id INT,
    part_id INT,
    quantity INT,
    PRIMARY KEY (supplier_id, part_id),
    FOREIGN KEY (supplier_id) REFERENCES Supplier(supplier_id),
    FOREIGN KEY (part_id) REFERENCES Parts(part_id)
);
```

**Explanation:**
- `PRIMARY KEY` ensures uniqueness and entity integrity.
- `FOREIGN KEY` enforces referential integrity between tables.
- `NOT NULL` on supplier_name and part_name ensures essential data is present.
- Data types are chosen appropriately (INT for IDs, VARCHAR for names/city, DECIMAL for weight).

---

#### B. Relational Algebra Queries

We'll write each query in relational algebra notation.

**b) Find the name of all parts supplied by "ABC Company".**

- First, find the supplier_id of "ABC Company":
  \[
  T1 = \sigma_{supplier\_name = 'ABC\ Company'}(Supplier)
  \]
- Then join with Supplies to get part_ids supplied by that supplier:
  \[
  T2 = T1 \bowtie Supplies
  \]
- Then join with Parts to get part names:
  \[
  T3 = T2 \bowtie Parts
  \]
- Finally, project part_name:
  \[
  Result = \pi_{part\_name}(T3)
  \]

**Alternatively, combined expression:**
\[
\pi_{part\_name}( (\sigma_{supplier\_name='ABC\ Company'}(Supplier)) \bowtie Supplies \bowtie Parts )
\]

---

**c) Find the name of all parts that are supplied in quantity greater than 300.**

- Select from Supplies those with quantity > 300:
  \[
  T1 = \sigma_{quantity > 300}(Supplies)
  \]
- Join with Parts to get part names:
  \[
  T2 = T1 \bowtie Parts
  \]
- Project part_name:
  \[
  Result = \pi_{part\_name}(T2)
  \]

---

**d) Find the name of all suppliers located in city "Kathmandu".**

- Select suppliers where city = 'Kathmandu':
  \[
  T1 = \sigma_{city = 'Kathmandu'}(Supplier)
  \]
- Project supplier_name:
  \[
  Result = \pi_{supplier\_name}(T1)
  \]

---

**e) Find the number of parts supplied by "ABC Company".**

- First, find supplier_id of 'ABC Company':
  \[
  T1 = \sigma_{supplier\_name='ABC\ Company'}(Supplier)
  \]
- Join with Supplies to get parts supplied:
  \[
  T2 = T1 \bowtie Supplies
  \]
- Count the tuples (this requires aggregation in relational algebra, typically using a count function). In pure relational algebra, we use the **count** aggregate:
  \[
  Result = \mathcal{G}_{count(part\_id)}(T2)
  \]
  (Here, we are counting the number of part_ids for that supplier.)

**Alternatively**, if we assume there is a count operator: 
\[
Result = \ ^{count}\pi_{part\_id}(T2)
\]

But for exam, we can write: 
\[
Result = \mathcal{G}_{COUNT(part\_id)}( \sigma_{supplier\_name='ABC\ Company'}(Supplier) \bowtie Supplies )
\]

---

**f) Find the name of all suppliers who supply more than 30 different parts.**

- First, we need to group Supplies by supplier_id and count distinct part_ids per supplier.
  \[
  T1 = \mathcal{G}_{supplier\_id, COUNT(part\_id) \rightarrow part\_count}(Supplies)
  \]
- Then select those with part_count > 30:
  \[
  T2 = \sigma_{part\_count > 30}(T1)
  \]
- Join with Supplier to get supplier names:
  \[
  T3 = T2 \bowtie Supplier
  \]
- Project supplier_name:
  \[
  Result = \pi_{supplier\_name}(T3)
  \]

**Alternative combined:**
\[
\pi_{supplier\_name}( ( \mathcal{G}_{supplier\_id, COUNT(part\_id) \rightarrow cnt}(Supplies) ) \bowtie \sigma_{cnt > 30} \bowtie Supplier )
\]

---

### 6. Weak entity, constraints, two-phase locking

#### A. When is the concept of a weak entity used in data modeling and how?

- **Definition:** A **weak entity** is an entity that cannot be uniquely identified by its own attributes alone. It depends on another entity (called the **identifying** or **owner entity**) for its existence and identification .
- **When used:**
  - When an entity's existence is logically dependent on another entity.
  - When the entity does not have a natural key and its primary key is formed by combining its own partial key (discriminator) with the primary key of the owner entity.
- **How modeled:**
  - In E-R diagrams, a weak entity is represented by a **double rectangle**, and its identifying relationship is represented by a **double diamond** .
  - The partial key (discriminator) is underlined with a dashed line.
- **Example:**
  - **Dependent** of an Employee: A dependent has a name, but multiple employees may have dependents with the same name. The dependent is identified by (dependent_name + Employee_ID). Here, Dependent is a weak entity, Employee is the owner entity.
  - **Room** in a Hotel: A room is identified by its room number within a specific hotel. Without the hotel, the room number is meaningless.

**Mapping to Relational Schema:**
- The weak entity table includes the primary key of the owner as a foreign key.
- The primary key of the weak entity is the combination of that foreign key and its partial key.

---

#### B. What is a constraint? How does SQL allow implementation of general integrity constraints?

- **Constraint:** A constraint is a rule enforced on data columns to ensure data integrity and accuracy. It prevents invalid data from being entered into the database .

- **Types of constraints in SQL:**
  1. **NOT NULL:** Ensures a column cannot have NULL values.
  2. **UNIQUE:** Ensures all values in a column (or set of columns) are distinct.
  3. **PRIMARY KEY:** Uniquely identifies each row; combination of NOT NULL and UNIQUE.
  4. **FOREIGN KEY:** Ensures referential integrity; values in a column must match values in another table's primary key or unique key.
  5. **CHECK:** Validates data based on a logical expression (e.g., age >= 18).
  6. **DEFAULT:** Provides a default value for a column when not specified.

- **How SQL implements general integrity constraints:**
  - Constraints are defined at the time of table creation (`CREATE TABLE`) or added later (`ALTER TABLE`).
  - They are stored in the **system catalog** and are automatically enforced by the DBMS on any data modification (INSERT, UPDATE, DELETE) .
  - For complex business rules that cannot be expressed with simple constraints, SQL provides:
    - **Triggers:** Stored procedures that automatically execute in response to certain events (INSERT, UPDATE, DELETE) and can enforce complex logic, validate data, or maintain derived data.
    - **Assertions:** (Supported in SQL standard but not widely implemented) are constraints that can involve multiple tables and aggregate conditions (e.g., "total salary budget must not exceed 1 million").

- **Example of CHECK constraint:**
  ```sql
  CREATE TABLE Employee (
      emp_id INT PRIMARY KEY,
      salary DECIMAL(10,2) CHECK (salary > 0),
      age INT CHECK (age >= 18)
  );
  ```

- **Example of a trigger for complex integrity:**
  ```sql
  CREATE TRIGGER check_salary_budget
  BEFORE INSERT ON Employee
  FOR EACH ROW
  BEGIN
      DECLARE total DECIMAL;
      SELECT SUM(salary) INTO total FROM Employee;
      IF total + NEW.salary > 1000000 THEN
          SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Budget exceeded';
      END IF;
  END;
  ```

---

#### C. What is the two-phase locking protocol? How does it guarantee serializability?

- **Definition:** Two-Phase Locking (2PL) is a **concurrency control protocol** that ensures **serializability** of transactions. It requires that every transaction follow two phases:
  1. **Growing Phase:** A transaction acquires all the locks it needs (shared or exclusive) but cannot release any lock.
  2. **Shrinking Phase:** After releasing the first lock, the transaction can only release locks; it cannot acquire any new locks.

- **How it works:**
  - A transaction must obtain a lock (read or write) on a data item before accessing it.
  - Once it releases a lock, it enters the shrinking phase and cannot obtain any more locks.
  - The point where the transaction has acquired all locks but hasn't released any is called the **lock point**.

- **How it guarantees serializability:**
  - 2PL ensures that the execution schedule of transactions is **conflict serializable** .
  - The lock point defines an order among transactions: if transaction T1's lock point comes before T2's lock point, then all of T1's operations will appear before T2's in a serial schedule.
  - By preventing transactions from acquiring new locks after releasing any, 2PL avoids the "unlock then lock" scenario that could lead to non-serializable schedules like dirty reads, unrepeatable reads, and lost updates.

- **Limitations:**
  - **Cascading rollbacks** may occur if a transaction releases a lock early and then aborts, forcing dependent transactions to roll back. This is addressed by **Strict 2PL** (holds all locks until commit/abort) and **Rigorous 2PL** (all locks held until commit/abort; commonly used in practice).
  - **Deadlocks** are possible under 2PL because transactions wait for locks held by others; deadlock detection/prevention mechanisms are needed.

---

### 7. Write short notes on any TWO

#### (a) Client-Server Architecture

- **Definition:** Client-server architecture is a distributed computing model where tasks are split between **service providers (servers)** and **service requesters (clients)** . Clients send requests to servers, which process them and return results .

- **Characteristics:**
  - Clients are typically user-facing applications (e.g., a mobile app, web browser).
  - Servers are powerful machines that host resources, databases, or services (e.g., web server, database server).
  - Communication occurs over a network using protocols like HTTP, TCP/IP.

- **Types in Database Context:**
  - **Two-Tier Architecture:** Client directly communicates with database server. Client handles presentation and business logic; server handles data. Example: a desktop application connecting to a DBMS.
  - **Three-Tier Architecture:** Client (presentation layer) communicates with an application server (business logic layer), which in turn communicates with the database server (data layer). This is common in web applications .

- **Advantages:**
  - **Centralized management:** Servers provide centralized data storage, security, and backup.
  - **Scalability:** Servers can be upgraded independently of clients.
  - **Security:** Sensitive data resides on servers, not on client machines.
  - **Maintainability:** Updates to business logic are done on the server, not on every client.

- **Disadvantages:**
  - **Single point of failure:** If the server goes down, all clients are affected.
  - **Network dependency:** Performance depends on network speed and reliability.
  - **Cost:** Server hardware and software can be expensive.

- **Real-world example:** A university's online registration system: Students use browsers (clients) to access a web application server, which queries a central database server for course information.

---

#### (b) Relational Algebra Operators

- **Definition:** Relational algebra is a **procedural query language** that takes relations (tables) as input and produces a new relation as output. It forms the theoretical foundation for SQL .

- **Basic Operators (Unary):**
  1. **Selection (σ):** Selects rows that satisfy a given condition.
     - Example: σ<sub>city='Kathmandu'</sub>(Supplier) returns suppliers from Kathmandu.
  2. **Projection (π):** Selects specific columns (attributes) and removes duplicates.
     - Example: π<sub>supplier_name, city</sub>(Supplier) returns only supplier names and cities.

- **Basic Operators (Binary):**
  3. **Union (∪):** Returns all tuples that are in either of two relations (must be union-compatible: same number and type of attributes).
     - Example: π<sub>part_id</sub>(Supplies) ∪ π<sub>part_id</sub>(Parts) would combine part IDs from both.
  4. **Set Difference (−):** Returns tuples in the first relation but not in the second.
     - Example: π<sub>part_id</sub>(Parts) − π<sub>part_id</sub>(Supplies) gives parts never supplied.
  5. **Cartesian Product (×):** Combines every tuple of one relation with every tuple of another.
     - Example: Supplier × Supplies produces all possible combinations.
  6. **Rename (ρ):** Renames a relation or its attributes for convenience.

- **Derived Operators:**
  7. **Join (⨝):** Combines related tuples from two relations based on a common attribute. Most common is **natural join**, which equates common attributes and removes duplicate columns.
     - Example: Supplier ⨝ Supplies joins on supplier_id.
  8. **Division (÷):** Used for queries like "find suppliers who supply all parts". More complex.

- **Aggregate Operators (Extended Algebra):** Grouping and aggregate functions (COUNT, SUM, AVG, MIN, MAX) are part of extended relational algebra.

- **Importance:** Understanding relational algebra helps in query optimization and understanding how SQL queries are executed internally.

---

#### (c) COMMIT and ROLLBACK

- **Definition:** COMMIT and ROLLBACK are **Transaction Control Language (TCL)** commands used to manage transactions in a database.

- **COMMIT:**
  - Permanently saves all changes made during the current transaction to the database .
  - Once a COMMIT is executed, the changes become **durable** (D in ACID) and visible to other transactions.
  - Releases any locks held by the transaction.
  - **Syntax:** `COMMIT;`
  - **Example:** After transferring money between accounts and verifying all steps, you issue COMMIT to make the transfer permanent.

- **ROLLBACK:**
  - Undoes all changes made during the current transaction, restoring the database to the state it was in before the transaction began .
  - Used when an error occurs or if the user decides to cancel the transaction.
  - Releases any locks held.
  - **Syntax:** `ROLLBACK;`
  - **Example:** If an error occurs during the transfer (e.g., insufficient funds), you issue ROLLBACK to cancel the entire operation and keep the database consistent.

- **Key Points:**
  - Both commands only affect **Data Manipulation Language (DML)** operations (INSERT, UPDATE, DELETE). **Data Definition Language (DDL)** commands (CREATE, ALTER, DROP) are **autocommit** (they commit immediately).
  - In many DBMS, by default, each DML statement is treated as a transaction and auto-committed unless explicit transaction control is used.
  - Transactions can be started implicitly with a DML statement or explicitly with `BEGIN TRANSACTION` or `START TRANSACTION`.

- **Real-world Importance:**
  - Essential for maintaining **atomicity** and **consistency** in multi-step operations.
  - Used in banking, e-commerce, reservation systems to ensure that either all steps succeed or none do.

- **Example Scenario:**
  ```sql
  START TRANSACTION;
  UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
  UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;
  -- If everything is fine:
  COMMIT;
  -- If an error occurs (e.g., second update fails):
  ROLLBACK;
  ```

---

### Exam Tips for Question 6 and 7

- For **weak entity**, always mention the double rectangle/diamond and provide an example (dependent, room).
- For **constraints**, list all types and mention triggers/assertions for complex rules.
- For **2PL**, explain the two phases clearly and link to serializability via conflict serializability and lock point.
- For short notes, cover definition, types, advantages/disadvantages (if applicable), and a real-world example to show practical understanding.

These answers are designed to fetch full marks by being comprehensive, technically accurate, and well-structured.
