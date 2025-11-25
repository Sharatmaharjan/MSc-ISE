# ✅ **UNIT 1 — Full 12-Marks Answers**

---

# **1. What is a complex system? Explain attributes of a complex system. (12 marks)**

### **Introduction**

A complex system is a system composed of many interacting components whose collective behavior cannot be easily predicted from the behavior of individual parts. Modern software systems, biological systems, social systems, and communication networks are examples of complex systems.

---

## **Definition**

A **complex system** is a large-scale system consisting of multiple interconnected and interdependent subsystems, demonstrating emergent, adaptive, and dynamic behavior.

---

# **Attributes of a Complex System**

### **1. Hierarchy**

Complex systems are organized into multiple hierarchical levels.
Example: A computer → CPU → ALU → Transistors.

### **2. Emergence**

The system exhibits behaviors that do not exist in individual components but arise when components interact together.
Example: Traffic patterns, social media trends.

### **3. Nonlinearity**

Input does not have a proportional output. Small changes may produce large, unpredictable outcomes.

### **4. Interconnectedness & Interdependency**

Components highly depend on each other. Failure in one component can affect the whole system.

### **5. Multitude of Components**

Contains many elements interacting in parallel, making the system hard to analyze.

### **6. Adaptability**

System evolves and adapts to internal or external changes.
Example: Machine learning systems adjusting behavior.

### **7. Uncertainty**

Future states are not easily predictable due to complexity in relationships.

### **8. Self-Organization**

Some systems automatically organize themselves without external control.

---

### **Conclusion**

Complex systems are multi-layered, dynamic, and adaptive. Understanding their attributes helps design robust, scalable, and maintainable object-oriented systems.

---

# **2. Software systems are always complex. Justify with example. (12 marks)**

### **Introduction**

Software systems inherently deal with diverse user requirements, numerous functional components, and constant evolution, making them complex by nature.

---

# **Why Software Systems Are Inherently Complex**

### **1. Immense Logical Complexity**

Software represents real-world logic using code.
Example: Banking system — thousands of business rules.

### **2. No Physical Constraints**

Unlike hardware systems bound by physics, software grows indefinitely, increasing complexity.

### **3. Changing Requirements**

User needs, regulations, and business rules frequently change, forcing continuous updates.

### **4. Interaction of Multiple Components**

Databases, servers, UI, external APIs — all interacting at runtime increase system complexity.

### **5. Concurrency**

Simultaneous processes, threads, and transactions lead to unpredictable behavior.

### **6. Large State Space**

Software maintains states across sessions, inputs, network conditions, making exhaustive testing impossible.

### **7. Integration with Heterogeneous Systems**

Must communicate with various existing systems (legacy, cloud, sensors).

### **8. Security and Performance Requirements**

Need for authentication, authorization, encryption, optimization increases complexity.

---

### **Example: Online Banking System**

* User management
* ATM integration
* Fraud detection
* Account management
* Network communication
* Audit logs
* Compliance rules

These tasks together make software inherently complex.

---

### **Conclusion**

Software complexity is unavoidable due to logic density, evolving requirements, integration challenges, and nonlinearity of interactions.

---

# **3. Explain the need for object-oriented systems. What are the attributes of a complex system? (12 marks)**

### **A. Need for Object-Oriented Systems**

### **1. Better Real-World Modeling**

OOS models entities as “objects,” making system design natural and intuitive.

### **2. Reusability**

Classes and objects promote reuse through inheritance and polymorphism.

### **3. Modularity**

Encapsulation ensures components are well-separated and easier to maintain.

### **4. Reduced Complexity**

Breaking system into interacting objects makes it more manageable.

### **5. Extensibility**

New functionalities can be added without modifying existing code (Open-Closed Principle).

### **6. Maintainability**

Encapsulation protects internal data, reducing side-effects and bugs.

### **7. Enhanced Security**

Access modifiers (private, protected, public) protect object integrity.

---

### **B. Attributes of a Complex System (Already explained)**

(Write the same eight attributes: Hierarchy, emergence, interdependency, adaptability, nonlinearity, numerous components, uncertainty, self-organization.)

---

### **Conclusion**

Object-oriented systems address the challenges of complexity by enabling modularity, reuse, and abstraction.

---

# **4. Compare object-oriented and traditional software development life cycle. (12 marks)**

### **Introduction**

Traditional SDLC (waterfall) focuses on functions and procedures, while OOSD focuses on modeling real-world objects.

---

# **Comparison Table (Highly Scoring 12-mark Format)**

| Aspect                     | Traditional SDLC                        | Object-Oriented SDLC              |
| -------------------------- | --------------------------------------- | --------------------------------- |
| **1. Focus**               | Functions & procedures                  | Objects, classes & interactions   |
| **2. Modeling Approach**   | Top-down, task-based                    | Bottom-up, object-based           |
| **3. Data Handling**       | Data & functions separate               | Data + methods in one unit        |
| **4. Reusability**         | Low                                     | High (inheritance, polymorphism)  |
| **5. Modifiability**       | Difficult to change                     | Easy due to encapsulation         |
| **6. Maintenance**         | Costly and complex                      | Easier due to modularity          |
| **7. Development Flow**    | Sequential (analysis → design → coding) | Iterative (OOA ↔ OOD ↔ OOP)       |
| **8. Code Structure**      | Monolithic                              | Modular                           |
| **9. Suitability**         | Small, stable systems                   | Complex, evolving systems         |
| **10. Design Artifacts**   | DFDs, ER diagrams                       | UML diagrams (class, sequence)    |
| **11. Testing**            | After coding                            | Continuous throughout lifecycle   |
| **12. Real-world Mapping** | Indirect                                | Direct representation of entities |

---

### **Conclusion**

Object-oriented SDLC is superior for modern, large, complex, and scalable systems due to modularity, reusability, and abstraction.

---

# ✅ **UNIT 2 — 12 Marks Answers**

---

# **1. Explain the characteristics of Object-Oriented Design (OOD). (12 marks)**

### **Introduction**

Object-Oriented Design (OOD) is the process of converting analysis models into implementable design models by using classes, objects, interfaces, and relationships. It focuses on creating robust, reusable, and maintainable software systems.

