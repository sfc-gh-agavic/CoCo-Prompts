# Demo 22: Iceberg Tables (~6 min)

## What You'll Show

Cortex Code helps set up Apache Iceberg tables in Snowflake — from catalog integrations and external volumes to creating and querying Iceberg tables with auto-refresh.

## Context for Presenter

Iceberg tables let customers bring open table format data into Snowflake, enabling interoperability with other engines while leveraging Snowflake's query performance. The setup involves multiple components (external volumes, catalog integrations), and Cortex Code guides the process.

**Key talking points:**
- Iceberg tables provide open format interoperability
- Snowflake can read/write Iceberg tables with full query performance
- Catalog integrations connect to external catalogs (Polaris, Glue, REST)
- Cortex Code generates the multi-step setup DDL

---

## Prompts to Execute

### 1. Explain the Iceberg setup

```
Walk me through what's needed to set up Iceberg tables in Snowflake. What objects do I need to create and in what order?
```

**What to highlight:** Cortex Code explains the full architecture — external volume, catalog integration, and Iceberg table — and the dependencies between them.

---

### 2. Create a catalog integration (pattern)

```
Show me the DDL to create a catalog integration for Snowflake Open Catalog (REST catalog type). Use placeholder values for the catalog URI and warehouse. Explain each parameter.
```

**What to highlight:** The catalog integration connects Snowflake to an external Iceberg catalog. Note: this requires a real catalog endpoint to execute — we're showing the pattern.

---

### 3. Create an Iceberg table (Snowflake-managed)

```
Create a Snowflake-managed Iceberg table in DEMO_DB.PUBLIC called ORDERS_ICEBERG with the same schema as SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS. Use DEMO_DB.PUBLIC as the base location and Snowflake as the catalog.
```

**What to highlight:** Snowflake-managed Iceberg tables are the simplest path — Snowflake handles the catalog and storage. This can actually be executed in the demo.

---

### 4. Query and check status

```
Insert a few sample rows into DEMO_DB.PUBLIC.ORDERS_ICEBERG from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS (limit to 100 rows), then query it. Also show me the table's Iceberg metadata — snapshot information and file details.
```

**What to highlight:** Iceberg tables work like any other Snowflake table for queries, but expose Iceberg-specific metadata like snapshots and data files.

---

## Expected Outcome

The audience understands the Iceberg table architecture in Snowflake and sees that Cortex Code can generate the setup and guide the configuration process.

## Cleanup (Optional)

```
Drop the Iceberg table: DROP ICEBERG TABLE IF EXISTS DEMO_DB.PUBLIC.ORDERS_ICEBERG;
```
