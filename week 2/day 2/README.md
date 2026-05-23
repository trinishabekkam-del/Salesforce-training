# Day 9 — Lightning Web Components Communication

## Overview

This module focuses on:
- Component communication in Lightning Web Components
- Parent-child interaction
- Event-driven UI behavior
- Data flow inside enterprise applications
- Dashboard architecture
- Reactive UI concepts
- Aura vs LWC
- Visualforce basics
- Modular enterprise architecture

---

# Goal of Day 9

By the end of this module, the objective is to understand:
- How components communicate
- How data flows inside applications
- Event-driven architecture
- Parent-child communication
- Dynamic application design
- Modern Salesforce frontend architecture

---

# Lightning Web Components and Salesforce Data

Lightning Web Components interact with Salesforce data to build dynamic applications.

LWC supports:
- Data retrieval
- Reactive UI
- User interaction
- Dynamic rendering
- Real-time updates

Components connect with Salesforce using:
- Wire Service
- Apex Methods
- Lightning Data Service

---

# Reactive UI

Reactive UI automatically updates when data changes.

Example:
If attendance percentage changes, the UI refreshes automatically without manual reload.

Benefits:
- Better user experience
- Real-time updates
- Faster interaction
- Dynamic applications

---

# Component Communication

Modern enterprise applications contain multiple components that work together.

Components communicate to:
- Share data
- Trigger actions
- Update the UI
- Synchronize information

---

# Parent-Child Communication

## Parent to Child Communication

Parent components send:
- Properties
- Values
- Data objects

Example:
Dashboard component sends student information to StudentCard component.

---

## Child to Parent Communication

Child components communicate using events.

Example:
Attendance component sends update events to Dashboard component.

---

# Events in LWC

Events are triggered by:
- Button clicks
- Form submissions
- Data updates
- Notifications

Event-driven architecture allows components to react dynamically to user actions.

---

# Dashboard Architecture

## Student Dashboard

Components:
- Header Component
- Student Info Component
- Attendance Component
- Notifications Component
- Course List Component

---

## Faculty Dashboard

Components:
- Faculty Profile Component
- Student Management Component
- Attendance Update Component
- Course Allocation Component
- Notifications Component

---

## Admin Dashboard

Components:
- User Management Component
- Reports Component
- Analytics Component
- Security Component
- Notifications Component

---

# Data Flow Thinking

## Selected Process: Student Registration

### Complete Flow

1. User enters student information in UI
2. Frontend validation checks data
3. Data moves to backend
4. Apex processes business logic
5. Database stores records
6. Notification displays success or error message

---

# Visualforce Basics

Visualforce is Salesforce’s older UI framework.

Characteristics:
- Older architecture
- Server-side rendering
- Limited dynamic interaction
- Used in legacy systems

Visualforce provides historical understanding of Salesforce UI evolution.

---

# Aura Components Basics

Aura was Salesforce’s component framework before LWC.

Aura introduced:
- Component-based architecture
- Event communication
- Modular development

---

# Aura vs LWC

| Aura | LWC |
|---|---|
| Older framework | Modern framework |
| Complex syntax | Simpler syntax |
| Slower performance | Faster performance |
| Heavy framework | Lightweight |
| Proprietary architecture | Web standards |

---

# Why Salesforce Moved Toward LWC

Salesforce moved from Visualforce and Aura toward LWC because:
- Better performance
- Faster rendering
- Modern JavaScript support
- Better scalability
- Improved security
- Better developer experience
- Lightweight architecture

---

# Modular Enterprise Architecture

Enterprise applications use modular architecture because:
- Components become reusable
- Systems become scalable
- Maintenance becomes easier
- Development becomes faster
- Teams collaborate efficiently

---

# Problems in Tightly Coupled Systems

Tightly coupled systems create:
- Difficult maintenance
- Poor scalability
- Hard debugging
- Reduced flexibility

One module change can affect the entire system.

---

# Importance of Frontend Architecture

Good frontend architecture provides:
- Better user experience
- Organized UI
- Faster interaction
- Easier scalability
- Cleaner code structure

---

# Why UI and Backend Should Remain Separate

Frontend handles:
- UI rendering
- User interaction

Backend handles:
- Business logic
- Database operations
- Security

This separation improves:
- Maintainability
- Scalability
- Security

---

# End of Day Outcome

After completing this module, I understood:
- Component communication
- Parent-child interaction
- Reactive UI behavior
- Event-driven architecture
- Data flow inside applications
- Dashboard architecture
- Aura vs LWC
- Visualforce basics
- Modular enterprise system design
- Importance of LWC in Salesforce