---

# **Characteristics of Object-Oriented Design**

### **1. Abstraction**

* Focuses on essential features of an object.
* Ignores implementation details.
  Example: “Student” object hides how CGPA is calculated.

---

### **2. Encapsulation**

* Combines data and methods in a single unit (class).
* Protects internal state using access specifiers (private, protected).
* Prevents unauthorized access.

---

### **3. Modularity**

* System is divided into independent modules (classes/packages).
* Each module handles a specific responsibility → reduces complexity.

---

### **4. Hierarchy**

* Uses inheritance to define parent-child relationships.
* Promotes generalization and specialization.
  Example: `Animal → Dog → German Shepherd`.

---

### **5. Reusability**

* Code reuse via inheritance, polymorphism, composition.
* Reduces development time and improves reliability.

---

### **6. Maintainability**

* Encapsulation and modularity make change management easy.
* New features can be added without modifying the entire system.

---

### **7. Polymorphism**

* Objects can take multiple forms.
* Same message → different actions.
  Example: `draw()` behaves differently for Circle and Rectangle.

---

### **8. Low Coupling**

* Classes have minimal interdependencies.
* Improves flexibility and reusability.

---

### **9. High Cohesion**

* Each class performs a single, well-defined task.
* Enhances clarity and reduces errors.

---

### **Conclusion**

OOD provides structural clarity, flexibility, reusability, and natural mapping with real-world entities, making it essential for designing complex systems.

---

# **2. OOA and OOD are parallel activities. Explain. (12 marks)**

### **Introduction**

Object-Oriented Analysis (OOA) identifies *what* the system must do, while Object-Oriented Design (OOD) determines *how* the system will be built. In modern development, both activities occur simultaneously rather than sequentially.

---

# **Reasons Why OOA and OOD Are Parallel**

### **1. Iterative Development Nature**

* Object-oriented processes like **RUP**, **Agile**, **Spiral** use iterative cycles.
* Each iteration refines both analysis and design.

---

### **2. Feedback Between Activities**

* Analysis discovers new requirements → design must adjust.
* Design reveals constraints → analysis model must update.

---

### **3. Shared Concepts**

OOA and OOD use the same modeling entities:

* Classes
* Objects
* Relationships
* Use cases
* Interaction diagrams

Thus, both activities complement each other.

---

### **4. Real-World Mapping**

* OOA finds real-world concepts (e.g., Customer, Order).
* OOD refines them with attributes, methods, visibility, patterns.
  This mapping happens in parallel.

---

### **5. Continuous Refinement**

* Analysts define responsibilities.
* Designers define how these responsibilities are implemented.
* Both refine the model at same time.

---

### **6. Reduced Development Time**

Parallel activities lead to:

* Faster delivery
* Early error detection
* Better stakeholder communication

---

### **7. Support from UML**

UML diagrams support iterative refinement.
Example:

* OOA → Use case, domain model
* OOD → Class diagram, sequence diagram

Both can be adjusted side-by-side.

---

### **Conclusion**

OOA and OOD are parallel because object-oriented development is iterative and evolutionary, requiring continuous refinement of analysis and design. This leads to better-quality, maintainable systems.

---

# **3. Explain SOLID principles for class identification. (12 marks)**

### **Introduction**

SOLID is a set of five object-oriented design principles formulated by Robert C. Martin. These help in designing classes that are flexible, maintainable, and modular. Useful during *class identification phase* in OOD.

---

# **SOLID Principles**

### **1. S – Single Responsibility Principle (SRP)**

* A class should have **only one reason to change**.
* Encourages high cohesion.
  Example:
  `InvoicePrinter` should not calculate tax.

---

### **2. O – Open/Closed Principle (OCP)**

* A class should be **open for extension** but **closed for modification**.
* Achieved using interfaces, abstract classes, and polymorphism.
  Example: Adding new payment methods without modifying existing code.

---

### **3. L – Liskov Substitution Principle (LSP)**

* Subclasses should be usable in place of their base class **without breaking behavior**.
  Example: `Square` should not violate behavior of `Rectangle`.

---

### **4. I – Interface Segregation Principle (ISP)**

* Clients should not be forced to depend on unused methods.
* Prefer **small, specific interfaces** over large, general ones.

Wrong:
`IPrinter { Print(); Scan(); Fax(); }`
Correct:

* `IPrint`
* `IScan`
* `IFax`

---

### **5. D – Dependency Inversion Principle (DIP)**

* High-level modules should not depend on low-level modules.
* Both should depend on **abstractions** (interfaces).
* Reduces tight coupling.

Example:
`PaymentProcessor` should depend on `IPaymentService`, not specific classes like `EsewaPay` or `PhonePay`.

---

### **Conclusion**

SOLID principles guide class identification and design, ensuring low coupling, high cohesion, and extensibility. Essential for creating high-quality, maintainable OO systems.

---

# **4. Define class and object. Explain different types of relationships exhibited by classes. (12 marks)**

### **Introduction**

Classes and objects are fundamental concepts of object-oriented systems. Class relationships define how objects collaborate to achieve system functionality.

---

# **Definition**

### **Class**

A blueprint or template that defines attributes and behaviors of objects.
Example:
`class Student { name, roll; attendClass(); }`

---

### **Object**

A real-world entity created from a class.
Has:

* Identity
* State
* Behavior
  Example:
  `Student s1 = new Student();`

---

# **Types of Class Relationships**

### **1. Association**

* A general relationship between two classes.
* Indicates communication or interaction.
  Example:
  Teacher — teaches — Student.

---

### **2. Aggregation (Has-A relationship)**

* Weaker form of whole-part relationship.
* Part can exist independently if the whole is destroyed.
  Example:
  Class *College* has Departments.
  If College closes, Department can exist elsewhere.

---

### **3. Composition (Strong Has-A relationship)**

* Strong whole-part relationship.
* Part cannot exist independently.
  Example:
  House and Room.
  Delete House → Rooms are deleted.

---

### **4. Inheritance (Is-A relationship)**

* One class acquires properties of another.
* Promotes reusability.
  Example:
  `Car extends Vehicle`.

---

### **5. Dependency (Uses relationship)**

