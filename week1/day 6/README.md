# Day 6 – SOQL, Apex Triggers, and Event-Driven Systems

## Introduction

As part of Day 6 Salesforce training, I learned how Salesforce handles data retrieval, automation, and event-driven processing using SOQL and Apex Triggers.

This session helped me understand how enterprise systems automatically react to business events and process large amounts of data efficiently.

I also learned the difference between declarative automation and programmatic automation, along with real-world use cases where Apex Triggers are required.

---

## Topics Covered
- Introduction to SOQL
- Salesforce Database Querying
- Apex Triggers
- Trigger Events
- Before vs After Triggers
- Flow vs Trigger
- Event-Driven Systems
- Enterprise Automation
- Business Logic Automation

---

# CORE TASKS

## 1. What is SOQL?

SOQL stands for Salesforce Object Query Language.

It is used to retrieve records from Salesforce objects. SOQL is specially designed for Salesforce applications and relationships.

Developers use SOQL to:
- Retrieve records
- Filter data
- Access related objects
- Process business information

---

## 2. Write Example SOQL Queries

### Find all students

```sql
SELECT Name FROM Student__c
```

### Find students with attendance below 75%

```sql
SELECT Name, Attendance__c
FROM Student__c
WHERE Attendance__c < 75
```

### Find students with pending fees

```sql
SELECT Name
FROM Student__c
WHERE Fee_Status__c = 'Pending'
```

### Find courses with available seats

```sql
SELECT Name
FROM Course__c
WHERE Available_Seats__c > 0
```

---

## 3. What is an Apex Trigger?

An Apex Trigger is code that runs automatically when records are inserted, updated, or deleted in Salesforce.

Triggers help systems react automatically to business events.

---

## 4. Explain Trigger Events

| Trigger Event | Description |
|---|---|
| Before Insert | Runs before saving records |
| After Insert | Runs after records are saved |
| Before Update | Runs before updating records |
| After Update | Runs after updating records |
| Before Delete | Runs before deleting records |
| After Delete | Runs after deleting records |

---

## 5. Write a Before Trigger Example

```apex
trigger StudentBeforeTrigger on Student__c (before insert) {

    for(Student__c stu : Trigger.new) {

        if(stu.Age__c < 0) {

            stu.addError('Age cannot be negative');

        }

    }

}
```

### Explanation

This trigger validates student age before saving the record.

---

## 6. Write an After Trigger Example

```apex
trigger StudentAfterTrigger on Student__c (after insert) {

    for(Student__c stu : Trigger.new) {

        System.debug('Welcome Email Sent To: ' + stu.Name);

    }

}
```

### Explanation

This trigger runs automatically after a student record is created.

---

## 7. Difference Between Before Trigger and After Trigger

| Before Trigger | After Trigger |
|---|---|
| Runs before saving | Runs after saving |
| Used for validation | Used for automation |
| Can modify values before save | Used for notifications |

---

## 8. Difference Between Flow and Trigger

| Flow | Trigger |
|---|---|
| No-code automation | Code-based automation |
| Easier to build | More flexible |
| Best for simple automation | Best for advanced logic |

---

## 9. Real-World Trigger Use Cases

### Student Registration
Automatically send welcome email after student registration.

### Attendance Warning
Notify students when attendance falls below 75%.

### Fee Pending Alert
Restrict hall ticket generation if fees are unpaid.

### Scholarship Eligibility
Automatically assign scholarship eligibility.

### Course Capacity
Block registrations when seats become full.

---

## 10. What are Event-Driven Systems?

Event-driven systems automatically react when events occur.

Examples:
- Sending notifications
- Updating records
- Triggering approvals
- Processing transactions

This improves automation and efficiency.

---

## 11. Query Thinking

```text
Find all students enrolled in Course A
Find all students with pending fees
Find all students with attendance below 75%
Find all courses handled by Faculty X
Find courses with available seats
```

---

## 12. Why Do Enterprise Systems Need Event-Driven Behavior?

Enterprise systems handle large amounts of data and users.

Event-driven systems help applications:
- React instantly
- Reduce manual work
- Improve automation
- Improve scalability
- Support real-time processing

---

## Key Learnings
- SOQL is used for querying Salesforce data.
- Apex Triggers automate actions when data changes.
- Before Triggers are mainly used for validation.
- After Triggers are used for automation.
- Flows are useful for simple automation.
- Triggers are useful for advanced business logic.
- Event-driven systems improve enterprise automation.

---

## Conclusion

From Day 6 learning, I understood how Salesforce retrieves data using SOQL and how Apex Triggers help systems react automatically to business events.

I also learned how enterprise applications use event-driven automation to improve efficiency, scalability, and productivity.
