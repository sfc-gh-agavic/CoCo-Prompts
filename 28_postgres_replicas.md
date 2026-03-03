# Demo 28: Snowflake Postgres Replicas (~6 min)

## What You'll Show

Cortex Code can set up read replicas for Snowflake Postgres instances and demonstrate connecting to them from Python notebooks — enabling analytics workloads to run against replicas without impacting production.

## Context for Presenter

Read replicas are a common pattern for offloading analytics queries from production databases. Snowflake Postgres supports replicas, and Cortex Code helps set them up and demonstrates access from Python using standard libraries like psycopg2 or SQLAlchemy.

**Key talking points:**
- Read replicas offload analytics from the primary instance
- Standard Python libraries (psycopg2, SQLAlchemy) work out of the box
- No application code changes needed to switch between primary and replica
- Cortex Code generates both the replica setup and the Python notebook code

---

## Prompts to Execute

### 1. Create a read replica

```
Create a read replica of the Snowflake Postgres instance DEMO_PG_INSTANCE. Show me the commands and explain the replication architecture.
```

**What to highlight:** Read replicas provide a separate endpoint for read-only queries — the replication is managed by Snowflake.

---

### 2. Connect from Python

```
Create a Python notebook that connects to the Snowflake Postgres replica using psycopg2. Query the orders_summary table and display the results in a pandas DataFrame.
```

**What to highlight:** Standard Python database connectivity — psycopg2 is the most common Postgres adapter, and it works directly with Snowflake Postgres.

---

### 3. Compare primary vs replica

```
In the notebook, add cells that connect to both the primary instance and the replica. Run the same query on both and compare the results to verify they're in sync. Show the connection details for each.
```

**What to highlight:** Both endpoints return the same data — the replica stays in sync automatically, and applications can route read traffic to the replica.

---

### 4. Analytics use case

```
Show a use case where you'd use the replica for analytics: connect to the replica, run an aggregation query on orders data, and create a simple matplotlib chart showing revenue by year. Explain why this is better than hitting the primary instance.
```

**What to highlight:** The practical benefit — analytics teams get their own endpoint with no impact on production workloads, using familiar Python tools.

---

## Expected Outcome

The audience sees that Snowflake Postgres replicas enable a clean separation between production and analytics workloads, with standard Python connectivity.

## Cleanup (Optional)

```
Drop the read replica and primary Postgres instance if no longer needed.
```
