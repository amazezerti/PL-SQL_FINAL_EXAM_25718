# PL-SQL_FINAL_EXAM_25718
# Names: Mahamat Adji Zezerti Abdramane
# ID: 25718
# NB: All files of queries executed along with screenshots and pptx files for this project are pushed above in the Folder "PLSQL" for verification.

# Pharmacy Management System (thurs_25718_mahamat_PharmacyMS)
# Overview
The Pharmacy Management System (thurs_25718_mahamat_PharmacyMS) is an Oracle 21c Enterprise Edition database application designed to streamline pharmacy operations, including drug inventory management, sales tracking, prescription handling, and auditing. Developed by Mahamat, the system ensures data integrity through triggers, automates processes with PL/SQL objects, and schedules inventory checks. The project spans eight phases, from planning to presentation, addressing inefficiencies in manual pharmacy processes.

# Project Structure(Phases)


# Phase I: Project Proposal

Objective: Establish the foundation for the Pharmacy Management System by defining its scope, objectives, and deliverables.
Activities:
Outlined system goals: automate drug inventory, sales, prescriptions, and auditing.
Specified scope: Oracle 21c database with 8 tables, triggers, PL/SQL objects, scheduler.
Planned deliverables across 8 phases, with timeline (May–June 2025).
Identified tools: Oracle 21c, SQL*Plus, draw.io, GitHub.

# NB: THE DOCUMENT PPTX FOR THIS PARTICULAR PHASE IS UPLOADED ABOVE IN THE REPOSITORY

Description: This phase set the project’s direction, ensuring alignment with pharmacy management needs, such as data integrity and automation.

# Phase II: Requirements Analysis

Objective: Identifying functional and non-functional requirements to guide system development.
Activities:
Defined functional requirements:
Manage drug inventory (add, update, delete).
Record sales with patient details.
Handle prescriptions.
Restrict DML on weekdays/holidays.
Log DML actions for auditing.


Defined non-functional requirements:
Ensure data integrity with constraints.
Support concurrent access.
Maintain security via auditing.


Developed use cases:
Pharmacist: Add drug, record sale.
Manager: View audit logs, schedule checks.


# Screenshot Placeholder:
  # Class diagram 
  <img width="953" alt="CLASS DIAGRAM" src="https://github.com/user-attachments/assets/0766573f-0fa6-4dac-b2a5-438ccb198932" />

  # Use Case diagaram
  <img width="797" alt="USE CASE DIAGRAM" src="https://github.com/user-attachments/assets/abea62b8-39ea-4b9d-bd66-78ffa979eb83" />

Description: This phase ensured the system’s functionality and constraints were clearly defined, forming the basis for design and implementation.

# Phase III: Database and System Design

Objective: Designing the database schema and visualizing system structure and interactions using UML diagrams.
Activities:
Created database schema:
Tables: Supplier, Drug, Patient, Prescription, Employee, Sale, Holiday, AuditLog.
Columns: E.g., Drug (DrugID, Name, Quantity, Price, ExpiryDate, SupplierID).
Constraints: Primary keys, foreign keys, checks (e.g., Quantity >= 0).


Defined relationships:
Drug.SupplierID references Supplier.SupplierID.
Prescription.PatientID references Patient.PatientID.
Sale.DrugID references Drug.DrugID.


Developed UML diagrams using PlantUML in draw.io:
Class Diagram:
Visualizes 8 tables and their relationships.
Example: Drug table (DrugID: NUMBER PK, Name: VARCHAR2, etc.) linked to Supplier via SupplierID.
Purpose: Represents database structure, showing attributes and foreign key dependencies.
Screenshot: <img width="953" alt="CLASS DIAGRAM" src="https://github.com/user-attachments/assets/0766573f-0fa6-4dac-b2a5-438ccb198932" />


Use Case Diagram:
Shows actors (Pharmacist, Manager) and interactions (e.g., Add Drug, Record Sale, View Audit Logs).
Includes extensions: E.g., Restrict DML for DML actions, Log DML for auditing.
Purpose: Illustrates system functionality and user roles.
Screenshot: <img width="797" alt="USE CASE DIAGRAM" src="https://github.com/user-attachments/assets/abea62b8-39ea-4b9d-bd66-78ffa979eb83" />

Description: This phase established the database’s structure and visualized it through UML diagrams, ensuring a clear design for implementation.

# Phase IV: Initial PDB Creation

Objective: Implement core database to begin schema development.
Activities: 
Created a PDB named "thurs_25718_mahamat_PharmacyMS_DB" and user mahamat with password mahamat.

Screenshots:
<img width="959" alt="PDB CREATION" src="https://github.com/user-attachments/assets/f16f7782-6ef6-4a92-8aee-966d278bd0d2" />

Description: This phase laid the groundwork for the project.

# Phase V: Full Schema Implementation

