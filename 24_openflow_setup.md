# Demo 24: OpenFlow Setup (~5 min)

## What You'll Show

Cortex Code helps set up OpenFlow — Snowflake's NiFi-based data integration platform — for building visual data replication and transformation pipelines.

## Context for Presenter

OpenFlow brings Apache NiFi into Snowflake as a managed service for data integration. It provides a visual flow designer for building data pipelines that connect to a wide range of sources and destinations. Cortex Code helps with the initial infrastructure setup.

**Key talking points:**
- OpenFlow is Apache NiFi managed by Snowflake — no infrastructure to manage
- Visual flow designer for building data integration pipelines
- Supports hundreds of connectors out of the box
- Cortex Code generates the setup commands and verifies deployment

---

## Prompts to Execute

### 1. Understand OpenFlow

```
What is Snowflake OpenFlow? Explain the architecture and what I can use it for. How does it compare to other data integration approaches?
```

**What to highlight:** Cortex Code explains OpenFlow's NiFi foundation, its managed nature, and typical use cases — data replication, CDC, and complex ETL flows.

---

### 2. Check prerequisites

```
What are the prerequisites for setting up OpenFlow in my Snowflake account? What roles, permissions, and configurations do I need?
```

**What to highlight:** OpenFlow requires specific account-level setup — Cortex Code outlines the requirements clearly so the presenter can verify readiness.

---

### 3. Create an OpenFlow instance

```
Show me how to create an OpenFlow instance in Snowflake. Walk me through the steps and the SQL commands needed to set up a basic instance.
```

**What to highlight:** The instance creation process — note that OpenFlow runs as a managed service within the Snowflake security perimeter.

---

### 4. Verify and access

```
How do I verify that an OpenFlow instance is running and access the NiFi web UI? Show me the relevant commands to check instance status.
```

**What to highlight:** Once running, OpenFlow provides a web UI for visual flow design — Cortex Code shows how to access it and verify health.

---

## Expected Outcome

The audience understands what OpenFlow is and how to get started with it, seeing that Cortex Code guides the infrastructure setup process.
