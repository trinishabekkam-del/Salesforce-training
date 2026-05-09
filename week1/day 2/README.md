
# 🚀 Salesforce Day 2 – Platform Basics

---

# 1️⃣ What is Salesforce Platform?

Salesforce Platform is a cloud-based platform that helps businesses manage customer relationships, automate business processes, store data, and build custom applications. It provides tools for sales, service, marketing, analytics, and application development.

Salesforce works completely on the cloud, so users can access it from anywhere using the internet. It follows a multi-tenant architecture, where multiple organizations share the same infrastructure securely.

The platform provides both:
- Configuration tools (clicks without coding)
- Development tools (coding using Apex, APIs, Lightning Components)

This allows both administrators and developers to build business solutions efficiently.

---

# 2️⃣ CORE TASK 1: Connect Day 1 + Day 2

# How CRM Concepts Fit into Salesforce Platform

CRM concepts like Account, Contact, and Opportunity are represented as Objects in Salesforce. These objects are organized inside Apps to help businesses manage customer data and sales processes effectively.

For example:

- Account Object stores company or customer organization details.
- Contact Object stores information about people associated with the company.
- Opportunity Object stores potential business deals or sales information.

These objects work together inside apps like the Sales App. Salesforce provides tabs and user interfaces to interact with these objects easily.

Example Flow:

Lead → Contact → Opportunity → Customer

Explanation:
1. A Lead represents a potential customer.
2. After qualification, the lead becomes a Contact linked with an Account.
3. A business deal is tracked as an Opportunity.
4. Once the deal is successful, the customer relationship continues in Salesforce.

This structure helps companies track customer communication, sales activities, and business growth efficiently.

---

# 3️⃣ CORE TASK 2: Platform Understanding

## 🔹 What is an App in Salesforce?

An App in Salesforce is a collection of related tabs, objects, and functionalities designed for a specific business purpose.

Apps help users organize their work efficiently by grouping all necessary tools in one place.

Examples:
- Sales App
- Service App
- Marketing App

A Sales App may contain:
- Accounts
- Contacts
- Opportunities
- Reports
- Dashboards

Purpose of Apps:
- Simplifies navigation
- Improves productivity
- Organizes business operations

---

## 🔹 What is an Object in Salesforce?

An Object in Salesforce is a database table used to store information.

Objects contain:
- Fields (columns)
- Records (rows)

Salesforce provides:
1. Standard Objects
2. Custom Objects

### Standard Objects
Pre-built objects provided by Salesforce.

Examples:
- Account
- Contact
- Opportunity
- Lead

### Custom Objects
Objects created by users according to business needs.

Examples:
- Student
- Hospital Patient
- Library Book

Objects help businesses store and manage data efficiently.

---

## 🔹 What is a Tab in Salesforce?

A Tab is a user interface element that allows users to access objects, records, dashboards, reports, and applications easily.

Tabs appear on the navigation bar in Salesforce.

Examples:
- Accounts Tab
- Contacts Tab
- Opportunities Tab

Purpose of Tabs:
- Easy navigation
- Quick access to records
- Better user experience

Without tabs, users would find it difficult to access data quickly.

---

# 4️⃣ Difference Between App and Object

| Feature | App | Object |
|---|---|---|
| Definition | Collection of related tools and objects | Database table used to store data |
| Purpose | Organizes business processes | Stores records and information |
| Contains | Tabs, Objects, Dashboards | Fields and Records |
| Example | Sales App | Account Object |

---

# 5️⃣ What is Multi-Tenant Architecture?

Multi-tenant architecture means multiple organizations share the same Salesforce infrastructure and servers securely.

In Salesforce:
- One platform serves many customers.
- Data remains secure and isolated.
- All users receive updates automatically.

Advantages:
- Cost efficient
- Automatic updates
- Scalable
- Secure

This is one of the major reasons why Salesforce is cloud-based and highly popular.

---

# 6️⃣ CORE TASK 3: Configuration vs Coding

## 🔹 What is Configuration?

Configuration means building functionality in Salesforce using clicks instead of code.

Salesforce provides many built-in tools for configuration.

Examples:
- Validation Rules
- Flows
- Process Builder
- Page Layouts
- Reports and Dashboards

### When to Use Configuration?
Use configuration when:
- Requirements are simple
- No complex logic is needed
- Faster development is required
- Maintenance should be easy

### Examples of Configuration

#### Example 1: Validation Rule
Prevent users from saving a record if a phone number is empty.

#### Example 2: Flow Automation
Automatically send an email when a new student record is created.

Benefits:
- Faster implementation
- No coding knowledge needed
- Easy maintenance

---

## 🔹 What is Coding in Salesforce?

Coding is used when advanced or complex business logic cannot be achieved using configuration tools.

Salesforce developers use:
- Apex
- Lightning Web Components (LWC)
- Visualforce
- APIs

### When to Use Coding?
Use coding when:
- Complex business logic is needed
- Custom integrations are required
- Advanced automation is needed
- Real-time processing is required

### Examples of Coding

#### Example 1: Apex Trigger
Automatically calculate scholarship eligibility for students based on marks.

#### Example 2: Payment Gateway Integration
Integrate Salesforce with external payment systems.

Benefits:
- Highly customizable
- Supports advanced logic
- Enables external integrations

---

# 7️⃣ CORE TASK 4: Real System Thinking

# College Management System using Salesforce

## 🔹 App Name
College Management App

---

## 🔹 Objects Inside the App

### Standard Objects
- Account
- Contact

### Custom Objects
- Student
- Faculty
- Course
- Attendance
- Fees
- Examination

---

## 🔹 How Users Interact With the System

### Admin
- Manage student records
- Manage fees
- Generate reports

### Faculty
- Update attendance
- Upload marks
- Manage courses

### Students
- View attendance
- Check marks
- View course details

The app helps automate college management processes and improves efficiency.

---

# 8️⃣ How Salesforce Developers Extend Functionality

Salesforce allows developers to extend platform functionality using:

- Apex Programming Language
- Lightning Web Components
- APIs
- Integrations
- Custom Objects
- Automation Tools

Developers can build:
- Custom business applications
- Integrations with external systems
- Automated workflows
- Dynamic user interfaces

This makes Salesforce highly flexible and scalable.

---

# 9️⃣ Trailhead Screenshots

## Add screenshots here:
- Trailhead Profile
- Completed Badges
- Completed Modules
- Points and Trails

---

# ✅ Conclusion

Through Day 2 learning, I understood:
- Salesforce platform architecture
- Apps, Objects, and Tabs
- CRM concepts in Salesforce
- Difference between configuration and coding
- How Salesforce developers build business solutions

Salesforce provides both no-code and coding capabilities, making it powerful for businesses and developers.
