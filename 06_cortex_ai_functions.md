# Demo 6: Cortex AI Functions (~6 min)

## What You'll Show

Cortex Code can write SQL that leverages Snowflake's built-in Cortex AI functions for text analytics — sentiment analysis, classification, summarization, and extraction — without requiring any external ML infrastructure.

## Context for Presenter

Snowflake Cortex AI functions bring LLM capabilities directly into SQL. Customers don't need to manage models, endpoints, or Python environments. Cortex Code knows these functions natively and generates correct SQL to use them.

**Key talking points:**
- AI functions run inside Snowflake — no data movement
- SQL-native interface means any analyst can use them
- Cortex Code knows the function signatures and generates valid calls
- Supports: AI_SENTIMENT, AI_CLASSIFY, AI_SUMMARIZE, AI_EXTRACT, AI_COMPLETE, AI_TRANSLATE

---

## Prompts to Execute

### 1. Sentiment analysis

```
Using Cortex AI functions, write and run a query that analyzes the sentiment of these product reviews:
- 'This product is amazing, best purchase I ever made!'
- 'Terrible quality, broke after one day. Very disappointed.'
- 'It works fine, nothing special but gets the job done.'
- 'Absolutely love it! Will buy again for sure.'
- 'Worst customer service experience of my life.'

Use the CORTEX AI_SENTIMENT function.
```

**What to highlight:** The AI function runs as a simple SQL call — no Python, no API keys, no model deployment.

---

### 2. Text classification

```
Write a query using CORTEX AI_CLASSIFY to categorize these support tickets into categories like 'billing', 'technical', 'account', or 'general':
- 'I was charged twice for my subscription this month'
- 'My dashboard keeps showing a 500 error when I try to load it'
- 'How do I add another user to my account?'
- 'What are your pricing plans for enterprise customers?'
- 'The API endpoint returns timeout errors after 30 seconds'
```

**What to highlight:** Classification without training data — the LLM understands categories from the labels alone.

---

### 3. Text completion and generation

```
Use CORTEX AI_COMPLETE to generate a SQL comment block that documents what the TPCH_SF1.LINEITEM table is used for in the TPC-H benchmark. Use the 'snowflake-arctic-instruct' model.
```

**What to highlight:** AI_COMPLETE brings general LLM capabilities into SQL. You can use it for data enrichment, documentation generation, or data transformation.

---

### 4. Combine AI functions with data

```
Write a query that takes the top 5 nations by total order revenue from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1 and uses CORTEX AI_COMPLETE to generate a one-sentence market summary for each nation based on its order volume and revenue. Use 'snowflake-arctic-instruct' as the model.
```

**What to highlight:** This is the power play — combining traditional SQL aggregation with AI-generated insights in a single query. No ETL, no external tools.

---

## Expected Outcome

The audience sees that AI/ML is not a separate workflow — it's embedded in SQL, and Cortex Code makes it trivially easy to use.
