
# Day 10 – Salesforce APIs, Integrations, and External Systems

## Introduction

Day 10 focused on understanding how Salesforce communicates with external systems using APIs and integrations.  
I learned how enterprise applications exchange data securely, how REST and SOAP APIs work, and why integrations are important in real-world business systems.

This session also helped me understand authentication, request-response architecture, connected apps, and external service communication in Salesforce.

---

# Topics Covered

- Introduction to APIs
- Salesforce Integrations
- REST API
- SOAP API
- HTTP Methods
- Request and Response
- JSON Basics
- Authentication
- OAuth
- Connected Apps
- Real-Time Integrations
- Third-Party System Communication
- API Testing Basics
- Enterprise Integration Architecture

---

# Key Learnings

- APIs help different applications communicate with each other.
- Salesforce provides multiple APIs for integration.
- REST API is lightweight and widely used.
- SOAP API is protocol-based and used in enterprise systems.
- JSON is commonly used for API communication.
- Authentication protects secure data exchange.
- OAuth is used for secure API authorization.
- Connected Apps enable external systems to access Salesforce securely.
- Integrations are important for enterprise automation.

---

# What is an API?

API stands for Application Programming Interface.

An API allows two systems to communicate and exchange information.

Using APIs, Salesforce can:
- Send data
- Receive data
- Connect external systems
- Automate communication
- Synchronize business operations

---

# Real-World Examples of APIs

## Payment Gateway Integration

When a student pays fees online:
- Payment app sends data to Salesforce
- Salesforce updates payment status
- Receipt gets generated automatically

---

## Student Portal Integration

Student portal can:
- Fetch attendance
- Display marks
- Show fee details
- Update profile information

using Salesforce APIs.

---

## SMS Notification System

External SMS systems can connect with Salesforce to:
- Send OTP messages
- Send fee reminders
- Send admission updates

---

# Types of Salesforce APIs

| API Type | Purpose |
|---|---|
| REST API | Lightweight web integration |
| SOAP API | Enterprise-level structured communication |
| Bulk API | Large-scale data operations |
| Streaming API | Real-time event communication |

---

# REST API

REST API is the most commonly used Salesforce API.

It works using:
- HTTP methods
- JSON data
- URLs/endpoints

REST APIs are:
- Lightweight
- Faster
- Easy to integrate

---

# HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create data |
| PUT | Update data |
| DELETE | Delete data |

---

# Example REST API Request

## Retrieve Student Records

```http
GET /services/data/v59.0/sobjects/Student__c
