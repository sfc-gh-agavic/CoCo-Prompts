# Cortex Code: Overview Demo Suite

## What is Cortex Code?

Cortex Code is Snowflake's AI-powered CLI for software engineering. It connects directly to your Snowflake account and helps you write SQL, generate Python code, build Streamlit apps, debug errors, and more — all from your terminal.

## Prerequisites

- Cortex Code installed and authenticated to a Snowflake account
- Access to `SNOWFLAKE_SAMPLE_DATA` database (included with every Snowflake account)
- A writable database/schema for creating objects (e.g., `DEMO_DB.PUBLIC`)

## Demo Lineup

The **Core Capabilities** demos (1-8) fit in a ~45-minute session. The extended demos (9-28) can be selected a la carte based on audience interest — each is self-contained and runs independently.

---

### Core Capabilities (~45 min)

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 1 | [Data Discovery](01_explore_snowflake.md) | Search objects, explore schemas, understand data | ~5 min |
| 2 | [SQL Generation](02_sql_generation.md) | Write SQL from natural language, iterate on queries | ~5 min |
| 3 | [Python UDFs & Stored Procs](03_python_udf.md) | Generate Snowflake-native Python functions | ~6 min |
| 4 | [Streamlit App](04_streamlit_app.md) | Build an interactive dashboard from scratch | ~6 min |
| 5 | [Code Review & Refactor](05_code_review.md) | Review, optimize, and improve existing code | ~5 min |
| 6 | [Cortex AI Functions](06_cortex_ai_functions.md) | Text analytics with built-in AI functions | ~6 min |
| 7 | [Debugging](07_debugging.md) | Diagnose and fix broken SQL and Python | ~5 min |
| 8 | [End-to-End Pipeline](08_end_to_end.md) | Build a complete data pipeline from scratch | ~7 min |

### Data Analysis & Quality

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 9 | [Analyzing Data](09_analyzing_data.md) | Business questions answered via natural language SQL | ~5 min |
| 10 | [Checking Freshness](10_checking_freshness.md) | Data freshness checks and staleness detection | ~4 min |
| 11 | [Profiling Tables](11_profiling_tables.md) | Deep table profiling and data quality investigation | ~5 min |
| 12 | [Data Quality](12_data_quality.md) | Data Metric Functions for quality monitoring | ~6 min |
| 13 | [Dynamic Tables](13_dynamic_tables.md) | Create and monitor incremental data pipelines | ~6 min |

### Lineage & Discovery

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 14 | [Data Lineage](14_lineage.md) | Upstream/downstream lineage and impact analysis | ~5 min |

### AI, ML & Agents

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 15 | [Cortex Agent](15_cortex_agent.md) | Create and manage domain-specific AI agents | ~7 min |
| 16 | [Semantic View](16_semantic_view.md) | Semantic views for natural language analytics | ~7 min |
| 17 | [Machine Learning](17_machine_learning.md) | End-to-end ML lifecycle with Model Registry | ~8 min |

### Governance & Security

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 18 | [Data Governance](18_data_governance.md) | Classification, masking policies, and access history | ~7 min |
| 19 | [Trust Center](19_trust_center.md) | Security findings, scanners, and remediation | ~5 min |

### Cost & Operations

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 20 | [Cost Management](20_cost_management.md) | Spending analysis, optimization, and budgets | ~5 min |
| 21 | [Integrations](21_integrations.md) | External API access via integrations and UDFs | ~6 min |
| 22 | [Iceberg Tables](22_iceberg.md) | Open Catalog setup and Iceberg table creation | ~6 min |

### Infrastructure

| # | Demo | What It Shows | Time |
|---|------|---------------|------|
| 23 | [dbt on Snowflake](23_dbt_on_snowflake.md) | Deploy dbt projects as native Snowflake objects | ~6 min |
| 24 | [OpenFlow Setup](24_openflow_setup.md) | NiFi-based data integration infrastructure | ~5 min |
| 25 | [OpenFlow Pipeline](25_openflow_pipeline.md) | Build and monitor data integration pipelines | ~6 min |
| 26 | [React App](26_react_app.md) | Embedded analytics React/Next.js application | ~7 min |
| 27 | [Postgres Setup](27_postgres_setup.md) | Snowflake Postgres instance creation and management | ~5 min |
| 28 | [Postgres Replicas](28_postgres_replicas.md) | Read replicas and Python notebook access | ~6 min |

---

## Tips for Presenters

- **Start a fresh session** for each micro-demo to keep context clean
- **Let Cortex Code run** — resist the urge to interrupt; the tool calls are part of the story
- **Highlight the tool usage** — point out when Cortex Code reads files, runs SQL, or searches objects
- **Narrate what's happening** — explain what Cortex Code is doing at each step for the audience
- Each demo is self-contained and can be run independently if time is limited
- The core 8 demos cover the essential capabilities in ~45 minutes
- Extended demos can be mixed and matched based on audience interest and role

## Quick Setup Check

Before starting, verify your connection works by pasting this into Cortex Code:

```
Show me the databases I have access to
```

You should see Cortex Code execute `SHOW DATABASES` and return results including `SNOWFLAKE_SAMPLE_DATA`.
