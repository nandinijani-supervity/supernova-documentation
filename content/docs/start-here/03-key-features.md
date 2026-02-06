---
title: "Key Features"
description: "Explore the core capabilities that power AI-driven operations in Supervity"
category: "Start Here"
order: 3
---

This page explains the **core capabilities of Supervity**, organized by how different users typically use the platform.

If you came here from:
- **Quick Start (Business User)** → focus on agent behavior and use cases  
- **Ops/Admin path** → focus on governance, execution, and monitoring  
- **Developer path** → focus on APIs, integrations, and extensibility  

You don’t need to learn everything at once — follow the sections relevant to your role.

---

## Overview

Supervity combines:
- AI agents that plan and execute work autonomously  
- Human-in-command controls for safety and governance  
- A powerful execution engine with APIs and integrations  

Together, these capabilities allow teams to **delegate operational work to AI** without losing visibility or control.

---

## Conversational Agent Creation

This is the foundation of Supervity.

Instead of configuring steps manually, you describe **what outcome you want**.

**Example:**
> "When someone fills out the contact form, create a lead in Salesforce and notify the sales team on Slack."

The agent:
- Understands intent  
- Plans the workflow  
- Selects tools and actions  
- Surfaces the plan for approval  

This is the primary entry point for **Business Users** and the abstraction layer for **Developers and Ops teams**.

---

## Common Use Cases
<a id="common-use-cases"></a>

If you are a **Business User**, start here.

### AI-Managed Email Operations
- Daily digest emails  
- Automated responses  
- Email-to-CRM workflows  
- Newsletter distribution  

### File & Document Operations
- Automatic backups  
- File organization  
- Format conversion  
- Cross-platform sync  

### Business Process Automation
- Lead qualification  
- Approval workflows  
- Task assignment  
- Report generation  

### Data Operations
- Data extraction  
- Format transformation  
- Multi-source aggregation  
- Scheduled exports  

These use cases are implemented by **agents**, not static workflows.

---

## Visual Workflow Oversight

Supervity automatically generates workflows.  
The visual builder exists for **inspection, refinement, and supervision**.

Capabilities include:
- Graph-based execution visualization  
- Real-time step status  
- Input/output inspection  
- Detailed execution logs  

This is especially important for **Ops/Admin teams** managing reliability and scale.

---

## Human Review & Approvals

Human oversight is a **first-class capability**, not an afterthought.

You can define:
- Approval steps for critical actions  
- Manual inputs when judgment is required  
- Multi-level approvals and escalation rules  
- Timeouts and fallback behavior  

Use cases include:
- Financial approvals  
- Content moderation  
- Compliance workflows  

→ **Next for Ops/Admins:**  
[Human Review & Approvals](../guides/human-review.md)

---

## Scheduling & Automation

Agents can run in multiple execution modes:

- Manual runs (on demand)  
- Scheduled execution (daily, weekly, cron)  
- Event-based triggers  
- API-driven execution  

Scheduling controls *when* agents operate — not *how* they work.

→ **Next for Ops/Admins:**  
[Scheduling & Automation](../product-guide/scheduling-automation.md)

---

## Execution History & Logs
<a id="execution-history--logs"></a>

Supervity provides full transparency into agent execution:

- Complete run history  
- Step-level logs and timings  
- Success/failure metrics  
- Search and filtering  
- Exportable audit logs  

This is critical for:
- Debugging  
- Audits  
- Reliability analysis  

---

## Intelligent Error Handling

Agents handle failure gracefully:

- Automatic retries with backoff  
- Timeouts to prevent hanging  
- Error notifications  
- Fallback paths  
- Detailed error context  

Errors pause execution when human intervention is required.

---

## Data Transformation & Logic

Agents can:
- Convert formats (JSON, CSV, XML)  
- Extract structured data from text  
- Apply calculations and formulas  
- Combine data from multiple sources  
- Apply conditional routing  

This powers complex operations without manual glue code.

---

## Parallel Execution

Independent steps can run simultaneously to improve speed:

- Faster end-to-end execution  
- Efficient resource use  
- Better user experience  

Parallelism is handled automatically where possible.

---

## Team Collaboration & Versioning

Teams can collaborate safely:

- Shared workspaces  
- Role-based access (Admin, Editor, Viewer, Runner)  
- Workflow version history  
- Rollback support  
- Change audit trails  

---

## API & Webhooks
<a id="api--webhooks"></a>

If you are an **IT or Developer user**, this is your next stop.

Supervity exposes:
- REST APIs for workflows, runs, schedules, chats, and forms  
- Webhooks for event-driven execution  
- Secure authentication and token-based access  

APIs allow you to:
- Trigger agents programmatically  
- Embed Supervity into external systems  
- Integrate with existing platforms  

→ **Next for Developers:**  
[API Reference](../reference/api-reference.md)  
[Integrations Overview](../product-guide/integrations-overview.md)

---

## Platform Capabilities

### Performance
- Fast step execution  
- Concurrent workflows  
- High availability  

### Security
- Encrypted connections  
- Secure credential storage  
- MFA and SSO  
- Compliance-ready architecture  

→ **Next:**  
[Security & Privacy](../guides/security-privacy.md)

---

## Where to Go Next

### 🧑‍💼 Business Users
- [Common Use Cases](#common-use-cases)  
- [Build Your First Workflow](/u/alpha/tutorials/getting-started/02-first-workflow)

### ⚙️ Ops & Admin Teams
- [Human Review & Approvals](../guides/human-review.md)  
- [Scheduling & Automation](../product-guide/scheduling-automation.md)  
- [Execution Logs](#execution-history--logs)

### 🧑‍💻 IT & Developers
- [API & Webhooks](#api--webhooks)  
- [API Reference](../reference/api-reference.md)  
- [Integrations Overview](../product-guide/integrations-overview.md)

---

Supervity’s features are designed to work together as a system —  
**agents execute, humans govern, and teams scale with confidence**.
