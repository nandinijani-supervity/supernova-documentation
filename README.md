# Documentation
 
---
layout: default
---

This folder contains customer-facing documentation rendered by the Supervity application.
 
## Structure
 
Documentation is organized into the following categories:
 
### Start Here
Essential guides for new users:
- Welcome to Supervity
- Quick Start Guide
- Key Features
 
### Product Guide
Core concepts and features:
- Platform Overview
- Understanding Agents
- Workflows Explained
- Integrations Overview
- Scheduling & Automation
 
### Guides
Practical guides for specific topics:
- Human Review & Approvals
- Troubleshooting
- Security & Privacy
- FAQ
 
### About
Company and support information:
- About Supervity
- Contact & Support
 
## File Conventions
 
- Files should include frontmatter with `title`, `description`, `category`, and `order`
- Use `kebab-case.md` for filenames
- Optionally prefix with numbers for ordering (e.g., `01-welcome.md`)
- `README.md` and files prefixed with `_` are ignored by the docs index
 
## Frontmatter Example
 
```markdown
---
title: "Your Page Title"
description: "Brief description for SEO and previews"
category: "Start Here"
order: 1
---
 
# Your Content Here
```
 
## Categories
 
Current categories:
- **Start Here**: First steps for new users (order: 1-10)
- **Product Guide**: Core concepts and features (order: 10-50)
- **Guides**: Topic-specific guides (order: 10-50)
- **About**: Company information (order: 1-10)
 
## Writing Guidelines
 
### Voice & Tone
- **Friendly and helpful**: Like talking to a knowledgeable colleague
- **Clear and concise**: Avoid jargon, explain technical terms
- **Action-oriented**: Focus on what users can do
- **Encouraging**: Build confidence in users
 
### Structure
- Start with overview/introduction
- Use clear headings (H2, H3) for sections
- Include practical examples
- Add "Next Steps" or "Learn More" links
- Use callouts for tips, warnings, notes
 
### Content Types
 
**Conceptual**: Explain what something is and why it matters
- What Are Agents?
- Understanding Workflows
 
**Task-based**: Show how to do something specific
- How to Connect Gmail
- Creating Your First Schedule
 
**Reference**: Detailed specifications and options
- Integration List
- API Reference
 
### Formatting
 
**Use markdown features:**
- `**Bold**` for emphasis
- `*Italic*` for subtle emphasis
- `` `Code` `` for code/technical terms
- Block quotes for important callouts
- Lists for steps or options
- Code blocks with language tags
 
**Examples:**
 
```markdown
**Important:** Always test workflows before deploying
 
*Tip:* Use parallel execution for faster workflows
 
To connect Gmail, click `Settings` → `Integrations`
 
> **Note:** OAuth tokens expire after 90 days
```
 
### Links
 
**Internal links:**
```markdown
[Quick Start Guide](../start-here/02-quick-start.md)
[Tutorial](/u/alpha/tutorials/getting-started/01-welcome)
```
 
**External links:**
```markdown
[Google Workspace](https://workspace.google.com)
```
 
## Review Checklist
 
Before publishing documentation:
 
- [ ] Frontmatter is complete and correct
- [ ] Content is accurate and up-to-date
- [ ] Links work (internal and external)
- [ ] Examples are tested
- [ ] Screenshots are current (if applicable)
- [ ] Grammar and spelling checked
- [ ] Follows voice & tone guidelines
- [ ] Category and order are appropriate
 
## Contributing
 
When adding or updating documentation:
 
1. Follow the file naming convention
2. Include proper frontmatter
3. Use clear, action-oriented language
4. Add practical examples
5. Link to related content
6. Test all examples and links
 
## Questions?
 
For questions about documentation:
- Check existing docs for patterns
- Ask in the team Slack channel
- Contact the documentation team
 
---
 
**Thank you for helping users succeed with Supervity!** 📚

This folder contains **customer-facing** documentation rendered by the app.

Conventions:
- Files should include frontmatter (`title`, `description`).
- Use `kebab-case.md` filenames (optionally `01-...md` for ordered sequences).
- `README.md` and files prefixed with `_` are ignored by the docs index.

