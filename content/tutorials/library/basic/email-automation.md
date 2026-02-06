---
title: "Email Automation Basics"
level: beginner
duration: 15 minutes
prerequisites: ["getting-started/02-first-workflow"]
tags: [email, automation, gmail, outlook, beginner]
category: library/basic
description: "Learn to automate email sending, reading, and management tasks"
---

# Email Automation Basics

Email automation is one of the most common workflow use cases. This tutorial covers the fundamentals of automating email tasks with Gmail and Outlook.

## What You'll Learn

- How to send automated emails
- How to read and search emails
- How to process email attachments
- How to filter and organize emails

## Prerequisites

- Gmail or Outlook account connected
- Completed "Build Your First Workflow" tutorial

## Sending Emails

### Basic Email Send

**Example Request:**
> "Create a workflow that sends a welcome email to new users"

The agent will create a workflow with:
- A step to compose the email
- Input fields for recipient, subject, and body
- Integration with your email service

### Personalized Emails

You can personalize emails using workflow inputs:

**Example:**
```
Input: recipient_name = "John"
Input: recipient_email = "john@example.com"

Email Subject: "Welcome, {{recipient_name}}!"
Email Body: "Hi {{recipient_name}}, welcome to our platform!"
```

## Reading Emails

### Search and Filter

**Example Request:**
> "Create a workflow that finds all emails from a specific sender in the last 7 days"

The workflow will:
1. Search your inbox using email filters
2. Return matching emails
3. Process the results

### Common Search Patterns

- **By sender**: `from:someone@example.com`
- **By subject**: `subject:Important`
- **With attachments**: `has:attachment`
- **Date range**: `after:2024/1/1 before:2024/1/31`

## Processing Attachments

### Download and Process

**Example Request:**
> "Create a workflow that downloads all PDF attachments from emails and saves them to Drive"

The workflow steps:
1. Search for emails with PDF attachments
2. Download each attachment
3. Upload to Google Drive
4. Send a summary email

## Email Organization

### Auto-labeling

**Example Request:**
> "Create a workflow that labels all emails from support@company.com with 'Support' label"

### Auto-forwarding

**Example Request:**
> "Create a workflow that forwards all emails matching a pattern to another address"

## Best Practices

1. **Use clear subject lines**: Make automated emails easy to identify
2. **Handle errors gracefully**: Add error handling for failed sends
3. **Respect rate limits**: Don't send too many emails too quickly
4. **Test first**: Always test with your own email before production use
5. **Use templates**: Create reusable email templates

## Common Use Cases

- **Welcome emails**: Automatically send to new users
- **Daily digests**: Summarize important emails
- **Notification forwarding**: Forward specific emails to team members
- **Attachment processing**: Download and process email attachments
- **Auto-responses**: Send automated replies based on criteria

## Next Steps

- Try creating an email automation workflow
- Explore [File Management](./file-management.md) tutorial
- Check out [Gmail Automation](../integrations/gmail-automation.md) for advanced patterns

