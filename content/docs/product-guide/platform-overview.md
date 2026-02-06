---
title: "Platform Overview"
description: "How Supervity works — core concepts, execution model, and governance"
category: "Product Guide"
order: 10
---

# Platform Overview

Supervity is an **agentic operations platform** that allows teams to delegate work to AI while keeping humans firmly in control.

This page explains:
- the core building blocks of the platform
- how work is planned, executed, and governed
- how humans, agents, and tools interact as a system

Every role in Supervity — business, ops, admin, or developer — operates on the same underlying model.

---

## The Supervity Mental Model

At a high level, work in Supervity flows through four layers:

```

Human (intent & authority)
↓
Agent / Operator (planning & decision-making)
↓
Job / Workflow (execution graph)
↓
Tools & Integrations (actions)

```

Each layer has a clear responsibility and boundary.

---

## Core Building Blocks

### Humans (Intent & Authority)

Humans define:
- what outcome is desired
- which actions require approval
- which systems agents may access
- escalation and override rules

Humans do not micro-manage execution, but they **retain authority at all critical decision points**.

---

### Agents / Operators (Planning & Orchestration)

Agents are **AI-powered operators** responsible for:

- understanding human intent
- reasoning about how work should be done
- planning multi-step execution
- deciding when to request human input
- resuming work after approvals

Agents do not blindly automate tasks.  
They **plan, validate, and adapt** within defined policies.

→ Deep dive: **[Understanding Agents](agents-overview.md)**

---

### Jobs & Workflows (Execution)

A **job** is a single execution of work initiated by an agent.

A **workflow** is the executable structure that defines how that job runs.

Workflows define:
- step order and dependencies
- parallel vs sequential execution
- conditional branching
- retries, timeouts, and fallbacks

Key properties:
- deterministic execution
- visual and inspectable
- fully auditable
- reusable across runs

Agents plan work.  
Jobs execute that plan through workflows.

→ Deep dive: **[Workflows Explained](workflows-explained.md)**

---

### Auto Apps (Packaged Capabilities)

An **auto app** is a packaged operational capability that combines:
- workflows
- tools and integrations
- policies and approvals
- execution rules

Auto apps allow agents to perform real-world work safely and consistently.

They are the unit through which operational intelligence is reused and scaled.

---

### Tools & Integrations (Action Layer)

Tools are **capabilities agents are allowed to use** during execution.

They include:
- built-in integrations (email, crm, chat, storage)
- external APIs
- internal systems
- custom registered tools

Agents decide *when* to use a tool.  
The platform governs *how* the tool is accessed and audited.

→ Deep dive: **[Integrations Overview](integrations-overview.md)**

---

### Human-in-Command (Governance Layer)

Human-in-Command ensures AI autonomy remains controlled.

It enables:
- approvals and rejections
- manual inputs
- decision overrides
- escalation paths
- timeout handling

When a human review step is reached:
- the job pauses safely
- context is preserved
- execution resumes only after a decision

→ Deep dive: **[Human Review & Approvals](../guides/human-review.md)**

---

## How Everything Works Together

### Example: Expense Approval Automation

**Goal:** Automate expense processing with manager oversight.

1. **Human** defines intent  
   > “Process expenses, but require approval above $1,000.”

2. **Agent** plans the job  
   - extract expense data  
   - evaluate amount  
   - route for approval if required  

3. **Workflow** executes  
   - runs steps deterministically  
   - applies conditional logic  
   - pauses during review  

4. **Human** approves or rejects  
5. **Agent** resumes execution  
6. **Tools** process reimbursement and notify stakeholders  

This pattern applies to all use cases, regardless of role.

---

## Execution Modes

Jobs can be triggered via:

- **Manual runs** (UI)
- **Schedules** (time-based)
- **Webhooks** (event-driven)
- **APIs** (programmatic)

This allows Supervity to function as both:
- a user-facing automation platform
- a backend execution engine

→ Learn more: **[Scheduling & Automation](scheduling-automation.md)**

---

## Roles & Access Control

Supervity uses role-based access control to enforce governance:

- **Admins**  
  Configure permissions, tools, and policies

- **Editors**  
  Create and modify agents and workflows

- **Runners**  
  Execute jobs

- **Viewers**  
  Observe runs and logs

All actions are logged and auditable.

---

## Observability & Control

Every job execution provides:
- real-time status
- step-level logs
- input and output visibility
- failure context
- retry and timeout history

Agents are **inspectable systems**, not black boxes.

---

## Platform Navigation

### Key Areas

**Chat**
- define intent
- interact with agents
- iterate on plans

**My Agents**
- saved agents and auto apps
- execution history
- versioning

**Schedule**
- time-based automation
- pause and resume
- upcoming runs

**Human Review**
- pending approvals
- review history
- delegation

**Integrations**
- connect services
- manage credentials
- audit access

---

## Who This Platform Is For

**Business Teams**
- delegate operational work
- retain control via approvals

**Operations & IT**
- standardize execution
- enforce governance and reliability

**Developers & Platform Teams**
- trigger agents programmatically
- extend capabilities via tools
- embed Supervity into products

---

## Where to Go Next

- How agents reason → **[Understanding Agents](agents-overview.md)**
- How execution works → **[Workflows Explained](workflows-explained.md)**
- How automation runs → **[Scheduling & Automation](scheduling-automation.md)**
- How to integrate → **[API Reference](../reference/api-reference.md)**

---

Supervity is not just automation.  
It is a **controlled delegation system** for AI-powered operations.
```
