---
title: "Data Transformation Pipelines"
level: intermediate
duration: 30 minutes
prerequisites: ["library/basic/simple-data-processing", "library/intermediate/multi-step-workflows"]
tags: [data, transformation, etl, pipelines, intermediate]
category: library/intermediate
description: "Learn to build data transformation pipelines with multiple processing stages"
---

# Data Transformation Pipelines

Build sophisticated data transformation pipelines that clean, transform, and enrich data through multiple stages. This tutorial covers ETL (Extract, Transform, Load) patterns.

## What You'll Learn

- How to design data transformation pipelines
- How to chain transformation steps
- How to handle data validation
- How to optimize transformation workflows

## Prerequisites

- Understanding of data processing basics
- Experience with multi-step workflows
- Knowledge of data formats (CSV, JSON, Excel)

## Pipeline Architecture

### ETL Pattern

**Extract → Transform → Load**

```
Step 1: Extract data from source
  ↓
Step 2: Clean and validate data
  ↓
Step 3: Transform data structure
  ↓
Step 4: Enrich with additional data
  ↓
Step 5: Load to destination
```

## Transformation Stages

### Stage 1: Extraction

**Purpose:** Get data from source systems

**Example:**
> "Extract sales data from CSV file, API, or database"

**Common Sources:**
- CSV/Excel files
- APIs
- Databases
- Cloud storage
- Email attachments

### Stage 2: Cleaning

**Purpose:** Fix data quality issues

**Operations:**
- Remove duplicates
- Fix formatting
- Handle missing values
- Standardize formats
- Validate data types

**Example:**
> "Clean customer data: remove duplicates, standardize phone numbers, fix email formats"

### Stage 3: Transformation

**Purpose:** Change data structure and format

**Operations:**
- Reshape data structure
- Calculate derived fields
- Aggregate data
- Filter and sort
- Merge datasets

**Example:**
> "Transform sales data: calculate totals, group by region, add computed fields"

### Stage 4: Enrichment

**Purpose:** Add additional data

**Operations:**
- Lookup additional information
- Merge with reference data
- Add calculated metrics
- Append metadata

**Example:**
> "Enrich customer data with demographic information from another source"

### Stage 5: Loading

**Purpose:** Save transformed data

**Destinations:**
- CSV/Excel files
- Databases
- Cloud storage
- APIs
- Email reports

## Real-World Example

### Complete Pipeline: Sales Data Processing

**Request:**
> "Create a workflow that processes daily sales data: extract from CSV, clean, calculate metrics, enrich with product info, and generate a report"

**Pipeline:**
```
Step 1: Extract sales CSV from Drive
  ↓
Step 2: Clean data (remove duplicates, fix dates)
  ↓
Step 3: Validate data (check required fields)
  ├─→ If invalid: Step 4: Send error notification
  └─→ If valid: Continue
        ↓
    Step 5: Calculate metrics (totals, averages)
        ↓
    Step 6: Enrich with product data (lookup product names)
        ↓
    Step 7: Generate report
        ↓
    Step 8: Save report to Drive
    Step 9: Send email notification (parallel)
```

## Transformation Patterns

### Pattern 1: Data Normalization

**Purpose:** Standardize data formats

**Example:**
- Dates: Convert all to YYYY-MM-DD
- Phone: Standardize to (XXX) XXX-XXXX
- Currency: Convert to single currency

### Pattern 2: Data Aggregation

**Purpose:** Summarize data

**Example:**
- Group by category
- Calculate totals
- Compute averages
- Count occurrences

### Pattern 3: Data Joining

**Purpose:** Combine multiple data sources

**Example:**
- Join customer data with order data
- Merge sales with product information
- Combine multiple CSV files

### Pattern 4: Data Filtering

**Purpose:** Select relevant data

**Example:**
- Filter by date range
- Filter by status
- Filter by criteria

## Validation and Error Handling

### Data Validation

**Validate at each stage:**
- Input validation (Stage 1)
- Data quality checks (Stage 2)
- Business rule validation (Stage 3)
- Output validation (Stage 5)

**Example:**
```
Step 1: Extract data
  ↓
Step 2: Validate structure (required fields present?)
  ├─→ Invalid: Log error, send notification
  └─→ Valid: Continue
        ↓
    Step 3: Validate business rules (values in range?)
        ├─→ Invalid: Flag for review
        └─→ Valid: Continue
```

### Error Handling

**Strategies:**
- Skip invalid records
- Flag for manual review
- Use default values
- Abort pipeline

## Performance Optimization

### Batch Processing

Process data in batches rather than row-by-row:

**Example:**
```
Step 1: Extract all data
  ↓
Step 2: Process in batches of 1000 records
  ├─→ Batch 1
  ├─→ Batch 2 (parallel)
  └─→ Batch 3 (parallel)
        ↓
    Step 3: Combine results
```

### Incremental Processing

Process only new/changed data:

**Example:**
```
Step 1: Extract data since last run
  ↓
Step 2: Process only new records
  ↓
Step 3: Append to existing results
```

## Best Practices

1. **Validate early**: Check data quality as soon as possible
2. **Log transformations**: Keep track of what changed
3. **Handle errors gracefully**: Don't fail entire pipeline for one bad record
4. **Test with sample data**: Verify transformations before full run
5. **Document transformations**: Explain what each step does
6. **Optimize for performance**: Use parallel processing where possible

## Common Use Cases

- **Data migration**: Move data between systems
- **Report generation**: Transform raw data into reports
- **Data integration**: Combine data from multiple sources
- **Data quality**: Clean and standardize data
- **Analytics preparation**: Prepare data for analysis

## Next Steps

- Build a data transformation pipeline
- Explore [Complex Branching](../advanced/complex-branching.md) for conditional transformations
- Check out [Workflow Composition](../advanced/workflow-composition.md) for reusable components

