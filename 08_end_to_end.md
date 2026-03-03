# Demo 8: End-to-End Pipeline (~7 min)

## What You'll Show

Cortex Code can build a complete data pipeline from scratch — creating tables, transforming data, scheduling with tasks, and validating results — all in a single conversational flow.

## Context for Presenter

This is the capstone demo. It ties together everything the audience has seen: SQL generation, object creation, code generation, and iterative refinement. The goal is to show that Cortex Code can handle a realistic workflow, not just isolated queries.

**Key talking points:**
- End-to-end pipeline in minutes, not hours
- Each step builds on the previous one — Cortex Code maintains context
- Production patterns: staging tables, transformations, validation checks
- The audience has seen each piece individually — now they see it work together

---

## Prompts to Execute

### 1. Set up the staging layer

```
In DEMO_DB.PUBLIC, create a pipeline for analyzing order profitability from the TPCH data. Start by creating a staging table called STG_ORDER_PROFITABILITY that joins ORDERS, LINEITEM, CUSTOMER, NATION, and SUPPLIER from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1. Include: order key, order date, customer name, customer nation, supplier nation, extended price, discount, tax, and a calculated profit column (l_extendedprice * (1 - l_discount) - l_supplycost * l_quantity). Only include completed orders (status = 'F').
```

**What to highlight:** Cortex Code generates the CREATE TABLE AS SELECT with all the joins and the calculated column. It handles the multi-table join correctly from a natural language description.

---

### 2. Create an aggregation layer

```
Now create a summary table called AGG_PROFITABILITY_BY_ROUTE that aggregates the staging table by customer nation and supplier nation (the "shipping route"). Calculate: total profit, order count, average profit per order, and the profit margin percentage. Add a rank column ranking routes by total profit.
```

**What to highlight:** The CTAS references the table just created. Cortex Code chains the pipeline steps naturally.

---

### 3. Add a data quality check

```
Create a stored procedure called VALIDATE_PROFITABILITY_PIPELINE that checks:
1. STG_ORDER_PROFITABILITY has more than 0 rows
2. No NULL values in the profit column
3. AGG_PROFITABILITY_BY_ROUTE has the expected number of route combinations
4. Total profit in the aggregation matches total profit in staging

The procedure should return a summary of all checks with pass/fail status.
```

**What to highlight:** Production pipelines need validation. Cortex Code generates a stored procedure with multiple data quality checks — something that usually requires significant boilerplate.

---

### 4. Query the final results

```
Run the validation procedure, then show me the top 10 most profitable shipping routes and the bottom 5. Also tell me which routes have the highest profit margin percentage.
```

**What to highlight:** The full pipeline is working — staging, aggregation, validation, and analytics. All built conversationally in a few minutes.

---

### 5. Clean up

```
Generate a cleanup script that drops STG_ORDER_PROFITABILITY, AGG_PROFITABILITY_BY_ROUTE, and the VALIDATE_PROFITABILITY_PIPELINE procedure. Write it to overview/cleanup.sql but don't execute it yet.
```

**What to highlight:** Cortex Code generates a cleanup script — responsible pipeline management. The presenter can choose to run it or leave the objects for attendees to explore.

---

## Expected Outcome

The audience sees Cortex Code handle a realistic, multi-step data engineering workflow end-to-end. The key message: Cortex Code isn't a toy for simple queries — it's a productivity tool for real work.

## Cleanup

Run the generated `overview/cleanup.sql` to remove all demo objects, or keep them for attendees to explore:

```
Run the cleanup script in overview/cleanup.sql
```
