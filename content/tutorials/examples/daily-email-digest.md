---
title: "Daily Email Digest Example"
level: intermediate
duration: 30 minutes
prerequisites: ["library/basic/email-automation", "library/intermediate/multi-step-workflows"]
tags: [example, email, digest, daily, real-world]
category: examples
description: "Complete example: Automatically generate and send daily email digests"
---

# Daily Email Digest Example

A complete real-world example workflow that generates and sends a daily email digest summarizing important information.

## Use Case

**Problem:** Team members receive too many emails and miss important information.

**Solution:** Create a workflow that collects important emails, generates a digest, and sends it once daily.

## Workflow Overview

```
Step 1: Search for important emails from yesterday
Step 2: Extract key information from emails
Step 3: Generate digest summary
Step 4: Format as email
Step 5: Send digest to team
```

## Step-by-Step Creation

### Step 1: Define the Goal

**Request:**
> "Create a workflow that generates a daily email digest. It should collect all emails labeled 'important' from the last 24 hours, summarize them, and send a digest email to the team every morning at 9 AM."

### Step 2: Workflow Structure

The agent will create:

```
Step 1: Search Gmail for important emails
  - Query: label:important after:yesterday
  - Get email list

Step 2: Extract email information
  - For each email:
    - Get subject
    - Get sender
    - Get snippet
    - Get date

Step 3: Generate digest summary
  - Group by sender or category
  - Create summary text
  - Format as HTML

Step 4: Send digest email
  - Recipient: team@company.com
  - Subject: Daily Digest - [Date]
  - Body: Generated summary
```

### Step 3: Inputs Required

- **Recipient email**: Who receives the digest
- **Digest time**: When to send (e.g., 9 AM)
- **Email labels**: Which labels to include

### Step 4: Schedule Configuration

- **Frequency**: Daily
- **Time**: 9:00 AM
- **Timezone**: Your timezone

## Workflow Details

### Email Search

**Gmail Query:**
```
label:important after:2024/1/15 before:2024/1/16
```

**Filters:**
- Only important emails
- From last 24 hours
- Exclude already processed

### Digest Generation

**Summary Format:**
- Email count
- Grouped by sender
- Key highlights
- Links to original emails

**Example Output:**
```
Daily Digest - January 16, 2024

Summary: 12 important emails

From: support@company.com (5 emails)
- System maintenance scheduled
- New feature release
- ...

From: sales@company.com (3 emails)
- Q4 results available
- ...
```

### Email Sending

**Email Format:**
- HTML formatted
- Clear sections
- Links to original emails
- Unsubscribe option

## Customization Options

### Customize Digest Content

**Request:**
> "Include email attachments in the digest summary"

**Request:**
> "Group emails by project instead of sender"

### Customize Schedule

**Request:**
> "Send digest every Monday, Wednesday, and Friday"

**Request:**
> "Send at 8 AM instead of 9 AM"

### Customize Recipients

**Request:**
> "Send different digests to different teams based on their interests"

## Testing

### Test Steps

1. **Manual execution**: Run workflow manually first
2. **Verify email search**: Check that correct emails are found
3. **Review digest**: Ensure summary is accurate
4. **Test email delivery**: Verify email is sent correctly
5. **Schedule test**: Test scheduled execution

### Sample Test Data

- Create test emails with "important" label
- Run workflow manually
- Verify digest content
- Check email delivery

## Troubleshooting

### No Emails Found
- Verify label exists
- Check date range
- Review search query

### Digest Too Long
- Limit number of emails
- Summarize more aggressively
- Group better

### Email Not Sending
- Check recipient address
- Verify email service connection
- Review email format

## Variations

### Weekly Digest
- Change schedule to weekly
- Summarize entire week
- Include weekly statistics

### Custom Digest
- Filter by specific senders
- Include only certain topics
- Custom formatting

## Next Steps

- Customize for your needs
- Explore other examples
- Learn more: [Email Automation Basics](../library/basic/email-automation.md)

