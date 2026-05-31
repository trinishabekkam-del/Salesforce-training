# Day 12 Notes – Professional Salesforce Developer Workflow

## Introduction

Day 12 focused on understanding how professional Salesforce developers work in real enterprise environments using modern development tools and workflows.

Earlier, most development activities were done directly through the Salesforce browser interface. But enterprise teams use professional tools like:
- Salesforce DX
- Salesforce CLI
- GitHub
- Version Control Systems
- Deployment Pipelines

This session helped me understand how large software teams collaborate efficiently while building enterprise-level Salesforce applications.

---

# Topics Covered

- Salesforce DX
- Salesforce CLI
- GitHub Workflow
- Source-Driven Development
- Team Collaboration
- Version Control
- Branching Workflow
- Deployment Workflow
- Sandbox vs Production
- Enterprise Development Process
- Rollback Systems
- Real Engineering Practices

---

# What is Salesforce DX?

Salesforce DX (Developer Experience) is a modern Salesforce development approach that supports:
- source-driven development
- team collaboration
- automated deployment
- version control integration

Salesforce DX improves developer productivity and makes Salesforce development similar to modern software engineering practices.

---

# Features of Salesforce DX

- Better project structure
- GitHub integration
- CLI support
- Source tracking
- Scratch org support
- Faster deployments
- Easier testing workflow

---

# What is Salesforce CLI?

CLI stands for Command-Line Interface.

Salesforce CLI allows developers to interact with Salesforce using terminal commands instead of only browser clicks.

---

# Advantages of CLI

- Faster execution
- Automation support
- Improved productivity
- Easier deployments
- Better developer workflow

---

# Common Salesforce CLI Commands

## Login to Salesforce Org

```bash
sf org login web
```

---

## Create New Salesforce Project

```bash
sf project generate --name CollegeManagement
```

---

## Deploy Metadata

```bash
sf project deploy start
```

---

## Retrieve Metadata

```bash
sf project retrieve start
```

---

## Open Salesforce Org

```bash
sf org open
```

---

# What is GitHub?

GitHub is a version control and collaboration platform used by developers to:
- store source code
- track changes
- manage versions
- collaborate with teams
- restore older code versions

---

# Why GitHub is Important

GitHub helps teams:
- avoid code conflicts
- maintain backup history
- review changes safely
- collaborate efficiently
- manage deployments properly

---

# Version Control

Version control helps developers:
- track code changes
- restore old versions
- manage updates
- identify bugs
- collaborate safely

---

# Branching Workflow

Branches allow developers to work independently without affecting the main project.

---

# Example

Developer A:
- Works on Attendance Module

Developer B:
- Works on Fee Module

Both developers use separate branches.

After testing:
- changes are merged safely.

---

# Source-Driven Development

In source-driven development:
- source code becomes the main system of record
- changes are managed through GitHub
- deployments become easier and safer

---

# Sandbox vs Production

## Sandbox
Used for:
- development
- testing
- experimentation

No impact on live users.

---

## Production
Used by real users.

Contains:
- live business data
- customer information
- actual business operations

---

# Why Teams Separate Sandbox and Production

Separating environments helps:
- avoid production errors
- improve testing quality
- protect business systems
- reduce deployment risks

---

# Team Collaboration Challenges

Without collaboration tools:
- code conflicts may happen
- work may get overwritten
- bugs become difficult to track
- deployment becomes risky

---

# Problems Without Version Control

## 1. Code Loss
Developers may accidentally remove important code.

---

## 2. No Backup
Older working versions cannot be restored easily.

---

## 3. Difficult Collaboration
Multiple developers editing same files creates confusion.

---

## 4. Deployment Risks
Unstable code may enter production.

---

# Deployment Workflow

Enterprise systems follow structured deployment workflow:

```text
Development
    ↓
Testing
    ↓
Code Review
    ↓
Validation
    ↓
Production Deployment
```

---

# Importance of Testing

Testing ensures:
- stable functionality
- fewer bugs
- better reliability
- safe deployment

---

# Types of Testing

- Unit Testing
- Integration Testing
- User Acceptance Testing

---

# Rollback Capability

Rollback means restoring an older stable version if deployment fails.

---

# Why Rollback is Important

If deployment causes:
- login issues
- payment failures
- system crashes

teams can restore previous stable version quickly.

---

# Enterprise Software Development vs College Assignments

| College Projects | Enterprise Systems |
|---|---|
| Small projects | Large-scale applications |
| Single developer | Multiple teams |
| Minimal testing | Extensive testing |
| No rollback | Rollback support required |
| Simple deployment | Structured deployment |
| Temporary use | Long-term maintenance |

---

# Real Engineering Thinking

Enterprise software engineering involves:
- collaboration
- deployment management
- testing
- version control
- scalability
- reliability
- maintenance

It is much more than simply writing code.

---

# Real-World Salesforce Workflow

```text
Requirement Analysis
        ↓
Development in Sandbox
        ↓
GitHub Commit
        ↓
Branch Creation
        ↓
Testing
        ↓
Code Review
        ↓
Deployment Validation
        ↓
Production Deployment
```

---

# Reflection

After learning Salesforce DX, CLI, and GitHub workflow, I realized that professional software engineering requires:
- proper collaboration
- structured workflow
- version control
- deployment planning
- testing strategy
- rollback systems

I also understood that enterprise development is much more organized and disciplined compared to small academic coding projects.

Modern Salesforce teams depend heavily on:
- GitHub
- Salesforce DX
- CLI tools
- deployment pipelines

to build scalable and reliable enterprise applications.

---

# Key Learnings

- Salesforce DX supports modern development workflow.
- CLI tools improve developer productivity.
- GitHub helps manage collaboration and version control.
- Source-driven development improves project management.
- Enterprise systems require structured workflow.
- Deployment workflow improves stability.
- Rollback systems improve reliability.
- Testing is critical in enterprise applications.
- Team collaboration becomes complex in large projects.
- Professional software engineering requires planning and discipline.

---

# Trailhead Modules Completed

- Quick Start: Salesforce DX
- Command-Line Interface Basics
- Org Development Model
- Agentforce DX Overview

---

# Overall Understanding After Day 12

After completing Day 12, I understood:
- Professional Salesforce development workflow
- Salesforce DX concepts
- Salesforce CLI workflow
- GitHub collaboration workflow
- Source-driven development
- Version control importance
- Deployment management
- Team collaboration challenges
- Rollback systems
- Enterprise engineering practices

This session helped me understand how professional Salesforce teams develop, manage, test, and deploy enterprise applications efficiently using modern engineering workflows.
