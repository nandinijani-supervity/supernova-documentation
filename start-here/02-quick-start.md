---
title: "Quick Start Guide"
description: "Understand Supervity’s core concepts and run your first agent"
category: "Start Here"
order: 2
---

This guide introduces **how Supervity works**, not just how to click through the UI.

By the end of this page, you will understand:
- what an agent (operator) is
- how jobs are executed
- how auto apps, integrations, approvals, and schedules fit together

All roles share this foundation.

---

## Core Concepts (Read This First)

### Agent (Operator)
An **agent** is an AI operator that:
- understands your intent
- plans how work should be done
- executes jobs using tools and policies

Agents don’t blindly automate. They operate within human-defined boundaries.

---

### Job
A **job** is a single execution of work:
- triggered manually, on a schedule, or via API
- composed of multiple steps
- observable, retryable, and auditable

Every agent action ultimately results in jobs.

---

### Auto App
An **auto app** is a packaged operational capability:
- workflows
- tools
- policies
- approvals
- integrations

Agents use auto apps to perform real work.

---

### Governance Primitives
These apply to **all roles**:
- integrations (what tools agents can use)
- approvals (where humans intervene)
- schedules (when work runs)

---

## Step 1: Sign Up & Workspace Setup

1. Log in to Supervity
2. Set up your workspace
3. Define who can create agents and approve actions

This establishes your execution boundary.

---

## Step 2: Connect an Integration

Agents need tools.

1. Go to **Settings → Integrations**
2. Connect a service (email, crm, chat, storage)
3. Review and approve permissions

Integrations become tools agents can use inside jobs.

---

## Step 3: Create Your First Agent

1. Click **Create Agent**
2. Describe the outcome you want

Example:
> "Send me a daily email summary of new leads"

The agent will:
- plan the job
- select tools
- define execution steps
- surface approval points

Nothing runs without your approval.

---

## Step 4: Test Execution

Run a test job to:
- observe step execution
- inspect inputs and outputs
- verify approvals and retries

This is where trust is built.

---

## Step 5: Operationalize

Choose how jobs should run:
- manual
- scheduled
- API-triggered
- event-driven

Execution always respects governance.

---

## Where to Go Next

- **Business & Ops** → [Common Use Cases](03-key-features.md#common-use-cases)
- **Admins** → [Human Review & Approvals](../guides/human-review.md)
- **Developers** → [API Reference](../reference/api-reference.md)
