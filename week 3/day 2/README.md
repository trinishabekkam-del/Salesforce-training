#  Day 16 — Debugging, Developer Tools & Best Practices
### Salesforce Summer Program | Enterprise Systems Thinking

---

> *"The best developers aren't the ones who write the most code — they're the ones who can find out why it breaks."*

---

##  What I Learned Today

Today's focus was on thinking like a real-world Salesforce engineer:

-  Diagnosing and fixing bugs using **Apex Replay Debugger**
-  Mastering the **Developer Console** for logs, queries, and execution
-  Writing **LWC Best Practices** for clean, performant components
-  Thinking about **performance at scale**
-  Understanding why **maintainable architecture** matters

---

##  Task 1 — Bug Analysis: Real Scenarios, Real Debugging

### Scenario A: Duplicate Notifications
**Problem:** Users receive the same notification multiple times.

**Debugging Approach:**
- Check if the triggering Flow or Apex trigger fires more than once (e.g., recursive trigger with no static flag guard)
- Open **Developer Console → Logs** and filter for the notification-related class
- Look for repeated `System.debug` outputs indicating multiple executions
- Use **Apex Replay Debugger** in VS Code to step through execution and identify where the duplicate call originates
- Fix: Add a static Boolean flag in the trigger to prevent recursion, or add a duplicate-check condition in the Flow

---

### Scenario B: Attendance Calculations Wrong
**Problem:** Attendance totals are incorrect or inconsistent.

**Debugging Approach:**
- Use **Developer Console → Query Editor** to run SOQL and inspect raw data values
- Check if the formula field or Apex logic handles null values properly
- Use debug logs with `System.debug(attendanceRecord)` to trace values mid-execution
- Replay the exact transaction using **Apex Replay Debugger** and watch variable states change step-by-step
- Fix: Add null-safe checks (`if (value != null)`), verify field types, and validate rollup summary filters

---

### Scenario C: Flow Not Triggering
**Problem:** A record-triggered Flow does not execute when expected.

**Debugging Approach:**
- Verify the Flow entry criteria — a small data mismatch (e.g., picklist value casing) can silently block execution
- Check if the Flow is **Active** in Flow Manager
- Enable **Flow Debug** mode and run it manually with sample data to test conditions
- Check **Debug Logs** for any Flow execution errors or governor limit exceptions
- Fix: Correct entry criteria, activate the Flow version, and handle exceptions within the Flow

---

### Scenario D: Approval Process Stuck
**Problem:** A record is stuck in a pending approval state with no action taken.

**Debugging Approach:**
- Query `ProcessInstance` and `ProcessInstanceStep` objects via SOQL to see where the process halted
- Check if the assigned approver is active and has a valid email
- Look at **Debug Logs** for any email delivery failures or exceptions during approval submission
- Use **Setup → Approval Processes** to verify step configuration
- Fix: Reassign the approver, recall and resubmit the approval, or add an automated fallback approver

---

##  Task 2 — Performance Thinking at Scale

> Imagine 50,000 users are using the system simultaneously. What breaks?

| Layer | Potential Problem | Solution |
|---|---|---|
| **UI** | LWC components re-rendering on every change, slow page load | Use `@wire` with caching, lazy load components, avoid unnecessary reactive properties |
| **Backend (Apex)** | Governor limits hit — 100 SOQL queries, 150 DML statements per transaction | Bulkify code, use collections, move queries outside loops |
| **Database** | Full table scans on large objects (Contacts, Leads) | Add indexed fields to SOQL `WHERE` clauses, avoid non-selective queries |
| **Notifications** | Email/push notification queue overwhelmed | Use async Apex (`@future`, Queueable), batch notifications, respect daily email limits |
| **Automation** | Flows and triggers firing in cascading chains | Audit trigger order, use a single trigger per object, add recursion guards |

**Key Takeaway:** Enterprise systems don't break in development — they break under real load. Always design with limits in mind.

---

##  Task 3 — Maintainability Thinking

### Why Write Modular, Reusable, Debuggable Code?

**Modular Code:**
When logic is broken into small, single-purpose units (one class per concern, one method per action), bugs are easier to isolate. You don't have to read 500 lines to find a problem — you go directly to the responsible module.

