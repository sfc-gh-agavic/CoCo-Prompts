# Demo 20: Cost Management (~5 min)

## What You'll Show

Cortex Code can analyze Snowflake spending — breaking down credit consumption by warehouse, identifying top spenders, spotting optimization opportunities, and helping set up budgets.

## Context for Presenter

Cost management is a top concern for every Snowflake customer. The ACCOUNT_USAGE views contain rich spending data, but writing the right queries is time-consuming. Cortex Code makes cost analysis conversational and surfaces optimization opportunities automatically.

**Key talking points:**
- Snowflake tracks granular credit consumption across all services
- Cortex Code queries ACCOUNT_USAGE views and summarizes spending patterns
- Identifies waste — idle warehouses, expensive queries, underutilized resources
- Can help set up resource monitors and budgets

---

## Prompts to Execute

### 1. Current month spending

```
What is my current month's credit consumption in Snowflake? Break it down by service type — compute, serverless, storage, and any Cortex AI costs.
```

**What to highlight:** Cortex Code queries the metering history and presents a clear spending summary — no need to remember which ACCOUNT_USAGE views to query.

---

### 2. Warehouse cost breakdown

```
Show me the credit consumption by warehouse for the last 30 days. Which warehouses are the most expensive and what percentage of total spend does each represent?
```

**What to highlight:** Warehouse-level breakdown is the most common cost question — Cortex Code generates the correct query against WAREHOUSE_METERING_HISTORY.

---

### 3. Top spenders and expensive queries

```
Who are the top 10 users by credit consumption this month? Also show me the 5 most expensive individual queries by credits consumed.
```

**What to highlight:** User-level and query-level attribution — essential for chargeback and optimization conversations.

---

### 4. Optimization recommendations

```
Based on the warehouse usage patterns, are there any optimization opportunities? Look for warehouses that could benefit from auto-suspend tuning, right-sizing, or consolidation.
```

**What to highlight:** Cortex Code goes beyond reporting to provide actionable optimization advice — analyzing utilization patterns and idle time.

---

## Expected Outcome

The audience sees that Cortex Code provides instant visibility into Snowflake spending and proactively identifies cost optimization opportunities.
