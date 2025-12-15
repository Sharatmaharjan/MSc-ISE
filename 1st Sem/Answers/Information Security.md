# MIE114: Information Security

Q1. As a CISO of a commercial bank of Nepal, suggest security measures using CIA triad and People–Policy–Technology framework (9 marks)

A commercial bank is a high-value target due to sensitive financial data, online banking systems, regulatory obligations (NRB guidelines), and customer trust. Hence, security measures must be holistic and layered.

1. Confidentiality

Ensures that information is accessible only to authorized individuals.

People

Employee background checks and vetting

Regular security awareness training on phishing, insider threats, and data privacy

Clear segregation of duties to prevent misuse of privileges


Policy

Data classification policy (public, internal, confidential, highly confidential)

Access control and password management policy

Non-disclosure agreements (NDA)


Technology

Strong encryption (AES for data at rest, TLS for data in transit)

Multi-Factor Authentication (MFA) for staff and customers

Database access control, VPNs for remote access



---

2. Integrity

Ensures accuracy, completeness, and reliability of data.

People

Authorized personnel for data modification

Dual control and maker–checker concept in banking transactions


Policy

Change management and configuration management policy

Logging and audit trail policy


Technology

Hashing algorithms (SHA-256)

Digital signatures for transaction verification

Database constraints and version control



---

3. Availability

Ensures systems and services are accessible whenever required.

People

Dedicated incident response and disaster recovery teams

Periodic DR drills and simulations


Policy

Business Continuity Plan (BCP)

Disaster Recovery Plan (DRP)

Backup and retention policy


Technology

Redundant servers and network links

Load balancing and failover mechanisms

UPS, generators, and DDoS mitigation tools


Conclusion:
Applying the CIA triad supported by People, Policy, and Technology ensures confidentiality, integrity, and availability of banking information systems.


---

Q2. List application security threats and explain three prevalent threats (9 marks)

Application Security Threats

SQL Injection

Cross-Site Scripting (XSS)

Cross-Site Request Forgery (CSRF)

Broken Authentication

Insecure Direct Object References

Buffer Overflow

Security Misconfiguration



---

1. SQL Injection

Occurs when unvalidated user input is executed as part of an SQL query.

Allows attackers to read, modify, or delete database records

Common in login forms and search fields


Impact:

Data breach

Financial fraud

Loss of confidentiality and integrity


Prevention:

Prepared statements

Input validation

Least privilege database accounts



---

2. Cross-Site Scripting (XSS)

Injection of malicious scripts into trusted web applications.

Script executes in victim’s browser

Can steal cookies or redirect users


Impact:

Session hijacking

Identity theft


Prevention:

Output encoding

Content Security Policy (CSP)

Input sanitization



---

3. Broken Authentication

Weak authentication mechanisms allow attackers to impersonate users.

Poor password storage

Session fixation


Impact:

Account takeover

Unauthorized access


Prevention:

Multi-factor authentication

Secure session management

Password hashing



---

Q3. Differentiate between DES, 3DES, AES, and RSA (9 marks)

Criteria	DES	3DES	AES	RSA

Algorithm Type	Symmetric	Symmetric	Symmetric	Asymmetric
Key Length	56-bit	112/168-bit	128/192/256-bit	1024–4096-bit
Block Size	64-bit	64-bit	128-bit	N/A
Speed	Fast	Slow	Very fast	Very slow
Security Level	Weak	Moderate	Very strong	Strong
Usage	Obsolete	Legacy systems	Modern standard	Key exchange
Example Use	Old banking	Legacy encryption	Disk, VPN, SSL	Digital signatures


Conclusion:

AES is the most secure and efficient symmetric algorithm

RSA is computationally expensive but essential for secure key exchange



---

Q4. What is a firewall? Compare types with pros and cons (9 marks)

Firewall

A firewall is a network security mechanism that enforces security policies by monitoring and controlling traffic between trusted and untrusted networks.


---

Types of Firewalls

1. Packet Filtering Firewall

Operates at network layer


Pros:

Simple and fast


Cons:

No payload inspection

Vulnerable to spoofing



---

2. Stateful Inspection Firewall

Tracks connection state


Pros:

Better security than packet filtering


Cons:

More memory and processing required



---

3. Proxy (Application-Level) Firewall

Acts as intermediary


Pros:

Deep packet inspection

High security


Cons:

Slower performance



---

4. Next-Generation Firewall (NGFW)

Combines firewall, IDS/IPS, malware detection


Pros:

Comprehensive protection


Cons:

High cost and complexity



---

Q5. Why IS audit is needed and steps of IS audit process (9 marks)

Need for IS Audit

Ensure confidentiality, integrity, and availability

Compliance with legal and regulatory requirements

Detect weaknesses and control failures

Protect organizational assets

Improve governance and risk management



---

Steps of IS Audit Process

1. Audit Planning

Define scope and objectives



2. Risk Assessment

Identify threats and vulnerabilities



3. Control Evaluation

Review administrative, technical, and physical controls



4. Audit Testing

Compliance and substantive testing



5. Audit Reporting

Findings, risk ratings, recommendations



6. Follow-Up

Ensure corrective actions implemented





---

Q6. What is BCP? Differentiate between BCP and DRP (9 marks)

Business Continuity Plan (BCP)

BCP is a strategic plan that ensures critical business operations continue during and after disruptive events.

Difference between BCP and DRP

Aspect	BCP	DRP

Focus	Business continuity	IT recovery
Scope	Organization-wide	IT systems only
Activation Time	Before and during disaster	After disaster
Objective	Business survival	System restoration
Example	Manual banking services	Data center recovery



---

Q7. Short Notes (Any TWO) – 2 × 4.5 = 9 marks

(a) Wireless Security Threats

Eavesdropping

Rogue access points

Man-in-the-middle attacks

Weak encryption (WEP)

Evil Twin attacks


Countermeasures:

WPA3 encryption

Strong authentication

Wireless IDS



---

(b) Codes of Ethics

Codes of ethics define moral responsibilities of IT professionals.

Key Principles:

Integrity and honesty

Confidentiality

Professional competence

Social responsibility


Examples: ACM and IEEE codes of ethics


---

(c) RTO and RPO

RTO: Maximum acceptable downtime

RPO: Maximum tolerable data loss


Importance:
Helps organizations design effective backup and recovery strategies.


---
