# Day 14 – Salesforce Flow Logic, Approval Workflows, and Governance

# Introduction

This README contains my learning progress, practical understanding, notes, and core task implementation completed as part of Day 14 of the Salesforce Summer Training Program.

Today’s learning focused on advanced Flow Builder concepts, branching automation logic, approval workflows, enterprise governance, and controlled business processes.

I learned how enterprise systems use structured workflows and approval mechanisms to avoid mistakes, maintain security, and ensure that important operations follow proper business rules.

---

# Topics Covered

- Flow Builder Logic
- Decision Elements
- Variables in Flow
- Branching Automation
- Multi-Step Workflows
- Approval Processes
- Multi-Level Approval Systems
- Governance in Enterprise Systems
- Controlled Business Operations
- Enterprise Workflow Design
- Auditable Systems
- Decision-Based Automation

---

# Key Learnings

- Salesforce Flows can handle complex business logic using decision elements.
- Branching workflows help systems take different actions based on conditions.
- Approval workflows ensure that important actions are verified before execution.
- Governance helps organizations maintain security and business control.
- Enterprise systems require structured workflows instead of unrestricted access.
- Multi-level approvals reduce business risk and improve accountability.

---

# CORE TASK 1 – Multi-Level Approval Design

## Question:
Design approval workflows for:
- Course creation
- Faculty leave request
- Student scholarship request
- Budget approval

Explain:
- Who approves?
- In what order?
- What happens after approval/rejection?

---

# 1. Course Creation Approval Workflow

## Scenario

When a faculty member wants to create a new course, the course should not become active immediately. The request must pass through multiple approval levels.

---

## Approval Workflow

### Step 1 – Faculty Submission
The faculty member submits a new course request.

### Step 2 – Department Head Approval
The Department Head checks:
- Course relevance
- Syllabus quality
- Faculty availability

### Step 3 – Academic Committee Approval
The Academic Committee reviews:
- Academic standards
- Credit structure
- Semester planning

### Step 4 – Admin Approval
The Admin verifies:
- Resource availability
- Classroom allocation
- Budget feasibility

---

## After Approval

If all approvals are successful:
- Course record becomes active
- Students can register
- Course appears in portal

---

## After Rejection

If rejected:
- Course status becomes "Rejected"
- Faculty receives notification
- Feedback/comments are shared

---

# Why Multi-Level Approval is Important

This prevents:
- Duplicate courses
- Invalid syllabus creation
- Unplanned academic operations

It ensures controlled academic management.

---

# 2. Faculty Leave Request Approval Workflow

## Workflow Steps

### Step 1 – Faculty submits leave request

The request contains:
- Leave reason
- Leave dates
- Substitute faculty details

---

### Step 2 – Department Head Approval

Checks:
- Faculty workload
- Class schedules
- Substitute availability

---

### Step 3 – HR Approval

HR verifies:
- Leave balance
- Policy compliance
- Official records

---

## After Approval

- Leave gets approved
- Attendance records update
- Notifications are sent

---

## After Rejection

- Leave request status becomes rejected
- Faculty receives reason for rejection

---

# 3. Student Scholarship Approval Workflow

## Workflow Steps

### Step 1 – Student submits scholarship request

Includes:
- Academic performance
- Income documents
- Attendance percentage

---

### Step 2 – Faculty Verification

Faculty verifies:
- Student performance
- Discipline
- Attendance

---

### Step 3 – Scholarship Committee Approval

Committee reviews:
- Eligibility criteria
- Scholarship availability
- Financial conditions

---

### Step 4 – Finance Department Approval

Finance confirms:
- Budget availability
- Fund allocation

---

## After Approval

- Scholarship gets sanctioned
- Fee amount updates automatically
- Student receives confirmation

---

## After Rejection

- Student receives rejection notification
- Reason is recorded for auditing

---

# 4. Budget Approval Workflow

## Workflow Steps

### Step 1 – Department submits budget request

Includes:
- Equipment requirements
- Infrastructure expenses
- Event costs

---

### Step 2 – Finance Team Review

Finance checks:
- Available funds
- Cost estimation
- Budget validity

---

### Step 3 – Management Approval

Management verifies:
- Business priority
- Organizational goals
- Resource allocation

---

## After Approval

- Budget becomes approved
- Procurement process begins

---

## After Rejection

- Budget request returns for modification
- Comments are added

---

# CORE TASK 2 – Branching Flow Logic

## Question:
Create a branching flow example.

Example:
- If attendance < 75% → warning email
- If attendance < 60% → parent notification
- If attendance < 50% → admin escalation

Explain:
- Decision points
- Branches
- Actions triggered

---

# Attendance Monitoring Flow

## Flow Name
Student Attendance Monitoring Flow

---

# Step-by-Step Flow Logic

## Step 1 – Record Trigger

Flow starts when:
- Student attendance record is updated

---

## Step 2 – Decision Element

The flow checks attendance percentage.

---

# Branch 1 – Attendance Below 75%

