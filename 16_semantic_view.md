# Demo 16: Semantic View (~7 min)

## What You'll Show

Cortex Code can create semantic views that define business-friendly data models over raw tables, then query them using natural language through Cortex Analyst.

## Context for Presenter

Semantic views bridge the gap between raw database schemas and business terminology. They define dimensions, measures, and metrics in a way that Cortex Analyst can understand, enabling reliable natural language querying. Cortex Code simplifies both creation and querying.

**Key talking points:**
- Semantic views define business meaning on top of physical tables
- Cortex Analyst uses semantic views to generate accurate SQL from natural language
- No data duplication — semantic views are metadata layers
- Cortex Code generates the DDL and tests queries end-to-end

---

## Prompts to Execute

### 1. Create a semantic view

```
Create a semantic view called DEMO_DB.PUBLIC.TPCH_REVENUE_VIEW over the SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 ORDERS and CUSTOMER tables. Define dimensions for customer name, nation, and order status. Define measures for total revenue, order count, and average order value. Add a time dimension on order date.
```

**What to highlight:** The CREATE SEMANTIC VIEW DDL — note how business concepts (revenue, order count) are mapped to physical columns and expressions.

---

### 2. Query using Cortex Analyst

```
Using Cortex Analyst with the semantic view DEMO_DB.PUBLIC.TPCH_REVENUE_VIEW, ask: "What is the total revenue by nation for completed orders?"
```

**What to highlight:** Natural language is translated to SQL using the semantic view definitions — the query is grounded in verified business logic, not guesswork.

---

### 3. More complex natural language query

```
Using Cortex Analyst with DEMO_DB.PUBLIC.TPCH_REVENUE_VIEW, ask: "Show me the monthly revenue trend for the top 3 nations by total revenue."
```

**What to highlight:** The semantic view enables complex queries while maintaining accuracy — Cortex Analyst knows which columns represent revenue and time.

---

### 4. Validate and iterate

```
Describe the semantic view DEMO_DB.PUBLIC.TPCH_REVENUE_VIEW. Are there any dimensions or measures I should add to make it more useful for business analysts?
```

**What to highlight:** Cortex Code can audit semantic views and suggest improvements — making it an iterative design tool.

---

## Expected Outcome

The audience sees that semantic views enable trusted natural language analytics, and Cortex Code makes the full lifecycle — create, query, iterate — fast and accessible.

## Cleanup (Optional)

```
Drop the semantic view DEMO_DB.PUBLIC.TPCH_REVENUE_VIEW.
```
