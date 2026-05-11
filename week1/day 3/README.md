#  Salesforce Day 3 – Data Modeling and Business Logic

---

# What I Learned Today

Today I learned how Salesforce stores and manages business data using objects, fields, records, and relationships. I also understood how enterprise applications are structured and why proper data modeling is important in real-world systems.

I learned:
- Difference between Objects, Fields, and Records
- Standard vs Custom Objects
- Relationships in Salesforce
- Formula Fields
- Validation Rules
- Structured enterprise data management

---

# 1️ Difference Between App, Object, Record, and Field

| Concept | Explanation | Example |
|---|---|---|
| App | Collection of related tools, tabs, and objects used for a business purpose | College Management App |
| Object | Database table used to store data | Student Object |
| Field | Individual piece of information inside an object | Student Name |
| Record | Single row of data stored in an object | Priya, Age 20 |

---

#  What is an App?

An App in Salesforce is a collection of related objects, tabs, reports, dashboards, and features designed for a specific business purpose.

Example:
A College Management App may contain:
- Students
- Faculty
- Courses
- Attendance
- Fees

Apps help users organize their work efficiently.

---

#  What is an Object?

An Object is a database table used to store information.

Objects contain:
- Fields
- Records

Examples:
- Student
- Faculty
- Course

Salesforce provides:
1. Standard Objects
2. Custom Objects

---

#  Standard vs Custom Objects

## Standard Objects

Standard Objects are already provided by Salesforce.

Examples:
- Account
- Contact
- Opportunity
- Lead

These objects are commonly used in CRM processes.

---

## Custom Objects

Custom Objects are created according to business requirements.

Examples:
- Student
- Department
- Attendance
- Examination

Custom objects help businesses build systems according to their needs.

---

# 2️ College Management System – Data Model Design

To understand data modeling better, I designed a simple College Management System using Salesforce concepts.

---

# 🎓 Objects Used

## Student
Stores student information.

### Fields
- Student Name
- Roll Number
- Email
- Age
- Percentage

---

## Faculty
Stores faculty details.

### Fields
- Faculty Name
- Employee ID
- Department
- Experience

---

## Course
Stores course information.

### Fields
- Course Name
- Course Code
- Total Seats
- Filled Seats

---

## Department
Stores department details.

### Fields
- Department Name
- HOD Name
- Department Code

---

# 🔗 Relationships Between Objects

Relationships are very important in enterprise systems because they connect related data.

---

#  Department → Student

One Department can contain many Students.

Example:
CSE Department → Multiple Students

### Relationship Type:
Lookup Relationship

### Why?
A student belongs to a department, but student records can still exist even if department details change.

---

#  Department → Faculty

One Department can have many Faculty members.

### Relationship Type:
Lookup Relationship

### Why?
Faculty members are associated with departments.

---

#  Faculty → Course

One Faculty can teach multiple Courses.

### Relationship Type:
Lookup Relationship

### Why?
Courses need to store which faculty teaches them.

---

#  One-to-Many Relationships

| Parent Object | Child Object |
|---|---|
| Department | Student |
| Department | Faculty |
| Faculty | Course |

These relationships help organize data properly and avoid duplication.

---

#  Data Model Diagram

```text
Department
   ↓
Student

Department
   ↓
Faculty

Faculty
   ↓
Course
```

This structure helps maintain proper relationships between data and improves system organization.

---

# 3️ Formula Fields

Formula Fields are used to calculate values automatically without writing code.

They reduce manual work and improve accuracy.

---

# 📌 Formula Field 1 – Full Name

## Formula
First Name + Last Name

### Example
Priya + Battula = Priya Battula

### Why should this be automatic?
Automatically generating full names saves time and avoids manual typing mistakes.

---

#  Formula Field 2 – Percentage

## Formula
(Obtained Marks / Total Marks) * 100

### Example
450 / 500 × 100 = 90%

### Why should this be automatic?
Whenever marks are updated, the percentage gets recalculated automatically without manual calculations.

---

#  Formula Field 3 – Remaining Seats

## Formula
Total Seats - Filled Seats

### Example
60 - 45 = 15 Seats Remaining

### Why should this be automatic?
This helps students and admins view live seat availability instantly.

---

#  Advantages of Formula Fields

- Reduces manual calculations
- Improves accuracy
- Saves time
- Automatically updates values
- Improves business efficiency

---

# 4️ Validation Rules

Validation Rules help prevent invalid or incorrect data from entering the system.

They improve data quality and consistency.

---

#  Validation Rule 1 – Email Cannot Be Empty

## Rule
Student Email field should not be blank.

### Problem Prevented
Prevents incomplete student records and communication issues.

---

#  Validation Rule 2 – Student Age Cannot Be Negative

## Rule
Age must always be greater than zero.

### Problem Prevented
Stops invalid age entries and incorrect student data.

---

#  Validation Rule 3 – Course Seats Cannot Exceed Limit

## Rule
Filled Seats should never exceed Total Seats.

### Problem Prevented
Prevents overbooking of courses and incorrect seat allocation.

---

#  Advantages of Validation Rules

- Improves data quality
- Prevents incorrect records
- Reduces business errors
- Maintains consistency
- Improves reporting accuracy

---

# 5️ Reflection – Why Structured Enterprise Data Matters

Companies cannot manage large-scale business operations using random spreadsheets because spreadsheets become difficult to maintain when data grows large.

Structured enterprise data is important because:
- Data remains organized
- Relationships between data can be maintained
- Reporting becomes easier
- Automation becomes possible
- Multiple users can work simultaneously
- Errors and duplication are reduced
- Business processes become scalable

Enterprise platforms like Salesforce provide structured data management, security, automation, and better collaboration compared to spreadsheets.

---

# 6️ Reflective Questions

## Why can’t companies manage everything using Excel sheets?

Excel sheets become difficult to manage when data becomes very large and multiple users work at the same time. Relationships between data are also hard to maintain in spreadsheets.

---

## Why are relationships important between objects?

Relationships connect related data and help businesses organize information properly.

---

## What problems happen if data is inconsistent?

Inconsistent data can cause:
- Duplicate records
- Incorrect reports
- Business errors
- Poor decision making

---

## Why should repetitive calculations be automated?

Automation saves time, improves accuracy, and reduces manual work.

---

## Why should invalid data be blocked early?

Blocking invalid data improves data quality and prevents future business problems.

---

## Why is Salesforce called a metadata-driven platform?

Salesforce is called a metadata-driven platform because applications are built using metadata like objects, fields, relationships, and configurations instead of hardcoding everything.

---

#  Trailhead Modules Completed

- Data Modeling
- Formulas and Validations

---

#  Conclusion

From Day 3 learning, I understood how Salesforce stores business data using objects, fields, records, and relationships. I also learned how Formula Fields and Validation Rules help automate business logic without coding.

This day helped me understand the importance of structured enterprise systems and proper data modeling in real-world business applications.
