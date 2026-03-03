# Demo 25: OpenFlow Pipeline (~6 min)

## What You'll Show

Cortex Code helps build and monitor OpenFlow data pipelines — creating flows that read, transform, and write data using NiFi's visual processor model.

## Context for Presenter

Once OpenFlow is set up, the real value is in building data flows. OpenFlow uses NiFi's processor-based model where data flows through a graph of processors — each one reading, transforming, routing, or writing data. Cortex Code helps configure and monitor these flows.

**Key talking points:**
- Flows are built from processors — modular, reusable data handling units
- Supports reading from and writing to Snowflake tables, files, APIs, and more
- Real-time monitoring shows throughput, backpressure, and errors
- Cortex Code helps configure processors and troubleshoot issues

---

## Prompts to Execute

### 1. Design a simple flow

```
I want to create an OpenFlow pipeline that reads data from one Snowflake table, applies a simple transformation (filter rows where amount > 1000), and writes the results to another table. Walk me through the processor configuration needed.
```

**What to highlight:** The processor chain — QuerySnowflake -> RouteOnAttribute/FilterRecord -> PutSnowflake — showing NiFi's modular pipeline approach.

---

### 2. Configure processors

```
Show me the detailed configuration for a QuerySnowflake processor that reads from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1.ORDERS. What properties do I need to set, and how do I configure the connection pool?
```

**What to highlight:** Processor configuration details — connection pooling, query scheduling, and output format settings.

---

### 3. Monitor the flow

```
How do I monitor a running OpenFlow pipeline? Show me how to check flow status, throughput, queue sizes, and identify any bottlenecks or errors.
```

**What to highlight:** Monitoring capabilities — real-time throughput metrics, queue backpressure, and error routing make production operation visible.

---

### 4. Troubleshoot issues

```
What are common issues with OpenFlow pipelines and how do I troubleshoot them? Show me how to check logs, handle failed records, and restart processors.
```

**What to highlight:** Practical troubleshooting — Cortex Code provides operational guidance beyond just setup, helping with day-to-day pipeline management.

---

## Expected Outcome

The audience sees that OpenFlow provides a powerful visual data integration platform, and Cortex Code helps with both the technical configuration and operational monitoring.