* Temporary relationship where one class uses another.
  Example:
  `ATM uses BankServer`.

---

### **6. Realization**

* Relationship between interface and class implementing it.

---

### **7. Generalization / Specialization**

* Parent-child relationship.
* General class → specific class derived from it.

---

### **Conclusion**

Understanding class relationships is crucial for building flexible, correct, and maintainable object-oriented systems.

---

# ✅ **UNIT 3 — 12 Marks Answers (Expert Level)**

---

# **1. What is UML? Explain the significance of UML in system analysis and design. (12 marks)**

### **Introduction**

Unified Modeling Language (UML) is a standardized visual modeling language used to describe, design, and document software systems. It supports object-oriented concepts and is widely used for analysis and design in modern software engineering.

---

# **Definition of UML**

UML is a **graphical language** that provides a set of notations (diagrams) to model the structure, behavior, and interactions of a software system.

It is **not a programming language**, but a modeling standard.

---

# **Significance of UML in System Analysis and Design**

### **1. Standardization**

* UML provides a **common modeling standard** used worldwide.
* Helps developers, analysts, and stakeholders communicate clearly.

---

### **2. Visualization of the System**

* Converts complex requirements into visual diagrams.
* Helps understand the system easily at various abstraction levels.

---

### **3. Supports Object-Oriented Approach**

* UML diagrams map naturally to OO concepts like classes, objects, inheritance, and interactions.

---

### **4. Improves Requirement Understanding**

* Use case diagrams help identify actors and system requirements.
* Reduces ambiguity in requirement collection.

---

### **5. Enhances Design Quality**

* Class, sequence, and state diagrams help design robust architecture.
* Ensures scalability, reusability, and maintainability.

---

### **6. Helps in Communication**

* Serves as a common language between analysts, designers, developers, testers, and clients.

---

### **7. Facilitates Documentation**

* UML diagrams act as long-term documentation of system architecture.

---

### **8. Supports Different Development Processes**

* Works with **Waterfall**, **Agile**, **Spiral**, **RUP**, etc.
* Flexibility is one of its strengths.

---

### **9. Aids in Code Generation and Reverse Engineering**

