# Demo 13: Dynamic Tables (~6 min)

## What You'll Show

Cortex Code helps build incremental data pipelines using Snowflake Dynamic Tables — creating materialized views that automatically refresh based on a target lag, with no orchestration required.

## Context for Presenter

Dynamic tables are Snowflake's declarative approach to data pipelines. Instead of writing ETL orchestration code, you define the transformation and a freshness target, and Snowflake handles the rest. Cortex Code simplifies the creation and monitoring of these pipelines.

**Key talking points:**
- Dynamic tables replace complex ETL orchestration with a declarative model
- Target lag defines how fresh the data needs to be — Snowflake handles scheduling
- Cortex Code generates the DDL and helps monitor refresh status

---

## Prompts to Execute

### 1. Create a dynamic table

```
Create a dynamic table called DEMO_DB.PUBLIC.ORDERS_SUMMARY that aggregates orders from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS by year and month, showing total revenue, order count, and average order value. Set the target lag to 1 hour and use the warehouse COMPUTE_WH.
```

**What to highlight:** The CREATE DYNAMIC TABLE syntax with TARGET_LAG — this single statement defines both the transformation and the refresh policy.

---

### 2. Check refresh status

```
What is the current refresh status of the dynamic table DEMO_DB.PUBLIC.ORDERS_SUMMARY? Is it up to date?
```

**What to highlight:** Cortex Code queries the dynamic table metadata to show refresh history, last refresh time, and current status.

---

### 3. Monitor the pipeline

```
Show me all dynamic tables in DEMO_DB.PUBLIC. For each one, show the target lag, last refresh time, and whether it's currently healthy.
```

**What to highlight:** A single prompt gives a pipeline health dashboard — useful for operations teams monitoring data freshness.

---

### 4. Troubleshoot if needed

```
If the dynamic table DEMO_DB.PUBLIC.ORDERS_SUMMARY had a refresh failure, how would I diagnose it? Show me the relevant diagnostic queries.
```

**What to highlight:** Cortex Code generates the troubleshooting queries — checking refresh history, error messages, and dependency status.

---

## Expected Outcome

The audience sees that dynamic tables provide a dramatically simpler alternative to traditional ETL pipelines, and Cortex Code makes them easy to create and monitor.

## Cleanup (Optional)

```
Drop the dynamic table DEMO_DB.PUBLIC.ORDERS_SUMMARY.
```
