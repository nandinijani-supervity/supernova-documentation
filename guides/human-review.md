---
title: "Human Review & Approvals"
description: "Add human oversight and governance to AI-driven operations"
category: "Guides"
order: 10
---

## Overview

Not all work should be fully autonomous.

Supervity follows a **Human-in-Command** model, where AI agents operate independently **until human judgment, approval, or input is required**.

Human review is not an exception or workaround — it is a **first-class governance mechanism** designed for real-world, enterprise-grade operations.

---

## Why Human Review Exists

Human review enables safe delegation of work to AI agents while preserving accountability.

### Compliance & Governance
- Financial approvals  
- Legal and contract review  
- Policy enforcement  
- Audit and regulatory requirements  

### Quality Control
- Content moderation  
- Output validation  
- Data accuracy checks  

### Critical Decisions
- External customer communication  
- Infrastructure or system changes  
- Access and permission changes  

### Exception Handling
- High-value transactions  
- Unusual patterns  
- Edge cases and anomalies  

---

## How Human Review Works

### Execution Pausing & Resumption

When an agent reaches a review step:

1. Execution **pauses automatically**
2. Reviewers are notified
3. A review form is generated with full execution context
4. A human submits a decision
5. The agent **resumes execution** based on that decision

Agents never bypass review steps unless explicitly configured to do so.

---

### Review Forms

Review forms are generated dynamically and can include:

- Approve / reject actions  
- Comments or rationale fields  
- File uploads and attachments  
- Multiple-choice decisions  
- Conditional logic based on responses  

Forms can be accessed inside Supervity or embedded externally.

---

## Creating Human Review Steps

### Using AI Agents (Recommended)

You can request human oversight in natural language:

> “Send the drafted email to the manager for approval before sending.”

The agent will:
- Insert a review step
- Design the approval form
- Configure notifications
- Define resume behavior

This is the fastest and safest way to add human review.

---

### Manual Configuration

You can also add review steps explicitly:

1. Add a **Human Review** step  
2. Configure the form:
   - Fields (text, choice, file, etc.)
   - Required inputs
   - Reviewer instructions  
3. Assign reviewers:
   - Specific users
   - Roles
   - External email addresses  
4. Define timeouts and escalation rules  

---

## Review Experience

### For Reviewers

#### Accessing Reviews

Reviewers receive review requests via:
- Email notifications  
- In-app review dashboard  
- Embedded external systems (Enterprise)  

Each review includes:
- Context from earlier steps
- Relevant data and attachments
- Clear instructions on what’s required

---

#### Reviewer Actions

Reviewers can:
- Approve or reject
- Add comments
- Upload supporting files
- Modify inputs (if allowed)
- Escalate or delegate (if enabled)

All actions are logged and auditable.

---

### For Workflow Owners

#### Monitoring Review Status

Each review moves through clear states:
- **Pending**
- **Approved**
- **Rejected**
- **Expired**

Status is visible in real time.

---

#### Audit Trail & History

Supervity records:
- Who reviewed
- When the decision was made
- The decision outcome
- Comments and attachments
- Impact on downstream execution

This supports audits, compliance, and retrospectives.

---

## Configuration Options

### Reviewer Assignment

Reviewers can be assigned as:
- Single reviewer  
- Multiple reviewers:
  - Any one
  - All required
  - Majority-based  
- Role-based (e.g. Manager, Admin)
- Dynamically based on workflow data  

---

### Notifications & Escalation

Notify reviewers via:
- Email  
- Slack / Microsoft Teams  
- In-app notifications  

Escalation options include:
- Reminder after X hours
- Backup reviewers
- Hierarchical escalation

---

### Timeouts & Fallbacks

Define what happens if no action is taken:
- Auto-approve
- Auto-reject
- Escalate
- Pause indefinitely

Example:
> “If not reviewed within 24 hours, escalate to the senior manager.”

---

## Common Human-in-Command Patterns

### Approval Gate

```

AI drafts content
→ Human Review: Approve / Reject
→ If approved → Publish
→ If rejected → Notify and stop

```

---

### Conditional Review

```

If amount > $5,000
→ Require Director approval
Else
→ Auto-approve

```

---

### Multi-Level Review

```

Manager approval
→ Director approval
→ Finance approval
→ Continue execution

```

---

## Best Practices

### Design Principles
- Use review only where judgment is required  
- Provide full context to reviewers  
- Keep forms concise  
- Avoid unnecessary approval layers  

### Performance Considerations
- Set reasonable timeouts  
- Use escalation paths  
- Monitor review bottlenecks  

### Security
- Restrict reviewer access  
- Protect sensitive data  
- Enable audit logging  

---

## External & API-Driven Reviews (Enterprise)

Human review can be embedded into:
- External dashboards
- Command centers
- Internal tools

Using APIs, external systems can:
- Fetch pending reviews
- Render review forms
- Submit approve or reject actions
- Resume agent execution programmatically

See **[API Reference](/docs/reference/api-reference)**.

---

## Monitoring & Analytics

Track review performance using:
- Average review time
- Approval and rejection rates
- Bottlenecks
- SLA compliance

These insights help improve operational efficiency.

---

## Troubleshooting

### Review Not Received
- Check notification settings
- Verify reviewer permissions
- Resend review request

### Workflow Stuck Waiting
- Check timeout configuration
- Escalate manually (Admin)
- Cancel or restart execution

---

## Getting Started

- **Tutorial: Approval Workflow**  
  `/u/alpha/tutorials/library/advanced/human-approval-workflows`

- **Example: Expense Approval**  
  `/u/alpha/tutorials/examples/content-approval-process`

- **View Pending Reviews**  
  Available from the Human Review dashboard

---

Human Review ensures AI agents act **with autonomy, but never without accountability**.
```
