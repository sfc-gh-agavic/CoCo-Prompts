# Demo 3: Python UDFs & Stored Procedures (~6 min)

## What You'll Show

Cortex Code generates Snowflake-native Python UDFs and stored procedures, deploys them directly to your account, and tests them — all from a single conversation.

## Context for Presenter

Writing Python UDFs in Snowflake requires knowing the exact DDL syntax, handler conventions, package specifications, and return types. Cortex Code handles all of this boilerplate and lets you focus on the logic.

**Key talking points:**
- Generates correct `CREATE OR REPLACE FUNCTION` DDL with Python handler
- Knows which packages are available in the Snowflake Anaconda channel
- Handles both scalar UDFs and tabular (UDTF) functions
- Can create stored procedures with proper `EXECUTE AS` and parameter handling

---

## Prompts to Execute

### 1. Create a simple UDF

```
Create a Python UDF in DEMO_DB.PUBLIC called EMAIL_DOMAIN that extracts the domain from an email address. For example, 'user@snowflake.com' should return 'snowflake.com'. Deploy it and test it with a few sample values.
```

**What to highlight:** The complete DDL is generated and executed. Note the correct handler function, return type, and the test query that follows.

---

### 2. Create a more complex UDF

```
Create a Python UDF called SENTIMENT_SCORE that takes a text string and returns a simple sentiment score. Use the built-in Python string methods to count positive words (like 'great', 'excellent', 'good', 'happy', 'love') vs negative words (like 'bad', 'terrible', 'poor', 'hate', 'awful') and return a score from -1.0 to 1.0. Deploy and test it.
```

**What to highlight:** Cortex Code handles the package-free approach, generates the scoring logic, and tests with sample inputs.

---

### 3. Create a stored procedure

```
Create a stored procedure in DEMO_DB.PUBLIC called SUMMARIZE_TABLE that takes a fully qualified table name as input and returns a summary including: row count, column count, column names with types, and the approximate size. Use SQL within the procedure. Test it against SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS.
```

**What to highlight:** The stored procedure uses proper Snowflake SQL scripting with `:variable` syntax for parameter references. It's created AND tested in one flow.

---

### 4. Modify the procedure

```
Update the SUMMARIZE_TABLE procedure to also include the top 3 most common values for any VARCHAR column that has fewer than 50 distinct values. This helps identify categorical columns.
```

**What to highlight:** Cortex Code modifies the existing procedure rather than starting from scratch — it remembers the previous version from context.

---

## Expected Outcome

The audience sees Cortex Code as a Python-on-Snowflake accelerator that eliminates boilerplate and gets code deployed and tested in minutes.
