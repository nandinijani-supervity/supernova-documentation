---
title: "Tooling & External App Integration"
description: "Register and consume external applications and APIs as agent tools"
category: "Reference"
order: 4
---

# Tooling & External App Integration

This guide explains how to **register and use external applications, APIs, and services as tools** that Supervity AI agents can invoke during execution.

Tools allow agents to:
- call third-party APIs
- interact with internal systems
- perform actions beyond built-in integrations
- extend agent capabilities in a controlled, auditable way

Tools are a core part of how Supervity enables **safe delegation**, not ad-hoc automation.

---

## Tooling Mental Model

In Supervity, **tools are governed actions**.

```

Human
↓ authorizes
Agent
↓ decides when
Workflow
↓ executes how
Tool
↓ acts on
External System

````

Key principles:
- agents decide **when** to use a tool
- workflows define **how** it is executed
- humans define **what tools are allowed**
- the platform enforces **security, limits, and auditability**

---

## What Is a Tool?

A **tool** is an explicit capability an agent is allowed to invoke.

Tools are:
- explicitly registered
- permission-scoped
- schema-defined
- auditable per execution
- reusable across agents and workflows

Agents cannot invent or access tools that are not registered.

---

## Types of Tools

### Built-in Integrations

Predefined tools maintained by Supervity.

Examples:
- email, chat, CRM
- file storage
- productivity tools
- databases and common SaaS platforms

Built-in tools are:
- preconfigured
- secure by default
- versioned and maintained by Supervity

---

### Custom Tools (External APIs)

Custom tools allow you to extend Supervity to any system.

Examples:
- internal company APIs
- third-party SaaS APIs
- microservices
- legacy systems

Custom tools make agents **infrastructure-aware without being infrastructure-coupled**.

---

## Registering a Custom Tool

Custom tools are registered at the **workspace or account level**.

Registration defines *what the tool does*, not *when it is used*.

---

### Required Tool Metadata

When registering a tool, you specify:

- tool name and description  
- API endpoint(s)  
- supported HTTP methods  
- authentication method  
- input parameters and types  
- expected output schema  

This metadata allows agents to:
- reason about tool suitability
- validate inputs safely
- understand outputs deterministically

---

### Example Tool Definition (Conceptual)

```json
{
  "name": "create_invoice",
  "description": "Create an invoice in the billing system",
  "endpoint": "https://api.billing.internal/v1/invoices",
  "method": "POST",
  "auth": "oauth2",
  "inputs": {
    "customer_id": "string",
    "amount": "number",
    "currency": "string"
  }
}
````

Once registered, the tool becomes available for agent planning and execution.

---

## Tool Authentication

Supported authentication methods include:

* OAuth 2.0
* API keys
* bearer tokens
* custom headers

Credential handling guarantees:

* encrypted storage at rest
* least-privilege access
* credential rotation without breaking agents
* revocation at any time

Agents never see raw secrets.

---

## How Agents Use Tools

Agents do not call tools arbitrarily.

During execution:

1. the agent determines a tool is required
2. the platform checks permissions and policies
3. inputs are validated against the schema
4. the tool call is executed
5. outputs are returned to the workflow context

Every tool invocation is:

* deterministic
* logged
* traceable to a specific run

---

## Tool Usage via APIs

Tool invocation is typically **implicit** through agent execution.

Via APIs, you can:

* inspect which tools a workflow uses
* restrict tools per agent or workspace
* override credentials per execution (where allowed)
* audit tool usage programmatically

Tools remain governed even when execution is API-triggered.

---

## Error Handling & Retries

If a tool call fails:

* the error is surfaced with context
* retries occur only when safe
* execution can pause for human review
* failures never disappear silently

Tool failures do not corrupt workflows or agents.

---

## Governance & Safety Controls

Tool usage is governed by:

* workspace-level permissions
* agent configuration
* human-in-command policies
* approval gates for sensitive actions

This prevents:

* unauthorized system access
* accidental destructive operations
* uncontrolled API usage

---

## Common Use Cases

### Internal API Access

* agents call internal services
* execute domain-specific operations
* respect internal auth and policies

---

### SaaS Extension

* integrate unsupported SaaS platforms
* use vendor-specific APIs
* avoid writing custom glue code

---

### Legacy System Automation

* wrap legacy APIs as tools
* let agents interact safely
* modernize execution without rewriting systems

---

## Observability & Auditing

For every tool invocation, Supervity records:

* tool name
* associated agent and workflow run
* inputs (redacted where sensitive)
* outputs
* timestamp and execution status

This supports:

* debugging
* compliance audits
* security reviews
* cost and usage tracking

---

## Security Best Practices

Recommended practices:

* grant minimum required permissions
* isolate credentials per tool
* enable human review for destructive actions
* rotate credentials regularly
* monitor tool usage patterns

---

## Tools + Human-in-Command

Tools can be combined with approvals for high-risk actions.

Example:

```
Agent plans to delete user account
→ execution pauses for approval
→ if approved → tool executes
→ if rejected → execution stops
```

This ensures **powerful tools never run unchecked**.

---

## Where to Go Next

* execute agents → **[Agent Execution APIs](./agent-execution.md)**
* add oversight → **[Human-in-Command APIs](./human-in-command.md)**
* explore endpoints → **[API Reference](./api-reference.md)**

---

Tools turn Supervity into an **extensible AI operations platform** —
open, governable, and production-ready.

```
