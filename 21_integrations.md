# Demo 21: Integrations (~6 min)

## What You'll Show

Cortex Code can create external access integrations, network rules, and UDFs that call external APIs — enabling Snowflake to interact with the outside world securely.

## Context for Presenter

Customers frequently need Snowflake to call external APIs — for data enrichment, notifications, or third-party service integration. Snowflake's external access framework provides secure, governed access to external endpoints. The setup involves multiple objects (network rules, integrations, UDFs), and Cortex Code generates all of them.

**Key talking points:**
- External access is governed — network rules define allowed endpoints
- API integrations wrap the access control into a reusable object
- UDFs provide a SQL-callable interface to external services
- Cortex Code generates the complete setup across all required objects

---

## Prompts to Execute

### 1. Create a network rule

```
Create a network rule in DEMO_DB.PUBLIC called HTTPBIN_NETWORK_RULE that allows outbound HTTPS access to httpbin.org. This will be used for testing external API calls.
```

**What to highlight:** Network rules are the first layer of security — they explicitly whitelist which external endpoints Snowflake can reach.

---

### 2. Create an external access integration

```
Create an external access integration called DEMO_DB.PUBLIC.HTTPBIN_ACCESS_INTEGRATION that uses the HTTPBIN_NETWORK_RULE we just created.
```

**What to highlight:** The integration object ties the network rule into something that can be referenced by functions and procedures.

---

### 3. Create a UDF that calls the API

```
Create a Python UDF in DEMO_DB.PUBLIC called CALL_HTTPBIN that uses the HTTPBIN_ACCESS_INTEGRATION to make a GET request to https://httpbin.org/get and returns the response as a string. Use the requests library.
```

**What to highlight:** The UDF is a SQL-callable function that securely reaches an external API — any SQL user can call it without managing credentials or network config.

---

### 4. Test the integration

```
Call the DEMO_DB.PUBLIC.CALL_HTTPBIN() function and show me the result. Verify that the external API call works correctly.
```

**What to highlight:** A simple SELECT statement triggers an external API call — the complexity of network rules and integrations is abstracted away for end users.

---

## Expected Outcome

The audience sees that Snowflake can securely call external APIs through a governed framework, and Cortex Code generates the complete multi-object setup from natural language.

## Cleanup (Optional)

```
Drop the UDF, integration, and network rule: drop function if exists DEMO_DB.PUBLIC.CALL_HTTPBIN(); drop integration if exists HTTPBIN_ACCESS_INTEGRATION; drop network rule if exists DEMO_DB.PUBLIC.HTTPBIN_NETWORK_RULE;
```
