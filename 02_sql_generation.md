# Demo 2: SQL Generation (~5 min)

## What You'll Show

Cortex Code generates, executes, and iterates on SQL queries from natural language descriptions. It understands Snowflake-specific syntax and can build complex queries including window functions, CTEs, and aggregations.

## Context for Presenter

This is the core "wow moment" for many users. They describe what they want in English, and Cortex Code writes production-quality SQL, runs it, and shows results. The iterative refinement is key — watch how follow-up prompts modify the query without starting over.

**Key talking points:**
- SQL is generated AND executed — not just shown
- Follow-up prompts refine the query contextually
- Snowflake-specific syntax (QUALIFY, FLATTEN, etc.) is handled natively

---

## Prompts to Execute

### 1. Simple analytical query

```
Using SNOWFLAKE_SAMPLE_DATA.TPCH_SF1, write and run a query that shows the top 10 customers by total order value. Include customer name, nation, and total spend.
```

**What to highlight:** Cortex Code joins ORDERS, CUSTOMER, and NATION tables correctly without being told the join keys.

---

### 2. Iterate on the query

```
Now break that down by year and add a rank column showing each customer's rank within their nation per year. Use a window function.
```

**What to highlight:** It modifies the previous query rather than starting from scratch. The window function uses Snowflake's QUALIFY or ROW_NUMBER correctly.

---

### 3. Complex aggregation

```
Write a query that finds the month-over-month percentage change in total revenue from the ORDERS table, but only for orders with status 'F'. Format the percentage to 2 decimal places.
```

**What to highlight:** LAG window function, date truncation, percentage formatting — all generated from a single English description.

---

### 4. Explain existing SQL

```
Can you explain what that last query does step by step? If there are any performance concerns, flag them.
```

**What to highlight:** Cortex Code can reverse-engineer SQL into plain English and provide optimization advice.

---

## Expected Outcome

The audience sees that Cortex Code is not just a query writer — it's an interactive SQL partner that understands context, iterates, and explains.
