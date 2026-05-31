# Day 13 Notes – Salesforce Integration and REST APIs

## Introduction

Today’s session focused on understanding how Salesforce communicates with external systems using APIs and integrations. I learned about REST APIs, HTTP methods, JSON data, Apex Callouts, authentication, and real-time communication between enterprise applications.

This topic helped me understand how large-scale enterprise systems exchange data securely and automate external communication processes.

---

# Topics Covered

- API Basics
- Integration Basics
- REST API
- HTTP Methods
- JSON Format
- Salesforce REST API
- Request and Response
- Apex Callouts
- API Authentication
- External System Communication
- Web Services
- Real-Time Integrations
- Postman Basics
- Enterprise Integration Architecture

---

# What is an API?

API stands for Application Programming Interface.

An API acts like a bridge between two software applications and allows them to communicate with each other.

Using APIs, systems can:
- Send data
- Receive data
- Perform operations
- Trigger automation

---

# Real-World Example of API

When a student pays fees online:
1. Salesforce sends payment data to the payment gateway
2. Payment gateway processes the payment
3. Response is sent back to Salesforce
4. Payment status updates automatically

This communication happens using APIs.

---

# What is Integration?

Integration means connecting two or more systems so they can share information automatically.

### Examples
- Salesforce + Payment Gateway
- Salesforce + Email Service
- Salesforce + ERP System
- Salesforce + SMS Service

---

# What is REST API?

REST API is a web-based API architecture used for communication between systems over HTTP.

REST APIs are:
- Lightweight
- Fast
- Scalable
- Easy to use

REST APIs commonly use JSON format for communication.

---

# HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create new data |
| PUT | Update existing data |
| DELETE | Remove data |

---

# HTTP Method Examples

## GET Example

```http
GET /services/data/v59.0/sobjects/Student__c
```

Used to retrieve student records.

---

## POST Example

```http
POST /services/data/v59.0/sobjects/Student__c
```

Used to create a new student record.

---

# What is JSON?

JSON stands for JavaScript Object Notation.

It is a lightweight data format used to transfer information between systems.

JSON is:
- Easy to read
- Easy to write
- Widely supported

---

# JSON Example

```json
{
  "Name": "Priya",
  "Department": "IT",
  "Attendance": 85
}
```

---

# Salesforce REST API

Salesforce REST API allows external applications to interact with Salesforce data.

Using Salesforce REST API, systems can:
- Create records
- Retrieve records
- Update records
- Delete records

---

# What is an Apex Callout?

An Apex Callout is used to send HTTP requests from Salesforce to external systems.

Callouts allow Salesforce to:
- Connect with APIs
- Retrieve external data
- Send information to other systems

---

# Apex Callout Example

```apex
public class StudentService {

    public static void getStudentInfo() {

        Http http = new Http();

        HttpRequest request = new HttpRequest();

        request.setEndpoint('https://api.example.com/student');

        request.setMethod('GET');

        HttpResponse response = http.send(request);

        System.debug(response.getBody());

    }

}
```

---

# Explanation of Apex Callout Code

| Code | Purpose |
|---|---|
| Http http = new Http(); | Creates HTTP object |
| HttpRequest request | Creates request |
| setEndpoint() | Defines API URL |
| setMethod('GET') | Defines HTTP method |
| http.send() | Sends request |
| response.getBody() | Retrieves response |

---

# API Authentication

Authentication ensures that only authorized users or systems can access APIs.

### Authentication Methods
- OAuth
- API Keys
- Access Tokens

Authentication improves:
- Security
- Access control
- Data protection

---

# Request vs Response

| Request | Response |
|---|---|
| Sent by client | Returned by server |
| Contains operation | Contains result |
| Example: GET request | Example: JSON data |

---

# Web Services

Web Services allow systems to communicate over the internet.

### Types of Web Services
- REST
- SOAP

REST is commonly preferred because it is lightweight and faster.

---

# Real-Time Integration Examples

## Payment Integration
- Salesforce communicates with payment gateway
- Payment gets verified
- Fee status updates automatically

---

## SMS Notification System
- Attendance alerts
- OTP verification
- Fee reminders

---

## Email Automation
- Confirmation emails
- Welcome emails
- Automated notifications

---

# Enterprise Workflow Example

## Student Fee Payment Workflow

1. Student submits payment
2. Salesforce sends API request
3. Payment gateway processes payment
4. Response returns to Salesforce
5. Receipt gets generated
6. Student receives notification

This workflow helped me understand real-time enterprise integrations.

---

# Postman Basics

Postman is an API testing tool.

Developers use Postman to:
- Test APIs
- Send requests
- Check responses
- Debug integrations

---

# Importance of Integrations

Integrations help businesses:
- Reduce manual work
- Improve automation
- Share data between systems
- Improve user experience
- Build scalable enterprise applications

---

# Key Learnings

- APIs allow applications to communicate.
- REST APIs are widely used in enterprise systems.
- HTTP methods perform CRUD operations.
- JSON is commonly used for API communication.
- Salesforce supports integrations using REST APIs.
- Apex Callouts are used for external communication.
- Authentication improves API security.
- Real-time integrations improve business automation.
- Enterprise systems depend heavily on integrations.

---

# Reflection

Today’s learning helped me understand how Salesforce communicates with external applications in real-world enterprise environments.

Earlier, I only understood Salesforce as a CRM platform, but now I learned that enterprise systems continuously exchange information with external services like payment systems, email services, and mobile applications.

Understanding REST APIs, JSON, and Apex Callouts gave me practical knowledge about real-time communication and system integrations. This session also helped me understand the importance of APIs in modern cloud-based enterprise applications.

---

# Trailhead Modules Completed

- API Basics
- REST API Basics
- Integration Basics
- Apex Integration Services
- Postman API Fundamentals

---

# Tools Used

- Salesforce Trailhead
- Salesforce Developer Edition
- VS Code
- Postman
- GitHub

---

# Overall Understanding After Day 13

After completing Day 13, I understood:
- API fundamentals
- REST API architecture
- HTTP methods
- JSON communication
- Salesforce integrations
- Apex Callouts
- API authentication
- Real-time communication
- Enterprise integration systems
- External API communication
- API testing using Postman

This session helped me understand how enterprise applications interact with each other using APIs and integrations to automate real-world business operations efficiently.
