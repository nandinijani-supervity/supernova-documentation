---
title: "Integrations Overview"
description: "Connect external systems and services as tools agents can use"
category: "Product Guide"
order: 40
---

# Integrations Overview

In Supervity, **integrations are tools that agents are allowed to use to take action**.

They enable agents to:
- read data from external systems
- write or update records
- trigger actions across tools
- coordinate work across platforms

Integrations are not scripts or static connectors.  
They are **governed capabilities** enforced by the platform.

---

## How Integrations Fit Into the Platform

```

human
↓ defines intent
agent
↓ decides when
workflow
↓ executes safely
integration / tool
↓ performs action
external system

```

- agents decide **when** a tool is needed  
- workflows define **how** it executes  
- the platform enforces **security, permissions, and auditability**

---

## Types of Integrations

### Built-In Integrations

Built-in integrations are maintained and supported by Supervity.

They are:
- preconfigured
- secure by default
- continuously updated
- optimized for agent execution

Examples include:
- communication and messaging tools
- file storage and document systems
- crm and business applications
- productivity tools
- dev and ops platforms

---

### Custom Integrations (External Tools & APIs)

For systems not available out of the box, you can extend Supervity by:

- registering rest apis as tools
- connecting internal services
- wrapping legacy systems
- exposing custom business actions

Once registered, these tools behave exactly like built-in integrations.

→ learn more: **[Tooling & External APIs](../reference/tooling.md)**

---

## Common Integration Categories

### Communication & Messaging
- gmail, outlook
- slack, microsoft teams
- sms and notification services

**typical actions**
- send messages
- read incoming communication
- notify stakeholders

---

### File Storage & Documents
- google drive
- onedrive
- dropbox
- enterprise file systems

**typical actions**
- upload and download files
- organize folders
- process documents

---

### CRM & Sales Systems
- salesforce
- hubspot

**typical actions**
- create or update leads
- sync contacts
- route opportunities

---

### Productivity & Data
- google sheets
- airtable
- excel-compatible services

**typical actions**
- read and write rows
- generate reports
- maintain datasets

---

### Project & Dev Tools
- jira
- asana
- github
- gitlab

**typical actions**
- create tasks or issues
- track progress
- trigger workflows from events

---

## Setting Up Integrations

### Step 1: Connect an Integration

1. go to **settings → integrations**
2. select the service
3. authenticate (oauth, api key, or service account)
4. grant required permissions

Integrations are scoped to the workspace and governed centrally.

---

### Step 2: Use Integrations in Agents & Workflows

Once connected, integrations become available:
- during agent planning
- as workflow steps
- as triggers or actions
- inside conditional logic

Agents automatically consider available integrations when planning execution.

---

## Authentication & Security

Supported authentication methods:
- oauth 2.0 (preferred)
- api keys
- service accounts
- custom headers (advanced)

Security guarantees:
- credentials encrypted at rest
- least-privilege scopes
- token rotation support
- immediate access revocation

→ see details: **[Security & Privacy](../guides/security-privacy.md)**

---

## Managing Integrations

### View Connected Integrations

For each integration, you can inspect:
- connection status
- permissions granted
- last used timestamp
- associated workflows and agents

---

### Reconnect or Rotate Credentials

If credentials expire:
1. you receive a notification
2. reconnect in **settings**
3. no workflow or agent changes required

---

### Disconnect Integrations

Disconnecting an integration:
- immediately revokes access
- prevents future executions
- does not delete workflows or agents

Any affected runs fail safely with clear errors.

---

## Integration Governance

Integrations respect platform-level controls:
- role-based access
- workspace permissions
- approval gates for sensitive actions
- full execution logs

Admins can restrict which integrations agents are allowed to use.

---

## Observability & Auditing

Every integration call is logged:
- which agent requested it
- which workflow step executed it
- inputs and outputs (redacted if sensitive)
- success or failure
- timestamp

This supports debugging, compliance, and cost tracking.

---

## Best Practices

### Design Safely
- grant minimum required permissions
- separate test and production integrations
- require human approval for destructive actions

### Design Reliably
- handle rate limits explicitly
- batch requests where possible
- monitor failures early

### Design for Scale
- prefer built-in integrations when available
- reuse tools across workflows
- monitor usage patterns over time

---

## Who This Is For

**business users**
- connect everyday tools
- automate work without writing code

**operations & it teams**
- govern access
- standardize integrations

**developers**
- extend supervity with apis
- embed agent capabilities into systems

---

## Where to Go Next

- see integrations in execution → **[Workflows Explained](workflows-explained.md)**
- understand decision-making → **[Understanding Agents](agents-overview.md)**
- register custom tools → **[Tooling & External APIs](../reference/tooling.md)**
- trigger programmatically → **[API Reference](../reference/api-reference.md)**

---

Integrations turn Supervity into a **connected execution layer** for agent-driven work.
```
