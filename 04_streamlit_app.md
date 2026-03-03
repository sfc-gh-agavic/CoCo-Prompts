# Demo 4: Build a Streamlit App (~6 min)

## What You'll Show

Cortex Code can generate a complete Streamlit in Snowflake application from a natural language description, write it to a file, and help you iterate on it — all within the terminal.

## Context for Presenter

Streamlit in Snowflake lets customers build data apps without leaving the platform. Cortex Code accelerates this by generating the full app code, handling Snowflake session management, and building interactive widgets tied to live data.

**Key talking points:**
- Generates complete, runnable Streamlit code
- Knows Streamlit-in-Snowflake patterns (session context, st.connection)
- Handles layout, charts, filters, and interactivity
- Writes the file locally so you can deploy or iterate

---

## Prompts to Execute

### 1. Generate the app

```
Build me a Streamlit app that connects to SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 and shows an order analytics dashboard. Include:
- A date range filter for order dates
- A bar chart of total revenue by nation
- A line chart of monthly order trends
- A table showing the top 10 customers by spend
Write the code to overview/order_dashboard.py
```

**What to highlight:** Cortex Code generates a complete app file with imports, data queries, layout, and visualizations. Point out how it structures the code with proper caching and session handling.

---

### 2. Add interactivity

```
Update the Streamlit app to add a sidebar with a multi-select filter for order status (F, O, P) and a nation dropdown. Both filters should affect all three visualizations. Also add a KPI row at the top showing total orders, total revenue, and average order value.
```

**What to highlight:** It edits the existing file, adding sidebar filters that propagate to all components. The KPI metrics use `st.metric` for a polished look.

---

### 3. Improve the styling

```
Make the dashboard look more professional. Add a title and subtitle, use Snowflake blue (#29B5E8) as the accent color where possible, and arrange the charts side by side using columns. Add a footer with the data source.
```

**What to highlight:** Cortex Code knows Streamlit layout primitives (columns, containers, markdown) and can style the app without you referencing Streamlit docs.

---

## Expected Outcome

A complete, styled Streamlit dashboard file is created locally. The audience sees that going from "I want a dashboard" to a working app takes minutes, not hours.

## Cleanup (Optional)

The generated file `overview/order_dashboard.py` can be deleted after the demo or kept as a reference.
