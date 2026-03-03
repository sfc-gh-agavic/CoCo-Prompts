# Demo 10: Checking Freshness (~4 min)

## What You'll Show

Cortex Code can check when tables were last updated, assess data currency, and identify potentially stale data — helping teams trust their data before making decisions.

## Context for Presenter

Data freshness is a constant concern for analytics teams. Before building a report or dashboard, users need to know if the underlying data is current. Cortex Code makes freshness checks conversational instead of requiring manual metadata queries.

**Key talking points:**
- Freshness checks use Snowflake metadata — no custom instrumentation needed
- Cortex Code interprets timestamps and flags potential staleness
- Useful as a pre-analysis validation step

---

## Prompts to Execute

### 1. Check a single table

```
Is the ORDERS table in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 up to date? When was it last modified?
```

**What to highlight:** Cortex Code queries table metadata to find the last altered timestamp and interprets what that means for data currency.

---

### 2. Check a specific table's details

```
When was SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.LINEITEM last updated? How many rows does it have and when was it created?
```

**What to highlight:** It pulls creation time, last altered time, and row count — a quick health check on the table.

---

### 3. Schema-wide freshness scan

```
Check the freshness of all tables in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1. Show me each table with its last modified date and row count, sorted by least recently updated first.
```

**What to highlight:** A single prompt scans all tables in the schema and presents a freshness overview — something that would normally require writing an INFORMATION_SCHEMA query.

---

### 4. Staleness assessment

```
Are there any stale tables in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 that I should be concerned about? Flag anything that hasn't been updated in over 30 days.
```

**What to highlight:** Cortex Code applies a staleness threshold and gives a plain-language assessment — not just raw dates.

---

## Expected Outcome

The audience understands that Cortex Code can act as a data freshness monitor, giving quick confidence checks before analysis begins.
