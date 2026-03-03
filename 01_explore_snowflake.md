# Demo 1: Data Discovery (~5 min)

## What You'll Show

Cortex Code can connect to your Snowflake account and explore data without you writing a single query. It searches objects, describes tables, previews data, and helps you understand what you're working with.

## Context for Presenter

This demo sets the stage. Customers often spend significant time navigating the Snowsight UI to understand their data landscape. Cortex Code makes this conversational — ask questions in plain English and get immediate answers grounded in your actual account.

**Key talking points:**
- No need to memorize `INFORMATION_SCHEMA` queries
- Cortex Code reads metadata directly from your account
- Results are live — this is your real data, not a simulation

---

## Prompts to Execute

### 1. Discover available data

Paste into Cortex Code:

```
What databases do I have access to? Give me a quick summary of what's available.
```

**What to highlight:** Cortex Code runs `SHOW DATABASES` and summarizes the results conversationally.

---

### 2. Explore a specific database

```
Show me all the schemas and tables in the SNOWFLAKE_SAMPLE_DATA database. Which tables have the most rows?
```

**What to highlight:** It navigates the hierarchy — database to schema to tables — and pulls row counts from metadata.

---

### 3. Understand a table's structure

```
Describe the SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS table. What does each column represent and what are the data types?
```

**What to highlight:** Cortex Code runs `DESCRIBE TABLE` and explains columns in plain language, not just raw DDL output.

---

### 4. Preview sample data

```
Show me 5 sample rows from the ORDERS table and tell me what kind of data this looks like. What questions could a business analyst answer with this table?
```

**What to highlight:** It queries the data, interprets it, and suggests analytical use cases — going beyond just showing rows.

---

## Expected Outcome

By the end of this demo, the audience should see that Cortex Code acts as a conversational interface to their Snowflake account — no SQL required for basic exploration.
