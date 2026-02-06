---
title: "Human-in-Command APIs"
description: "APIs for approvals, human review, and agent interruption & resumption"
category: "Reference"
order: 3
---

# Human-in-Command APIs

This guide documents the APIs used to **embed human oversight into Supervity AI agent execution**.

Use these APIs when you want to:
- surface approvals outside Supervity
- embed review actions in external applications
- pause, approve, reject, or resume agent execution
- build custom command centers or approval dashboards

These APIs enable both:
- **Agent → Human (A2H)** interaction
- **Human → Agent (H2A)** control

---

## Execution Model

Human-in-Command is implemented through **interruptible execution**.

At runtime:
- an agent may pause execution
- a human decision is required
- execution resumes based on that decision

From an API perspective:
- a paused run exposes a **review object**
- humans act on that object
- the agent resumes with the submitted payload

Execution is deterministic and auditable at every step.

---

## Human Review Objects

Human review is represented as a **User Form**.

A user form encapsulates:
- execution context from the agent
- the decision required from a human
- allowed actions (approve, reject, modify, etc.)
- metadata linking back to the paused run

A form exists **only while execution is waiting**.

---

## Listing Pending Reviews

### Endpoint

**GET** `/api/v1/user-forms`

Query parameters:
- `page`
- `limit`
- `search` (optional)

Example:

```bash
curl "$SUPERVITY_API_URL/api/v1/user-forms?page=1&limit=20" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN"
````

Typical response:

```json
{
  "items": [
    {
      "formId": "form_123",
      "runId": "run_abc123",
      "workflowId": "workflow_456",
      "status": "pending",
      "createdAt": "..."
    }
  ]
}
```

This endpoint is commonly used to:

* power approval dashboards
* build command center queues
* detect pending human actions

---

## Fetching a Review Form

### Endpoint

**GET** `/api/v1/user-forms/:formId`

Example:

```bash
curl "$SUPERVITY_API_URL/api/v1/user-forms/form_123" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN"
```

Typical response:

```json
{
  "formId": "form_123",
  "runId": "run_abc123",
  "html": "<form>...</form>",
  "schema": {
    "fields": [
      {
        "name": "decision",
        "type": "enum",
        "options": ["approve", "reject"]
      },
      {
        "name": "comments",
        "type": "text"
      }
    ]
  }
}
```

You may:

* render the provided HTML directly
* build a custom UI using the schema
* embed the form into an external system

---

## Submitting a Review Decision

### Endpoint

**POST** `/api/v1/user-forms/:formId/submit`

Request body (JSON):

```json
{
  "decision": "approve",
  "comments": "Looks good. Proceed."
}
```

Example:

```bash
curl -X POST "$SUPERVITY_API_URL/api/v1/user-forms/form_123/submit" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "decision": "approve",
    "comments": "Looks good. Proceed."
  }'
```

---

## What Happens After Submission

Once a review form is submitted:

1. input is validated
2. decision is recorded
3. agent execution resumes
4. decision payload becomes part of run context
5. downstream workflow steps execute accordingly

All actions are:

* logged
* auditable
* traceable to the reviewing user

---

## Execution States & Interrupts

When execution requires human input, the run enters:

```
status = "waiting"
reason = "human_review"
```

You can observe this via:

**GET** `/api/v1/workflow-runs/:runId`

Execution remains paused until the form is submitted.

---

## Agent → Human (A2H) Events

In streaming or interactive contexts, human review triggers an **interrupt event**.

Example event payload:

```json
{
  "type": "interrupt",
  "runId": "run_abc123",
  "formId": "form_123",
  "message": "Approval required before sending email"
}
```

This is how:

* UIs display approval prompts
* external systems detect required intervention
* command centers surface actionable items

---

## Human → Agent (H2A) Resumption

Submitting a form automatically resumes execution.

No explicit “resume” API call is required.

If a decision results in rejection:

* execution may stop
* or branch into an alternate path
  (based on workflow design)

---

## External Command Centers

These APIs enable enterprise-grade tooling such as:

* centralized approval dashboards
* operational command centers
* compliance and audit portals
* embedded approval widgets

Typical pattern:

1. list pending review forms
2. fetch review context
3. render decision UI
4. submit decision
5. monitor execution resumption

---

## Security & Permissions

Human-in-Command APIs are governed by:

* user roles
* workspace permissions
* token scopes

Only authorized users can:

* view review forms
* submit decisions
* influence execution

All actions are attributed and logged.

---

## Common Use Cases

### Manager Approval Outside Supervity

* agent pauses execution
* backend fetches review form
* manager approves in internal app
* agent resumes automatically

---

### Compliance Review Dashboard

* centralized queue of pending reviews
* SLA tracking and escalation
* audit-ready decision history

---

### Human Override

* reviewer modifies values
* agent continues with corrected inputs
* decision becomes part of execution context

---

## Where to Go Next

* agent execution → **[Agent Execution APIs](./agent-execution.md)**
* tool registration → **[Tooling & External Apps](./tooling.md)**
* core endpoints → **[API Reference](./api-reference.md)**

---

Human-in-Command APIs ensure AI agents operate **with autonomy, but never without accountability**.

```

