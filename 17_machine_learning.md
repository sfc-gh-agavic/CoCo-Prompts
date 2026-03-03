# Demo 17: Machine Learning (~8 min)

## What You'll Show

Cortex Code supports the full ML lifecycle — from data preparation and model training in a notebook, to logging in the Snowflake Model Registry, deploying as a service, and running inference.

## Context for Presenter

Data science teams often struggle with the gap between experimentation and production. Snowflake's Model Registry and Model Service close that gap by keeping models inside the platform. Cortex Code orchestrates the entire workflow from a conversational interface.

**Key talking points:**
- End-to-end ML without leaving the Snowflake ecosystem
- Model Registry provides versioning, metadata, and governance
- Model Service enables scalable inference via SQL
- Cortex Code generates the notebook, training code, and deployment DDL

---

## Prompts to Execute

### 1. Prepare a training dataset

```
Create a notebook that prepares a training dataset from SNOWFLAKE_SAMPLE_DATA.TPCH_SF1. I want to predict the total price of an order (O_TOTALPRICE) based on features from LINEITEM: total quantity, average discount, number of line items, and average extended price. Aggregate LINEITEM features per order and join with ORDERS. Save the dataset as DEMO_DB.PUBLIC.ML_TRAINING_DATA.
```

**What to highlight:** Cortex Code creates a notebook with the feature engineering SQL — the data stays in Snowflake.

---

### 2. Train a regression model

```
In the same notebook, add cells to train a simple linear regression model using scikit-learn on the DEMO_DB.PUBLIC.ML_TRAINING_DATA table. Split into train/test sets (80/20), train the model, and print R-squared and RMSE metrics.
```

**What to highlight:** Standard Python ML workflow running in a Snowflake notebook — the data never leaves the platform.

---

### 3. Log the model to the registry

```
Add cells to log the trained model to the Snowflake Model Registry under DEMO_DB.PUBLIC with the name ORDER_PRICE_PREDICTOR and version V1. Include the training metrics as metadata.
```

**What to highlight:** The Model Registry provides centralized model management — version tracking, metadata, and access control.

---

### 4. Run inference

```
Write a SQL query that uses the registered model ORDER_PRICE_PREDICTOR to predict O_TOTALPRICE for orders in the test set. Show the predicted vs actual values for the first 10 rows.
```

**What to highlight:** Inference runs as a SQL function — any analyst can use the model without Python knowledge.

---

## Expected Outcome

The audience sees that Snowflake supports the complete ML lifecycle natively, and Cortex Code makes each step — data prep, training, registration, inference — accessible from natural language.

## Cleanup (Optional)

```
Drop the table DEMO_DB.PUBLIC.ML_TRAINING_DATA and remove the model ORDER_PRICE_PREDICTOR from the registry.
```
