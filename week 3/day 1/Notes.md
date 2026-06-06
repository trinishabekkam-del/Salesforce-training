
# Day 15 – Salesforce Security, Sharing, and Access Management

## Introduction

Day 15 focused on understanding Salesforce Security and Access Management concepts.  
In enterprise applications, security is one of the most important aspects because organizations handle sensitive customer, employee, financial, and business data.

During this session, I learned how Salesforce controls:
- User access
- Record visibility
- Object permissions
- Field-level security
- Data sharing
- Role hierarchy
- Profiles and Permission Sets

I also understood how Salesforce maintains secure and scalable enterprise applications using layered security architecture.

---

# Topics Covered

- Salesforce Security Model
- Organization-Wide Defaults (OWD)
- Profiles
- Roles and Role Hierarchy
- Permission Sets
- Field-Level Security
- Record-Level Security
- Sharing Rules
- Manual Sharing
- Login Access
- Enterprise Security Architecture
- Secure Business Workflow Design

---

# Key Learnings

- Salesforce follows a layered security model.
- Profiles control object permissions and user access.
- Roles control record visibility through hierarchy.
- Permission Sets provide additional permissions without changing profiles.
- OWD defines default access for records.
- Sharing Rules help extend record access automatically.
- Field-Level Security protects sensitive information.
- Enterprise systems require strong security architecture for data protection.

---

# What is Salesforce Security?

Salesforce Security is a system used to control:
- Who can access data
- What actions users can perform
- Which records users can view or edit
- Which fields users can access

Security helps organizations:
- Protect sensitive business data
- Maintain privacy
- Prevent unauthorized access
- Improve compliance
- Secure enterprise workflows

---

# Salesforce Security Layers

Salesforce security works in multiple layers:

| Security Layer | Purpose |
|---|---|
| Organization Level | Controls login and password policies |
| Object Level | Controls object permissions |
| Field Level | Controls field visibility |
| Record Level | Controls record access |

---

# Profiles

Profiles control what users can do inside Salesforce.

Profiles define:
- Object permissions
- Field permissions
- App access
- Tab visibility
- Login permissions

---

## Example

### Student Management User
Can:
- View Student records
- Edit attendance
- View reports

Cannot:
- Delete student records
- Access admin settings

---

# Roles and Role Hierarchy

Roles control record visibility in Salesforce.

Role Hierarchy allows higher-level users to access records owned by lower-level users.

---

## Example Hierarchy

```text
Principal
   ↓
HOD
   ↓
Faculty
```

### Explanation
- Principal can view all records
- HOD can view department records
- Faculty can view only assigned records

---

# Organization-Wide Defaults (OWD)

OWD defines the default access level for records.

---

## OWD Types

| OWD Type | Meaning |
|---|---|
| Private | Only owner can access |
| Public Read Only | Everyone can view |
| Public Read/Write | Everyone can edit |
| Controlled by Parent | Access depends on parent object |

---

## Example

### Student Records
OWD = Private

Meaning:
- Only the record owner can access the student record by default.

---

# Sharing Rules

Sharing Rules automatically provide record access to users.

They help extend access beyond role hierarchy.

---

## Example

### Department Sharing Rule
- IT Department faculty can access IT student records.

### Benefits
- Improves collaboration
- Maintains controlled access
- Supports enterprise workflows

---

# Manual Sharing

Manual Sharing allows record owners to share records individually.

---

## Example

A Faculty member manually shares a student record with another Faculty member for review purposes.

---

# Field-Level Security

Field-Level Security controls access to specific fields.

---

## Example

### Sensitive Fields
- Salary
- Scholarship Amount
- Personal Contact Number

Some users may:
- View the field
- Edit the field
- Not access the field at all

---

# Permission Sets

Permission Sets provide additional permissions without modifying profiles.

---

## Advantages
- Flexible access control
- Easier permission management
- Reduces profile complexity

---

## Example

### Event Coordinator Permission Set
Provides:
- Event Management access
- Report generation access
- Dashboard visibility

without changing the base profile.

---

# Record-Level Security

Record-Level Security controls which records users can access.

Implemented using:
- Role Hierarchy
- Sharing Rules
- Manual Sharing
- Teams

---

# Real-World Security Example

## College Management System

### Admin
Can:
- Manage all records
- Configure system settings
- Access reports

---

### Faculty
Can:
- View assigned students
- Update attendance
- Enter marks

Cannot:
- Delete fee records
- Access admin configuration

---

### Students
Can:
- View their own details
- View attendance
- View marks

Cannot:
- Edit official records
- Access other student records

---

# Secure Business Workflow

## Student Registration Workflow

### Step 1 – Student Registration
- Student submits registration form

### Step 2 – Validation
- System validates user permissions

### Step 3 – Record Creation
- Student record gets created securely

### Step 4 – Role-Based Access
- Faculty can access assigned records
- Admin can access all records

### Step 5 – Secure Reporting
- Reports are generated based on permissions

---

# Security Best Practices

- Follow least privilege principle
- Use profiles carefully
- Avoid unnecessary admin access
- Use permission sets for flexibility
- Protect sensitive fields
- Use strong password policies
- Enable secure login practices

---

# Why Security is Important in Enterprise Systems

Enterprise systems handle:
- Customer information
- Financial records
- Employee details
- Business transactions

Without security:
- Data leaks may occur
- Unauthorized access becomes possible
- Compliance issues may arise
- Business trust may reduce

Salesforce security helps organizations build secure and scalable enterprise applications.

---

# Reflection

This session helped me understand how Salesforce protects enterprise data using layered security architecture.

I learned:
- How users receive permissions
- How records are shared securely
- How organizations manage access control
- Why enterprise systems require proper security planning

I also understood that security is not only about restricting users but also about ensuring the right users get the correct access at the right time.

---

# Trailhead Modules Completed

- Data Security
- User Authentication
- Permission Sets
- Role Hierarchy Basics
- Sharing and Visibility

---

# Tools Used

- Salesforce Trailhead
- Salesforce Developer Edition
- VS Code
- GitHub
- Salesforce CLI

---

# Overall Understanding After Day 15

After completing Day 15, I understood:
- Salesforce Security Model
- Profiles and Permissions
- Role Hierarchy
- Sharing Rules
- Organization-Wide Defaults
- Field-Level Security
- Record-Level Security
- Secure enterprise workflow design
- Access management strategies
- Enterprise security architecture

This learning improved my understanding of how Salesforce organizations securely manage enterprise business operations while maintaining scalability, collaboration, and data protection.
