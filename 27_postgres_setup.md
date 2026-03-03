# Demo 27: Snowflake Postgres Setup (~5 min)

## What You'll Show

Cortex Code can create and manage Snowflake Postgres instances — a PostgreSQL-compatible interface for Snowflake that enables existing Postgres applications to work with Snowflake data.

## Context for Presenter

Snowflake Postgres gives customers a PostgreSQL wire-compatible endpoint for their Snowflake data. This means existing tools, ORMs, and applications that speak Postgres can connect to Snowflake without code changes. Cortex Code handles instance creation and management.

**Key talking points:**
- PostgreSQL wire-compatible interface to Snowflake
- Existing Postgres tools and applications work without modification
- Managed by Snowflake — no separate Postgres infrastructure to maintain
- Cortex Code generates the setup commands and manages the lifecycle

---

## Prompts to Execute

### 1. Create a Postgres instance

```
Create a Snowflake Postgres instance called DEMO_PG_INSTANCE. Show me the steps and commands needed to set it up.
```

**What to highlight:** The instance creation process — note that this creates a PostgreSQL-compatible endpoint backed by Snowflake compute and storage.

---

### 2. Connect and verify

```
How do I connect to the Snowflake Postgres instance DEMO_PG_INSTANCE? Show me the connection string and how to verify the connection is working.
```

**What to highlight:** Standard PostgreSQL connection parameters — any tool that connects to Postgres can connect to this endpoint.

---

### 3. Load mock data

```
Using the Postgres instance, create a sample table called orders_summary and load some data from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS — aggregate by year showing total revenue and order count. Verify the data is accessible via the Postgres endpoint.
```

**What to highlight:** Data loaded through Snowflake SQL is immediately accessible via the Postgres interface — a single data platform with multiple access patterns.

---

### 4. Instance management

```
Show me how to manage the Snowflake Postgres instance — describe its current status, and show me how to suspend and resume it. What are the cost implications?
```

**What to highlight:** Lifecycle management — instances can be suspended when not in use to save costs, and resumed on demand.

---

## Expected Outcome

The audience sees that Snowflake Postgres removes the need for separate PostgreSQL infrastructure while maintaining full compatibility with existing tools.

## Cleanup (Optional)

```
Drop the Postgres instance if no longer needed.
```
