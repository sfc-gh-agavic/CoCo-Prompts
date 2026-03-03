# Demo 14: Data Lineage (~5 min)

## What You'll Show

Cortex Code traces data lineage in both directions — upstream ("where does this data come from?") and downstream ("what depends on this?") — enabling impact analysis and root cause debugging.

## Context for Presenter

Understanding data dependencies is critical for change management and debugging. When a source table changes, teams need to know what downstream reports break. When a report shows wrong numbers, they need to trace back to the root cause. Cortex Code makes lineage exploration conversational.

**Key talking points:**
- Upstream lineage traces data origins — useful for debugging incorrect results
- Downstream lineage shows impact — critical before making schema changes
- Cortex Code uses Snowflake's ACCESS_USAGE and OBJECT_DEPENDENCIES metadata
- No third-party lineage tools required

---

## Prompts to Execute

### 1. Upstream lineage — where does data come from?

```
What are the upstream dependencies of the tables in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1? Trace the lineage for the LINEITEM table — what objects does it depend on?
```

**What to highlight:** Cortex Code queries dependency metadata to show the full upstream chain. For sample data this may be simple, but the pattern applies to complex pipelines.

---

### 2. Downstream impact analysis

```
If I were to modify the SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS table, what downstream objects would be affected? Show me all views, dynamic tables, or other objects that depend on it.
```

**What to highlight:** This is the classic "what breaks if I change this?" question. Cortex Code checks object dependencies to identify all downstream consumers.

---

### 3. Column-level lineage

```
Trace the lineage at the column level — for the ORDERS table in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1, which downstream queries or objects reference the O_TOTALPRICE column? Use access history if available.
```

**What to highlight:** Column-level lineage is more granular than table-level — it tells you exactly which fields are used where.

---

### 4. Full dependency graph

```
Show me the full dependency graph for the DEMO_DB.PUBLIC schema. List all objects and their relationships — which objects feed into which, and are there any circular dependencies?
```

**What to highlight:** A schema-level dependency overview — useful for understanding the overall architecture of a data platform.

---

## Expected Outcome

The audience sees that Snowflake's built-in lineage metadata, combined with Cortex Code, provides powerful impact analysis and debugging capabilities without external tools.
