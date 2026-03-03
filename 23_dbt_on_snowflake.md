# Demo 23: dbt Projects on Snowflake (~6 min)

## What You'll Show

Cortex Code helps deploy dbt projects as native Snowflake objects using the `snow dbt` CLI — enabling dbt execution, scheduling, and management entirely within Snowflake.

## Context for Presenter

This demo is about dbt-as-a-Snowflake-object, not regular dbt CLI usage. With `snow dbt deploy`, a dbt project becomes a first-class Snowflake object that can be executed with SQL, scheduled with Tasks, and managed with standard DDL. Cortex Code guides the setup and deployment process.

**Key talking points:**
- dbt projects are deployed INTO Snowflake as native objects
- Execution happens via `EXECUTE DBT PROJECT` SQL — no external scheduler needed
- Can be scheduled with Snowflake Tasks for automated runs
- Cortex Code generates the deployment commands and scheduling DDL

---

## Prompts to Execute

### 1. Understand dbt on Snowflake

```
Explain how dbt projects work as Snowflake-native objects. What's the difference between running dbt from the CLI versus deploying it to Snowflake with `snow dbt deploy`?
```

**What to highlight:** Cortex Code explains the architecture — dbt project as a Snowflake object vs. dbt as an external CLI tool. This sets the conceptual foundation.

---

### 2. Set up a basic project structure

```
Show me the steps to set up a minimal dbt project that I could deploy to Snowflake. What files do I need, and what does the snow dbt deploy command look like?
```

**What to highlight:** The project structure requirements and the `snow dbt deploy` command — note that the project becomes a database object after deployment.

---

### 3. Execute a deployed project

```
Show me how to execute a deployed dbt project using SQL. What does the EXECUTE DBT PROJECT command look like, and how do I check the execution status?
```

**What to highlight:** `EXECUTE DBT PROJECT` runs the dbt project entirely within Snowflake — no external compute or CI/CD pipeline required.

---

### 4. Schedule with a Snowflake Task

```
Create a Snowflake Task that executes a deployed dbt project on a daily schedule. The project is at DEMO_DB.PUBLIC.MY_DBT_PROJECT. Schedule it to run every day at 6 AM UTC using warehouse COMPUTE_WH.
```

**What to highlight:** Native scheduling — the dbt project runs on a cron schedule as a Snowflake Task, with all the monitoring and alerting that Tasks provide.

---

## Expected Outcome

The audience sees that dbt projects can be fully managed within Snowflake as native objects, eliminating the need for external orchestration infrastructure.

## Cleanup (Optional)

```
Drop the task if created: DROP TASK IF EXISTS DEMO_DB.PUBLIC.DAILY_DBT_RUN;
```
