---
title: "File Backup Automation Example"
level: intermediate
duration: 25 minutes
prerequisites: ["library/basic/file-management"]
tags: [example, backup, files, automation, real-world]
category: examples
description: "Complete example: Automatically backup files to cloud storage"
---

# File Backup Automation Example

A complete workflow example that automatically backs up files from one location to another.

## Use Case

**Problem:** Important files need regular backups to prevent data loss.

**Solution:** Create a workflow that automatically backs up files from source to backup location on a schedule.

## Workflow Overview

```
Step 1: List files in source folder
Step 2: Check which files need backup
Step 3: Copy new/changed files
Step 4: Verify backup success
Step 5: Send backup report
```

## Step-by-Step Creation

### Step 1: Define the Goal

**Request:**
> "Create a workflow that backs up files from Google Drive folder 'Documents' to a backup folder 'Backups' every night at 2 AM. Only backup files that have changed since the last backup."

### Step 2: Workflow Structure

The agent will create:

```
Step 1: List files in source folder
  - Folder: Documents
  - Get file list with metadata

Step 2: Check backup status
  - Compare with previous backup
  - Identify new/changed files

Step 3: Copy files to backup
  - For each file to backup:
    - Copy to backup folder
    - Preserve folder structure
    - Update backup log

Step 4: Verify backup
  - Check file counts
  - Verify file integrity
  - Update backup log

Step 5: Send backup report
  - Generate summary
  - Send email notification
```

## Workflow Details

### File Detection

**New Files:**
- Files not in backup location
- Files with newer modification dates

**Changed Files:**
- Compare file hashes or dates
- Only backup if different

### Backup Process

**Folder Structure:**
```
Backups/
  └── 2024-01-16/
      └── [preserve source structure]
```

**File Naming:**
- Preserve original names
- Add date prefix if needed
- Handle duplicates

### Backup Verification

**Checks:**
- File count matches
- File sizes match
- Backup log updated

## Customization Options

### Customize Backup Frequency

**Request:**
> "Backup files every 6 hours instead of daily"

### Customize Backup Location

**Request:**
> "Backup to OneDrive instead of Google Drive"

### Customize File Selection

**Request:**
> "Only backup PDF and Word documents"

**Request:**
> "Exclude files larger than 100MB"

## Advanced Features

### Incremental Backup

**Pattern:** Only backup changed files

**Benefits:**
- Faster backups
- Less storage used
- Efficient processing

### Backup Retention

**Pattern:** Keep multiple backup versions

**Example:**
- Keep daily backups for 7 days
- Keep weekly backups for 4 weeks
- Keep monthly backups for 12 months

### Backup Encryption

**Pattern:** Encrypt backups for security

**Implementation:**
- Encrypt files before backup
- Store encryption keys securely
- Decrypt when restoring

## Testing

### Test Steps

1. **Create test files**: Add files to source folder
2. **Run backup**: Execute workflow manually
3. **Verify backup**: Check backup location
4. **Test changes**: Modify files and re-backup
5. **Test schedule**: Verify scheduled execution

## Troubleshooting

### Files Not Backing Up
- Check folder permissions
- Verify file access
- Review error logs

### Backup Too Slow
- Optimize file operations
- Use parallel processing
- Filter files better

### Storage Issues
- Check available space
- Implement retention policy
- Clean old backups

## Variations

### Multi-Location Backup
- Backup to multiple locations
- Verify all backups
- Handle failures

### Selective Backup
- Backup only specific file types
- Exclude certain folders
- Custom filtering rules

## Next Steps

- Customize for your needs
- Explore [File Management Basics](../library/basic/file-management.md)
- Learn [Scheduled Automation](../library/intermediate/scheduled-automation.md)

