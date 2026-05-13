# Salesforce Day 5 Notes

## Introduction

Today’s session was focused on Apex programming and understanding why coding is important in Salesforce development even though Salesforce already provides many no-code tools.

Until now, most of the learning was based on declarative tools like:
- Flows
- Validation Rules
- Reports
- Dashboards

But in real enterprise applications, some business requirements become too complex for configuration alone. That is where Apex programming becomes important.

This session helped me understand how Salesforce developers build advanced business logic and scalable applications using Apex.

---

# What is Apex?

Apex is Salesforce’s programming language used for implementing custom business logic and advanced automation.

Apex is similar to Java and is specially designed for Salesforce development.

Developers use Apex when:
- Flows are not enough
- Complex calculations are required
- External integrations are needed
- Advanced automation is required
- Large-scale business processing is involved

Apex helps developers create flexible and scalable enterprise applications.

---

# Why Apex is Needed

Salesforce provides many declarative tools such as:
- Flow Builder
- Validation Rules
- Reports
- Dashboards

These tools are useful for simple and medium-level automation.

However, enterprise applications often require:
- Complex calculations
- Dynamic business logic
- External API integrations
- Bulk data processing
- Advanced validations

These requirements cannot always be handled efficiently using only Flows.

That is why Apex programming is required.

---

# Declarative vs Programmatic Development

## Declarative Development

Declarative development means building applications using clicks instead of code.

### Examples
- Flows
- Validation Rules
- Reports
- Dashboards

### Advantages
- Faster implementation
- Easier maintenance
- No coding required

Declarative tools are best for simple and medium-level automation.

---

## Programmatic Development

Programmatic development means building applications using code.

### Examples
- Apex Classes
- Triggers
- API Integrations
- Custom business logic

### Advantages
- More flexibility
- Better scalability
- Handles advanced business requirements

Programming is used when declarative tools are not sufficient.

---

# Difference Between Flow and Apex

| Flow | Apex |
|---|---|
| No-code automation | Code-based development |
| Easier to build | Requires programming knowledge |
| Best for simple workflows | Best for advanced business logic |
| Limited flexibility | Highly flexible |
| Faster for small automation | Better for enterprise systems |

---

# Real Examples Where Apex is Needed

## 1. Complex Fee Calculation

In a college management system, fee calculation may depend on:
- Scholarship
- Hostel facility
- Transport facility
- Attendance
- Previous dues

Managing all these conditions becomes difficult using Flow.

Apex handles complex calculations more efficiently.

---

## 2. Payment Gateway Integration

If a college wants online payment integration using:
- Razorpay
- PhonePe
- Payment verification APIs

then Apex is required because integrations involve:
- API communication
- Authentication
- Response handling

Flows alone cannot fully handle these operations.

---

## 3. Advanced Eligibility Checking

Student eligibility may depend on:
- Attendance percentage
- Internal marks
- Pending fees
- Course prerequisites

This logic contains multiple conditions and validations.

Apex provides:
- Better flexibility
- Better control
- Better scalability

for handling such enterprise logic.

---

# Integrated College Management System

Today’s task connected all concepts learned from previous days into one system.

---

# CRM Workflow

Student Inquiry  
↓  
Admission Process  
↓  
Course Registration  
↓  
Fee Payment  
↓  
Student Management

This workflow helped me understand how CRM concepts work in real-world systems.

---

# Objects Used

| Object | Purpose |
|---|---|
| Student | Stores student information |
| Faculty | Stores faculty details |
| Course | Stores course information |
| Department | Stores department details |
| Fees | Stores payment information |

---

# Relationships

| Parent Object | Child Object |
|---|---|
| Department | Student |
| Department | Faculty |
| Faculty | Course |

Relationships help maintain structured and connected enterprise data.

---

# Validation Rules

Validation Rules prevent invalid data entry.

### Examples
- Email cannot be empty
- Age cannot be negative
- Filled seats cannot exceed total seats

### Advantages
- Improves data quality
- Reduces business errors
- Maintains consistency

---

# Formula Fields

Formula Fields automatically calculate values.

### Examples
- Full Name
- Percentage
- Remaining Seats

### Advantages
- Reduces manual calculations
- Improves accuracy
- Saves time

---

# Flows

Flows automate repetitive business processes.

### Examples
- Admission confirmation emails
- Fee reminder notifications
- Course registration automation

### Advantages
- Reduces manual work
- Improves efficiency
- Automates communication

---

# Apex Usage in the System

Apex is used when business logic becomes too advanced for Flow.

## Example Scenario

A student should be allowed to register for exams only if:
- Attendance is above 75%
- No pending fee exists
- Internal marks are above minimum requirement

Implementing this logic entirely using Flow becomes difficult.

Apex makes the logic:
- Easier to maintain
- More scalable
- More flexible

---

# Pseudocode Examples

## Example 1

```text
IF seats are full
THEN block registration
