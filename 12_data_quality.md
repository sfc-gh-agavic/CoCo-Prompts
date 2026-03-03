# Demo 12: Data Quality with DMFs (~6 min)

## What You'll Show

Cortex Code can set up and manage Snowflake Data Metric Functions (DMFs) for ongoing data quality monitoring — detecting nulls, duplicates, and freshness issues automatically.

## Context for Presenter

Data quality monitoring is critical for production pipelines. Snowflake's built-in DMFs provide a native way to measure quality without external tools. Cortex Code simplifies the setup, configuration, and review of these metrics.

**Key talking points:**
- DMFs are Snowflake-native — no external tools or orchestration needed
- Cortex Code handles the DDL for creating test tables and attaching metrics
- Quality scores provide an at-a-glance view of data health

---

## Prompts to Execute

### 1. Create a test table with quality issues

```
Create a table called DEMO_DB.PUBLIC.QUALITY_TEST with columns: ID (number), CUSTOMER_NAME (varchar), EMAIL (varchar), ORDER_DATE (date), AMOUNT (number). Insert 20 rows of sample data, but intentionally include 3 null emails, 2 duplicate IDs, and 1 null customer name to simulate data quality issues.
```

**What to highlight:** We're setting up a controlled test with known issues so we can show DMFs detecting them.

---

### 2. Attach data metric functions

```
Set up data quality monitoring on DEMO_DB.PUBLIC.QUALITY_TEST using Snowflake's built-in Data Metric Functions. Attach NULL_COUNT metrics on the EMAIL and CUSTOMER_NAME columns, and DUPLICATE_COUNT on the ID column. Schedule them to run on a regular basis.
```

**What to highlight:** Cortex Code uses the `$data_quality` skill to generate the correct `ALTER TABLE ... SET DATA_METRIC_FUNCTION` syntax.

---

### 3. Check quality results

```
Check the data quality results for DEMO_DB.PUBLIC.QUALITY_TEST. Show me the current quality scores and any failing metrics.
```

**What to highlight:** Cortex Code queries the DMF results and presents a clear quality assessment — flagging the nulls and duplicates we intentionally introduced.

---

### 4. Assess overall schema quality

```
Give me an overall data quality summary for the DEMO_DB.PUBLIC schema. Are there any tables with quality issues I should investigate?
```

**What to highlight:** Schema-level quality monitoring — a single prompt gives visibility across all monitored tables.

---

## Expected Outcome

The audience sees that Snowflake has built-in data quality monitoring and Cortex Code makes it simple to set up, configure, and review quality metrics.

## Cleanup (Optional)

```
Drop the table DEMO_DB.PUBLIC.QUALITY_TEST.
```
