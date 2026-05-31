# Day 13 – Salesforce Integration, REST APIs, and External Communication

## Introduction

This README contains my learning progress, hands-on practice, notes, core tasks, and implementation work completed as part of Day 13 of the Salesforce Summer Training Program.

Today’s learning focused on Salesforce Integrations, REST APIs, HTTP methods, API communication, JSON handling, and connecting Salesforce with external systems. I understood how enterprise applications exchange data securely and how APIs help different systems communicate with each other in real time.

---

# Topics Covered

- Introduction to APIs
- What is Integration
- REST API Basics
- HTTP Methods
- Request and Response
- JSON Data Format
- Salesforce REST API
- API Authentication
- Apex Callouts
- External System Communication
- Real-Time Integrations
- Web Services
- Postman Basics
- Integration Architecture
- Enterprise Communication Systems

---

# Key Learnings

- APIs help different applications communicate with each other.
- REST API is widely used for web-based communication.
- HTTP methods define operations like create, read, update, and delete.
- JSON is commonly used for transferring data between systems.
- Salesforce supports integration using REST APIs and Apex Callouts.
- Enterprise systems use integrations for payments, notifications, and external services.
- Real-time communication improves automation and user experience.

---

# Core Tasks

## Question 1 – What is an API?

An API (Application Programming Interface) is a communication bridge between two software applications.

APIs allow systems to:
- Share data
- Send requests
- Receive responses
- Perform operations remotely

### Real-World Example

When a student makes an online payment:
- Salesforce sends payment details to the payment gateway
- Payment gateway processes the transaction
- Response is sent back to Salesforce
- Payment status gets updated automatically

This entire communication happens using APIs.

---

## Question 2 – What is REST API?

REST API (Representational State Transfer API) is a web-based API architecture used for communication between systems over HTTP.

REST APIs are:
- Lightweight
- Fast
- Scalable
- Easy to use

REST APIs use:
- URLs
- HTTP Methods
- JSON data

---

# HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create new data |
| PUT | Update data |
| DELETE | Remove data |

---

# Example REST API Request

## GET Request

```http
GET /services/data/v59.0/sobjects/Account
```

This retrieves Account records from Salesforce.

---

## POST Request

```http
POST /services/data/v59.0/sobjects/Student__c
```

This creates a new Student record.

---

# Question 3 – What is JSON?

JSON (JavaScript Object Notation) is a lightweight data format used for API communication.

JSON is:
- Human-readable
- Easy to transfer
- Supported by most systems

---

# JSON Example

```json
{
  "Name": "Priya",
  "Department": "IT",
  "Attendance": 82
}
```

This data can be transferred between Salesforce and external systems.

---

# Question 4 – What is Salesforce REST API?

Salesforce REST API allows external applications to:
- Access Salesforce data
- Create records
- Update records
- Delete records
- Perform automation

It helps Salesforce communicate with:
- Websites
- Mobile apps
- Payment gateways
- ERP systems
- External databases

---

# Question 5 – What is an Apex Callout?

An Apex Callout is used to send HTTP requests from Salesforce to external systems.

Callouts help Salesforce:
- Connect with APIs
- Fetch external data
- Send information outside Salesforce

---

# Apex Callout Example

```apex
public class StudentAPIService {

    public static void getStudentData() {

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

# Explanation of the Code

| Line | Purpose |
|---|---|
| Http http = new Http(); | Creates HTTP object |
| HttpRequest request = new HttpRequest(); | Creates request |
| setEndpoint() | Defines API URL |
| setMethod('GET') | Uses GET method |
| http.send(request) | Sends request |
| response.getBody() | Retrieves response |

---

# Question 6 – What is API Authentication?

Authentication ensures that only authorized systems can access APIs.

### Common Authentication Methods
- OAuth
- Access Tokens
- API Keys

Authentication improves:
- Security
- Data protection
- Access control

---

# Real-World Integration Examples

## Payment Gateway Integration

Salesforce communicates with:
- Razorpay
- PhonePe
- Stripe

for:
- Fee payments
- Transaction verification
- Receipt generation

---

## SMS Notification System

Salesforce sends:
- OTP messages
- Attendance alerts
- Fee reminders

using external SMS APIs.

---

## Email Service Integration

Salesforce integrates with email systems for:
- Confirmation emails
- Notifications
- Automated communication

---

# Enterprise Integration Workflow

## Student Fee Payment Workflow

1. Student submits payment
2. Salesforce sends API request
3. Payment gateway verifies payment
4. Response returns to Salesforce
5. Fee status gets updated
6. Receipt is generated
7. Notification is sent

This workflow helped me understand real-time enterprise communication systems.

---

# Request vs Response

| Request | Response |
|---|---|
| Sent by client | Returned by server |
| Contains operation | Contains result |
| Example: GET request | Example: JSON response |

---

# Web Services

Web Services allow applications to communicate over the internet.

### Types
- REST
- SOAP

REST is more commonly used because it is lightweight and easier to manage.

---

# Postman Basics

Postman is an API testing tool.

Developers use Postman to:
- Test APIs
- Send requests
- Verify responses
- Debug integrations

---

# Integration Architecture Understanding

Enterprise applications rarely work alone.

Salesforce often integrates with:
- Payment systems
- Banking systems
- ERP applications
- Mobile apps
- Email platforms

Integration architecture helps organizations:
- Share data efficiently
- Improve automation
- Reduce manual work
- Build scalable systems

---

# Human-Written Reflection

Today’s learning helped me understand how enterprise applications communicate with each other using APIs and integrations.

Earlier, I thought Salesforce only manages CRM data internally, but now I understood that real-world enterprise systems constantly exchange information with external applications such as payment gateways, messaging systems, and websites.

I also learned how REST APIs use HTTP methods and JSON data to transfer information between systems. Understanding Apex Callouts gave me clarity on how Salesforce developers implement real-time integrations programmatically.

This session gave me a better understanding of how large-scale enterprise ecosystems work together through APIs and secure communication systems.

---

# GitHub Submission Tasks

## Question 1 – Explain Why APIs Are Important

APIs are important because they allow different systems to communicate automatically without manual work.

Advantages:
- Faster communication
- Real-time automation
- Better scalability
- Reduced manual work
- Improved integration capability

---

## Question 2 – Difference Between REST and SOAP

| REST | SOAP |
|---|---|
| Lightweight | Heavy protocol |
| Uses JSON | Uses XML |
| Faster | Slower |
| Easier to use | More complex |

---

## Question 3 – Explain HTTP Methods

- GET → Retrieve data
- POST → Create data
- PUT → Update data
- DELETE → Remove data

These methods help APIs perform different operations.

---

## Question 4 – Explain Real-Time Integrations

Real-time integrations allow systems to communicate instantly when events occur.

Examples:
- Payment confirmation
- Attendance notifications
- OTP verification
- Order tracking

---

# Practical Task Code

## Simple JSON Example

```json
{
  "StudentName": "Priya",
  "Course": "Salesforce Development",
  "Attendance": 88,
  "FeeStatus": "Paid"
}
```

---

## Simple Apex REST Callout

```apex
public class CourseService {

    public static void fetchCourses() {

        Http http = new Http();

        HttpRequest req = new HttpRequest();

        req.setEndpoint('https://api.example.com/courses');

        req.setMethod('GET');

        HttpResponse res = http.send(req);

        System.debug(res.getBody());

    }

}
```

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
- Authentication basics
- Request and response handling
- Real-time communication systems
- Enterprise integration workflows
- External system communication
- API testing using Postman

This learning helped me understand how Salesforce interacts with external systems and how enterprise applications exchange data securely and efficiently using APIs and integrations.
