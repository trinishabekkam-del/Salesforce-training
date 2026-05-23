
# Salesforce Summer Program — Day 9 Detailed Notes
# Lightning Web Components Communication & Data Flow

---

# Goal for Today

By the end of Day 9, the goal is to clearly understand:

- How Lightning Web Components communicate
- Data flow inside applications
- Event-driven UI behavior
- Parent-child communication
- Dynamic application architecture
- Reactive UI concepts
- Modern Salesforce frontend architecture
- Difference between modern and legacy UI frameworks

---

# 1. Lightning Web Components and Salesforce Data

## Introduction

Lightning Web Components (LWC) are not only used to build UI screens but also to interact with Salesforce data dynamically.

Modern enterprise applications require:
- Real-time data updates
- Dynamic UI rendering
- User interaction handling
- Efficient communication between components
- Data retrieval and storage

LWC supports all these features using modern web standards.

---

# 2. Connecting Components with Salesforce Data

LWC components connect with Salesforce data using:

- Wire Service
- Apex Methods
- Lightning Data Service (LDS)

---

## Why Data Integration is Important

Enterprise applications continuously interact with data.

Components must:
- Retrieve records
- Display information
- Update records
- Respond to user actions
- Show live updates

---

## Example

A Student Dashboard component can:
- Fetch student details
- Display attendance
- Show notifications
- Display enrolled courses
- Update information dynamically

---

# 3. Reactive UI

## What is Reactive UI?

Reactive UI means the user interface automatically updates whenever data changes.

The user does not need to manually refresh the page.

---

## Example

If attendance changes from:
75% → 80%

The UI automatically updates and displays the latest value.

---

## Benefits of Reactive UI

- Better user experience
- Faster interaction
- Real-time updates
- Dynamic applications
- Improved responsiveness

---

# 4. Data Retrieval in LWC

Data retrieval means fetching information from Salesforce.

Methods used:
- Wire Adapters
- Apex Calls
- Lightning Data Service

---

## Example

A Course Dashboard retrieves:
- Course names
- Faculty details
- Student enrollment data
- Course schedules

---

# 5. User Interaction in Applications

User interaction includes:
- Clicking buttons
- Filling forms
- Submitting records
- Viewing notifications
- Updating information

LWC handles user interactions using JavaScript events and reactive properties.

---

# 6. Communicate Between Lightning Web Components

## Why Components Communicate

Modern applications are built using multiple small components.

These components must communicate to:
- Share data
- Trigger actions
- Update UI
- Synchronize application state

---

## Examples

- Parent sends data to child
- Child sends events to parent
- Notification component updates dashboard
- Attendance component refreshes student information

---

# 7. Parent-Child Communication

## What is Parent-Child Communication?

A parent component can pass data to a child component using public properties.

Child components can communicate back using custom events.

---

# Parent to Child Communication

Parent components send:
- Values
- Properties
- Objects
- Record information

---

## Example

Dashboard Component → StudentCard Component

The Dashboard sends:
- Student name
- Roll number
- Attendance percentage

to the StudentCard component.

---

## Advantages

- Better organization
- Easier data management
- Clean architecture
- Reusable components

---

# Child to Parent Communication

Child components communicate with parent components using events.

---

## Example

Attendance Component:
- User updates attendance
- Child component fires an event
- Parent dashboard receives update
- UI refreshes automatically

---

## Benefits

- Dynamic communication
- Loose coupling
- Better modularity
- Real-time updates

---

# 8. Events in LWC

## What are Events?

Events are actions triggered by:
- User interaction
- System updates
- Component behavior

---

## Examples of Events

- Button click
- Form submit
- Data save
- Attendance update
- Notification trigger

---

# Event-Driven UI Behavior

Modern enterprise applications use event-driven architecture.

This means:
- Components react to actions
- UI changes dynamically
- Communication becomes efficient

---

## Example Flow

When user clicks "Save":

1. Button click event triggers
2. Validation starts
3. Data moves to Apex
4. Database updates
5. Notification displays
6. UI refreshes

---

# 9. Component Interaction

Component interaction allows multiple components to work together.

Benefits:
- Modularity
- Reusability
- Scalability
- Better architecture

---

## Example

Student Dashboard contains:
- Header Component
- Attendance Component
- Notification Component
- Course Component

All these components communicate together to create a complete application.

---

# 10. Visualforce Basics (Overview)

## What is Visualforce?

Visualforce is Salesforce’s older UI technology.

Before Aura and LWC, Salesforce applications used Visualforce pages.

---

## Characteristics of Visualforce

- Older architecture
- Server-side rendering
- Limited interactivity
- Less dynamic UI
- More page reloads

