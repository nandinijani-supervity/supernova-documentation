---
title: "Security & Privacy"
description: "How Supervity protects your data and ensures secure AI-driven operations"
category: "Guides"
order: 30
---

## Overview

Supervity is designed for **enterprise-grade security, privacy, and governance**.

This guide explains how Supervity protects data while enabling AI agents to operate safely under **Human-in-Command** controls, approvals, and policies.

Security is built into:
- Agent execution
- Integrations and APIs
- Human review workflows
- Monitoring and auditability

---

## Core Security Principles

Supervity’s security model is based on four principles:

1. **Least Privilege**  
   Agents only access what you explicitly authorize.

2. **Human-in-Command**  
   Critical actions require human approval and oversight.

3. **Transparency & Auditability**  
   Every action is logged and traceable.

4. **Enterprise Isolation**  
   Strong boundaries between customers, systems, and data.

---

## Data Security

### Encryption

**In Transit**
- TLS 1.3 for all API, UI, and streaming connections
- Secure WebSocket and SSE channels for agent interaction

**At Rest**
- AES-256 encryption for databases and file storage
- Encrypted storage for credentials, tokens, and secrets

---

### Access Control

- **Role-Based Access Control (RBAC)**  
  Admin, Editor, Viewer, Runner roles
- **Multi-Factor Authentication (MFA)** support
- **Single Sign-On (SSO)** for Enterprise deployments
- Session timeouts and device-level controls

Access to workflows, agents, and approvals is always permission-bound.

---

## Agent & Workflow Security

### Controlled Agent Execution

AI agents:
- cannot act outside defined workflows
- cannot bypass approval steps
- cannot access unconnected systems
- pause automatically when human input is required

Execution always respects:
- approval rules
- access permissions
- execution policies

---

### Secrets & Variables

- Secrets stored securely (never hardcoded)
- Environment variables encrypted at rest
- Per-workflow and per-run overrides supported
- Rotation supported without redeploying workflows

---

## Integration Security

### OAuth 2.0 Integrations

Most integrations use OAuth:

- No password storage
- Scoped permissions only
- Encrypted token storage
- Automatic token refresh
- Easy revocation at any time

---

### API Keys & Custom Integrations

For API-key–based integrations:

- AES-256 encrypted storage
- Access logging
- Rotation support
- Least-privilege recommended

---

### Permissions Management

You remain in control:
1. Review scopes before connecting
2. Grant minimum required permissions
3. Revoke access anytime
4. Audit usage through logs

---

## Data Privacy

### What Supervity Collects

**Account & Workspace Data**
- User profiles
- Organization information
- Roles and permissions

**Operational Data**
- Workflow definitions
- Execution logs and metadata
- Approval records

**Temporary Execution Data**
- Inputs and outputs required for execution
- Files processed during runs (temporary)

---

### What Supervity Does NOT Store

- ❌ Integration passwords
- ❌ Long-term storage of file contents
- ❌ Email bodies or message content beyond execution needs
- ❌ Unnecessary sensitive personal data

---

### Data Retention

- Execution logs: **90 days** (configurable for Enterprise)
- Temporary files: deleted after execution
- Account data: retained until account deletion
- Deleted workflows: purged within 30 days

Enterprise customers may request custom retention policies.

---

## Compliance & Standards

Supervity aligns with enterprise compliance requirements, including:

- **SOC 2 Type II** (in progress)
- **GDPR**
- **CCPA**
- **HIPAA** (Enterprise, upon request)
- **ISO 27001** (planned / aligned)

For the latest compliance posture, refer to official documentation or contact sales.

---

## Auditability & Monitoring

### Activity Logs

Supervity maintains detailed logs for:
- Agent executions
- Workflow changes
- Human approvals and decisions
- Integration access
- User activity

Logs are searchable and exportable for audits.

---

### Alerts & Notifications

Get notified about:
- Workflow failures
- Approval delays
- Integration disconnections
- Suspicious login activity

Configured via **Settings → Notifications**.

---

## Incident Response

### Our Commitment

If a security incident occurs:
1. Immediate investigation
2. Containment and mitigation
3. Customer notification (within 24 hours)
4. Detailed incident report
5. Preventive remediation

---

### Reporting Security Issues

Report vulnerabilities responsibly:

- **Email**: security@supervity.com  
- **Bug bounty program**: (if applicable)

We appreciate responsible disclosure and coordinated reporting.

---

## Enterprise Security Features

Available for Enterprise deployments:

- SSO (SAML 2.0)
- Custom roles and permissions
- IP allow-listing
- Dedicated VPC or isolated infrastructure
- On-premises deployment option
- Enhanced audit logging
- Custom SLAs

---

## User Responsibilities (Best Practices)

### Account Security
- Enable MFA
- Use strong passwords
- Review login activity
- Remove unused users

### Workflow Security
- Avoid hardcoding secrets
- Use approval steps for critical actions
- Limit workflow access
- Review logs regularly

### Integration Hygiene
- Disconnect unused integrations
- Rotate API keys
- Review permissions periodically

---

## Transparency & Trust

Supervity prioritizes transparency through:
- Clear documentation
- Audit trails
- Status and incident communication
- Security best-practice sharing

---

## Questions & Support

- **Security questions**: security@supervity.com  
- **Privacy inquiries**: privacy@supervity.com  
- **DPA requests**: legal@supervity.com  
- **General support**: support@supervity.com  

---

## Where to Go Next

- Understand governance → **[Human Review & Approvals](../guides/human-review.md)**  
- Review API security → **[API Reference](/docs/reference/api-reference)**  
- Common questions → **[FAQ](../guides/faq)**  

---

Security at Supervity is designed to let AI agents work **fast**, while humans remain **fully in control**.
