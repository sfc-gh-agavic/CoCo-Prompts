# Demo 5: Code Review & Refactor (~5 min)

## What You'll Show

Cortex Code can read existing code, identify issues, suggest improvements, and refactor it — acting as an on-demand code reviewer that understands Snowflake-specific patterns.

## Context for Presenter

Code review is time-consuming and often delayed. Cortex Code provides instant feedback on SQL and Python code quality, performance, and Snowflake best practices. This is especially valuable for teams ramping up on Snowflake who may not know the platform's idioms yet.

**Key talking points:**
- Reviews code for correctness, performance, and Snowflake best practices
- Suggests concrete refactors, not just vague advice
- Can rewrite code in place with your approval
- Understands anti-patterns specific to Snowflake (e.g., implicit cartesian joins, missing clustering)

---

## Prompts to Execute

### 1. Review inefficient SQL

First, create a file for Cortex Code to review:

```
Write this SQL to overview/slow_query.sql — it's intentionally not great and I want you to review it after:

SELECT *
FROM SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.LINEITEM l,
     SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS o,
     SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.CUSTOMER c
WHERE l.L_ORDERKEY = o.O_ORDERKEY
AND o.O_CUSTKEY = c.C_CUSTKEY
AND YEAR(o.O_ORDERDATE) = 1995
AND l.L_QUANTITY > 20
ORDER BY l.L_EXTENDEDPRICE DESC
```

Then ask:

```
Review the SQL in overview/slow_query.sql. Identify any performance issues, anti-patterns, or Snowflake best practices violations. Suggest a rewritten version.
```

**What to highlight:** It identifies SELECT *, implicit joins (comma syntax), function-on-column in WHERE (YEAR()), and suggests explicit JOINs, column selection, and predicate pushdown.

---

### 2. Review generated Python

```
Read the file overview/order_dashboard.py that we created in the Streamlit demo. Review it for code quality, potential bugs, and Streamlit best practices. Suggest 3 specific improvements.
```

**What to highlight:** If the Streamlit demo was run first, Cortex Code reviews the generated file. If not, it will note the file doesn't exist — either way, the interaction pattern is clear. This shows Cortex Code can review its own output critically.

---

### 3. Refactor on command

```
Rewrite the SQL in overview/slow_query.sql with all your suggested improvements applied. Replace the file contents.
```

**What to highlight:** It applies its own review feedback, replacing the file with an optimized version. Point out the edit tool usage — it's not rewriting from memory, it's reading and editing the actual file.

---

## Expected Outcome

The audience sees that Cortex Code can serve as a senior engineer's first pass at code review, catching common issues and applying fixes immediately.

## Cleanup (Optional)

Delete `overview/slow_query.sql` after the demo.