---

## Why Learn Visualforce?

Visualforce is still used in:
- Legacy Salesforce projects
- Older enterprise applications

Understanding Visualforce helps developers:
- Maintain old systems
- Understand Salesforce evolution

---

# 11. Aura Components Basics

## What is Aura?

Aura is Salesforce’s older component framework introduced before LWC.

Aura introduced:
- Component-based development
- Event communication
- Modular UI structure

---

# Why Aura Existed

Aura improved Salesforce UI by replacing many limitations of Visualforce.

Aura introduced reusable components and dynamic interaction.

---

# Why LWC Replaced Aura

Salesforce replaced Aura with LWC because LWC provides:

- Better performance
- Simpler development
- Modern JavaScript standards
- Faster rendering
- Better browser compatibility
- Improved security
- Lightweight framework

---

# 12. Aura vs LWC

| Aura | LWC |
|---|---|
| Older framework | Modern framework |
| Complex syntax | Simpler syntax |
| Slower rendering | Faster rendering |
| Heavy framework | Lightweight |
| Proprietary architecture | Uses web standards |
| Less optimized | Better performance |

---

# 13. Dashboard Architecture Task

# Student Dashboard

## Components

- Header Component
- Student Info Component
- Attendance Component
- Notifications Component
- Course List Component

---

## Communication Between Components

- Student Info shares student data
- Attendance component updates dashboard
- Notification component receives alerts
- Course list updates dynamically

---

# Faculty Dashboard

## Components

- Faculty Profile Component
- Attendance Update Component
- Student Management Component
- Course Allocation Component
- Notifications Component

---

## Communication

- Attendance updates student records
- Course allocation shares subject data
- Notifications update faculty information

---

# Admin Dashboard

## Components

- User Management Component
- Reports Component
- Analytics Component
- Security Component
- Notifications Component

---

## Communication

- Reports retrieve database data
- Security validates permissions
- Analytics displays charts and summaries
- Notifications display alerts

---

# 14. Data Flow Thinking

## Selected Process: Student Registration

---

# Complete Data Flow

# Step 1 — UI Layer

User enters:
- Student name
- Email
- Department
- Contact number

Frontend collects the information.

---

# Step 2 — Validation Layer

Frontend validates:
- Required fields
- Proper email format
- Empty inputs
- Duplicate values

---

# Step 3 — Flow Layer

Validated data moves from:
UI → Backend

---

# Step 4 — Apex Layer

Apex handles:
- Business logic
- Validation checks
- Database operations
- Duplicate prevention

---

# Step 5 — Database Layer

Salesforce database stores student information securely.

---

# Step 6 — Notification Layer

Application displays:
- Success notification
OR
- Error message

---

# 15. Modern vs Legacy Thinking

## Why Salesforce Moved from Visualforce/Aura to LWC

Salesforce moved toward LWC because:

- Faster UI rendering
- Better performance
- Modern JavaScript support
- Better scalability
- Improved developer experience
- Better maintainability
- Lightweight architecture
- Better security

---

# 16. Why Enterprise Applications Need Modular Architecture

Enterprise applications become very large and complex.

Without modular architecture:
- Code becomes difficult to manage
- Maintenance becomes harder
- Scalability becomes limited

---

## Benefits of Modular Architecture

- Reusable components
- Easier maintenance
- Faster development
- Better debugging
- Team collaboration
- Scalable systems

---

# 17. Problems in Tightly Coupled Systems

Tightly coupled systems create many problems:

- Difficult maintenance
- Hard debugging
- Reduced flexibility
- Poor scalability
- One change affects multiple modules

---

# 18. Importance of Frontend Architecture

Good frontend architecture provides:

- Better user experience
- Organized UI structure
- Faster interaction
- Easier scaling
- Cleaner development process

---

# 19. Why UI and Backend Should Remain Separate

Frontend handles:
- UI rendering
- User interaction
- Display logic

Backend handles:
- Business logic
- Database operations
- Security

---

## Benefits of Separation

- Better maintainability
- Improved security
- Easier scaling
- Cleaner architecture

---

# 20. Why Large Systems Need Reusable Modules

Reusable modules help enterprise systems by:

- Reducing duplicate code
- Improving consistency
- Speeding up development
- Simplifying maintenance
- Supporting scalability

---

# 21. End of Day Outcome

After completing Day 9, you should clearly understand:

- Component communication
- Parent-child interaction
- Event-driven UI architecture
- Reactive UI behavior
- Data flow in applications
- Dashboard architecture
- Aura vs LWC
- Visualforce basics
- Modular enterprise systems
- Importance of LWC in Salesforce
