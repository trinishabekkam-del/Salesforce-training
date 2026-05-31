# Day 11 – Salesforce Security, Sharing, and Access Management

## Introduction

Day 11 focused on understanding Salesforce Security and Access Management concepts.  
In enterprise applications, protecting data is one of the most important responsibilities.  
Salesforce provides multiple security layers that help organizations control who can access records, objects, fields, and applications.

During this session, I learned how Salesforce handles:
- Organization-level security
- Object-level security
- Field-level security
- Record-level security
- Sharing settings
- Profiles and Roles
- Permission Sets
- Data visibility and access control

This learning helped me understand how enterprise companies secure sensitive business data while still allowing users to work efficiently.

---

# Topics Covered

- Salesforce Security Basics
- Organization-Wide Defaults (OWD)
- Profiles in Salesforce
- Roles and Role Hierarchy
- Permission Sets
- Object-Level Security
- Field-Level Security
- Record-Level Security
- Sharing Rules
- Manual Sharing
- Public Groups
- Data Access Management
- Enterprise Security Architecture

---

# Key Learnings

- Salesforce security works in multiple layers.
- Profiles control object and application permissions.
- Roles control record visibility through hierarchy.
- Permission Sets provide additional access without changing profiles.
- Sharing Rules help extend record access automatically.
- Organization-Wide Defaults define the baseline level of access.
- Enterprise systems require strong security models to protect sensitive information.

---

# What is Salesforce Security?

Salesforce Security is used to control:
- Who can log in
- What users can view
- What users can create
- What users can edit
- What users can delete

Security ensures that sensitive business information remains protected.

---

# Layers of Salesforce Security

## 1. Organization-Level Security
Controls:
- Login hours
- IP restrictions
- Password policies

### Example
A company allows employees to log in only during office hours.

---

## 2. Object-Level Security
Controls access to objects.

Permissions include:
- Create
- Read
- Edit
- Delete

### Example
A student user can view Course records but cannot delete them.

---

## 3. Field-Level Security
Controls visibility of specific fields.

### Example
Only finance staff can view the Scholarship Amount field.

---

## 4. Record-Level Security
Controls access to individual records.

### Example
Faculty members can view only their own student records.

---

# Organization-Wide Defaults (OWD)

OWD defines the default access level for records.

## Types of Access

| Access Type | Meaning |
|---|---|
| Private | Only owner can access |
| Public Read Only | Everyone can view |
| Public Read/Write | Everyone can view and edit |

---

## Example

Student records are set to Private:
- Students can view only their own records
- Faculty can view related records through sharing

---

# Profiles in Salesforce

Profiles define what users can do inside Salesforce.

Profiles control:
- Object permissions
- App access
- Tabs
- Field permissions
- Login access

---

## Example Profiles

| Profile | Responsibility |
|---|---|
| Admin | Full access |
| Faculty | Manage attendance and marks |
| Student | View personal details |
| Finance Staff | Manage fee information |

---

# Roles and Role Hierarchy

Roles help control record visibility.

Higher roles can access records owned by lower roles.

---

## Example Hierarchy

```text
Principal
   |
HOD
   |
Faculty
   |
Students
```

This structure helps organizations manage data access efficiently.

---

# Permission Sets

Permission Sets provide extra permissions without modifying profiles.

---

## Example

A faculty member may temporarily receive:
- Report export permission
- Additional object access

using a Permission Set.

---

# Sharing Rules

Sharing Rules automatically share records with users or groups.

---

## Example

All Finance Team members can access Fee records.

This can be configured using Sharing Rules.

---

# Manual Sharing

Manual Sharing allows record owners to share records manually.

---

## Example

A faculty member manually shares a student record with another faculty member.

---

# Public Groups

Public Groups help manage access for multiple users together.

---

## Example

Groups:
- Finance Team
- HR Team
- Faculty Members

Sharing rules can be applied to groups instead of individual users.

---

# Real-World College Management Security Model

## Admin
- Full system access
- Manage all records

---

## Faculty
- Manage attendance
- Update marks
- View assigned students

---

## Students
- View personal records
- View attendance and marks

---

## Finance Team
- Manage fee records
- Generate payment reports

---

# Example Security Scenario

## Requirement
Students should not view other students’ fee details.

## Solution
- OWD set to Private
- Role hierarchy configured
- Sharing rules applied only for Finance Team

This improves data privacy and security.

---

# Importance of Salesforce Security

Security is important because organizations handle:
- Student data
- Employee records
- Financial information
- Customer information
- Business reports

Without proper security:
- Data leakage may occur
- Unauthorized access becomes possible
- Business trust may be affected

---

# Reflection – Why Enterprise Systems Need Security

Enterprise applications manage large amounts of sensitive information.

Security helps organizations:
- Protect confidential data
- Maintain privacy
- Prevent unauthorized access
- Follow compliance standards
- Improve trust and reliability

Salesforce provides a flexible and scalable security architecture that helps businesses safely manage enterprise data.

---

# Trailhead Modules Completed

- Data Security
- User Access and Permissions Assistant
- Profiles and Permission Sets
- Record-Level Security

---

# Core Tasks Completed

## Core Task 1 – Understanding OWD
- Learned how Organization-Wide Defaults define baseline access.
- Configured Private access for records.

---

## Core Task 2 – Creating Profiles
- Created separate profiles for:
  - Admin
  - Faculty
  - Students
  - Finance Team

---

## Core Task 3 – Role Hierarchy Design
- Implemented role hierarchy for college management structure.

---

## Core Task 4 – Permission Set Usage
- Assigned extra permissions using Permission Sets.

---

## Core Task 5 – Sharing Rules Configuration
- Shared records automatically between teams.

---

# Sample Security Workflow

```text
Student Record Created
        ↓
OWD checks default access
        ↓
Role hierarchy determines visibility
        ↓
Sharing rules provide additional access
        ↓
Field-level security protects sensitive fields
```

---

# Tools Used

- Salesforce Trailhead
- Salesforce Developer Edition
- VS Code
- GitHub

---

# Overall Understanding After Day 11

After completing Day 11, I understood:
- Salesforce security architecture
- Organization-Wide Defaults
- Profiles and Roles
- Permission Sets
- Record-level security
- Sharing Rules
- Public Groups
- Enterprise data protection
- Access management concepts
- Real-world business security implementation

This session helped me understand how Salesforce protects enterprise data using layered security models and controlled access management.
