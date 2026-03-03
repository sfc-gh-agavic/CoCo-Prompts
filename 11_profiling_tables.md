# Demo 11: Profiling Tables (~5 min)

## What You'll Show

Cortex Code can generate deep statistical profiles of tables — column distributions, null rates, cardinality, min/max values, and potential data quality issues — from a single prompt.

## Context for Presenter

Table profiling is one of the first things data engineers do when onboarding new data or investigating quality issues. Manually writing profiling queries for every column is tedious. Cortex Code automates this entirely.

**Key talking points:**
- Full table profiles generated from a single natural language request
- Identifies potential quality issues like high null rates or low cardinality
- Can compare profiles across tables to spot structural differences

---

## Prompts to Execute

### 1. Profile a table

```
Profile the ORDERS table in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1. For each column, show the data type, null count, distinct values, and min/max where applicable.
```

**What to highlight:** Cortex Code generates a comprehensive profiling query covering all columns — this would take significant manual effort to write.

---

### 2. Distribution analysis

```
What are the distributions of the O_ORDERSTATUS and O_ORDERPRIORITY columns in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS? Show value counts and percentages for each.
```

**What to highlight:** Categorical distribution analysis — useful for understanding the shape of the data before building pipelines or reports.

---

### 3. Data quality investigation

```
Look at SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.LINEITEM and identify any potential data quality issues. Check for nulls, outliers in numeric columns, and any columns with suspiciously low cardinality.
```

**What to highlight:** Cortex Code goes beyond basic stats to flag anomalies and interpret what they might mean for data quality.

---

### 4. Cross-table comparison

```
Compare the profile of the CUSTOMER table versus the SUPPLIER table in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1. Which table has more rows, more columns, and how do their key columns differ in terms of cardinality and null rates?
```

**What to highlight:** Side-by-side table comparison — useful when evaluating data assets or planning joins.

---

## Expected Outcome

The audience sees that Cortex Code eliminates the tedious work of writing profiling queries and provides instant visibility into data characteristics and quality.
