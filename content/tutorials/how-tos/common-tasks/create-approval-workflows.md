---
title: "How to Create Approval Workflows"
level: intermediate
duration: 20 minutes
prerequisites: ["getting-started/03-workflow-structure"]
tags: [how-to, approval, human-in-the-loop]
category: how-tos/common-tasks
description: "Step-by-step guide to creating workflows that require human approval"
---

# How to Create Approval Workflows

Learn to build workflows that pause for human approval before proceeding.

## Quick Start

### Step 1: Design Your Approval Process

Identify:
- **What needs approval**: Content, decision, action
- **Who approves**: Individual, team, or multiple approvers
- **Approval criteria**: What makes something approvable

### Step 2: Create the Workflow

**Request Pattern:**
> "Create a workflow that [generates content], sends it for [approval type], and [action if approved/rejected]"

**Example:**
> "Create a workflow that generates a report, sends it for manager approval, and distributes it if approved"

### Step 3: Configure Approval Step

The agent will create an approval step that:
- Pauses workflow execution
- Presents content for review
- Collects approval decision
- Continues based on decision

### Step 4: Define Approval Logic

Specify:
- **Approval type**: Simple yes/no or detailed review
- **Approver**: Who needs to approve
- **Timeout**: How long to wait
- **Actions**: What happens if approved/rejected

### Step 5: Test and Deploy

Test the approval workflow with sample content.

## Common Patterns

### Pattern 1: Simple Approval

**Request:**
> "Create a workflow that generates an email draft and requires approval before sending"

**Workflow:**
```
Step 1: Generate email draft
Step 2: [Approval] Review and approve
  ├─→ Approved: Step 3: Send email
  └─→ Rejected: Step 4: Request revisions
```

### Pattern 2: Multi-Stage Approval

**Request:**
> "Create a workflow that requires approval from manager, then finance"

**Workflow:**
```
Step 1: Generate content
Step 2: [Manager Approval]
  ├─→ Approved: Continue
  └─→ Rejected: Notify and stop
        ↓
    Step 3: [Finance Approval]
      ├─→ Approved: Step 4: Execute
      └─→ Rejected: Notify and stop
```

### Pattern 3: Conditional Approval

**Request:**
> "Create a workflow that only requires approval for high-value items"

**Workflow:**
```
Step 1: Check item value
  ├─→ If > threshold: Step 2: [Approval Required]
  └─→ If <= threshold: Step 3: Process directly
```

## Approval Step Configuration

### Required Information
- **Content to approve**: What's being reviewed
- **Approver**: Who needs to approve
- **Decision options**: Approve, reject, request changes

### Optional Features
- **Comments**: Allow approver to add comments
- **Revisions**: Allow requesting changes
- **Delegation**: Allow approver to delegate
- **Notifications**: How to notify approver

## Best Practices

1. **Clear approval requests**: Explain what's being approved
2. **Provide context**: Include all necessary information
3. **Set timeouts**: Define how long to wait
4. **Handle timeouts**: Define behavior if no response
5. **Track approvals**: Log who approved and when
6. **Enable revisions**: Allow approvers to request changes

## Troubleshooting

### Approval Not Received
- Check approver notifications
- Verify approver access
- Check timeout settings

### Approval Workflow Stuck
- Check for pending approvals
- Verify workflow status
- Review timeout configuration

## Next Steps

- Learn more: [Human Approval Workflows](../library/advanced/human-approval-workflows.md)
- Advanced: [Complex Branching Logic](../library/advanced/complex-branching.md)
- Examples: See approval workflow examples

