
# Salesforce Day 2 Notes

## Introduction to Salesforce Platform

Today I learned about the Salesforce Platform and how it works internally. Salesforce is a cloud-based CRM platform that helps companies manage customer data, sales activities, and business processes. Since it is cloud-based, users can access it from anywhere using the internet without installing software on their systems.

Salesforce is not only used for storing customer information but also for building applications, automating tasks, generating reports, and improving communication inside organizations.

---

# What is CRM?

CRM stands for Customer Relationship Management. It is used by companies to manage customer interactions and maintain customer information in an organized way.

Using CRM, companies can:
- Store customer details
- Track sales activities
- Maintain communication history
- Improve customer service
- Increase business productivity

Salesforce is one of the most popular CRM platforms used worldwide.

---

# CRM Concepts in Salesforce

Salesforce stores CRM information using objects.

Some important CRM concepts are:

### Account
An Account represents a company or organization.

Example:
Infosys, TCS, Wipro

### Contact
A Contact represents a person associated with an account.

Example:
HR Manager, Project Manager, Employee

### Opportunity
An Opportunity represents a possible business deal or sales process.

Example:
A company discussing a software project with a client.

These concepts work together to help companies track their business activities properly.

---

# What is an App in Salesforce?

An App in Salesforce is a collection of related features, tabs, and objects designed for a specific business purpose.

For example, a Sales App may contain:
- Accounts
- Contacts
- Opportunities
- Reports
- Dashboards

Apps help users organize their work efficiently and make navigation easier.

---

# What is an Object?

An Object in Salesforce is similar to a database table that stores information.

Objects contain:
- Fields
- Records

Salesforce provides two types of objects:

### Standard Objects
These are already provided by Salesforce.

Examples:
- Account
- Contact
- Opportunity
- Lead

### Custom Objects
These are created according to business requirements.

Examples:
- Student
- Faculty
- Attendance
- Course

Objects help businesses store and manage data in a structured format.

---

# What is a Tab?

A Tab is used to access objects and records easily from the Salesforce user interface.

Examples:
- Accounts Tab
- Contacts Tab
- Opportunities Tab

Tabs improve navigation and make it easier for users to work with data.

---

# Difference Between App and Object

An App is a collection of related tools and objects used for a specific business purpose, whereas an Object is used to store data records.

For example:
- Sales App is an App
- Account is an Object

Apps contain multiple objects inside them.

---

# Multi-Tenant Architecture

Salesforce follows multi-tenant architecture.

This means multiple organizations use the same Salesforce infrastructure and servers, but each organization's data remains secure and separate.

Advantages:
- Cost efficient
- Automatic updates
- Secure
- Easy maintenance

This architecture is one of the major reasons why Salesforce is scalable and widely used.

---

# Configuration in Salesforce

Configuration means creating functionality using Salesforce tools without writing code.

Examples:
- Validation Rules
- Flows
- Page Layouts
- Reports

Configuration is used when requirements are simple and can be implemented quickly using clicks instead of programming.

Advantages:
- Faster implementation
- Easy maintenance
- No coding required

---

# Coding in Salesforce

Coding is used when complex business requirements cannot be achieved using configuration tools.

Salesforce developers mainly use:
- Apex
- Lightning Web Components
- APIs

Examples:
- Payment gateway integration
- Complex automation
- Custom calculations

Coding provides more flexibility and customization options.

---

# Configuration vs Coding

Configuration is suitable for simple business requirements and faster implementation, while coding is used for advanced functionality and complex logic.

Configuration uses clicks, whereas coding uses programming.

---

# Salesforce Admin vs Developer

### Salesforce Admin
A Salesforce Admin mainly works with configuration tools like flows, reports, dashboards, users, and security settings.

### Salesforce Developer
A Salesforce Developer writes code using Apex and Lightning Web Components to build custom features and integrations.

Both roles are important in Salesforce projects.

---

# Real-Time System Example

## College Management System

### App Name
College Management App

### Objects
- Student
- Faculty
- Course
- Attendance
- Fees
- Examination

### User Interaction

#### Admin
Manages student records, fees, and reports.

#### Faculty
Updates attendance and marks.

#### Students
View attendance, marks, and course details.

This system helps in managing college activities efficiently using Salesforce.

---

# How Salesforce Developers Extend Functionality

Salesforce allows developers to extend platform functionality using:
- Apex Programming
- APIs
- Lightning Web Components
- Integrations

Developers can create custom applications and automate business processes according to company requirements.

---

# Conclusion

From Day 2 learning, I understood how Salesforce platform works internally and how CRM concepts are connected with Apps, Objects, and Tabs. I also learned the difference between configuration and coding, along with the roles of Salesforce Admin and Developer.

Salesforce provides both no-code and coding capabilities, making it powerful and flexible for different business needs.