* Tools like Enterprise Architect, StarUML can generate skeleton code (Java/C#/C++).
* Can also reverse engineer existing systems.

---

### **10. Reduces Development Risks**

* Early modeling helps detect design issues before coding begins.

---

### **Conclusion**

UML is an essential tool in system analysis and design, offering standard diagrams that simplify requirement representation, system structure visualization, and behavior modeling.

---

# **2. What is a class diagram? Explain with an example. (12 marks)**

### **Introduction**

A class diagram is a **static structure diagram** in UML that shows the classes, their attributes, operations, and relationships. It forms the backbone of object-oriented design.

---

# **Definition**

A **class diagram** visually represents the structure of a system by modeling its classes and the relationships among them.

---

# **Elements of Class Diagram**

### **1. Class**

Represents blueprint of objects.
Contains:

* Class Name
* Attributes
* Methods

### **2. Relationships**

* Association
* Aggregation
* Composition
* Inheritance
* Dependency
* Realization

### **3. Multiplicity**

Shows how many objects participate in relationships.
Example: `1..*`, `0..1`.

---

# **Example: Library Management System**

### **Classes**

1. **Book**
   Attributes: bookID, title, author
   Methods: issue(), return()

2. **Member**
   Attributes: memberID, name
   Methods: register(), payFine()

3. **Librarian**
   Attributes: employeeID
   Methods: addBook(), removeBook()

4. **Loan**
   Attributes: issueDate, returnDate

---

# **Sample Class Diagram (Describe This in Exam Text Form)**

* Member *borrows* Book → Association
* Librarian *manages* Book → Association
* Loan *links* Book and Member → Association class
* Book *is a* Resource → Inheritance

```
          Resource
             |
            Book
           /    \
       Loan — Member
            |
        Librarian
```

*(Draw simple rectangles with attributes and methods in exam.)*

---

### **Conclusion**

Class diagrams are essential for designing the static structure of an OO system and act as the foundation for coding and further design.

---

# **3. Draw a class diagram and use case diagram. (12 marks)**

*(I will write the description and structure that you can directly draw in your answer sheet. PU doesn’t require perfect diagram art.)*

### **Introduction**

Class diagrams show static structure; use case diagrams show functional behavior.

---

# **A. Class Diagram — Example: Online Shopping System**

### **Classes**

* Customer
* ShoppingCart
* Product
* Order
* Payment
* Admin

### **Relationships**

* Customer *creates* Order
* Customer *adds* Product to ShoppingCart
* Order *contains* Product
* Payment *processes* Order
* Admin *manages* Product

### **Structure to Draw**

```
Customer ----- ShoppingCart ----- Product
   |                |                 |
   | places         | contains        | managed by
   |                |                 |
  Order -------- Payment -------- Admin
```

*(Draw attributes and methods under each class rectangle.)*

---

# **B. Use Case Diagram — Online Shopping System**

### **Actors**

* Customer
* Admin
* Payment Gateway

### **Use Cases**

* Register
* Login
* Add to Cart
* Checkout
* Make Payment
* Manage Products (Admin)
* View Order History

### **Diagram to Draw**

```
         Customer
             |
   ------------------------
   |         |            |
Register   Login     Add to Cart
             |
        Checkout ---- Payment Gateway
             |
        Make Payment
             |
     View Order History

            Admin
              |
       Manage Products
```

---

### **Conclusion**

Both diagrams help understand system structure and user interactions, providing complementary perspectives for design.

---

# **4. Explain sequence diagram with an example. (12 marks)**

### **Introduction**

A sequence diagram is a UML **interaction diagram** showing how objects interact through messages over time. It emphasizes the order of message flow.

---

# **Definition**

Sequence diagram represents **time-ordered interactions** between actors and objects to fulfill a specific scenario.

---

# **Key Elements**

1. **Lifelines**
   Represent objects or actors.

2. **Activation Bars**
   Show period during which an object is performing an action.

3. **Messages**

   * Synchronous
   * Asynchronous
   * Return messages

4. **Objects**
   Represented at the top of the diagram.

5. **Time Flow**
   Top → bottom.

---

# **Example: ATM Withdrawal Sequence Diagram**

### **Actors/Objects**

* User
* ATM
* BankServer
* Account

### **Steps**

1. User inserts card.
2. ATM requests PIN.
3. User enters PIN.
4. ATM sends PIN to BankServer.
5. BankServer validates credentials via Account.
6. User chooses "Withdraw".
7. ATM sends request to BankServer.
8. BankServer authorizes withdrawal.
9. ATM dispenses cash.
10. ATM prints receipt.

---

# **Diagram to Draw (Text Description)**

```
User → ATM : insertCard()
ATM → User : requestPIN()
User → ATM : enterPIN()
ATM → BankServer : validatePIN()
BankServer → Account : checkPIN()
Account → BankServer : valid
ATM → User : selectAmount()
User → ATM : enterAmount()
ATM → BankServer : requestWithdrawal()
BankServer → ATM : approve
ATM → User : dispenseCash()
ATM → User : printReceipt()
```

(Time flows from top to bottom; messages are arrows between lifelines.)

---

### **Conclusion**

Sequence diagrams are essential for modeling dynamic behavior, illustrating message flow clearly for complex interactions such as ATM, login, online ordering, etc.

---

# ✅ **UNIT 4 — 12-Marks Answers**

---

# **1. What is domain analysis? Explain the stages of domain analysis. (12 marks)**

### **Introduction**

Domain analysis is the first and most important activity in object-oriented development. It studies the application domain to identify reusable concepts, common requirements, and domain knowledge that guide system design.

---

# **Definition**

**Domain analysis** is the process of studying and understanding the problem domain (business area) to identify:

* domain concepts
* domain objects
* relationships
* constraints
* reusable components

It focuses on "understanding the real world before designing the software."

---

# **Stages of Domain Analysis**

### **1. Domain Scoping**

* Determines the boundaries of the domain.
* Identifies what is inside or outside the system.
  Example: In an ATM system, bank rules & card validation are in domain; network hardware is outside.

---

### **2. Domain Exploration / Investigation**

* Collect domain knowledge from users, reports, manuals, rules, existing systems.
* Identifies common concepts, terms, constraints, rules.
  Sources: Interviews, documents, business rules.

---

### **3. Domain Modeling**

* Represents identified domain concepts using:

  * Class diagrams
  * Use-case diagrams
  * Context diagrams
* Defines entities, attributes, and relationships.

---

### **4. Domain Classification**

* Groups similar concepts together.
* Identifies patterns and reusable components.
  Example: Customer, Account, Loan are financial domain classes.

---

### **5. Production of Domain Dictionary**

* Creates vocabulary of domain terms.
* Ensures analysts and clients use consistent terminology.

---

### **6. Domain Validation**

* Ensures domain model accurately reflects business rules.
* Involves clients, domain experts, and analysts.

---

### **7. Reuse Analysis**

* Identifies aspects that can be reused in other systems.
* Reduces development cost for future projects.

---

### **Conclusion**

Domain analysis provides a clear understanding of the problem environment, improves communication with stakeholders, and guides the creation of accurate OO models.

---

# **2. Explain class-based modeling in domain analysis. (12 marks)**

### **Introduction**

Class-based modeling is the core component of domain analysis. It identifies the domain classes and their interrelationships to create the domain class model.

---

# **Explanation of Class-Based Modeling**

### **1. Identifying Domain Classes**

* Analyze requirements, scenarios, and use cases.
* Extract **nouns** that may represent domain objects.
  Examples: Customer, Order, Payment, Invoice.

---

### **2. Identifying Class Attributes**

* Describe important properties of each class.
  Example:
  Customer → name, phone, address.

---

### **3. Identifying Class Methods**

* Define responsibilities or operations of each class.
  Example:
  Order → createOrder(), cancelOrder().

---

### **4. Identifying Class Relationships**

Includes:

* Association
* Aggregation
* Composition
* Inheritance
* Dependency
* Realization

This defines collaborations between classes.

---

### **5. Building the Domain Class Diagram**

* Draw UML class diagrams showing:

  * Classes
  * Attributes
  * Functions
  * Relationships
  * Multiplicity (1..*, 0..1)

Example (Textual):

```
Customer ---- places ---- Order ---- contains ---- Product
```

---

### **6. Refinement and Validation**

* Remove redundant classes
* Merge similar classes
* Validate with domain experts

---

### **7. Adding Constraints and Business Rules**

* Represent domain rules using notes or stereotypes.
  Example:
  "An order must have at least one product."

---

### **Conclusion**

Class-based modeling creates a clear structural representation of the system and forms the foundation for object-oriented design (OOD) and coding.

---

# **3. Explain scenario-based modeling in domain analysis. (12 marks)**

### **Introduction**

Scenario-based modeling defines how users interact with the system and how the system behaves in different situations. It supports requirement gathering and behavioral understanding.

---

# **Scenario-Based Modeling Explanation**

### **1. Use-Case Modeling**

* Identifies actors and system functionalities.
* Each use case represents a scenario of interaction.
  Example: "Withdraw Cash" for ATM.

Elements:

* Actor
* Use case
* Precondition
* Postcondition
* Main flow
* Alternate flows

---

### **2. Use-Case Diagrams**

Graphical representation of use cases and actors.
Shows interactions and system boundaries.

---

### **3. Activity Modeling**

* Uses activity diagrams to represent workflow.
* Shows sequence of actions and branching conditions.

Example:
Login → Validate → Dashboard.

---

### **4. Event Modeling**

* Identifies external events affecting system behavior.
* Defines how system reacts to each event.
  Example:
  "Card inserted", "PIN entered".

---

### **5. Sequence Diagrams**

* Show how objects interact over time.
* Focus on message flow.
  Example: ATM → BankServer → Account.

---

### **6. Collaboration Diagrams**

* Emphasize structural relationships among interacting objects.

---

### **7. Scenarios for Exception Handling**

* Defines alternate flows.
  Example:
  If PIN is wrong → display error message.

---

### **Conclusion**

Scenario-based modeling captures dynamic behavior and user-system interactions, providing essential input for system design and validation.

---

# **4. Explain behavior modeling in domain analysis. (12 marks)**

### **Introduction**

Behavior modeling describes how objects in the system change states and interact in response to events. It focuses on dynamic behavior.

---

# **Behavior Modeling Explanation**

### **1. Identifying Events**

* Events trigger transitions.
  Examples:
  *PIN entered*, *Button pressed*, *Payment confirmed*.

---

### **2. Identifying States**

* State defines a significant condition of an object.
  Example:
  For Order object:
* New
* Processing
* Shipped
* Delivered
* Cancelled

---

### **3. State Machine Diagram (State Chart)**

Represents states, events, transitions, and actions.
Example (ATM):
Idle → CardInserted → ValidateCard → PINEntered → Transaction.

---

### **4. Sequence Diagrams**

Used for modeling dynamic interactions among objects.

---

### **5. Activity Diagrams**

Show workflow and action sequences.

---

### **6. Internal Behavior Representation**

* Guards
* Actions
* Conditions
* Transition rules

Example:
If balance ≥ withdrawal amount → approve; else → reject.

---

### **7. Behavioral Constraints**

UML notes/stereotypes used to express rules.
Example:
"Order cannot be shipped if payment = pending."

---

### **Conclusion**

Behavior modeling provides an understanding of how the system reacts to events, ensuring accurate and predictable system behavior.

---

# **5. Define domain analysis. Explain activities performed in domain analysis. (12 marks)**

### **Introduction**

Domain analysis is the study of the application environment to identify necessary knowledge, reusable components, common requirements, and patterns.

---

# **Definition**

Domain analysis is the process of analyzing a specific domain to identify domain concepts, commonalities, constraints, requirements, and reusable elements before system design begins.

---

# **Activities in Domain Analysis**

### **1. Domain Scoping**

Define boundaries and identify stakeholders.

---

### **2. Data Collection**

Gather domain knowledge using:

* Interviews
* Documents
* Existing systems
* Observations

---

### **3. Identification of Domain Concepts**

Extract classes, entities, and objects relevant to the domain.

---

### **4. Creation of the Domain Model**

Use UML diagrams to represent:

* Classes
* Relationships
* Attributes
* Constraints

---

### **5. Scenario Analysis**

Prepare use cases, workflows, and user interactions.

---

### **6. Behavioral Analysis**

Use state charts and sequence diagrams to visualize dynamic behavior.

---

### **7. Classification & Categorization**

Group similar domain concepts and identify reusable components.

---

### **8. Preparing the Domain Dictionary**

Create vocabulary of domain terms to avoid ambiguity.

---

### **9. Validation**

Review domain models with stakeholders and domain experts.

---

### **10. Documentation**

Maintain complete domain analysis artifacts for future use.

---

### **Conclusion**

Domain analysis ensures that system requirements are complete, accurate, and well-understood, forming the foundation of successful object-oriented system development.

---

# ✅ **UNIT 5 — 12 Marks Answers**

---

# **1. Define an agent. Explain the role of an agent in improving performance of a software system. (12 marks)**

### **Introduction**

In modern intelligent systems, an *agent* is an autonomous software entity capable of sensing its environment and acting rationally to achieve goals. Agents are widely used in AI-driven systems, network management, robotics, e-commerce, and distributed computing.

---

# **Definition of an Agent**

An **agent** is a software-based entity that:

* perceives its environment,
* processes information autonomously,
* makes decisions,
* takes actions to achieve predefined goals.

Examples:
Chatbots, autonomous robots, recommender systems, network monitoring agents.

---

# **Role of Agents in Improving Software System Performance**

### **1. Autonomy**

Agents can operate without human intervention.
This reduces manual workload and improves system responsiveness.

---

### **2. Proactive Behavior**

Agents can predict events and take actions *before* the event occurs.
Example:
A caching agent preloads user queries to improve performance.

---

### **3. Reactive Behavior**

Agents can react quickly to changes in the environment.
Example:
Intrusion detection agent responds instantly to suspicious activity.

---

### **4. Distributed Problem Solving**

Agents collaborate to solve complex tasks faster.
Example:
Multiple agents process transactions in distributed payment systems.

---

### **5. Flexibility and Scalability**

Agents can be added, removed, or reconfigured dynamically.
Useful in cloud systems and IoT environments.

---

### **6. Adaptability**

Agents learn and adapt from environment changes.
Example:
Recommendation agents improve accuracy over time.

---

### **7. Improved Decision-Making**

Agents can analyze large datasets and make optimal decisions faster than humans.

---

### **8. Better Resource Utilization**

Agents intelligently manage system resources.
Example:
Load-balancing agents distribute traffic evenly across servers.

---

# **Conclusion**

Agents enhance performance through autonomy, intelligence, scalability, and adaptability, making them essential for modern complex software systems.

---

# **2. What is an agent? Explain the properties of an agent. (12 marks)**

### **Introduction**

Agents are the central concept in Agent-Oriented Programming (AOP) and intelligent systems. Their unique properties differentiate them from traditional software objects.

---

# **Definition of an Agent**

An agent is an independent, goal-driven entity capable of sensing its environment and acting upon it intelligently to achieve objectives.

---

# **Properties of an Agent**

### **1. Autonomy**

Agents control their internal state and behavior without external interference.

---

### **2. Reactivity**

Agents perceive the environment and respond to stimuli appropriately.

---

### **3. Pro-activeness**

Agents not only react but also initiate actions to meet goals.

---

### **4. Social Ability**

Agents communicate with other agents using agent communication languages (ACL).

---

### **5. Adaptability / Learning**

Agents may use AI techniques to learn from interactions and improve.

---

### **6. Mobility (Optional Property)**

Some agents can move from one machine to another.
Example: Mobile agents for distributed computing.

---

### **7. Goal-Oriented Behavior**

Every agent is designed with goals, beliefs, and intentions.

---

### **8. Persistence**

Agents maintain their state across sessions and time.

---

### **9. Rationality**

Agents choose the best possible action to achieve goals.

---

# **Conclusion**

Agent properties such as autonomy, intelligence, communication, and learning make them suitable for building modern distributed intelligent systems.

---

# **3. Compare OOP and AOP. (12 marks)**

### **Introduction**

Object-Oriented Programming (OOP) deals with objects and classes, while Agent-Oriented Programming (AOP) deals with intelligent autonomous agents capable of decision-making. Both approaches have different goals.

---

# **Comparison Between OOP and AOP**

| Aspect              | OOP                                   | AOP (Agent-Oriented Programming)                     |
| ------------------- | ------------------------------------- | ---------------------------------------------------- |
| **Basic Component** | Object                                | Agent                                                |
| **Control**         | Controlled externally by method calls | Autonomous control; agents decide their own actions  |
| **State Change**    | Based on explicit method invocation   | Based on reasoning, goals, events                    |
| **Communication**   | Message passing or method calls       | Agent Communication Languages (ACL), negotiation     |
| **Behavior**        | Reactive and deterministic            | Proactive, reactive, goal-driven, adaptive           |
| **Concurrency**     | Managed through threads               | Agents typically have independent threads of control |
| **Focus**           | Data + Behavior                       | Beliefs + Desires + Intentions (BDI model)           |
| **Design Goal**     | Reusability, modularity               | Intelligence, autonomy, distributed problem solving  |
| **Usage**           | Traditional software systems          | AI systems, robotics, distributed systems            |
| **Examples**        | Java, C++, Python                     | JADE, JACK, AgentSpeak(L)                            |

---

# **Conclusion**

OOP is ideal for structured, modular software, whereas AOP is suited for intelligent, autonomous, and distributed applications. Both can coexist to build sophisticated systems.

---

# **4. Explain agent representation in a class diagram with example. (12 marks)**

### **Introduction**

Agents can be represented using UML class diagrams by modeling their internal structure (beliefs, goals, plans) and external interactions. UML is extended using stereotypes such as «agent».

---

# **Agent Representation in Class Diagram**

### **1. Use of Stereotype**

Agents are denoted with the stereotype:
`«agent»`
This distinguishes them from normal objects.

---

### **2. Internal Components of an Agent**

A typical agent contains:

* **Beliefs** → Knowledge base
* **Goals** → Desired objectives
* **Plans** → Strategies to achieve goals
* **Percepts** → Information received from environment
* **Actions** → Tasks executed by the agent

These can be modeled as attributes or separate classes.

---

### **3. Interactions**

Agents often interact using:

* Signals
* Messages
* Communication protocols
  These can be shown using associations or dependencies.

---

# **Example: Class Diagram of a Shopping Recommendation Agent**

### **Classes**

1. **«agent» RecommendationAgent**

   * Attributes:
     beliefs: UserPreferences
     goals: ProvideSuggestions
     plans: AnalyzeData(), RecommendProducts()
   * Methods: receiveData(), compute(), sendRecommendation()

2. **User**

   * Attributes: name, purchaseHistory

3. **Product**

   * Attributes: productID, category, price

4. **RecommendationEngine** (support class)

   * Methods: filter(), sort(), suggest()

---

# **Text-Based Diagram Structure (For Exam Writing)**

```
                «agent» RecommendationAgent
      ----------------------------------------------------
      - beliefs: UserPreferences
      - goals: ProvideSuggestions
      - plans: AnalyzeData, RecommendProducts
      ----------------------------------------------------
      + receiveData()
      + compute()
      + sendRecommendation()
                     |
                     |
        interacts with (association)
                     |
        --------------------------------
        |                              |
      User                         Product
```

---

### **Explanation**

* The agent uses user data and product data.
* It contains internal states (beliefs, goals, plans).
* It interacts with supporting classes.

---

### **Conclusion**

Agent representation in class diagrams helps visualize its internal architecture, interactions, and intelligent behavior, making design of multi-agent systems organized and clear.

---

# ✅ **UNIT 6 — 12 Marks Answers**

---

# **1. Compare internal and external quality of a software. (12 marks)**

### **Introduction**

Software quality determines how well a system meets user expectations, performs its intended function, and adheres to standards. Quality can be evaluated from two perspectives: **internal quality** and **external quality**.

---

# **A. Internal Quality**

### **Definition**

Internal quality refers to characteristics of the **source code, design, architecture, and internal structure** of software that are not visible to end users.

### **Characteristics**

1. **Code Maintainability**

   * Ease of updating, modifying, or extending code.
2. **Readability**

   * Quality of variable names, comments, formatting.
3. **Consistency**

   * Use of standard patterns, structured design.
4. **Low Coupling & High Cohesion**

   * Better modularity and design quality.
5. **Reusability**

   * Components can be reused across systems.
6. **Testability**

   * Code is easier to unit test.

### **Example**

A system may look perfect to users but have poor internal quality (duplicate code, no documentation).

---

# **B. External Quality**

### **Definition**

External quality refers to the **user-visible** characteristics of software that determine usability and performance.

### **Characteristics**

1. **Functionality**

   * Software performs required functions correctly.
2. **Usability**

   * Easy to use, intuitive interfaces.
3. **Reliability**

   * Minimal failures and accurate results.
4. **Efficiency**

   * Fast response, low resource usage.
5. **Portability**

   * Works in different environments.
6. **Security**

   * Protects data and resists attacks.

### **Example**

A UI may be user-friendly and fast, representing high external quality.

---

# **C. Comparison Table**

| Aspect           | Internal Quality       | External Quality           |
| ---------------- | ---------------------- | -------------------------- |
| **Visibility**   | Not visible to users   | Visible to users           |
| **Focus**        | Design, code structure | Functionality, performance |
| **Evaluated by** | Developers, testers    | End users, clients         |
| **Examples**     | Clean code, modularity | Usability, reliability     |
| **Impact**       | Long-term maintenance  | User satisfaction          |

---

### **Conclusion**

Both internal and external qualities are essential for creating successful software. Internal quality ensures maintainability, while external quality ensures user acceptance.

---

# **2. What is a software metric? Explain with an example. (12 marks)**

### **Introduction**

Software metrics measure software attributes quantitatively. They help assess quality, predict effort, and evaluate design and code characteristics.

---

# **Definition of Software Metric**

A **software metric** is a numerical measure used to evaluate aspects of software, such as complexity, performance, quality, or development effort.

---

# **Purpose of Software Metrics**

* Improve quality
* Predict cost and time
* Measure complexity
* Monitor project progress
* Support decision-making

---

# **Types of Metrics**

1. **Product Metrics**
   e.g., Lines of Code (LOC), Cyclomatic Complexity
2. **Process Metrics**
   e.g., Defect detection rate
3. **Project Metrics**
   e.g., Person-hours, schedule variance

---

# **Example: Cyclomatic Complexity**

Cyclomatic Complexity (McCabe’s Metric) measures the **logical complexity** of a program.

### **Formula:**

`CC = E – N + 2`
Where:

* E = Number of edges
* N = Number of nodes

### **Interpretation**

* CC = 1 → simple program
* CC = 10–20 → complex
* CC > 20 → very complex and risky

### **Example**

```
if (x > 0)
   print("Positive");
else
   print("Negative");
```

This has 2 decision points → CC = 3.

---

### **Conclusion**

Software metrics provide objective measurement, improve quality, and help managers and developers make informed decisions.

---

# **3. Explain metrics for object-oriented systems. (12 marks)**

### **Introduction**

Object-oriented systems require special metrics due to the complexity of classes, inheritance, polymorphism, and relationships.

---

# **Key OO Metrics**

## **1. CK Metrics Suite (Most Important)**

### **a. WMC — Weighted Methods per Class**

* Measures class complexity based on the number of methods.
* High WMC → complex, harder to maintain.

---

### **b. DIT — Depth of Inheritance Tree**

* Measures levels of inheritance.
* Higher DIT → more complexity and reuse.

---

### **c. NOC — Number of Children**

* Counts number of subclasses.
* High NOC → better reuse, but harder to test.

---

### **d. CBO — Coupling Between Objects**

* Number of classes coupled to a class.
* Lower coupling is desirable.

---

### **e. RFC — Response for a Class**

* Number of methods that can be invoked by a class.
* High RFC → complexity and defect probability.

---

### **f. LCOM — Lack of Cohesion in Methods**

* Measures how related methods are.
* High LCOM → poor cohesion → should split the class.

---

## **2. MOOD Metrics (Metrics for OO Design)**

### **a. Encapsulation (MHF/ AHF)**

Measures hidden attributes/methods.

### **b. Inheritance (MIF/ AIF)**

Measures inheritance usage.

### **c. Polymorphism (POF)**

Measures overriding and overloading.

### **d. Coupling (COF)**

Inter-class dependencies.

---

## **3. Size Metrics**

* Number of classes
* Number of attributes
* Number of methods
* Lines of Code per class

---

## **4. Quality Metrics**

* Reusability index
* Maintainability index
* Modularity index

---

### **Conclusion**

OO metrics help evaluate design quality, maintainability, complexity, coupling, cohesion, and overall system performance.

---

# **4. Prepare a candidate solution matrix and explain how it can be helpful in selecting a programming language. (12 marks)**

### **Introduction**

Selecting a programming language requires analyzing different alternatives based on project requirements. A **candidate solution matrix** helps compare multiple languages on various criteria.

---

# **Candidate Solution Matrix (Example for Web Application)**

| Criterion            | Java       | Python     | PHP    | JavaScript |
| -------------------- | ---------- | ---------- | ------ | ---------- |
| Performance          | High       | Medium     | Medium | High       |
| Learning Curve       | Medium     | Easy       | Easy   | Medium     |
| Libraries/Frameworks | Excellent  | Excellent  | Good   | Excellent  |
| Security             | Strong     | Medium     | Medium | Strong     |
| Scalability          | High       | Medium     | Medium | High       |
| Community Support    | Very Large | Very Large | Large  | Very Large |
| Cost                 | Free       | Free       | Free   | Free       |
| Suitability for Web  | Medium     | Medium     | High   | High       |

---

# **How Candidate Solution Matrix Helps**

### **1. Objective Evaluation**

Provides a **quantitative comparison** between languages.

---

### **2. Considers Multiple Factors**

Evaluates languages based on:

* Performance
* Security
* Scalability
* Ease of use
* Library availability
* Community support

---

### **3. Helps in Decision Making**

Managers and architects can select the **most suitable** language based on the project goals.

---

### **4. Reduces Risk**

Avoids choosing a language that causes future problems.

---

### **5. Aligns Language Choice with Requirements**

For example:

* **AI system** → Python
* **Large enterprise app** → Java
* **Web apps** → PHP, JavaScript

---

### **6. Saves Cost & Time**

Selecting the right language early prevents costly rework.

---

### **Conclusion**

A candidate solution matrix provides a structured method to compare programming languages and select the most appropriate one based on project needs.

---

# ✅ **UNIT 7 — 12 Marks Answers**

---

# **1. Explain the role of standard methodology in developing a quality software. (12 marks)**

### **Introduction**

A standard software development methodology provides a structured approach for planning, designing, building, testing, and maintaining software. It ensures consistency, predictability, and high quality in software projects.

---

# **Role of Standard Methodologies**

### **1. Provides a Structured Framework**

Standard methodologies (Waterfall, Agile, Spiral, RUP) define systematic steps:

* Requirement analysis
* Design
* Implementation
* Testing
* Deployment

This ensures no phase is overlooked.

---

### **2. Improves Software Quality**

Standards like ISO 9001, CMMI, IEEE encourage:

* Quality checks
* Documentation
* Reviews
* Testing procedures
  This improves reliability and correctness.

---

### **3. Enhances Communication**

A methodology ensures all team members follow the same process:

* Common documentation style
* Defined terminology
* Standard workflows

This removes ambiguity.

---

### **4. Risk Management**

Methodologies identify and mitigate risks early:

* Spiral model integrates risk assessment
* Agile reduces risk through frequent iterations

---

### **5. Better Project Planning & Monitoring**

Standard methodologies provide:

* Gantt charts
* Resource allocation
* Milestones
* Progress tracking

This increases predictability.

---

### **6. Ensures Reusability**

Object-oriented methodologies encourage:

* Use of design patterns
* Component libraries
* Frameworks

This reduces development time.

---

### **7. Supports Quality Assurance Activities**

Methodologies require:

* Code reviews
* Test planning
* Verification & validation
* Documentation checks

---

### **8. Improves Maintainability**

Well-structured methods produce:

* Modular designs
* Clean coding
* High cohesion, low coupling

Maintenance becomes easier and cheaper.

---

### **Conclusion**

Standard methodologies play a critical role in delivering high-quality software by providing structure, ensuring consistency, managing risks, and improving communication and maintainability.

---

# **2. Define testing. Explain test case with an example. (12 marks)**

### **Introduction**

Testing is essential to ensure a software system is correct, reliable, secure, and performs as expected. A test case is the fundamental unit of software testing.

---

# **Definition of Testing**

Testing is the process of **executing software with the intent of finding errors** and verifying that the system meets specified requirements.

---

# **Objectives of Testing**

* Detect defects
* Verify functionality
* Validate performance
* Ensure security
* Improve confidence in the system

---

# **Test Case**

### **Definition**

A **test case** is a documented set of:

* inputs,
* execution conditions, and
* expected outputs

designed to verify a specific behavior of the software.

---

### **Components of a Good Test Case**

1. Test Case ID
2. Test Title
3. Pre-conditions
4. Test Steps
5. Input values
6. Expected output
7. Actual output
8. Status (Pass/Fail)

---

### **Example: Login Functionality**

**Test Case ID:** TC_Login_001
**Objective:** Verify that user can login with valid credentials.
**Pre-condition:** User must be registered.

**Test Steps:**

1. Open login page
2. Enter email: "[test@gmail.com](mailto:test@gmail.com)"
3. Enter password: "123456"
4. Click Login

**Input:**
Email = [test@gmail.com](mailto:test@gmail.com)
Password = 123456

**Expected Output:**
System should redirect to dashboard with welcome message.

**Actual Output:**
(Display output after running.)

---

### **Conclusion**

A test case ensures systematic testing, making it easier to detect defects and ensure that the software functions as expected.

---

# **3. What is prototyping? Explain types of prototypes. (12 marks)**

### **Introduction**

Prototyping is a software development technique where a preliminary version of the system is built to understand requirements and refine them before actual development starts.

---

# **Definition of Prototyping**

Prototyping is the process of developing an **early working model** (prototype) of the software to help users visualize the final product and clarify requirements.

---

# **Types of Prototypes**

---

# **1. Throw-away (Rapid) Prototype**

* Built quickly to clarify user requirements
* Not used in final system
* Helps identify misunderstandings early

**Example:**
Quick mock-up of an ATM interface.

---

# **2. Evolutionary Prototype**

* Continuously refined based on feedback
* Used as part of the final system
* Grows through multiple iterations

**Example:**
E-commerce website updated based on user feedback.

---

# **3. Incremental Prototype**

* System is divided into small parts
* Each prototype implements one part
* Final system integrates all prototypes

**Example:**
Banking system → Account module → Loan module → Transaction module.

---

# **4. Extreme Prototyping (Used in Web Development)**

Stages:

1. Static UI prototype
2. Functional UI prototype
3. Fully working system with services

---

# **5. Horizontal Prototype**

* Shows entire UI
* No business logic
  Used for **usability testing**.

---

# **6. Vertical Prototype**

* Works deeply for one functionality
  Used for **performance testing**.

---

### **Conclusion**

Prototyping reduces requirement ambiguity, improves communication, minimizes rework, and increases user satisfaction.

---

# **4. Compare evolutionary and throw-away prototype. (12 marks)**

### **Introduction**

Both evolutionary and throw-away prototypes help validate requirements, but their purpose and usage differ significantly.

---

# **Comparison**

| Aspect                    | Evolutionary Prototype           | Throw-away Prototype          |
| ------------------------- | -------------------------------- | ----------------------------- |
| **Purpose**               | Build a working system gradually | Clarify requirements quickly  |
| **Usage in Final System** | Becomes part of final system     | Discarded after use           |
| **Development Time**      | Longer (continuous refinement)   | Short (rapid development)     |
| **Quality**               | High-quality, production-ready   | Low-quality, quick design     |
| **Changes**               | Incremental improvements         | Rebuilt if needed             |
| **Cost**                  | Higher                           | Lower                         |
| **Risk Handling**         | Good for complex requirements    | Good for unclear requirements |
| **Example**               | Online banking system            | ATM interface mock-up         |

---

### **Conclusion**

Evolutionary prototypes evolve into the final product, while throw-away prototypes are temporary models used to refine requirements.

---

# **5. Compare validation and verification. Explain different strategies for software testing. (12 marks)**

### **Introduction**

Software quality is ensured through **verification** and **validation**, which are complemented by multiple testing strategies.

---

# **A. Verification vs Validation**

| Aspect           | Verification                         | Validation                              |
| ---------------- | ------------------------------------ | --------------------------------------- |
| **Definition**   | “Are we building the product right?” | “Are we building the right product?”    |
| **Focus**        | Process correctness                  | Product correctness                     |
| **Approach**     | Static (reviews, analysis)           | Dynamic (execution)                     |
| **Performed by** | Developers                           | Testers and users                       |
| **Examples**     | Code review, design inspection       | System testing, user acceptance testing |

---

# **B. Testing Strategies**

### **1. Unit Testing**

* Tests individual units or functions.
* Ensures correctness of small code blocks.
  Example: Testing login validation function.

---

### **2. Integration Testing**

* Tests combined modules.
* Types:

  * Top-down
  * Bottom-up
  * Sandwich
    Example: Payment module + Order module.

---

### **3. System Testing**

* Tests the complete system against requirements.
  Types:
* Functional testing
* Non-functional testing

---

### **4. Acceptance Testing**

Performed by client/end user.
Types:

* UAT (User Acceptance Testing)
* Alpha testing
* Beta testing

---

### **5. Regression Testing**

* Ensures new changes do not break existing functionality.

---

### **6. Smoke Testing**

* Initial quick test to check basic stability.

---

### **7. Stress & Performance Testing**

* Tests system under extreme load and conditions.

---

### **8. Black-Box Testing**

* Tests functionality without seeing code.

---

### **9. White-Box Testing**

* Tests internal logic and structure.

---

### **Conclusion**

Verification ensures the development process is correct, while validation ensures the product meets user expectations. Using systematic testing strategies ensures reliable, high-quality software.

---




