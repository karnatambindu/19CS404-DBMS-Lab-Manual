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

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![Screenshot 2025-04-29 085929](https://github.com/user-attachments/assets/ac677582-bc37-48f4-9f37-2429dff4775a)


## Entities and Attributes:
Student
First Name
Last Name
Name (composite attribute: First Name + Last Name)
Date of Birth
Age (derived attribute – dashed oval)
Address
Email
Phone
Login
Register Number
Email ID
Password
Courses
Course Name
Course Code
College
College Name
College Code
Staff
Faculty Name
Phone
Teacher ID
ERP
Department

## Relationships and Constraints:

HAS: STUDENT has LOGIN
Cardinality: One-to-One
Participation: Total for LOGIN, Partial for STUDENT
Explanation: Each student must have one login to access the system, but a student entity might exist without login details in some cases.
ENROLL: LOGIN enrolls in COURSES
Cardinality: Many-to-Many
Participation: Total for COURSES and Partial for LOGIN
Explanation: A login can be used to enroll in multiple courses, and a course can be taken by multiple users. However, not every login might be used to enroll.
ASSIGNED TO: COURSES are assigned to STAFF
Cardinality: Many-to-One
Participation: Total for COURSES, Partial for STAFF
Explanation: Every course must have an assigned staff member, but a staff member may or may not be teaching a course.
BELONGS TO: STUDENT belongs to COLLEGE
Cardinality: Many-to-One
Participation: Total for STUDENT, Partial for COLLEGE
Explanation: Every student is associated with one college, but a college can exist without having students (e.g., newly registered colleges).
HAS: COLLEGE has ERP
Cardinality: One-to-One
Participation: Total for ERP, Partial for COLLEGE
Explanation: Every ERP must be linked to one college, but not every college may have an ERP implemented yet.
BELONGS TO: COURSES belong to DEPARTMENT
Cardinality: Many-to-One
Participation: Total for COURSES, Partial for DEPARTMENT
Explanation: Each course must belong to one department, but a department may exist without courses initially.

## Extension (Prerequisite / Billing):
Prerequisite: Prerequisites are modeled through a reflexive relationship on the COURSE entity. The attribute
PREREQUISIT (which should likely be PREREQ_ID to reference another course's ID) in the COURSE entity indicates which course(s)
are required before taking a particular course. This structure allows for defining chains or multiple prerequisites for a single course.

## Design Choices:
This ER diagram provides a good foundation for a student registration system, capturing key entities and their relationships.
However, depending on the specific requirements, further refinement might be needed, especially in areas like billing and a clearer
definition of the 'TYPE' attribute in the REGISTRATION entity.
## RESULT
The Student-Course Management ER model was successfully designed with essential entities, relationships, and real-world extensions.
