---
title: "Simple Data Processing"
level: beginner
duration: 20 minutes
prerequisites: ["getting-started/02-first-workflow"]
tags: [data, processing, csv, excel, beginner]
category: library/basic
description: "Learn to process and transform data in workflows"
---

# Simple Data Processing

Process and transform data using workflows. This tutorial covers basic data operations like reading CSV files, filtering data, and generating reports.

## What You'll Learn

- How to read CSV and Excel files
- How to filter and transform data
- How to generate summaries and reports
- How to export processed data

## Prerequisites

- Basic understanding of data formats (CSV, Excel)
- Completed "Build Your First Workflow" tutorial

## Reading Data Files

### Read CSV Files

**Example Request:**
> "Create a workflow that reads a CSV file and processes each row"

The workflow will:
1. Read the CSV file
2. Parse rows and columns
3. Process each record
4. Generate output

### Read Excel Files

**Example Request:**
> "Create a workflow that reads data from an Excel spreadsheet"

The workflow automatically:
- Detects sheet names
- Identifies column headers
- Parses data types

## Filtering Data

### Filter by Condition

**Example Request:**
> "Create a workflow that filters a CSV to show only records where status is 'active'"

### Filter by Date Range

**Example Request:**
> "Create a workflow that filters records from the last 30 days"

## Transforming Data

### Calculate Totals

**Example Request:**
> "Create a workflow that calculates the total sales from a CSV file"

### Group and Aggregate

**Example Request:**
> "Create a workflow that groups sales data by region and calculates totals"

## Generating Reports

### Summary Reports

**Example Request:**
> "Create a workflow that generates a summary report from sales data"

The workflow will:
1. Read the data file
2. Calculate statistics (totals, averages, etc.)
3. Format the report
4. Send via email or save to Drive

### Data Visualization

**Example Request:**
> "Create a workflow that generates a chart from data and includes it in a report"

## Exporting Data

### Export to CSV

**Example Request:**
> "Create a workflow that processes data and exports results to a new CSV file"

### Export to Excel

**Example Request:**
> "Create a workflow that creates an Excel report with multiple sheets"

## Common Data Operations

### Data Validation

- Check for missing values
- Validate data formats
- Ensure data consistency

### Data Cleaning

- Remove duplicates
- Fix formatting issues
- Standardize values

### Data Enrichment

- Add calculated fields
- Merge with other data sources
- Add metadata

## Best Practices

1. **Validate input data**: Check data quality before processing
2. **Handle errors**: Add error handling for malformed data
3. **Use appropriate data types**: Ensure correct data type handling
4. **Optimize for large files**: Consider performance for large datasets
5. **Document transformations**: Keep track of data transformations

## Example Workflow

**Complete Example:**
> "Create a workflow that reads a sales CSV, filters for the current month, calculates totals by product, and sends a summary email"

This workflow includes:
1. Read CSV file
2. Filter by date
3. Group by product
4. Calculate totals
5. Format summary
6. Send email

## Next Steps

- Try creating a data processing workflow
- Explore [Multi-Step Workflows](../intermediate/multi-step-workflows.md) for complex processing
- Check out [Data Transformation](../intermediate/data-transformation.md) for advanced patterns