Objective: Complete the database schema with all tables, constraints, sequences, and sample data.
Activities:
Implemented all 8 tables: Supplier, Drug, Patient, Prescription, Employee, Sale, Holiday, AuditLog.
Added constraints:
Primary keys: E.g., DrugID, SaleID.
Foreign keys: E.g., Drug.SupplierID → Supplier.SupplierID.
Checks: E.g., Drug.Quantity >= 0.


Created sequences: Drug_seq, Sale_seq, Patient_seq, etc.
Inserted sample data: E.g., drugs (Paracetamol, 100 units), patients, sales.

Screenshots:
-Sequence creation:
<img width="947" alt="SEQUENCE CREATION" src="https://github.com/user-attachments/assets/3eb01b1b-663e-4c23-8c6d-0f25efee794c" />
- Tables creation:
  <img width="959" alt="TABLES CREATION" src="https://github.com/user-attachments/assets/8fbc93df-9955-4a77-a921-3d9be6d06695" />
- Confirmation of the above queries:
  <img width="914" alt="confirmation sequences tables creation" src="https://github.com/user-attachments/assets/8edbb0c4-fc77-4dff-93aa-20202858faaa" />
- Data insertion:
  <img width="959" alt="DATA INSERTION" src="https://github.com/user-attachments/assets/50823528-0a44-40b9-a04c-266f389823b9" />

Description: This phase finalized the database structure, enabling data storage and manipulation, with outputs pending listener fix.

# Phase VI: PL/SQL Implementation

Objective: Add business logic and automation through PL/SQL objects and scheduling.
Activities:
Created PL/SQL package: InventoryPkg
Procedure RestockDrug: Updates drug quantity.
Procedure SellDrug: Records sale, reduces stock.

Created function: CheckStock
Returns current stock for a drug.

Set up scheduler:
Created INVENTORY_CHECK_WINDOW: Daily window for inventory checks.

Tested objects locally via SYS connection.

Screenshots:
-package creation:
<img width="959" alt="PACKAGES CREATION" src="https://github.com/user-attachments/assets/1b483917-5cec-4389-a59c-9ee78e4d10a2" />
- Functions:
<img width="959" alt="FUNCTIONS CREATION" src="https://github.com/user-attachments/assets/94084d5a-1759-4df8-ad3c-a81299e2bad4" />
- Procedures:
  <img width="959" alt="PROCEDURES CREATION" src="https://github.com/user-attachments/assets/02022068-b361-4055-8d1f-7d6b0f180f72" />
-Windows scheduler:
<img width="891" alt="WINDOWS FUNCTIONS" src="https://github.com/user-attachments/assets/c30adaf2-7eff-45ba-9b78-b30406b1cada" />
- DML and DDL Operations:
  <img width="959" alt="DML DDL Operations" src="https://github.com/user-attachments/assets/3a71b2e9-fc1e-4842-a55a-a3c98c656dd8" />

Description: This phase introduced automation and business logic, enhancing system functionality, with testing limited by listener issues.

# Phase VII: Triggers and Auditing

Objective: Implemented triggers to enforce data integrity and audit DML actions.
Activities:
Created RestrictDML trigger:
Blocks INSERT/UPDATE/DELETE on Drug table during weekdays or holidays.
Logs failed attempts to AuditLog.


Created AuditDML trigger:
Logs all DML actions (success/failure) to AuditLog.


Built AuditLog table:
Columns: AuditID, UserID, ActionDate, Operation, Status.


Created audit_seq sequence for AuditID.
Tested triggers locally, logging sample DML attempts.


Screenshots:
<img width="917" alt="TRIGGERS CREATION" src="https://github.com/user-attachments/assets/d371f8da-148d-40b5-a1ff-b2121d68973b" />

Description: This phase ensured data security and accountability, with triggers restricting and logging DML actions.

Phase VIII: Final Presentation

Objective: Summarize the project in a presentation, highlighting all phases.
Activities:
Developed a 10-slide PowerPoint:
Covers: Introduction, Problem Definition, Methodology (Phases I–VII), Results, Conclusion.
Includes UML diagrams and screenshot placeholders.

Link to the pptx: https://docs.google.com/presentation/d/1u_bF-AqsHPHCvXIVQG_gvdB8Ycu2tB9A/edit?usp=drive_link&ouid=101099769312899546410&rtpof=true&sd=true

Description: This phase consolidates the project’s achievements, preparing for final submission.

Setup Instructions

Install Oracle 21c Enterprise Edition.
Configure listener.ora with HOST=localhost or 192.168.43.44.
Run SQL scripts in order (Phases IV–VII) using SQL*Plus.
Generate UML diagrams in draw.io using PlantUML code.
Capture screenshots.
Use GitHub for version control.

License
MIT License. Copyright (c) 2025 Mahamat.
