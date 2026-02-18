# Unit 4: Relational Database Design (5 Hrs)

---

# 1. Functional Dependencies (FD)

---

## 1.1 Definition

* A **Functional Dependency (FD)** is a relationship between attributes.
* Denoted as:

[
X \rightarrow Y
]

Meaning:

* If two tuples agree on X, they must agree on Y.

---

## 1.2 Example

Relation:
STUDENT(SID, Name, Dept, DeptHead)

### Functional Dependencies:

* SID → Name, Dept
* Dept → DeptHead

### Interpretation:

* Each SID uniquely determines Name and Dept.
* Each Dept uniquely determines DeptHead.

---

## 1.3 Types of Functional Dependencies

---

### 1. Trivial FD

* Y ⊆ X
* Example:

  * {SID, Name} → SID

✔ Always true.

---

### 2. Non-Trivial FD

* Y ⊄ X
* Example:

  * SID → Name

---

### 3. Completely Non-Trivial FD

* X ∩ Y = ∅
* Example:

  * SID → Dept

---

## 1.4 Closure of Attribute (X⁺)

### Definition:

* Set of attributes functionally determined by X.

### Purpose:

* To find candidate keys.

### Steps:

1. Start with X⁺ = X
2. Apply FDs repeatedly
3. Add derived attributes

---

## 1.5 Armstrong’s Axioms

Fundamental inference rules:

1. Reflexivity:

   * If Y ⊆ X → X → Y

2. Augmentation:

   * If X → Y → XZ → YZ

3. Transitivity:

   * If X → Y and Y → Z → X → Z

---

## 1.6 Importance of Functional Dependencies

* Detect redundancy
* Determine candidate keys
* Basis for normalization
* Ensure consistency

---

# 2. Normal Forms

Normalization:

* Process of organizing data to reduce redundancy and anomalies.

---

## 2.1 Problems in Poor Design

1. Insertion anomaly
2. Deletion anomaly
3. Update anomaly

---

## 2.2 First Normal Form (1NF)

### Condition:

* Atomic values (no repeating groups).

### Example (Violation):

Student(SID, Name, Subjects)
Subjects = {DBMS, OS}

✔ Not atomic.

### Solution:

Create separate rows for each subject.

---

## 2.3 Second Normal Form (2NF)

### Condition:

* Must be in 1NF.
* No partial dependency.
* Every non-prime attribute fully depends on whole primary key.

### Example:

ENROLL(SID, CID, StudentName, CourseName)

Primary Key: (SID, CID)

FDs:

* SID → StudentName
* CID → CourseName

❌ Partial dependency exists.

✔ Decompose into:

* STUDENT(SID, StudentName)
* COURSE(CID, CourseName)
* ENROLL(SID, CID)

---

## 2.4 Third Normal Form (3NF)

### Condition:

* Must be in 2NF.
* No transitive dependency.

### Transitive Dependency:

If:

* A → B
* B → C
  Then:
* A → C (indirect)

---

### Example:

STUDENT(SID, Dept, DeptHead)

FDs:

* SID → Dept
* Dept → DeptHead

❌ Transitive dependency.

✔ Decompose:

* STUDENT(SID, Dept)
* DEPARTMENT(Dept, DeptHead)

---

## 2.5 Boyce-Codd Normal Form (BCNF)

### Condition:

For every FD X → Y:

* X must be super key.

### Stronger than 3NF.

---

### Example:

Relation: R(A, B, C)

FDs:

* A → B
* B → C

If B is not super key → violates BCNF.

---

## 2.6 Comparison of Normal Forms

| Normal Form | Removes               |
| ----------- | --------------------- |
| 1NF         | Repeating groups      |
| 2NF         | Partial dependency    |
| 3NF         | Transitive dependency |
| BCNF        | All FD violations     |

---

## 2.7 Advantages of Normalization

* Reduces redundancy
* Eliminates anomalies
* Improves consistency
* Logical clarity

---

## 2.8 Disadvantages

* More tables
* Complex joins
* Slight performance overhead

---

# 3. Atomic Domains

---

## 3.1 Definition

* Domain is atomic if elements are indivisible.

Example:
✔ Atomic → Age = 25
❌ Non-atomic → Address = “City, State, Country”

---

## 3.2 Importance

* Required for 1NF
* Prevents repeating groups
* Ensures relational integrity

---

## 3.3 Example

Non-Atomic:
Student(Name, PhoneNumbers)

PhoneNumbers = {9841, 9852}

✔ Violation of atomic domain.

Solution:
Create separate rows or separate table.

---

# 4. Decomposition Using Functional Dependencies

---

## 4.1 Decomposition

* Breaking a relation into smaller relations.
* Goal:

  * Remove redundancy
  * Maintain dependency
  * Maintain lossless join

---

## 4.2 Lossless Join Decomposition

### Condition:

After decomposition, joining relations should reconstruct original relation.

If:
R → R1 and R2

Then:
R1 ∩ R2 must be super key of at least one relation.

---

### Example:

R(A, B, C)

FD:
A → B

Decompose into:

* R1(A, B)
* R2(A, C)

✔ Lossless (A is common and key).

---

## 4.3 Lossy Join

* Join does not recreate original data exactly.
* Leads to spurious tuples.

---

## 4.4 Dependency Preservation

* All functional dependencies must be preserved after decomposition.

If original FDs cannot be enforced in decomposed tables → dependency not preserved.

---

## 4.5 Steps for Decomposition to 3NF

1. Find minimal cover of FDs.
2. Create relation for each FD.
3. Ensure at least one relation contains candidate key.

---

## 4.6 BCNF Decomposition Algorithm

1. Find violation (X → Y where X not super key).
2. Decompose:

   * R1 = X ∪ Y
   * R2 = R − (Y − X)
3. Repeat until no violation.

---

# Real-World Example

Bank Account System:

ACCOUNT(AccountNo, CustomerName, Branch, BranchManager)

FDs:

* AccountNo → CustomerName, Branch
* Branch → BranchManager

Problems:

* If branch manager changes → update many rows.
* Redundant data.

Decompose into:

* ACCOUNT(AccountNo, CustomerName, Branch)
* BRANCH(Branch, BranchManager)

✔ Removes redundancy.

---

# Important Exam-Oriented Questions

1. Define Functional Dependency with example.
2. Explain Armstrong’s axioms.
3. Define and explain 1NF, 2NF, 3NF, BCNF.
4. Differentiate 3NF and BCNF.
5. What is atomic domain?
6. Explain lossless join decomposition.
7. Explain dependency preservation.
8. Solve a normalization problem up to 3NF.
9. Explain anomalies with example.

---