**Reusable Components:**
A reusable LWC button, a shared utility Apex class, or a common validation method means:
- Less code written overall
- One fix propagates everywhere
- Consistent behavior across the system

**Debuggable Systems:**
Code that logs meaningful messages, uses named variables, and avoids deeply nested conditions is code that can be debugged by *anyone* — including yourself three months later.

**Quick Hacks = Future Emergencies:**
A shortcut that skips validation today becomes a production incident tomorrow. Enterprise systems have real users, real data, and real consequences. Clean code is not optional — it's professional responsibility.

---

##  Task 4 — Reflection

### Why is Debugging One of the Most Important Skills in Software Engineering?

Writing code is only half the job. The other half is figuring out why it doesn't work the way you expected.

Debugging teaches you to:
- **Think systematically** — form a hypothesis, test it, eliminate possibilities one by one
- **Understand systems deeply** — you can't debug what you don't understand
- **Stay calm under pressure** — production bugs happen; good engineers don't panic, they investigate
- **Read other people's code** — most real bugs are in code you didn't write

In Salesforce specifically, debugging is complex because the platform has:
- Multiple interacting automation layers (Triggers, Flows, Validation Rules, Processes)
- Governor limits that fail silently in some cases
- Async operations that are hard to trace in real time

A developer who can debug well is a developer who can be trusted with real systems.

---

##  LWC Best Practices Summary

```javascript
//  Use @wire for data — cached, reactive, efficient
@wire(getRecord, { recordId: '$recordId', fields: FIELDS })
record;

//  Break big components into small ones
// parent.html
<c-child-component data={record}></c-child-component>

//  Use getters for derived values — keep templates clean
get formattedName() {
    return this.record?.fields?.Name?.value ?? 'Unknown';
}

//  Avoid imperative Apex calls when @wire works
//  Don't store API responses directly in arrays without error handling
//  Don't manipulate the DOM directly — let the framework handle it
` ` `

**Principles:**
- One component, one responsibility
- Pass data down via `@api`, send events up via `CustomEvent`
- Always handle loading and error states in your template
- Use `connectedCallback` for setup, `disconnectedCallback` for cleanup

---

##  Resources

| Resource | Link |
|---|---|
| Apex Replay Debugger — Salesforce Tutorial | [Watch](https://www.youtube.com/watch?v=iWXvnylWuR8) |
| Debug Logs for Troubleshooting | [Watch](https://www.youtube.com/watch?v=tPPv4VQY89k) |
| Developer Console in Salesforce | [Watch](https://www.youtube.com/watch?v=2KRGa86nbOg) |
| LWC Best Practices | [Watch](https://www.youtube.com/watch?v=q3e0Qx2D6lY) |

---

##  Revision Questions & Answers

**1. Why are debug logs important?**
They give you a timestamped record of exactly what ran, in what order, with what values — without needing to reproduce the issue live.

**2. Why is debugging difficult in enterprise systems?**
Because many components interact — triggers, flows, validation rules, integrations — and a bug in one can silently affect another. Tracing the source requires understanding the whole system.

**3. What problems happen when systems scale?**
Governor limits get hit, queries slow down, automations cascade, and UI components become unresponsive. Systems must be designed for volume from the start.

**4. Why should components be reusable?**
Reusability reduces duplication, ensures consistency, and means a single fix resolves issues everywhere the component is used.

**5. Why is maintainability important?**
Systems evolve. Code written for today must be understood and modified tomorrow — by other developers, possibly under pressure. Maintainable code reduces risk and cost over time.

**6. Why should developers avoid tightly coupled code?**
Tightly coupled code creates a domino effect — changing one part breaks others. Loose coupling means components can be updated, tested, and replaced independently.

**7. Why do enterprise systems require monitoring?**
Enterprise systems run continuously at scale. Without monitoring, silent failures, performance degradation, or data issues can go unnoticed until they cause significant damage.

**8. Why is troubleshooting an important engineering skill?**
Because no system is bug-free. The ability to diagnose and resolve issues quickly is what separates a reliable engineer from one who can only build in ideal conditions.



---

*Salesforce Summer Program — Day 16 | Debugging · Developer Tools · Best Practices*
