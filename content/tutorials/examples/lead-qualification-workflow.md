---
title: "Lead Qualification Workflow Example"
level: advanced
duration: 35 minutes
prerequisites: ["library/intermediate/multi-step-workflows", "library/advanced/complex-branching"]
tags: [example, crm, sales, qualification, real-world]
category: examples
description: "Complete example: Automatically qualify and route sales leads"
---

# Lead Qualification Workflow Example

A complete advanced workflow example that automatically qualifies sales leads and routes them to appropriate sales representatives.

## Use Case

**Problem:** Sales team receives many leads but needs to prioritize and route them efficiently.

**Solution:** Create a workflow that automatically qualifies leads, scores them, and routes to the right sales rep based on criteria.

## Workflow Overview

```
Step 1: Receive new lead data
Step 2: Qualify lead (check criteria)
Step 3: Score lead
Step 4: Route to appropriate sales rep
Step 5: Send notifications
Step 6: Update CRM
```

## Step-by-Step Creation

### Step 1: Define the Goal

**Request:**
> "Create a workflow that qualifies sales leads. When a new lead comes in, check if they meet qualification criteria, score the lead, route to the appropriate sales rep based on territory and lead score, send notifications, and update the CRM system."

### Step 2: Workflow Structure

The agent will create:

```
Step 1: Receive lead data
  - Input: Lead information (name, email, company, etc.)
  - Validate required fields

Step 2: Qualify lead
  - Check company size
  - Check industry
  - Check budget indicators
  - Check decision maker status

Step 3: Score lead
  - Calculate lead score
  - Assign priority level
  - Determine fit

Step 4: Route lead
  - Determine territory
  - Find appropriate sales rep
  - Check rep availability

Step 5: Send notifications
  - Notify sales rep
  - Notify sales manager
  - Send to lead (if qualified)

Step 6: Update CRM
  - Create/update lead record
  - Add qualification data
  - Assign to sales rep
```

## Workflow Details

### Lead Qualification Criteria

**Qualification Checks:**
- Company size (employees)
- Industry match
- Budget indicators
- Decision maker contact
- Geographic location

**Scoring Factors:**
- Company size: +10 points per 100 employees
- Industry match: +20 points
- Budget confirmed: +30 points
- Decision maker: +25 points
- Geographic fit: +15 points

### Routing Logic

**Territory Assignment:**
```
If region = "North": Assign to North team
If region = "South": Assign to South team
If region = "East": Assign to East team
If region = "West": Assign to West team
```

**Rep Assignment:**
```
If score >= 80: Assign to senior rep
If score >= 50: Assign to mid-level rep
If score < 50: Assign to junior rep or queue
```

### Notification Logic

**Notifications:**
- Sales rep: New lead assigned
- Sales manager: High-value lead alert
- Lead: Welcome email if qualified

## Advanced Features

### Lead Enrichment

**Pattern:** Add additional data to leads

**Example:**
- Look up company information
- Find decision makers
- Check social media presence
- Verify contact information

### Lead Scoring Refinement

**Pattern:** Dynamic scoring based on behavior

**Example:**
- Website visits: +5 points
- Email opens: +3 points
- Content downloads: +10 points
- Demo requests: +25 points

### Multi-Stage Qualification

**Pattern:** Progressive qualification

**Example:**
```
Stage 1: Basic qualification
  ├─→ Qualified: Stage 2: Detailed qualification
  └─→ Not qualified: Archive lead
        ↓
    Stage 2: Detailed qualification
      ├─→ Qualified: Assign to sales
      └─→ Needs nurturing: Add to nurture campaign
```

## Customization Options

### Customize Scoring

**Request:**
> "Adjust lead scoring to weight company size more heavily"

### Customize Routing

**Request:**
> "Route leads based on product interest instead of territory"

### Customize Notifications

**Request:**
> "Send Slack notifications instead of email"

## Testing

### Test Scenarios

1. **High-value lead**: Should route to senior rep
2. **Low-value lead**: Should route to queue
3. **Unqualified lead**: Should be archived
4. **Missing data**: Should request additional information

## Troubleshooting

### Leads Not Routing
- Check qualification criteria
- Verify routing rules
- Review sales rep assignments

### Scoring Issues
- Verify scoring calculation
- Check data quality
- Review scoring weights

### CRM Updates Failing
- Check CRM connection
- Verify API permissions
- Review data format

## Variations

### Industry-Specific
- Customize for your industry
- Adjust qualification criteria
- Modify scoring model

### Multi-Channel
- Handle leads from multiple sources
- Normalize lead data
- Route consistently

## Next Steps

- Customize for your sales process
- Explore [Complex Branching](../library/advanced/complex-branching.md)
- Learn [Workflow Composition](../library/advanced/workflow-composition.md)

