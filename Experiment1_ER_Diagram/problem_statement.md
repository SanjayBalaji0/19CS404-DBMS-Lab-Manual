# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).


## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

## Scenario Chosen:
Hospital

## ER Diagram:
![image](https://github.com/user-attachments/assets/236a7e45-21e2-434e-b8b3-f1aa9a1edae3)

## Entities and Attributes
### Doctor:
DoctorID (Primary Key)
Full Name
Phone
Work Schedule
Email
Specialization
Nurse

### Patient:
PatientID (Primary Key)
Full Name
DOB (Date of Birth)
Gender
Address
Phone
Email
Insurance

### Department:
DepartmentID (Primary Key)
DepartmentName
DepartmentHead

### Appointment:
AppointmentID (Primary Key)
Appointment Date
Time
Reason
Notes
PatientID (Foreign Key)
DoctorID (Foreign Key)

### Billing:
BillingID (Primary Key)
AppointmentID (Foreign Key)
Billing Date
Total Amount
Status
PatientID (Foreign Key)

### Payment:
PaymentID (Primary Key)
BillingID (Foreign Key)
Payment Date
Transaction Details
Payment Method

### Medical Record:
MedicalRecordID (Primary Key)
PatientID (Foreign Key)
AppointmentID (Foreign Key)
DoctorID (Foreign Key)
Treatments
Test Results
Diagnoses
Medications

## Relationships and Constraints
### Assigned to (Doctor - Department):
1 Department → M Doctors
(1:M cardinality)
Conducts (Doctor - Appointment):
1 Doctor → M Appointments
(1:M cardinality)

### Schedule (Patient - Appointment):
1 Patient → M Appointments
(1:M cardinality)

### Generates (Appointment - Billing):
1 Appointment → 1 Billing
(1:1 cardinality)

### Pays (Billing - Payment):
1 Billing → 1 Payment
(1:1 cardinality)

### Has Records (Patient - Medical Record):
1 Patient → M Medical Records
(1:M cardinality)

### Creates Record (Doctor - Medical Record):
1 Doctor → M Medical Records
(1:M cardinality)

### Documents (Appointment - Medical Record):
1 Appointment → 1 Medical Record
(1:1 cardinality)

## Design Choices
### Clear Department-Doctor Assignment:
Departments are distinct and relate to multiple doctors to allow specialization management.

### Appointment as a Connector:
Appointment links both doctor and patient, recording when and why they meet.

### Separate Billing and Payment Entities:
Billing is generated after appointments, and payment is linked separately, supporting more complex billing cycles.

### Independent Medical Records:
Medical records are attached to both patients and doctors but are independent of billing or payment processes.

### Email and Insurance Captured at Patient Level:
To ensure communication and insurance verification are handled directly.

## RESULT:

The ERD effectively models the hospital appointment system, clearly separating key aspects like scheduling, department assignment, and medical history tracking, ensuring scalability and ease of future extensions like billing and lab test integration.
