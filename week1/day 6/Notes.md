# Day 6 Notes – SOQL and Apex Triggers

## SOQL

SOQL stands for Salesforce Object Query Language.

It is used to retrieve data from Salesforce objects. SOQL is similar to SQL, but it is specially designed for Salesforce applications and relationships.

Using SOQL, developers can:
- Retrieve records
- Filter data
- Access related objects
- Process business information

### Example Queries

```sql
SELECT Name FROM Student__c
```

```sql
SELECT Name, Attendance__c
FROM Student__c
WHERE Attendance__c < 75
```

```sql
SELECT Name
FROM Student__c
WHERE Fee_Status__c = 'Pending'
```

---

# Apex Triggers

An Apex Trigger is code that runs automatically when records are inserted, updated, or deleted.

Triggers help automate business processes and event-driven actions.

### Trigger Events
- Before Insert
- After Insert
- Before Update
- After Update
- Before Delete
- After Delete

---

# Before Trigger

Before Triggers run before records are saved into the database.

They are mainly used for:
- Validation
- Updating values before save
- Preventing incorrect data

### Example

```apex
trigger StudentBeforeTrigger on Student__c (before insert) {

    for(Student__c stu : Trigger.new) {

        if(stu.Age__c < 0) {

            stu.addError('Age cannot be negative');

        }

    }

}
```

This trigger prevents invalid age values.

---

# After Trigger

After Triggers run after records are saved.

They are mainly used for:
- Notifications
- Related record creation
- Automation processes

### Example

```apex
trigger StudentAfterTrigger on Student__c (after insert) {

    for(Student__c stu : Trigger.new) {

        System.debug('Welcome Email Sent');

    }

}
```

This trigger runs after a student record is created.

---

# Flow vs Trigger

| Flow | Trigger |
|---|---|
| No-code automation | Code-based automation |
| Easier to build | More powerful |
| Best for simple tasks | Best for advanced logic |
| Faster development | More flexibility |

---

# Before Trigger vs After Trigger

| Before Trigger | After Trigger |
|---|---|
| Runs before save | Runs after save |
| Used for validation | Used for automation |
| Modifies values before save | Used for notifications |

---

# Event-Driven Systems

Event-driven systems react automatically when events occur.

Examples:
- Sending notifications
- Updating records
- Triggering approvals
- Processing payments

These systems improve:
- Automation
- Productivity
- Real-time processing
- Efficiency

---

# Real-World Trigger Examples

### Student Registration
Automatically send welcome email after student registration.

### Attendance Warning
Notify students when attendance falls below 75%.

### Fee Payment
Update finance records automatically after payment.

### Scholarship Eligibility
Assign scholarships automatically based on marks.

### Course Capacity
Block registrations when seats are full.

---

# Reflection

Enterprise systems handle large amounts of data and users.

Event-driven automation helps systems react automatically without manual work.

Triggers and automation improve:
- Efficiency
- Scalability
- Accuracy
- Business productivity

---

# Key Learnings

- SOQL is used for querying Salesforce data.
- Triggers automate actions when data changes.
- Before Triggers are mainly used for validation.
- After Triggers are used for automation.
- Flows are suitable for simple automation.
- Triggers are suitable for advanced business logic.
- Event-driven systems improve enterprise applications.
