---
title: "Service-Specific Setup Guides"
level: beginner
duration: 20 minutes
prerequisites: []
tags: [how-to, setup, integration, configuration]
category: how-tos/integration-setup
description: "Service-specific setup instructions for common integrations"
---

# Service-Specific Setup Guides

Detailed setup instructions for specific services and integrations.

## Google Services

### Gmail Setup
1. Connect Gmail account via OAuth
2. Grant email read/send permissions
3. Verify connection with test email
4. Ready to use in workflows

### Google Drive Setup
1. Connect Google account
2. Grant Drive access permissions
3. Select default folder (optional)
4. Test file operations

### Google Sheets Setup
1. Connect Google account
2. Grant Sheets access
3. Share sheets with service account if needed
4. Test read/write operations

## Microsoft Services

### Outlook Setup
1. Connect Microsoft account
2. Grant Mail.ReadWrite permissions
3. Verify connection
4. Test email operations

### Teams Setup
1. Connect Microsoft account
2. Grant Teams messaging permissions
3. Verify workspace access
4. Test message sending

### OneDrive Setup
1. Connect Microsoft account
2. Grant OneDrive access
3. Configure default folder
4. Test file operations

## Communication Services

### Slack Setup
1. Create Slack app (if custom)
2. Connect workspace
3. Grant required scopes
4. Install to workspace
5. Test messaging

### Microsoft Teams Setup
1. Connect Microsoft account
2. Grant Teams API permissions
3. Verify team/channel access
4. Test operations

## CRM Services

### Salesforce Setup
1. Create connected app in Salesforce
2. Configure OAuth settings
3. Connect via OAuth
4. Grant API permissions
5. Test API access

### HubSpot Setup
1. Generate API key in HubSpot
2. Connect via API key or OAuth
3. Grant required permissions
4. Test API operations

## Best Practices by Service

### Email Services (Gmail, Outlook)
- Use delegated access when possible
- Set up proper scopes
- Test with your own email first

### File Services (Drive, OneDrive)
- Organize files in dedicated folders
- Set appropriate sharing permissions
- Test read/write operations

### Communication (Slack, Teams)
- Use appropriate channels
- Respect rate limits
- Test with small groups first

## Troubleshooting by Service

### Gmail Issues
- Check OAuth scopes
- Verify account permissions
- Test with Gmail API directly

### Microsoft Issues
- Verify Azure AD permissions
- Check service principal setup
- Review Microsoft Graph permissions

### Slack Issues
- Verify app installation
- Check workspace permissions
- Review Slack API scopes

## Next Steps

- Learn OAuth basics: [OAuth Connections](./oauth-connections.md)
- Manage credentials: [Credential Management](./credential-management.md)
- Start automating: Create workflows with your services

