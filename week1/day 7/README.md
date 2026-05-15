# Day 7 – Salesforce Testing, Async Apex & Salesforce DX

## Introduction

As part of Day 7 training, I learned how enterprise Salesforce applications are developed, tested, and maintained using professional development practices.

Today’s learning focused on:
- Testing
- Asynchronous Apex
- Salesforce DX
- Enterprise workflow understanding
- System integration
- Structured software development

I also understood how different Salesforce technologies work together inside a complete business application.

---

# CORE TASK 1 – Why Testing Matters

## 1. Why Testing Matters

Testing is one of the most important parts of enterprise software development.

Enterprise applications are used by:
- Thousands of users
- Multiple departments
- Large business systems

If applications are not tested properly:
- Bugs may occur
- Incorrect data may be stored
- Automation may fail
- Reports may become inaccurate
- Business operations may stop working properly

Testing helps developers:
- Find bugs early
- Improve software reliability
- Maintain data accuracy
- Ensure business logic works correctly
- Improve application stability

In Salesforce, testing is very important because:
- Apex code requires test coverage
- Deployments need successful test execution
- Enterprise applications depend on stable automation

---

# CORE TASK 2 – What is Asynchronous Apex?

## 2. What is Asynchronous Apex?

Asynchronous Apex is used to run processes in the background instead of executing them immediately.

This improves:
- Performance
- Scalability
- User experience

Background processing is useful for operations that:
- Take longer time
- Process large data
- Communicate with external systems

---

## Types of Asynchronous Apex

### Future Method
Used for background processing.

### Queueable Apex
Used for advanced background jobs.

### Batch Apex
Used for large data processing.

### Scheduled Apex
Used to execute jobs at scheduled times.

---

## Real-Time Examples

### Example 1 – Sending Bulk Emails
Emails are processed in the background to improve performance.

### Example 2 – Report Generation
Large reports are generated asynchronously.

### Example 3 – API Integration
External system communication is handled asynchronously.

---

## Future Method Example

```apex
public class StudentAsyncHandler {

    @future
    public static void sendNotification(String studentName) {

        System.debug(
            'Notification sent to: ' + studentName
        );
    }
}
```

---

## Queueable Apex Example

```apex
public class StudentQueueJob implements Queueable {

    public void execute(QueueableContext qc) {

        System.debug('Queueable Job Started');

    }
}
```

---

# CORE TASK 3 – What is Salesforce DX?

## 3. What is Salesforce DX?

Salesforce DX (Developer Experience) is a modern development environment for Salesforce developers.

It supports:
- Source-driven development
- Team collaboration
- Better deployment workflow
- Version control integration

Salesforce DX helps developers:
- Work efficiently
- Manage code properly
- Improve project organization

---

## Why Salesforce DX is Important

### Advantages
- Better teamwork
- Faster development
- Easier deployments
- Better source control
- Improved productivity

---

## Common Salesforce DX Commands

### Authorize Org

```bash
sfdx auth:web:login
```

### Create Project

```bash
sfdx force:project:create
```

### Push Source

```bash
sfdx force:source:push
```

### Pull Source

```bash
sfdx force:source:pull
```

### Open Org

```bash
sfdx force:org:open
```

---

# CORE TASK 4 – Complete System Workflow

## 4. Complete System Workflow (End-to-End Explanation)

Today I understood how multiple Salesforce technologies work together inside one enterprise application.

---

## Step 1 – Student Registration

A student submits details using a registration form.

### Example Fields
- Student Name
- Email
- Department
- Course

---

## Step 2 – Validation Rules Execute

Validation Rules verify data correctness.

### Example Validations
- Email format check
- Mandatory field validation
- Seat limit validation

---

## Step 3 – Flow Executes Automatically

Record-Triggered Flow performs:
- Record creation
- Email notifications
- Admin alerts

---

## Step 4 – Apex Trigger Executes

Trigger updates business-related data automatically.

### Example
- Increase filled seats count
- Update department statistics

---

## Apex Trigger Example

```apex
trigger StudentTrigger on Student__c (after insert) {

    List<Course__c> courseList = new List<Course__c>();

    for(Student__c stu : Trigger.new) {

        if(stu.Course__c != null) {

            Course__c courseObj = [
                SELECT Id, Filled_Seats__c
                FROM Course__c
                WHERE Id = :stu.Course__c
                LIMIT 1
            ];

            courseObj.Filled_Seats__c =
                courseObj.Filled_Seats__c + 1;

            courseList.add(courseObj);
        }
    }

    update courseList;
}
```

---

## Step 5 – Formula Fields Calculate Values

Formula Fields automatically calculate:
- Remaining seats
- Attendance percentage
- Eligibility status

---

## Step 6 – Reports and Dashboards

Admins monitor:
- Student reports
- Attendance reports
- Fee reports
- Course analytics

---

# CORE TASK 5 – Important Test Cases

## 5. Important Test Cases (Your Examples)

### Test Case 1 – Invalid Email Validation

#### Scenario
User enters invalid email.

#### Expected Result
System should reject invalid email.

---

### Test Case 2 – Duplicate Student Registration

#### Scenario
Same student registers twice.

#### Expected Result
Duplicate records should not be created.

---

### Test Case 3 – Course Seat Limit

#### Scenario
Course becomes full.

#### Expected Result
Further registration should stop.

---

### Test Case 4 – Attendance Percentage Calculation

#### Scenario
Attendance is calculated automatically.

#### Expected Result
Correct percentage should display.

---

### Test Case 5 – Trigger Execution

#### Scenario
Student registration occurs.

#### Expected Result
Filled seats count should update correctly.

---

## Apex Test Class Example

```apex
@isTest
public class StudentTriggerTest {

    @isTest
    static void verifySeatUpdate() {

        Course__c courseObj = new Course__c(
            Name = 'Salesforce Course',
            Filled_Seats__c = 0
        );

        insert courseObj;

        Student__c stu = new Student__c(
            Name = 'Priya',
            Course__c = courseObj.Id
        );

        insert stu;

        Course__c updatedCourse = [
            SELECT Filled_Seats__c
            FROM Course__c
            WHERE Id = :courseObj.Id
        ];

        System.assertEquals(
            1,
            updatedCourse.Filled_Seats__c
        );
    }
}
```

---

# CORE TASK 6 – Reflection

## 6. Reflection – Why Enterprise Software Development Needs Structured Workflows

Enterprise software systems are large, complex, and continuously evolving.

Without structured workflows:
- Development becomes difficult
- Bugs increase
- Deployments fail
- Team collaboration becomes harder

Structured development practices help:
- Improve software quality
- Maintain project organization
- Reduce production issues
- Improve scalability
- Support teamwork

Enterprise workflows usually include:
- Testing
- GitHub
- Salesforce DX
- Version control
- Deployment process
- Automation
- CI/CD practices

These practices help companies build stable and scalable enterprise applications.

---

# Overall Understanding After Day 7

After completing Day 7, I understood:
- Importance of testing in enterprise systems
- Role of Asynchronous Apex
- How background processing improves performance
- Importance of Salesforce DX
- How professional Salesforce development workflow works
- Importance of structured software development
- How different Salesforce technologies integrate together
- Why enterprise applications require testing, automation, and version control
