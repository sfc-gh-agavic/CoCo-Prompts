# Demo 18: Data Governance (~7 min)

## What You'll Show

Cortex Code helps manage data governance in Snowflake — from discovering who has access to what, to classifying sensitive data, creating masking policies, and reviewing access history.

## Context for Presenter

Data governance is a top priority for enterprise customers. Snowflake has rich built-in capabilities for masking, classification, and access control, but the DDL can be complex. Cortex Code makes governance tasks conversational and reduces the risk of misconfiguration.

**Key talking points:**
- Snowflake has native data classification, masking, and row access policies
- Cortex Code generates the correct DDL for complex governance configurations
- Access history provides audit trails for compliance
- Tag-based masking scales governance across the organization

---

## Prompts to Execute

### 1. Check access permissions

```
Who has access to the DEMO_DB.PUBLIC schema? Show me all roles with grants on this schema and what privileges they have.
```

**What to highlight:** Cortex Code queries the grants metadata and presents a clear access matrix — useful for security audits.

---

### 2. Classify sensitive data

```
Create a test table DEMO_DB.PUBLIC.CUSTOMER_PII with columns: ID (number), FULL_NAME (varchar), EMAIL (varchar), PHONE (varchar), SSN (varchar), CREDIT_CARD (varchar), ADDRESS (varchar). Insert 5 rows of realistic mock data. Then run data classification on this table to detect which columns contain sensitive or PII data.
```

**What to highlight:** Snowflake's built-in classification detects PII categories (email, phone, SSN) automatically — no manual tagging required.

---

### 3. Create a masking policy

```
Create a masking policy in DEMO_DB.PUBLIC that masks the EMAIL column — showing full email to the SYSADMIN role but masking it as '***@***.com' for all other roles. Apply this policy to the CUSTOMER_PII table's EMAIL column.
```

**What to highlight:** The masking policy DDL with role-based conditional logic — data is protected at the column level without changing the underlying data.

---

### 4. Review access history

```
Show me the recent access history for tables in DEMO_DB.PUBLIC. Who has been querying these tables and when? Are there any unusual access patterns?
```

**What to highlight:** Access history from SNOWFLAKE.ACCOUNT_USAGE provides a full audit trail — Cortex Code summarizes it into actionable insights.

---

## Expected Outcome

The audience sees that Snowflake has comprehensive governance built in, and Cortex Code makes it practical to implement classification, masking, and auditing without memorizing complex DDL.

## Cleanup (Optional)

```
Drop the masking policy and table: drop masking policy if exists DEMO_DB.PUBLIC.EMAIL_MASK; drop table if exists DEMO_DB.PUBLIC.CUSTOMER_PII;
```
