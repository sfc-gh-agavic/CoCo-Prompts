# Demo 9: Analyzing Data (~5 min)

## What You'll Show

Cortex Code translates natural language business questions into SQL queries, executes them against your Snowflake data, and returns actionable results — no SQL knowledge required from the person asking.

## Context for Presenter

This demo highlights Cortex Code's ability to act as a data analyst on demand. Customers often have business questions that require joining multiple tables, writing aggregations, and understanding data models. Cortex Code handles all of that from a plain English prompt.

**Key talking points:**
- Questions are answered with live SQL against real data — not canned responses
- Cortex Code infers joins, aggregations, and filters from the question context
- Follow-up questions refine the analysis without starting over

---

## Prompts to Execute

### 1. Nation-level analysis

```
Which nations have the highest average order value? Use SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 tables and show the top 10 nations with their average order value and total number of orders.
```

**What to highlight:** Cortex Code joins ORDERS, CUSTOMER, and NATION tables automatically and applies the correct aggregation.

---

### 2. Revenue trend over time

```
What's the revenue trend by quarter for the ORDERS table in SNOWFLAKE_SAMPLE_DATA.TPCH_SF1? Show total revenue per quarter, ordered chronologically.
```

**What to highlight:** Date truncation to quarter, aggregation, and ordering — all inferred from the question.

---

### 3. Supplier diversity analysis

```
Which suppliers have the most diverse product lines? Show the top 10 suppliers by number of distinct parts they supply, along with their nation and the total value of parts they supply. Use SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.
```

**What to highlight:** This requires joining SUPPLIER, PARTSUPP, PART, and NATION — Cortex Code navigates the schema relationships without being told the join keys.

---

### 4. Cross-region comparison

```
Compare customer spending patterns across regions. For each region, show the average customer lifetime spend, the median order size, and the number of active customers. Use SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.
```

**What to highlight:** Multi-metric aggregation with region-level grouping. Point out the use of REGION and NATION tables to roll up from customer to region.

---

## Expected Outcome

The audience sees that Cortex Code can serve as an on-demand analyst — translating business questions into precise SQL, executing it, and delivering results in seconds.
