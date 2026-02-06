---
title: "Workflows Explained"
description: "How workflows are structured, executed, and monitored in Supervity"
category: "Product Guide"
order: 30
---

# Workflows Explained

In Supervity, a **workflow** is the executable structure that defines *how work runs*.

It specifies:
- what actions are performed
- in what order
- under what conditions
- with what failure and retry behavior

Workflows are:
- deterministic
- visual
- auditable
- reusable

They do **not** reason or make decisions.  
That responsibility belongs to agents.

---

## Workflow vs Agent (Important Distinction)

| Agents | Workflows |
|------|----------|
| Understand intent | Execute instructions |
| Reason and plan | Follow defined logic |
| Decide what should happen | Define how it happens |
| Pause for human judgment | Wait but do not decide |
| Conversational | Deterministic |

Agents **plan and control** execution.  
Workflows **execute safely and predictably**.

→ Learn more: **[Understanding Agents](agents-overview.md)**

---

## Core Workflow Concepts

### Steps

A **step** is a single executable action.

Examples:
- send an email
- call an API
- read or write a file
- transform data
- request human approval

Each step:
- receives inputs
- produces outputs
- succeeds or fails
- emits logs and timing data

---

### Connections & Dependencies

Steps can be connected in multiple ways.

#### Sequential
```

Step A → Step B → Step C

```

#### Parallel
```

Step A
├─ Step B
├─ Step C
└─ Step D

```

#### Conditional
```

If condition true → Step B
Else → Step C

```

Dependencies ensure correct execution order and data flow.

---

### Triggers

Triggers define **when a workflow execution begins**.

Supported triggers:
- manual (UI or API)
- scheduled (time-based)
- webhook (event-driven)
- integration events

Triggers start **runs (jobs)**, not workflows themselves.

---

### Runs, Jobs & Executions

- A **workflow** defines structure
- A **run (job)** is a single execution of that workflow

Each run:
- has its own inputs
- produces its own outputs
- maintains its own logs
- moves independently through execution states

---

### Variables & Data Flow

Data moves through workflows via variables:

- **inputs** — provided at run start
- **step outputs** — results of execution
- **transformed data** — computed or reformatted values

Variables are:
- typed
- scoped per run
- traceable step by step

---

## Workflow Patterns

### Sequential Workflows

Best for linear processes:

```

1. receive form submission
2. validate input
3. create crm record
4. send confirmation email

```

---

### Parallel Workflows

Best for independent actions:

```

on order placed:
├─ send confirmation email
├─ update inventory
├─ notify finance
└─ log analytics

```

---

### Conditional Workflows

Best for routing and decision outcomes:

```

if ticket priority = high:
→ page on-call engineer
else:
→ add to support queue

```

---

### Human-in-the-Loop Workflows

Best for governance and compliance:

```

1. generate contract draft
2. pause for legal approval
3. if approved → send to customer
4. if rejected → notify requester

```

→ Deep dive: **[Human Review & Approvals](../guides/human-review.md)**

---

## Workflow Execution Lifecycle

Each run moves through a defined lifecycle:

1. **Triggered**
2. **Running**
3. **Waiting** (human review or delay)
4. **Completed**
5. **Failed**
6. **Cancelled**

All state transitions are logged and observable.

---

## Monitoring & Observability

For every run, you can inspect:

- step-by-step timeline
- inputs and outputs
- execution duration
- retry attempts
- failure reasons

This makes workflows **debuggable and auditable**, not opaque.

---

## Error Handling & Reliability

Workflows support:

- automatic retries with backoff
- step and workflow timeouts
- fallback execution paths
- failure notifications
- safe cancellation

Failures are explicit and visible.  
Nothing fails silently.

---

## Advanced Workflow Patterns

### Loops & Iteration

```

for each invoice:
→ validate
→ process
→ archive

```

---

### Nested Workflows

```

main workflow:
→ fetch new leads
→ run "lead qualification" workflow
→ generate summary

```

---

### Data Transformation

Built-in steps allow you to:
- parse json or xml
- format data
- filter lists
- compute values
- merge multiple sources

---

## Security & Governance

Workflows inherit platform-wide controls:

- role-based access
- least-privilege integrations
- approval gates
- audit logs
- version history

Every change is tracked.

---

## Best Practices

### Design for Clarity
- use descriptive step names
- keep workflows focused
- document assumptions

### Design for Reliability
- validate inputs early
- handle failure paths explicitly
- avoid unnecessary branching

### Design for Scale
- use parallel execution
- batch operations where possible
- monitor execution trends

---

## Who This Is For

**Business Users**
- understand what runs and when

**Operations Teams**
- standardize and govern execution

**Developers**
- treat workflows as execution primitives

---

## Where to Go Next

- delegate decisions → **[Understanding Agents](agents-overview.md)**
- automate over time → **[Scheduling & Automation](scheduling-automation.md)**
- extend execution → **[API Reference](../reference/api-reference.md)**
- add governance → **[Human Review & Approvals](../guides/human-review.md)**

---

Workflows are the **execution backbone** of Supervity —  
predictable, inspectable, and safe by design.
```
