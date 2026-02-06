---
title: "Content Approval Process Example"
level: advanced
duration: 30 minutes
prerequisites: ["library/advanced/human-approval-workflows"]
tags: [example, approval, content, publishing, real-world]
category: examples
description: "Complete example: Multi-stage content approval and publishing workflow"
---

# Content Approval Process Example

A complete workflow example for content creation, review, approval, and publishing with multiple approval stages.

## Use Case

**Problem:** Content needs multiple approvals before publishing, but the process is manual and error-prone.

**Solution:** Create a workflow that automates content generation, routes through approval stages, and publishes when approved.

## Workflow Overview

```
Step 1: Generate content draft
Step 2: Editor review and approval
Step 3: Legal review and approval
Step 4: Final formatting
Step 5: Final approval
Step 6: Publish content
Step 7: Distribute notifications
```

## Step-by-Step Creation

### Step 1: Define the Goal

**Request:**
> "Create a content approval workflow. Generate a blog post draft, send for editor approval, then legal review, format the content, get final approval, and publish. If any stage rejects, allow revisions and re-submission."

### Step 2: Workflow Structure

The agent will create:

```
Step 1: Generate content draft
  - Input: Topic, keywords, tone
  - Generate draft content
  - Save to Drive

Step 2: [Editor Approval] Editor reviews
  - Present draft for review
  - Collect approval/rejection
  - Collect feedback if rejected
  ├─→ Approved: Continue
  └─→ Rejected: Step 2a: Revise based on feedback → Back to Step 2

Step 3: [Legal Review] Legal reviews
  - Present content for legal review
  - Check compliance
  - Collect approval/rejection
  ├─→ Approved: Continue
  └─→ Rejected: Step 3a: Request legal changes → Back to Step 1

Step 4: Format content
  - Apply formatting
  - Add images
  - Optimize for publishing

Step 5: [Final Approval] Final review
  - Present formatted content
  - Collect final approval
  ├─→ Approved: Continue
  └─→ Rejected: Step 5a: Make final revisions → Back to Step 5

Step 6: Publish content
  - Publish to website/CMS
  - Set publication date
  - Configure SEO

Step 7: Distribute notifications
  - Notify stakeholders
  - Share on social media
  - Send email announcement
```

## Workflow Details

### Content Generation

**Inputs:**
- Topic or subject
- Target audience
- Content type (blog, article, etc.)
- Tone and style

**Output:**
- Draft content
- Metadata
- Suggested images

### Approval Stages

**Stage 1: Editor Review**
- Content quality
- Grammar and style
- Structure and flow
- Fact-checking

**Stage 2: Legal Review**
- Compliance check
- Copyright verification
- Disclaimers
- Regulatory requirements

**Stage 3: Final Approval**
- Overall quality
- Brand alignment
- Publication readiness

### Revision Handling

**Revision Process:**
- Collect feedback
- Revise content
- Re-submit for approval
- Track revision history

## Advanced Features

### Parallel Reviews

**Pattern:** Multiple reviewers review simultaneously

**Example:**
```
Step 1: Generate draft
  ↓
Step 2: [Editor Review] (parallel)
Step 3: [Technical Review] (parallel)
Step 4: [SEO Review] (parallel)
  ↓
Step 5: Evaluate all reviews
  ├─→ All approved: Continue
  └─→ Any rejected: Revise and re-review
```

### Conditional Approval

**Pattern:** Skip stages based on content type

**Example:**
```
Step 1: Generate content
  ↓
Step 2: Check content type
  ├─→ If "internal": Step 3: Editor approval only
  └─→ If "external": 
        ├─→ Step 4: Editor approval
        ├─→ Step 5: Legal review
        └─→ Step 6: Final approval
```

### Automated Publishing

**Pattern:** Schedule publication

**Example:**
- Publish immediately if approved
- Schedule for specific date/time
- Queue for optimal publishing time

## Customization Options

### Customize Approval Stages

**Request:**
> "Add a marketing review stage before final approval"

### Customize Revision Process

**Request:**
> "Allow unlimited revisions at editor stage, but limit to 2 at legal stage"

### Customize Publishing

**Request:**
> "Publish to multiple platforms: website, Medium, and LinkedIn"

## Testing

### Test Scenarios

1. **Full approval path**: All stages approve
2. **Editor rejection**: Editor requests changes
3. **Legal rejection**: Legal requires modifications
4. **Final rejection**: Final approval requests changes

## Troubleshooting

### Approval Stuck
- Check approval notifications
- Verify approver access
- Review timeout settings

### Content Not Publishing
- Check publishing platform connection
- Verify content format
- Review publishing permissions

### Revision Loop
- Set revision limits
- Track revision count
- Escalate if needed

## Variations

### Industry-Specific
- Customize for your industry
- Add industry-specific reviews
- Adjust approval criteria

### Multi-Format
- Handle different content types
- Different approval paths
- Format-specific publishing

## Next Steps

- Customize for your content process
- Explore [Human Approval Workflows](../library/advanced/human-approval-workflows.md)
- Learn [Workflow Composition](../library/advanced/workflow-composition.md)

