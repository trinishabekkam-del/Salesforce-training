# Day 10 – College Management Mini Project

## Introduction

Day 10 was the most important learning phase in the Salesforce Summer Training Program because all previously learned concepts were integrated into one connected mini project.

This project combined:
- CRM Concepts
- Data Modeling
- Validation Rules
- Formula Fields
- Flow Automation
- Apex Programming
- SOQL
- Apex Triggers
- Lightning Web Components (LWC)

The goal of this project was to understand how real enterprise applications are designed using frontend, backend, database, automation, and event-driven architecture together.

---

# Deep Learning Modules Completed

## 1. Build a Simple LWC Application

### Focus Areas
- Connecting UI with backend
- Real application structure
- Data flow
- User interaction

---

## 2. Lightning Web Components and Salesforce Data

### Focus Areas
- Data retrieval
- User interaction
- Reactive UI

---

# Light Completion Modules

- Visualforce Basics (Overview)
- Aura Components Basics (Overview)

---

# CORE MINI PROJECT (MANDATORY)

# College Management Mini Project

This project was designed using Salesforce concepts learned throughout the training.

The system manages:
- Students
- Faculty
- Courses
- Departments
- Attendance
- Registration
- Notifications

---

# CRM Concepts Used

| CRM Concept | Usage |
|---|---|
| Student | Customer-like entity |
| Faculty | Service provider |
| Course | Product/Service |
| Department | Organizational unit |

---

# Data Modeling

## Objects Used

### Standard Concepts
- Account-like structure
- Contact-like relationships

### Custom Objects
- Student__c
- Faculty__c
- Course__c
- Department__c
- Attendance__c
- Registration__c

---

# Relationships

| Parent Object | Child Object | Relationship |
|---|---|---|
| Department__c | Student__c | Lookup |
| Department__c | Faculty__c | Lookup |
| Faculty__c | Course__c | Lookup |
| Student__c | Registration__c | Lookup |

Relationships helped maintain connected and structured enterprise data.

---

# Fields Used

## Student Object Fields

| Field Name | Type |
|---|---|
| Name | Text |
| Email__c | Email |
| Attendance__c | Number |
| Fee_Status__c | Picklist |
| Department__c | Lookup |

---

# Validation Rules

## Question 1 – Email Mandatory Validation

### Purpose
Prevent saving student records without email.

### Validation Rule

```text
ISBLANK(Email__c)
```

### Error Message

```text
Email is mandatory.
```

---

## Question 2 – Seats Cannot Exceed Limit

### Purpose
Prevent over-registration.

### Validation Rule

```text
Filled_Seats__c > Total_Seats__c
```

### Error Message

```text
Seats cannot exceed total limit.
```

---

# Formula Fields

## Question 3 – Remaining Seats Formula

### Formula

```text
Total_Seats__c - Filled_Seats__c
```

### Purpose
Automatically calculate available seats.

---

## Question 4 – Attendance Percentage Formula

### Formula

```text
(Classes_Attended__c / Total_Classes__c) * 100
```

### Purpose
Automatically calculate attendance percentage.

---

# Flow Automation

## Question 5 – Auto Confirmation Email Flow

### Workflow
- Student registers
- Record gets created
- Confirmation email sent automatically

### Flow Type
Record-Triggered Flow

---

## Question 6 – Attendance Warning Flow

### Workflow
- Attendance falls below 75%
- Warning notification triggered automatically

### Flow Type
Scheduled Flow

---

# Apex Logic

## Question 7 – Eligibility Calculation

### Requirement
Student eligible only if:
- Attendance > 75%
- Fees cleared
- Marks above minimum requirement

---

## Apex Example

```apex
public class EligibilityChecker {

    public static Boolean checkEligibility(Student__c stu) {

        if(stu.Attendance__c >= 75 &&
           stu.Fee_Status__c == 'Paid' &&
           stu.Internal_Marks__c >= 40) {

            return true;

        }

        return false;

    }

}
```

---

# Question 8 – Bulk Operation Logic

### Purpose
Handle multiple records efficiently.

### Example

```apex
trigger StudentTrigger on Student__c (before insert) {

    for(Student__c stu : Trigger.new) {

        if(stu.Attendance__c < 0) {

            stu.addError('Attendance cannot be negative');

        }

    }

}
```

---

# SOQL Examples

## Retrieve All Students

```sql
SELECT Name FROM Student__c
```

---

## Students Below 75% Attendance

```sql
SELECT Name, Attendance__c
FROM Student__c
WHERE Attendance__c < 75
```

---

## Students With Pending Fees

```sql
SELECT Name
FROM Student__c
WHERE Fee_Status__c = 'Pending'
```

---

