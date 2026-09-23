# Web-Based Information Management System for Tepi Clinic

## Project Overview
This repository contains the design, schema normalization, and security architecture of a Web-Based Information Management System developed as my Senior Capstone Project at Mizan-Tepi University. The system transitioned a local clinic from slow, manual paper records to a secure, relational digital system.

---

## Technical Architecture & Stack
* **Frontend:** HTML5, CSS3, JavaScript (dynamic form validation)
* **Backend:** PHP (OOP architectural design, session management)
* **Database:** MySQL / MariaDB (relational schema normalized to 3NF)
* **Web Server:** Apache (deployed on local server environment)

---

## Key Engineering Features Implemented

### 1. Database Normalization (3NF Schema)
To prevent data redundancy and anomalies, the database schema was normalized to the **Third Normal Form (3NF)**:
* **First Normal Form (1NF):** Ensured all attributes were atomic; eliminated multi-valued fields.
* **Second Normal Form (2NF):** Removed partial dependencies; ensured all non-key fields depended fully on the composite primary keys.
* **Third Normal Form (3NF):** Eliminated transitive functional dependencies (e.g., patient ZIP codes separated into lookup tables).

### 2. Role-Based Access Control (RBAC) Security
Implemented robust system-level security to protect sensitive patient healthcare data:
* **Authentication:** Password hashing using PHP `password_hash()` with bcrypt.
* **Access Control:** Designed explicit session validation checks separating three user tiers:
  * **System Admins:** Full system configuration and staff management.
  * **Nurses:** Read/write patient vitals and triage records.
  * **Doctors:** Access medical history, input diagnoses, and write prescriptions.

### 3. Defensive Programming Against Web Vulnerabilities
* **SQL Injection Prevention:** Implemented **Parameterized SQL Queries (Prepared Statements)** via PHP Data Objects (PDO) to stop malicious SQL insertions.
* **XSS (Cross-Site Scripting) Mitigation:** Sanitized and escaped all patient search and form outputs using `htmlspecialchars()` before rendering to browser terminals.

---

## Sample SQL Security Snippet (Prepared Statement)
