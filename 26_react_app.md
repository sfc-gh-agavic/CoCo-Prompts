# Demo 26: React App with Snowflake Data (~7 min)

## What You'll Show

Cortex Code can scaffold a React/Next.js application that connects to Snowflake, queries data, and renders interactive charts — building an embedded analytics dashboard from a conversational prompt.

## Context for Presenter

Many customers want to build custom data applications on top of Snowflake. While Streamlit is great for internal tools, some teams need React-based apps for customer-facing analytics or complex UIs. Cortex Code generates the full application stack.

**Key talking points:**
- Full React/Next.js app scaffolded from natural language
- Connects to Snowflake using the Node.js driver or REST API
- Interactive charts using popular visualization libraries
- Cortex Code generates components, data fetching, and styling

---

## Prompts to Execute

### 1. Scaffold the application

```
Create a Next.js application that connects to Snowflake and displays a dashboard with TPCH data. Set up the project structure with a Snowflake connection utility, an API route that queries SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS for monthly revenue, and a main page that displays the data.
```

**What to highlight:** Cortex Code generates the full project — package.json, connection config, API route, and page component — all from a single prompt.

---

### 2. Add a chart component

```
Add a bar chart component to the dashboard that visualizes the monthly revenue data. Use recharts as the charting library. Show revenue on the y-axis and month on the x-axis with proper formatting.
```

**What to highlight:** The chart component integrates with the data fetched from Snowflake — reactive and interactive out of the box.

---

### 3. Add an interactive filter

```
Add a dropdown filter that lets users select a specific year to filter the revenue chart. The available years should come from the ORDERS data. When a year is selected, the chart should update to show only that year's monthly data.
```

**What to highlight:** Interactive filtering — the filter triggers a new query to Snowflake and re-renders the chart. This is a real data application pattern.

---

### 4. Run the application

```
Show me how to run this Next.js application locally. What environment variables do I need for the Snowflake connection, and what should I see when I open the browser?
```

**What to highlight:** The app runs locally and connects to Snowflake in real time — from conversational prompt to working application.

---

## Expected Outcome

The audience sees that Cortex Code can build a complete data application — not just SQL queries — connecting React frontends to Snowflake backends.

## Cleanup (Optional)

Remove the generated project directory if no longer needed.