# LWC UI Design

## Question 9 – Student Dashboard

### Features
- View attendance
- View course details
- View fee status
- View notifications

---

## Question 10 – Faculty Dashboard

### Features
- Manage attendance
- Update marks
- View course registrations

---

## Question 11 – Registration Screen

### Features
- Student registration form
- Validation handling
- Course selection
- Confirmation message

---

# Basic LWC Structure

## HTML File

```html
<template>

    <lightning-card title="Student Dashboard">

        <p class="slds-p-around_medium">
            Welcome Student
        </p>

    </lightning-card>

</template>
```

---

## JavaScript File

```javascript
import { LightningElement } from 'lwc';

export default class StudentDashboard extends LightningElement {

}
```

---

## Meta XML File

```xml
<?xml version="1.0" encoding="UTF-8"?>

<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">

    <apiVersion>59.0</apiVersion>

    <isExposed>true</isExposed>

    <targets>

        <target>lightning__AppPage</target>

    </targets>

</LightningComponentBundle>
```

---

# Trigger/Event Thinking

## Question 12 – Notify Faculty When Course Full

### Event Flow
- Seats become full
- Trigger executes
- Faculty receives notification

---

## Question 13 – Low Attendance Alert

### Event Flow
- Attendance drops below limit
- Warning notification sent automatically

---

# SYSTEM THINKING TASKS

# Question 14 – Complete Data Flow

## End-to-End Workflow

```text
Student clicks Register
        ↓
LWC Registration Screen
        ↓
Validation Rules Execute
        ↓
Flow Automation Starts
        ↓
Apex Trigger Executes
        ↓
Database Updates
        ↓
Notification Sent
```

---

# Explanation of Complete Flow

1. Student interacts with LWC frontend.
2. Validation Rules verify input data.
3. Flow automates record creation.
4. Trigger handles backend business logic.
5. Salesforce database stores records.
6. Notifications are generated automatically.

This demonstrates how frontend, backend, automation, and database systems work together in enterprise applications.

---

# Question 15 – Architecture Thinking

## Why Enterprise Systems Need Multiple Layers

### Frontend
Used for user interaction.

### Backend
Handles business logic.

### Database
Stores enterprise data securely.

### Automation
Reduces repetitive manual work.

### Events
Enable real-time communication.

Enterprise systems need all these layers together for scalability and efficiency.

---

# Question 16 – Scaling Thinking

## Scenario
Suppose 50,000 students use the system.

---

## Problems That May Occur

### Performance Issues
Large data may slow down processing.

### Data Consistency Problems
Multiple users updating same records.

### Notification Delays
Large-scale notifications may fail.

### Security Risks
Unauthorized access attempts.

### Storage Problems
Massive records increase storage usage.

---

# Reflection Task

## Question 17 – What I Realized About Enterprise Systems

After learning Salesforce deeply, I realized that enterprise software systems are much more than simple applications.

Real systems require:
- Structured architecture
- Connected modules
- Automation
- Backend programming
- Scalable databases
- Event-driven communication
- Secure integrations
- Reusable UI components

I understood how Salesforce combines declarative tools and programmatic development to build scalable enterprise applications.

---

# Revision Questions

## 1. Why do enterprise systems need modular architecture?

Modular architecture improves maintainability, scalability, and reusability.

---

## 2. Why are relationships important?

Relationships help maintain connected and structured data.

---

## 3. Why are Flows insufficient for some cases?

Flows are limited for complex calculations and enterprise-level logic.

---

## 4. Why do systems need event-driven behavior?

Event-driven systems support real-time automation and communication.

---

## 5. Why is UI/backend separation important?

It improves scalability, maintainability, and clean architecture.

---

## 6. Why do enterprise systems require testing?

Testing ensures reliability, security, and bug prevention.

---

## 7. Why is reusable UI architecture powerful?

Reusable components reduce development time and improve consistency.

---

## 8. What problems happen when systems scale?

Performance, storage, security, and consistency issues occur.

---

## 9. Why should automation be designed carefully?

Poor automation may create errors and system conflicts.

---

## 10. How do all Salesforce concepts integrate together?

Salesforce combines:
- CRM
- Database
- Automation
- Apex
- SOQL
- Triggers
- APIs
- LWC

to build scalable enterprise applications.

---

# End of Day Understanding

After completing Day 10, I understood:
- Enterprise application architecture
- Frontend and backend integration
- Real-world data flow
- Salesforce LWC basics
- UI and backend communication
- Automation with Flows
- Apex business logic
- Trigger-based systems
- Event-driven architecture
- Modular application design
- Enterprise scalability concepts

This project helped me understand how real Salesforce enterprise systems are designed and integrated together.
