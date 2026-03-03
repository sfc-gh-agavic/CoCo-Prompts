# Demo 15: Cortex Agent (~7 min)

## What You'll Show

Cortex Code can create and manage Cortex Agents — AI-powered assistants that answer domain-specific questions using tools, semantic views, and curated instructions within Snowflake.

## Context for Presenter

Cortex Agents let organizations build domain-specific AI assistants that are grounded in their actual data. Instead of a generic chatbot, teams get an agent that knows their schema, business logic, and data definitions. Cortex Code streamlines the entire agent lifecycle.

**Key talking points:**
- Agents are Snowflake-native objects — no external infrastructure
- They combine tools (SQL, semantic views) with curated instructions
- Cortex Code handles the creation DDL and helps iterate on agent design
- Agents can be shared across the organization

---

## Prompts to Execute

### 1. Discover existing agents

```
List all Cortex Agents in my account. Show me what agents are available and what they're configured to do.
```

**What to highlight:** Cortex Code discovers existing agents and summarizes their purpose and configuration.

---

### 2. Create a new agent

```
Create a Cortex Agent called DEMO_DB.PUBLIC.TPCH_ANALYST that answers business questions about the TPC-H dataset. It should use a SQL tool that can query SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 tables. Add instructions that tell it to focus on revenue analysis, customer segmentation, and supply chain metrics.
```

**What to highlight:** The CREATE CORTEX AGENT DDL — note the tool configuration and instruction block that shapes the agent's behavior.

---

### 3. Test the agent

```
Test the DEMO_DB.PUBLIC.TPCH_ANALYST agent by asking it: "What are the top 5 nations by total revenue and how does their order volume compare?"
```

**What to highlight:** The agent processes the question using its configured tools and returns a grounded answer from live data.

---

### 4. Iterate on the agent

```
Update the TPCH_ANALYST agent to also include guidance about the LINEITEM table's relationship to ORDERS. Add a note in its instructions that revenue calculations should use L_EXTENDEDPRICE * (1 - L_DISCOUNT) for accurate results.
```

**What to highlight:** Iterating on agent instructions is how you refine accuracy — Cortex Code makes this a conversational loop.

---

## Expected Outcome

The audience sees that building a domain-specific AI assistant is straightforward with Cortex Code, and the iterative workflow makes it easy to refine the agent's behavior.

## Cleanup (Optional)

```
Drop the Cortex Agent DEMO_DB.PUBLIC.TPCH_ANALYST.
```
