---
title: "Scheduling & Automation"
description: "Trigger workflow runs automatically using schedules, events, and APIs"
category: "Product Guide"
order: 50
---

# Scheduling & Automation

Scheduling in Supervity allows you to **automatically trigger workflow runs** at specific times or in response to events.

Important distinction:
- **Schedules trigger runs**
- **Workflows define execution**
- **Agents plan and govern behavior**

Scheduling controls *when work starts*, not *how work is done*.

---

## Triggers in Supervity

Supervity supports multiple ways to start execution.  
Schedules are one type of trigger.

| Trigger Type | Purpose |
|-------------|---------|
| Manual | User-initiated execution |
| Schedule | Time-based automation |
| Webhook | External event-driven execution |
| API | Programmatic execution |

All triggers ultimately create a **run (job)** for a workflow.

---

## Schedule Types

### Recurring Schedules

Recurring schedules trigger runs on a fixed cadence.

Supported patterns:
- Daily (specific time)
- Weekly (specific days)
- Monthly (specific dates)
- Hourly (every N hours)
- Custom cron expressions

**Examples**
- every weekday at 9:00 am
- first monday of each month
- every 2 hours during business hours

---

### One-Time Schedules

One-time schedules trigger a single run at a future time.

Common use cases:
- delayed actions
- reminders
- deferred processing
- time-based approvals

---

## Creating Schedules

### From the Schedule Page

1. navigate to **schedule**
2. click **create schedule**
3. select an existing workflow
4. configure timing
5. provide inputs (if required)
6. activate the schedule

---

### From a Saved Agent or Workflow

1. open a saved agent
2. click **schedule**
3. configure timing and options
4. save and activate

Schedules reference workflows but do not modify them.

---

## Schedule Configuration

### Required Fields

- **workflow** — the execution structure
- **schedule type** — recurring or one-time
- **timezone** — critical for correctness
- **active status** — enable or pause execution

---

### Optional Controls

- retry on failure
- maximum retry attempts
- execution timeout
- success or failure notifications
- pre-filled inputs

Schedules can be adjusted independently of workflow logic.

---

## Timezones & Reliability

All schedules execute in the **configured timezone**.

Best practices:
- always set timezone explicitly
- avoid relying on defaults
- use utc for global systems
- validate the next-run preview

Daylight saving changes are handled automatically.

---

## Webhook Triggers (Event-Based Automation)

Webhooks allow **external systems** to trigger workflow runs in real time.

### How Webhooks Work

1. supervity generates a webhook url
2. an external system sends an http request
3. the payload becomes workflow input
4. a run is created and executed

---

### Example Webhook Payload

```json
{
  "event": "new_lead",
  "data": {
    "email": "user@example.com",
    "source": "website"
  }
}
````

---

### Webhook Security

Webhooks support:

* optional authentication
* payload validation
* rate limiting
* ip allowlisting

Webhook-triggered runs follow the same execution and governance rules as scheduled runs.

---

## Integration-Based Triggers

Some integrations emit events automatically.

Examples:

* new email received
* file uploaded
* calendar event created
* form submitted

Internally, these behave like webhook triggers.

---

## Managing Schedules

### View & Monitor

The **schedule** page shows:

* active and paused schedules
* next run time
* last run status
* associated workflows

---

### Pause & Resume

* pausing stops future runs
* execution history is preserved
* no configuration is lost

---

### Edit or Delete

* editing affects future runs only
* deleting removes the schedule
* underlying workflows and agents remain unchanged

---

## Execution Monitoring

Every scheduled run produces:

* execution logs
* step-level status
* inputs and outputs
* retry history

Failures are visible and actionable.

→ See: **[Workflows Explained](workflows-explained.md)**

---

## Common Scheduling Patterns

### Daily Reports

```
schedule: daily at 8:00 am
workflow:
  → fetch data
  → generate report
  → send email
```

---

### Weekly Cleanup

```
schedule: sunday at 2:00 am
workflow:
  → identify old files
  → archive
  → notify team
```

---

### Real-Time Alerts

```
trigger: webhook
workflow:
  → parse event
  → check severity
  → notify responders
```

---

### Business Process Automation

```
schedule: first day of month
workflow:
  → generate invoices
  → send to customers
  → update accounting
```

---

## Error Handling & Safeguards

Schedules support:

* retry with backoff
* execution timeouts
* failure notifications
* manual intervention

If a run fails repeatedly, it surfaces clearly and does not loop silently.

---

## Governance & Access Control

* only authorized users can create or edit schedules
* all schedule changes are logged
* execution history is auditable
* approval steps still apply even for scheduled runs

Scheduling never bypasses governance.

---

## Best Practices

### Design Safely

* test workflows manually before scheduling
* start with low frequency
* enable failure notifications

### Design Reliably

* avoid overlapping long-running schedules
* stagger heavy workloads
* monitor initial runs closely

### Design for Scale

* batch operations
* use parallel steps
* track execution metrics

---

## Where to Go Next

* understand execution → **[Workflows Explained](workflows-explained.md)**
* delegate decisions → **[Understanding Agents](agents-overview.md)**
* trigger programmatically → **[API Reference](../reference/api-reference.md)**
* add governance → **[Human Review & Approvals](../guides/human-review.md)**

---

Scheduling defines **when work starts**.
Workflows define **what happens**.
Agents decide **how it should run**.
