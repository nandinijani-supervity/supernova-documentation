---
title: "Troubleshooting"
description: "Diagnose and resolve common issues when running AI agents and workflows"
category: "Guides"
order: 50
---

## Overview

This guide helps you **diagnose and resolve common issues** when working with Supervity agents, workflows, integrations, schedules, and approvals.

Supervity is designed so failures are:
- visible
- recoverable
- auditable

Most issues can be resolved **without rebuilding workflows**.

---

## Execution Issues

### Execution Fails Immediately

**Symptoms**
- Execution fails as soon as it starts
- Error shown in logs
- No steps complete

**What to check**
- Step configuration is valid
- Required inputs are present
- Integration is connected
- Permissions and scopes are correct

**Fixes**
- Correct the configuration
- Reconnect the integration if needed
- Verify permissions
- Retry execution (no rebuild required)

---

### Execution Hangs or Times Out

**Symptoms**
- Execution runs for a long time
- A step never completes
- Execution eventually times out

**What to do**
1. Identify the step where execution is stuck
2. Check the external service health
3. Reduce data size or batch inputs
4. Increase timeout if appropriate
5. Use parallel execution where possible

---

## Integration Issues

### Can’t Connect an Integration

**Symptoms**
- OAuth window fails
- Authorization error shown

**What to check**
1. Browser popups enabled
2. Try incognito or private mode
3. Confirm you have admin access in the external system
4. Retry authorization

---

### Integration Keeps Disconnecting

**Symptoms**
- Frequent “Reconnect required” messages
- Token expiration errors

**Common causes**
- Password change
- Token revoked externally
- Service account restrictions

**Fixes**
- Reconnect the integration
- Prefer service accounts where supported
- Rotate API keys if applicable

---

### Integration Action Fails

**Symptoms**
- Integration is connected
- Specific action fails during execution

**What to check**
- Action-level permissions
- Resource existence (file, record, object)
- API rate limits
- Execution frequency

**Fixes**
- Adjust permissions
- Reduce frequency or batch requests
- Add retries or backoff

---

## Human Review Issues

### Review Notification Not Received

**Symptoms**
- Execution waiting for review
- Reviewer not notified

**What to check**
1. Reviewer email or role assignment
2. Notification preferences
3. Spam or junk folders
4. Resend review request

---

### Review Form Can’t Be Submitted

**Symptoms**
- Submit button disabled
- Error on submission

**Fixes**
- Ensure all required fields are filled
- Refresh the page or re-authenticate
- Try a different browser
- Request a new review link

---

### Execution Stuck Waiting for Review

**Symptoms**
- Workflow paused indefinitely

**Fixes**
- Verify timeout and escalation settings
- Escalate to a backup reviewer
- Admin can manually approve, reject, or cancel
- Adjust review configuration for future runs

→ See **[Human Review & Approvals](../guides/human-review.md)**

---

## Scheduling Issues

### Scheduled Execution Didn’t Run

**Symptoms**
- Schedule is active
- No execution occurred

**Checklist**
1. Is the schedule active?
2. Is the start time in the past?
3. Correct timezone selected?
4. Does the workflow run manually?
5. Any platform outage?

---

### Scheduled Execution Ran at the Wrong Time

**Symptoms**
- Execution offset by hours
- Expected run skipped

**Fixes**
- Verify timezone configuration
- Review cron expression
- Account for daylight saving changes
- Use UTC for global consistency

---

## Data & Variable Issues

### Variables Appear as `{{variable}}`

**Symptoms**
- Templates not rendered
- Empty or unresolved values

**What to check**
1. Variable name (case-sensitive)
2. Producing step completed successfully
3. Variable scope (loop vs global)
4. Defaults for optional values

---

### Data Format or Parsing Errors

**Symptoms**
- Type mismatch errors
- Parsing failures

**Fixes**
- Add explicit transformation steps
- Validate inputs early
- Handle null or empty values
- Convert data types intentionally

---

## API & Developer Issues

### API Call Fails

**Checklist**
- Token is valid
- Correct environment (prod vs staging)
- Required permissions granted
- Correct content type
- Rate limits not exceeded

→ Refer to **[API Reference](/docs/reference/api-reference)**

---

### Streaming or Chat Appears Stuck

**Symptoms**
- No response from SSE stream
- Execution appears frozen

**Fixes**
- Ensure the connection remains open
- Check firewall or proxy settings
- Use an Idempotency-Key
- Retry with a new thread if needed

---

## When to Contact Support

Contact support if:
- The issue is consistently reproducible
- Logs don’t explain the failure
- Execution is blocked and time-sensitive
- You suspect a platform issue

**Include**
- Workflow name and ID
- Run ID
- Timestamp
- Error message
- Steps already tried

📧 support@supervity.com  
💬 In-app chat  
👥 Community forum

---

## Preventive Best Practices

### Before Going Live
- Test with realistic data
- Add approvals for critical actions
- Start with limited permissions
- Monitor initial executions closely

### Ongoing
- Review logs regularly
- Audit integrations periodically
- Remove unused workflows
- Optimize long-running agents

---

## Quick Diagnostic Checklist

Before escalating, verify:
- Agent plan matches intent
- Required inputs are provided
- Integrations are connected
- Permissions are sufficient
- No pending human review
- Execution logs reviewed

---

## Related Resources

- **[FAQ](../guides/faq)**  
- **[Human Review & Approvals](../guides/human-review.md)**  
- **[Security & Privacy](../guides/security-privacy.md)**  
- **[API Reference](/docs/reference/api-reference)**  

---

Most issues are part of normal operations.  
Supervity is designed so **failures pause safely, not fail silently**.
```

