# Demo 7: Debugging (~5 min)

## What You'll Show

Cortex Code can diagnose broken SQL and Python, explain what went wrong, and fix the code — turning cryptic error messages into clear explanations and working solutions.

## Context for Presenter

Debugging is where developers spend a huge portion of their time. Snowflake error messages can be cryptic for newcomers. Cortex Code acts as a translator between error output and actionable fixes.

**Key talking points:**
- Paste an error message and get a plain-English explanation
- Cortex Code can fix the code and re-run to verify
- Understands Snowflake-specific errors (binding, type mismatches, permissions)
- Works with both SQL and Python errors

---

## Prompts to Execute

### 1. Fix broken SQL

```
Run this SQL and help me fix whatever is wrong:

SELECT
    c.C_NAME,
    c.C_NATIONKEY,
    TOTAL_ORDERS
FROM SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.CUSTOMER c
JOIN (
    SELECT O_CUSTKEY, COUNT(*) AS TOTAL_ORDERS
    FROM SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS
    GROUP BY O_CUSTKEY
) o
WHERE c.C_CUSTKEY = o.O_CUSTKEY
AND TOTAL_ORDERS > 10
QUALIFY ROW_NUMBER() OVER (PARTITION BY c.C_NATIONKEY ORDER BY TOTAL_ORDERS DESC) <= 3
```

**What to highlight:** The query is missing the ON clause for the JOIN (uses WHERE instead). Cortex Code will identify this, explain the issue, fix it, and re-run successfully.

---

### 2. Debug a type error

```
Run this and tell me what's wrong:

SELECT
    O_ORDERKEY,
    O_ORDERDATE,
    O_TOTALPRICE,
    O_TOTALPRICE + '100' AS ADJUSTED_PRICE
FROM SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS
LIMIT 5;
```

**What to highlight:** This may succeed due to implicit casting in Snowflake, but Cortex Code should flag the anti-pattern of adding a string to a number and suggest using an explicit numeric literal or CAST.

---

### 3. Explain a cryptic error

```
I tried to create a stored procedure but got this error. What does it mean and how do I fix it?

Error: "JavaScript execution error: Uncaught ReferenceError: snowflake is not defined"
```

**What to highlight:** Cortex Code explains that this error comes from JavaScript stored procedures where the `snowflake` object is only available in the handler context. It will suggest the correct pattern or recommend using SQL/Python procedures instead.

---

### 4. Fix a logical bug

```
This query is supposed to find customers who have NEVER placed an order, but it's returning customers who HAVE placed orders. Fix it:

SELECT c.C_NAME, c.C_CUSTKEY
FROM SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.CUSTOMER c
LEFT JOIN SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS o
    ON c.C_CUSTKEY = o.O_CUSTKEY
WHERE o.O_ORDERKEY > 0
LIMIT 20;
```

**What to highlight:** The WHERE clause filters out the NULL rows from the LEFT JOIN that would indicate "no orders." Cortex Code should explain that `WHERE o.O_ORDERKEY IS NULL` is the correct filter for finding non-matching rows.

---

## Expected Outcome

The audience sees that Cortex Code is not just a code generator — it's a debugging partner that can diagnose, explain, and fix errors interactively.
