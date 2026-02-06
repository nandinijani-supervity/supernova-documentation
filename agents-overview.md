---
title: "Understanding Agents"
description: "What Supervity agents are, how they operate, and how they execute work"
category: "Product Guide"
order: 20
---

# Understanding Agents

In Supervity, **agents are AI-powered operators** responsible for planning, executing, and supervising work on behalf of humans.

Agents do not simply respond to prompts.  
They act as **decision-making systems** that operate within clearly defined permissions, policies, and human controls.

They are the primary abstraction through which all work in Supervity is delegated.

---

## What Agents Are (and Aren’t)

### Agents are:

- Autonomous but governed
- Capable of multi-step reasoning
- Responsible for planning execution
- Able to use tools and integrations
- Designed to pause for human input
- Fully observable and auditable

### Agents are not:

- Simple chatbots
- Prompt-only assistants
- Static workflows
- Hardcoded scripts
- Black-box automation

Agents reason first, execute second.

---

## The Agent Execution Model

Agents operate through a consistent lifecycle that applies to all roles and use cases.

### 1. Intent Understanding

A human defines *what outcome is desired*.

Example:
> “Every weekday, review new support tickets and escalate urgent ones.”

The agent:
- interprets intent
- identifies required systems
- detects missing information
- asks clarifying questions when needed

No execution begins at this stage.

---

### 2. Planning & Reasoning

Once intent is clear, the agent constructs a plan that defines:

- triggers (schedule, event, API)
- steps required to complete the job
- conditional logic and branching
- approval and review checkpoints
- retry and failure behavior

This plan is:
- visible
- reviewable
- modifiable

Humans always approve the plan before execution.

---

### 3. Jobs & Workflows

When execution begins, the agent creates a **job**.

- A job represents a single execution of work.
- The job runs through a deterministic **workflow**.
- The workflow defines execution order, dependencies, and logic.

Agents **plan jobs**.  
Workflows **execute jobs**.

→ Learn more: **[Workflows Explained](workflows-explained.md)**

---

### 4. Tool & Integration Usage

During execution, agents may use tools to act on systems.

Tools include:
- built-in integrations (email, CRM, files, chat)
- registered external APIs
- internal services
- custom tools

Tool usage is:
- explicitly permissioned
- scoped per workspace
- logged and auditable

Agents decide *when* to use tools.  
The platform governs *how* tools are accessed.

→ Learn more: **[Integrations Overview](integrations-overview.md)**

---

### 5. Human-in-Command Oversight

For sensitive or high-impact steps, agents pause execution.

Examples:
- approval required
- manual input needed
- exception handling
- decision escalation

When a review step is reached:
- the job pauses safely
- full context is preserved
- execution resumes only after a human decision

→ Learn more: **[Human Review & Approvals](../guides/human-review.md)**

---

### 6. Execution, Monitoring & Adaptation

Once approved, agents:
- execute steps sequentially or in parallel
- retry safely on failure
- emit logs, metrics, and events
- surface progress and outputs in real time

Jobs can be triggered via:
- manual runs
- schedules
- webhooks
- APIs

Agents adapt execution based on outcomes and human input.

---

## What Agents Can Do

### Orchestrate Workflows

- build multi-step execution plans
- coordinate across multiple systems
- apply conditional logic
- handle failures gracefully

---

### Process Data & Content

- extract structured data
- transform formats
- summarize or generate content
- route outputs downstream

---

### Support Decision-Making

- evaluate conditions
- classify or score inputs
- recommend actions
- defer final authority to humans

---

### Operate via APIs

- act as backend execution primitives
- trigger jobs programmatically
- support headless operation
- embed into external systems

→ See details: **[API Reference](../reference/api-reference.md)**

---

## Agent Ownership & Access Control

Agents exist within a workspace and respect role-based access.

- **Admins**  
  Configure permissions, tools, and policies

- **Editors**  
  Create and modify agents and workflows

- **Runners**  
  Execute jobs

- **Viewers**  
  Observe runs and logs

Every action is logged and auditable.

---

## Saved Agents & Reuse

Agents are persistent system entities.

They can be:
- saved and reused
- shared across teams
- scheduled to run automatically
- triggered externally
- versioned and rolled back

Agents evolve over time.  
They are not one-off automations.

---

## Security & Governance

Agents operate under strict controls:

- least-privilege permissions
- encrypted credentials
- policy-based restrictions
- approval gates
- full audit trails

An agent cannot act outside what a human has explicitly allowed.

---

## Who Uses Agents?

**Business Users**
- delegate operational work
- stay in control through approvals

**Operations Teams**
- standardize execution
- enforce governance and reliability

**Developers & Platform Teams**
- use agents as execution units
- integrate via APIs
- extend capabilities with tools

---

## Where to Go Next

- Understand execution → **[Workflows Explained](workflows-explained.md)**
- Add governance → **[Human Review & Approvals](../guides/human-review.md)**
- Integrate systems → **[Integrations Overview](integrations-overview.md)**
- Trigger programmatically → **[API Reference](../reference/api-reference.md)**

---

Agents are the **core system primitive** in Supervity.  
Everything else exists to support how they plan, execute, and collaborate with humans.
```

