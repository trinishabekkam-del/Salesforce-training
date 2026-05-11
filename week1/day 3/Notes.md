# Salesforce Day 3 Notes

## Introduction

Today’s session was mainly focused on understanding how Salesforce stores and manages business data. I learned about objects, fields, records, relationships, formula fields, and validation rules. This day was important because it explained how real-world enterprise systems are designed using structured data instead of random spreadsheets.

---

# Objects, Fields, and Records

## Object
An Object in Salesforce is similar to a database table. It is used to store data related to a specific purpose.

Examples:
- Student
- Faculty
- Course
- Department

Objects help organize information properly inside the system.

---

## Field
A Field stores a specific piece of information inside an object.

Examples:
- Student Name
- Email
- Age
- Course Name

Fields are like columns in a table.

---

## Record
A Record is a single entry inside an object.

Example:

| Student Name | Age | Department |
|---|---|---|
| Priya | 19 | IT |

This complete row is considered one record.

---

# Standard Objects vs Custom Objects

## Standard Objects
These are already provided by Salesforce for CRM-related activities.

Examples:
- Account
- Contact
- Opportunity
- Lead

These objects are commonly used in sales and customer management.

---

## Custom Objects
Custom Objects are created according to business requirements.

Examples:
- Student
- Attendance
- Faculty
- Examination

Custom objects help businesses build systems based on their needs.

---

# App vs Object vs Tab

## App
An App is a collection of related objects, tabs, and features used for a specific business purpose.

Example:
College Management App

---

## Object
An Object stores data.

Example:
Student Object

---

## Tab
A Tab helps users access objects and records from the Salesforce interface.

Example:
Students Tab

Tabs improve navigation and make data access easier.

---

# Relationships in Salesforce

Relationships are used to connect objects with each other.

In real-world systems, data is always connected.

Examples:
- One department contains many students.
- One faculty teaches multiple courses.

Relationships help maintain structured and connected data.

---

# Lookup Relationship

Lookup Relationship is used when two objects are related but not completely dependent on each other.

Examples:
- Student → Department
- Course → Faculty

This relationship helps maintain flexibility inside the system.

---

# College Management System Design

Today I designed a simple College Management System using Salesforce concepts.

## Objects Used
- Student
- Faculty
- Course
- Department

---

## Relationships

### Department → Student
One department can contain multiple students.

### Department → Faculty
One department can contain multiple faculty members.

### Faculty → Course
One faculty member can teach multiple courses.

These relationships help organize data properly and avoid duplication.

---

# Formula Fields

Formula Fields are used to calculate values automatically without writing code.

They help reduce manual calculations and improve accuracy.

---

## Example 1 – Full Name
First Name + Last Name

This avoids manually entering full names repeatedly.

---

## Example 2 – Percentage
(Obtained Marks / Total Marks) × 100

The percentage gets updated automatically whenever marks change.

---

## Example 3 – Remaining Seats
Total Seats - Filled Seats

This helps show available seats automatically.

---

# Validation Rules

Validation Rules are used to prevent invalid data from entering the system.

They improve data quality and reduce errors.

---

## Example 1 – Email Cannot Be Empty
This prevents incomplete student records.

---

## Example 2 – Student Age Cannot Be Negative
This prevents incorrect age values.

---

## Example 3 – Filled Seats Cannot Exceed Total Seats
This prevents overbooking of courses.

---

# Why Structured Data is Important

Companies cannot depend only on Excel sheets because managing large amounts of data becomes difficult. As the number of records increases, spreadsheets become harder to maintain and errors increase.

Structured data helps companies:
- Organize information properly
- Maintain relationships between data
- Reduce duplication
- Improve reporting
- Support automation
- Allow multiple users to work together

Enterprise systems like Salesforce provide better security, scalability, and automation compared to spreadsheets.

---

# Formula Fields vs Validation Rules

## Formula Fields
Used for automatic calculations.

Examples:
- Percentage
- Remaining Seats

---

## Validation Rules
Used for restricting invalid data.

Examples:
- Empty Email restriction
- Invalid Age restriction

Formula fields calculate values, while validation rules prevent incorrect data.

---

# Key Learnings from Day 3

- Salesforce stores business data using objects and records.
- Fields store individual pieces of information.
- Relationships are important for connecting related data.
- Formula fields automate calculations.
- Validation rules improve data quality.
- Structured enterprise data is important for large organizations.
- Salesforce supports business logic without coding using declarative tools.

---

# Conclusion

From Day 3 learning, I understood how enterprise systems are designed using structured data and relationships. I also learned the importance of formula fields and validation rules in maintaining accurate and reliable business data.

This session improved my understanding of how Salesforce handles real-world business systems using objects, relationships, and automation features.
