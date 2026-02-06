---
title: "Human Approval Workflows"
level: advanced
duration: 25 minutes
prerequisites: ["getting-started/03-workflow-structure", "library/advanced/complex-branching"]
tags: [approval, human-in-the-loop, interactive, advanced]
category: library/advanced
description: "Learn to build workflows that require human approval and input"
---

# Human Approval Workflows

Build workflows that pause for human approval, input, or review. This tutorial covers human-in-the-loop patterns and interactive workflow steps.

## What You'll Learn

- How to add approval steps to workflows
- How to collect human input during execution
- How to handle approval workflows
- How to design review and approval processes

## Prerequisites

- Understanding of workflow structure
- Knowledge of conditional branching
- Experience with multi-step workflows

## Approval Step Basics

### What Are Approval Steps?

Approval steps pause workflow execution and wait for human input:
- **Review**: Human reviews generated content
- **Approve/Reject**: Human makes a decision
- **Input**: Human provides additional information
- **Confirmation**: Human confirms an action

### When to Use Approval Steps

✅ **Good for:**
- Content that needs review (emails, reports)
- Decisions requiring human judgment
- Sensitive operations (payments, deletions)
- Quality control checkpoints
- Compliance requirements

❌ **Not needed for:**
- Fully automated processes
- Low-risk operations
- High-volume tasks

## Basic Approval Pattern

### Simple Approval

**Pattern:** Generate → Review → Approve/Reject → Continue

**Example:**
> "Create a workflow that generates a report, sends it for approval, then distributes if approved"

```
Step 1: Generate report
  ↓
Step 2: [Human Approval] Review and approve report
  ├─→ If approved: Step 3: Distribute report
  └─→ If rejected: Step 4: Request revisions
```

### Approval with Feedback

**Pattern:** Include feedback mechanism

**Example:**
```
Step 1: Generate draft email
  ↓
Step 2: [Human Input] Review email and provide feedback
  Input fields:
    - approved (yes/no)
    - feedback (text)
    - changes_needed (text)
  ├─→ If approved: Step 3: Send email
  └─→ If not approved: Step 4: Revise based on feedback
```

## Multi-Stage Approval

### Sequential Approvals

**Pattern:** Multiple approval stages

**Example:**
> "Create a workflow that requires approval from manager, then finance, then executive"

```
Step 1: Generate expense report
  ↓
Step 2: [Manager Approval] Manager reviews
  ├─→ If approved: Continue
  └─→ If rejected: Step 3: Notify requester
        ↓
    Step 4: [Finance Approval] Finance reviews
      ├─→ If approved: Continue
      └─→ If rejected: Step 5: Notify requester
            ↓
        Step 6: [Executive Approval] Executive reviews
          ├─→ If approved: Step 7: Process payment
          └─→ If rejected: Step 8: Notify requester
```

### Parallel Approvals

**Pattern:** Multiple approvers review simultaneously

**Example:**
> "Create a workflow that requires approval from multiple departments in parallel"

```
Step 1: Generate proposal
  ↓
Step 2: [Legal Approval] Legal reviews (parallel)
Step 3: [Finance Approval] Finance reviews (parallel)
Step 4: [Technical Approval] Technical reviews (parallel)
  ↓ (all complete)
Step 5: Evaluate all approvals
  ├─→ If all approved: Step 6: Execute proposal
  └─→ If any rejected: Step 7: Notify and revise
```

## Conditional Approval

### Approval Based on Criteria

**Pattern:** Only request approval when needed

**Example:**
> "Create a workflow that only requires approval for high-value orders"

```
Step 1: Get order details
  ↓
Step 2: Check order value
  ├─→ If value > $1000: Step 3: [Manager Approval] Request approval
  │     ├─→ If approved: Step 4: Process order
  │     └─→ If rejected: Step 5: Cancel order
  └─→ If value <= $1000: Step 4: Process order directly
```

## Input Collection

### Collecting Additional Information

**Pattern:** Request input during workflow execution

**Example:**
> "Create a workflow that collects customer feedback during processing"

```
Step 1: Process order
  ↓
Step 2: [Human Input] Collect customer feedback
  Input fields:
    - satisfaction_rating (1-5)
    - feedback_text (text)
    - follow_up_needed (yes/no)
  ↓
Step 3: Save feedback
Step 4: If follow_up_needed: Step 5: Schedule follow-up
```

### Dynamic Forms

**Pattern:** Forms adapt based on previous steps

**Example:**
```
Step 1: Analyze request type
  ↓
Step 2: [Human Input] Collect type-specific information
  Form fields vary based on request type:
    - If "refund": amount, reason
    - If "exchange": item, size, color
    - If "support": issue_description, priority
  ↓
Step 3: Process based on collected information
```

## Approval Workflow Patterns

### Pattern 1: Single Approval

```
Generate → Approve → Execute
```

### Pattern 2: Approval with Revision

```
Generate → Review → Approve/Revise → (Loop if revise) → Execute
```

### Pattern 3: Multi-Stage Approval

```
Generate → Stage 1 Approval → Stage 2 Approval → Execute
```

### Pattern 4: Parallel Approval

```
Generate → [Approver 1] → Evaluate → Execute
           [Approver 2] ↗
           [Approver 3] ↗
```

## Real-World Example

### Complete Approval Workflow: Content Publishing

**Request:**
> "Create a workflow that: generates blog post, gets editor approval, gets legal review, then publishes"

**Workflow:**
```
Step 1: Generate blog post draft
  ↓
Step 2: [Editor Approval] Editor reviews content
  ├─→ If approved: Continue
  └─→ If rejected: Step 3: Revise based on feedback → Back to Step 2
        ↓
    Step 4: [Legal Review] Legal reviews for compliance
      ├─→ If approved: Continue
      └─→ If rejected: Step 5: Request legal changes → Back to Step 1
            ↓
        Step 6: Final formatting
            ↓
        Step 7: [Final Approval] Editor final check
          ├─→ If approved: Step 8: Publish
          └─→ If rejected: Step 9: Make final revisions → Back to Step 7
```

## Best Practices

1. **Clear approval requests**: Explain what's being approved and why
2. **Set timeouts**: Define how long to wait for approval
3. **Provide context**: Include all information needed for decision
4. **Handle timeouts**: Define behavior if approval isn't received
5. **Track approvals**: Log who approved and when
6. **Enable revisions**: Allow approvers to request changes
7. **Notify stakeholders**: Keep relevant people informed

## Approval Step Configuration

### Required Fields

- **Approval type**: Simple yes/no or detailed review
- **Approver**: Who needs to approve
- **Timeout**: How long to wait
- **Notification**: How to notify approver

### Optional Features

- **Comments**: Allow approver to add comments
- **Revisions**: Allow requesting changes
- **Delegation**: Allow approver to delegate
- **Escalation**: Auto-escalate if no response

## Next Steps

- Build an approval workflow
- Explore [Workflow Composition](./workflow-composition.md) for reusable approval patterns
- Check out [Scheduled Automation](../intermediate/scheduled-automation.md) for time-based approvals

