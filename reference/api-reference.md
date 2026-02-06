---
title: "API Reference"
description: "API reference for agent execution, workflows, schedules, chats, and human review"
category: "Reference"
order: 1
---

# API Reference

This reference documents the **Supervity APIs** used to programmatically interact with the platform.

These APIs allow you to:
- execute AI agents and workflows
- monitor execution runs and schedules
- interact with agents via chat and streaming
- embed **human-in-command** approval flows
- access execution artifacts such as logs, forms, and attachments

If you are coming from **Key Features → API & Webhooks**, this is the canonical technical contract.

---

## API Model Overview

Supervity exposes an **agent-driven execution model**.

Core objects you interact with via APIs:

- **Agent** — plans and governs execution
- **Workflow** — executable representation of the plan
- **Run** — a single execution of a workflow
- **Human review form** — approval or input checkpoint
- **Chat thread** — conversational and streaming interaction
- **Object** — files and attachments used during execution

Most APIs are used to **trigger, observe, or govern execution**.

---

## Base URL & Authentication

### Base URL

All endpoints are relative to your Supervity API base URL  
(provided by your Supervity admin or deployment team):

```bash
export SUPERVITY_API_URL="https://api.your-supervity-domain.example.com"
````

---

### Authentication

All requests require a bearer token.

```bash
export SUPERVITY_TOKEN="YOUR_ACCESS_TOKEN"
```

Include the token in every request:

```bash
-H "Authorization: Bearer $SUPERVITY_TOKEN"
```

Tokens control:

* which workflows can be executed
* which runs can be inspected
* which approvals can be acted upon

---

## API Conventions

### Pagination

List endpoints typically support:

* `page` (default: 1)
* `limit` (endpoint-specific)

---

### Content Types

* **JSON APIs**
  Use `Content-Type: application/json`

* **Execution & Streaming APIs**
  Use `multipart/form-data` (via `curl -F ...`)

---

## Workflow & Agent Management APIs

These APIs are used to **inspect and manage agent-generated workflows**.

---

### List workflows

**GET** `/api/v1/workflows`

Query params:

* `page`
* `limit`
* `search` (optional)

```bash
curl "$SUPERVITY_API_URL/api/v1/workflows?page=1&limit=20&search=invoice" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN"
```

---

### Get workflow by ID

**GET** `/api/v1/workflows/:workflowId`

```bash
curl "$SUPERVITY_API_URL/api/v1/workflows/123" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN"
```

---

### Delete workflow

**DELETE** `/api/v1/workflows/:workflowId`

```bash
curl -X DELETE "$SUPERVITY_API_URL/api/v1/workflows/123" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN"
```

Deleting a workflow does not affect past runs or audit history.

---

## Scheduling APIs

Scheduling controls **when workflows execute**, not how they behave.

---

### Pause or resume a schedule

**PUT** `/api/v1/workflows/:workflowId/schedule`

```json
{ "paused": true }
```

---

### Delete a schedule

**DELETE** `/api/v1/workflows/:workflowId/schedule`

This removes the schedule but keeps the workflow intact.

---

### Parse a natural-language schedule

**POST** `/api/v1/workflows/:workflowId/schedule/parse`

```json
{ "input": "Every weekday at 9am" }
```

Returns a normalized schedule expression.

---

### Get upcoming scheduled runs

**GET** `/api/v1/workflows/:workflowId/upcoming-runs`

---

## Execution & Run APIs

Runs represent **individual executions** of an agent workflow.

---

### List workflow runs

**GET** `/api/v1/workflow-runs`

Common query params:

* `workflowId`
* `status`
* `page`
* `limit`

---

### Get workflow run by ID

**GET** `/api/v1/workflow-runs/:runId`

Returns:

* run status
* step-level activity runs
* inputs and outputs
* error context (if any)

---

### Cancel workflow runs

**POST** `/api/v1/workflow-runs/cancel`

Body can include:

* `workflowId` (cancel active runs)
* or `runIds` (cancel specific runs)

---

### Dashboard counts per workflow

**GET** `/api/v1/workflow-runs/dashboard/:workflowId`

Used for UI dashboards and monitoring systems.

---

### Execute a workflow (agent execution)

**POST** `/api/v1/workflow-runs/execute`

This endpoint triggers **agent-backed execution**.

**multipart/form-data fields:**

* `workflowId` (required)
* `inputs[FIELD_NAME]`
* `envs[ENV_NAME]` (optional execution overrides)

Example:

```bash
curl -X POST "$SUPERVITY_API_URL/api/v1/workflow-runs/execute" \
  -H "Authorization: Bearer $SUPERVITY_TOKEN" \
  -F "workflowId=123" \
  -F "inputs[query]=Summarize this document"
```

Execution always respects:

* approval gates
* permissions
* human-in-command policies

---

## Chat & Streaming APIs (Agent Interaction)

These APIs support **conversational and streaming interaction** with agents.

---

### Create a chat thread

**POST** `/api/v1/chats`

Response:

```json
{ "threadId": "thread_..." }
```

---

### Stream messages to an agent (SSE)

**POST** `/api/v1/chats/:threadId/messages`

Used for:

* conversational interaction
* planner visibility
* streaming execution updates
* human-in-command interrupts

Common stream event types:

* `message`
* `workflow`
* `workflow-run`
* `activity-run`
* `interrupt`
* `resume`
* `notification`

---

## Human Review APIs (Human-in-Command)

These APIs allow **external systems** to participate in approval flows.

---

### List pending review forms

**GET** `/api/v1/user-forms`

---

### Fetch a rendered review form

**GET** `/api/v1/user-forms/:formId`

Typical response:

```json
{ "html": "<form>...</form>" }
```

Forms can be embedded in:

* internal tools
* approval dashboards
* ops command centers

Submitting a form resumes execution automatically.

---

## Objects & Attachments

Objects represent files exchanged during execution.

---

### Download an attachment

**GET** `/api/v1/objects/download`

Query params:

* `objectKey`
* `type` (e.g. `attachment`)

---

## Notes on Extensibility

Depending on deployment, Supervity may also expose APIs for:

* registering external tools
* integrating custom services
* advanced policy or governance controls

These are documented in dedicated reference sections when enabled.

---

## Where to Go Next

* understand execution → **[Workflows Explained](/docs/product-guide/workflows-explained)**
* see agents in action → **[Examples](/u/alpha/tutorials)**
* add governance → **[Human Review & Approvals](/docs/guides/human-review)**

---

These APIs let you **embed Supervity agents into your systems**
while preserving control, observability, and human oversight.

```