## Condition

```text
Attendance < 75%
```

## Action Triggered

- Warning email sent to student
- Attendance warning stored in system

---

# Branch 2 – Attendance Below 60%

## Condition

```text
Attendance < 60%
```

## Action Triggered

- Parent notification email sent
- Faculty advisor gets notified

---

# Branch 3 – Attendance Below 50%

## Condition

```text
Attendance < 50%
```

## Action Triggered

- Admin escalation triggered
- Meeting request generated
- Student added to risk monitoring list

---

# Decision Points in the Flow

| Decision Point | Purpose |
|---|---|
| Attendance < 75% | Warning stage |
| Attendance < 60% | Parent intervention |
| Attendance < 50% | Administrative escalation |

---

# Why Branching Logic is Important

Branching workflows help systems:
- React differently based on conditions
- Handle multiple scenarios automatically
- Reduce manual monitoring
- Improve automation accuracy

---

# CORE TASK 3 – Governance Thinking

## Question:
Why can’t enterprise systems allow everyone to directly change important records?

Think about:
- Security
- Misuse
- Wrong approvals
- Business risk

---

# Detailed Answer

Enterprise systems contain sensitive and critical business data. Allowing every user to directly modify important records can create major business problems.

---

# 1. Security Risks

Sensitive data such as:
- Financial records
- Student information
- Employee details
- Approval records

must be protected.

Without governance:
- Unauthorized users may access data
- Confidential information may leak
- Data integrity may get compromised

---

# 2. Misuse of System

Without restrictions:
- Users may misuse permissions
- Fake approvals may happen
- Incorrect records may get created

This can damage organizational trust and operations.

---

# 3. Wrong Approvals

Important business operations require verification.

Examples:
- Scholarship approval
- Budget approval
- Course activation

Without structured approval workflows:
- Wrong decisions may occur
- Policies may be violated
- Financial loss may happen

---

# 4. Business Risk

Uncontrolled systems increase:
- Operational risk
- Security risk
- Financial risk
- Compliance issues

Enterprise systems require accountability and traceability.

---

# Why Governance is Important

Governance helps organizations:
- Maintain control
- Improve security
- Track changes
- Ensure accountability
- Follow business rules

---

# CORE TASK 4 – Reflection

## Question:
Why do enterprises require controlled workflows instead of unrestricted actions?

---

# Reflection Answer

Large organizations handle thousands of records, approvals, employees, customers, and transactions every day.

If systems allow unrestricted actions:
- Data inconsistency may occur
- Unauthorized changes may happen
- Business policies may break
- Security issues may arise

Controlled workflows ensure:
- Proper approvals
- Secure operations
- Business rule enforcement
- Accountability
- Auditing capability

Approval workflows and branching automation help enterprises maintain structure and reliability while reducing manual errors and operational risks.

Today’s learning helped me understand that enterprise software is not only about automation but also about governance, security, accountability, and controlled business operations.

---

# Revision Questions

## 1. Why are approval workflows important?

Approval workflows ensure that important actions are verified before execution. They improve accountability, security, and business control.

---

## 2. Why do businesses require governance?

Governance helps organizations maintain security, prevent misuse, and ensure that operations follow business policies.

---

## 3. What are branching workflows?

Branching workflows use conditions to trigger different actions based on business logic.

---

## 4. Why should automation follow business rules?

Automation must follow business rules to avoid incorrect actions and maintain organizational standards.

---

## 5. Why are decision nodes important in flows?

Decision nodes help workflows evaluate conditions and choose appropriate actions automatically.

---

## 6. Why should enterprises restrict sensitive operations?

Sensitive operations involve critical business data and require controlled access to prevent misuse and security risks.

---

## 7. Why are approvals important in large organizations?

Approvals ensure accountability, verification, and proper business process management.

---

## 8. Why should workflows be auditable?

Auditable workflows help organizations:
- Track actions
- Identify errors
- Maintain transparency
- Support compliance

---

# Practical Flow Logic Example

## Attendance Monitoring Pseudocode

```text
IF attendance < 75%
THEN send warning email

IF attendance < 60%
THEN notify parent

IF attendance < 50%
THEN escalate to admin
```

---

# Example Approval Logic

```text
Faculty submits leave request
→ Department Head approval
→ HR approval
→ Final confirmation
```

---

# Trailhead Modules Completed

- Flow Builder Logic
- Approve Records with Approval Processes

---

# Tools Used

- Salesforce Trailhead
- Salesforce Developer Edition
- Flow Builder
- GitHub
- VS Code

---

# Overall Understanding After Day 14

After completing Day 14, I understood:
- Advanced Flow Builder logic
- Decision-based automation
- Branching workflows
- Multi-step process design
- Approval workflows
- Multi-level approvals
- Governance in enterprise systems
- Controlled business operations
- Security and accountability
- Structured enterprise workflow management

This learning helped me understand how enterprise applications use governance and approval systems to maintain secure, scalable, and reliable business operations.
