**# Experiment 1: Entity-Relationship (ER) Diagram

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

# ER Diagram Submission

NAME - HEMA LOKITHA P
REGISTER NUMBER - 212223110014

## Scenario Chosen:
University ER Diagram

## ER Diagram:

![ER_DIAGRAM](https://github.com/user-attachments/assets/0cb90708-269b-4af0-8fa2-f88eea3ac0ba)

## Entities and Attributes
STUDENT

Attributes: STUDENT_ID (PK), NAME, DOB, GENDER, EMAIL, PHONE (Multivalued), ADDRESS

 COURSE

Attributes: COURSE_ID (PK), COURSE_NAME, CREDITS, DEPARTMENT

INSTRUCTOR

Attributes: INSTRUCTOR_ID (PK), NAME, EMAIL, PHONE, DEPARTMENT

ENROLLMENT

Attributes: ENROLLMENT_ID (PK), STUDENT_ID (FK), COURSE_ID (FK), ENROLLDATE, GRADE

CLASSROOM

Attributes: CLASS_ID (PK), ROOM_NO, BUILDING, CAPACITY

SCHEDULE

Attributes: SCHEDULE_ID (PK), COURSE_ID (FK), CLASSROOM_ID (FK), INSTRUCTOR_ID (FK), TIME, DAY

DEPARTMENT

Attributes: DEPT_ID (PK), DEPT_NAME, HOD

## Relationships and Constraints
ENROLLMENT (between STUDENT and COURSE)

Cardinality: Many-to-Many

Participation: Total participation from ENROLLMENT to both STUDENT and COURSE

TEACHERS (between COURSE and INSTRUCTOR)

Cardinality: Many-to-One (Each Course can have multiple instructors; each Instructor can teach multiple courses)

Participation: Partial

BELONGS (between COURSE and DEPARTMENT)

Cardinality: Many-to-One

Participation: Total from COURSE to DEPARTMENT

SCHEDULE (associates COURSE, CLASSROOM, INSTRUCTOR)

Cardinality: Many-to-Many (A Course can have multiple schedules across days/classrooms/instructors)

Participation: Total from SCHEDULE to all three entities

## Extension: Prerequisite / Billing
This ER diagram does not explicitly model prerequisites or billing. If you want to model prerequisites:

Add a PREREQUISITE relationship:

Between COURSE (as both dependent and prerequisite)

With attributes like PREREQUISITE_TYPE if needed (e.g., hard/soft prereq)

For billing:

Add a new entity BILLING:

Attributes: BILL_ID, STUDENT_ID, AMOUNT, DUE_DATE, STATUS

Related to STUDENT (1:M)

## Design Choices
Multivalued Attribute (PHONE) in STUDENT is modeled with a double oval to denote multiple phone numbers.

Associative Entities (ENROLLMENT, SCHEDULE) capture the many-to-many relationships and carry extra attributes like GRADE, TIME, etc.

Composite Participation: COURSE is linked to multiple entities (INSTRUCTOR, DEPARTMENT, SCHEDULE) to ensure modularity.

Normalization: Attributes are properly distributed among entities to reduce redundancy and maintain atomicity.

DEPARTMENT handles course organization and instructor grouping to maintain academic structure.

## RESULT
The ER model captures students, instructors, courses, programs, and their relationships, including enrollments and prerequisites. It’s clear, efficient, and supports future database extensions.**
