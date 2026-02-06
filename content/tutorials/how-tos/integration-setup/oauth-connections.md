---
title: "How to Set Up OAuth Connections"
level: beginner
duration: 15 minutes
prerequisites: []
tags: [how-to, oauth, integration, setup]
category: how-tos/integration-setup
description: "Step-by-step guide to connecting services via OAuth"
---

# How to Set Up OAuth Connections

Learn to connect external services to your workflows using OAuth authentication.

## What is OAuth?

OAuth is a secure way to grant applications access to your accounts without sharing passwords. It's used to connect services like Gmail, Slack, Teams, and more.

## Quick Start

### Step 1: Navigate to Integrations

Go to the Integrations section in your workspace.

### Step 2: Select Service

Choose the service you want to connect (e.g., Gmail, Slack, Teams).

### Step 3: Initiate Connection

Click "Connect" or "Authorize" to start the OAuth flow.

### Step 4: Authorize Access

You'll be redirected to the service's authorization page:
- Review requested permissions
- Sign in if needed
- Click "Allow" or "Authorize"

### Step 5: Confirm Connection

You'll be redirected back and the connection will be confirmed.

## Common Services

### Gmail
1. Select "Gmail" integration
2. Click "Connect Gmail"
3. Sign in with Google account
4. Grant permissions
5. Connection confirmed

### Microsoft Teams/Outlook
1. Select "Microsoft" integration
2. Click "Connect Microsoft"
3. Sign in with Microsoft account
4. Grant permissions
5. Connection confirmed

### Slack
1. Select "Slack" integration
2. Click "Connect Slack"
3. Select workspace
4. Review permissions
5. Authorize connection

## Permissions Explained

### Common Permission Types

- **Read**: Access to read your data
- **Write**: Ability to create/modify data
- **Send**: Permission to send messages/emails
- **Manage**: Full management access

### Best Practices

- **Grant minimum permissions**: Only grant what's needed
- **Review permissions**: Understand what you're granting
- **Regular review**: Periodically review connected services
- **Revoke if needed**: Disconnect services you no longer use

## Troubleshooting

### Connection Fails
- Check internet connection
- Verify service account access
- Try disconnecting and reconnecting
- Clear browser cache

### Permissions Denied
- Ensure you have admin rights if needed
- Check service account status
- Verify service is available

### Connection Expired
- Re-authenticate the connection
- Check token expiration
- Reconnect the service

## Security Tips

1. **Use secure accounts**: Connect with accounts that have appropriate security
2. **Review regularly**: Periodically review connected services
3. **Revoke unused**: Disconnect services you no longer use
4. **Monitor access**: Watch for unexpected access

## Next Steps

- Learn more: [Service-Specific Setup](./service-specific-setup.md)
- Advanced: [Credential Management](./credential-management.md)
- Start using: Create workflows with your connected services

