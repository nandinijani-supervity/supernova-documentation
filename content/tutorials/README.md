# Tutorials Directory

This directory contains all tutorial content for the Supervity Agents help documentation system.

## Structure

```
tutorials/
├── getting-started/     # Getting started tutorials
│   ├── 01-welcome.md
│   ├── 02-first-workflow.md
│   ├── 03-workflow-structure.md
│   └── 04-core-concepts.md
├── library/            # Tutorial library (basic, intermediate, advanced)
│   ├── basic/          # Beginner-friendly tutorials
│   │   ├── email-automation.md
│   │   ├── file-management.md
│   │   └── simple-data-processing.md
│   ├── intermediate/   # Common use cases and patterns
│   │   ├── multi-step-workflows.md
│   │   ├── parallel-processing.md
│   │   └── data-transformation.md
│   ├── advanced/       # Complex workflows and advanced features
│   │   ├── complex-branching.md
│   │   ├── human-approval-workflows.md
│   │   └── workflow-composition.md
│   └── integrations/   # Integration-specific tutorials
│       ├── gmail-automation.md
│       ├── teams-workflows.md
│       ├── slack-integrations.md
│       └── google-sheets-automation.md
├── how-tos/            # How-to guides
│   ├── common-tasks/   # Task-specific guides
│   │   ├── send-automated-emails.md
│   │   ├── process-files-from-drive.md
│   │   └── create-approval-workflows.md
│   └── integration-setup/  # Integration setup guides
│       ├── oauth-connections.md
│       ├── service-specific-setup.md
│       └── credential-management.md
└── examples/           # Real-world examples
    ├── daily-email-digest.md
    ├── file-backup-automation.md
    ├── lead-qualification-workflow.md
    └── content-approval-process.md
```

### Directory Descriptions

#### `getting-started/`

Essential tutorials for new users. These should be completed in order:

- Introduction and platform overview
- First workflow creation
- Understanding core concepts
- Building foundational knowledge

#### `library/basic/`

Beginner-friendly tutorials covering fundamental use cases:

- Simple automations (email, file operations)
- Basic data processing
- Single-step workflows
- Common integrations

#### `library/intermediate/`

Tutorials for users comfortable with basics:

- Multi-step workflows with dependencies
- Parallel processing patterns
- Data transformation pipelines
- Integration between multiple services

#### `library/advanced/`

Complex workflows and advanced features:

- Complex conditional branching
- Human-in-the-loop workflows
- Scheduled automation
- Error handling and retries
- Workflow composition and reuse

#### `library/integrations/`

Service-specific tutorials for each integration:

- Gmail automation patterns
- Microsoft Teams workflows
- Slack bot integrations
- Google Workspace automation
- CRM integrations (Salesforce, HubSpot)
- Project management (Jira, Notion)

#### `how-tos/common-tasks/`

Step-by-step guides for specific tasks:

- How to send automated emails
- How to process files from cloud storage
- How to create approval workflows
- How to schedule recurring tasks
- How to handle errors
- How to debug workflows

#### `how-tos/integration-setup/`

Guides for setting up and managing integrations:

- OAuth connection process
- Service-specific configuration
- Credential management
- Troubleshooting connection issues

#### `examples/`

Real-world workflow examples with full context:

- Complete use case descriptions
- Workflow diagrams
- Step-by-step creation guides
- Input/output examples
- Troubleshooting tips

## Tutorial Format

Each tutorial is a Markdown file with frontmatter metadata:

```markdown
---
title: "Tutorial Title"
level: beginner | intermediate | advanced
duration: "10 minutes"
prerequisites: []
tags: [tag1, tag2]
category: getting-started
description: "Brief description"
---

# Tutorial Content

Your tutorial content here...
```

## Frontmatter Fields

- **title** (required): Tutorial title
- **level** (required): Difficulty level (beginner, intermediate, advanced)
- **duration** (required): Estimated time to complete
- **prerequisites** (optional): Array of prerequisite tutorial slugs
- **tags** (optional): Array of tags for search/filtering
- **category** (optional): Category name (auto-detected from directory)
- **description** (optional): Brief description for listings

## Adding New Tutorials

1. Create a Markdown file in the appropriate directory
2. Add frontmatter with required fields
3. Write your tutorial content
4. The tutorial will be automatically available via the API

## API Endpoints

Tutorials are served via the following API endpoints:

- `GET /api/v1/tutorials` - List all tutorials
- `GET /api/v1/tutorials/:slug` - Get specific tutorial
- `GET /api/v1/tutorials/categories` - Get categories
- `GET /api/v1/tutorials/search` - Search tutorials
