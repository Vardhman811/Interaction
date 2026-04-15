# 🚀 Vertex AI AutoML – End-to-End Guide

---

## 1. Introduction to AutoML

### What is AutoML?
AutoML (Automated Machine Learning) enables building machine learning models without manually implementing algorithms.

It automates:
- Model selection
- Feature engineering
- Hyperparameter tuning

This allows teams to focus more on data and problem definition rather than model implementation.

---

### When to Use AutoML

Use AutoML when:
- The problem is difficult to solve using rule-based logic
- Data contains patterns that are not easily defined manually
- Faster model development is required

**Example scenarios:**
- Customer behavior prediction
- Image or text classification

---

### How Vertex AI Works

Vertex AI uses supervised learning, where:
- **Features** = input data
- **Target** = what needs to be predicted

The model learns patterns from historical data and applies them to new data.

The same dataset can be reused for different problems by changing the target column.

---

### Vertex AI Workflow

1. Gather Data  
2. Prepare Data  
3. Train Model  
4. Evaluate Model  
5. Deploy & Predict  

---

## 2. Assess Your Use Case

### Define the Problem

Start with:
- What do you want to predict?
- What type of output is expected?

---

### Model Types

#### Binary Classification
- Output: Yes / No  
- Example: Will a customer purchase a product?

#### Multi-class Classification
- Output: Multiple categories  
- Example: Customer segmentation (Basic / Premium / VIP)

#### Regression
- Output: Numeric value  
- Example: Predict customer spending

#### Forecasting
- Output: Time-based sequence  
- Example: Predict product demand over time

---

## 3. Data Gathering

### Key Principle

Better data leads to better models.  
Poor or irrelevant data directly impacts predictions.

---

### Feature Selection

- Features are input variables used for training  
- Only include features relevant to the problem  

**Example:**
- Purchase history  
- Total spending  
- Customer profile  

Irrelevant features add noise and reduce accuracy.

---

### Data Volume

General guidance:
- Classification → 50 × features  
- Regression → 200 × features  
- Forecasting → 5000 × features  

More complex problems require more data.

---

### Data Variation

Ensure data represents real-world scenarios.

**Example:**
- Only winter data ❌  
- Multiple seasons ✅  

This helps the model generalize to new situations.

---

## 4. Data Preparation

### Keep Data Realistic

#### Data Leakage
- Occurs when training uses information not available during prediction  

**Example:**
- Using future data to predict current behavior  

Leads to unrealistic model performance.

---

#### Training-Serving Skew
- Training data differs from real-world input  

**Example:**
- Training on weekly data, predicting on daily data  

Causes poor predictions in production.

---

### Data Cleaning

- Handle missing values  
- Correct incorrect data  
- Standardize formats  

**Example:**
- “Hyd”, “HYD”, “Hyderabad” → consistent format  

---

### Understand Your Data

- Know what each feature represents  
- Ensure it is valid for prediction  
- Check for overly strong correlation with target (possible leakage)

---

## 5. Model Training

### Feature Selection

- Use relevant features  
- Avoid:
  - Unique identifiers  
  - Irrelevant columns  

---

### Training Process

Vertex AI:
- Trains multiple models  
- Tunes parameters  
- Selects the best model  

---

### Data Splitting

#### Training Set
- Used to learn patterns  

#### Validation Set
- Used to tune the model during training  
- Helps prevent overfitting  

#### Test Set
- Used after training  
- Represents real-world performance  

---

## 6. Model Evaluation

Model evaluation helps you check:  
**Is my model good enough for real use?**

---

### Confidence Score & Threshold

- Model gives a score (probability), not Yes/No  
- Example: 0.7 (70% chance)  

**Threshold converts it into decision:**
- If score ≥ threshold → Yes  
- If score < threshold → No  

- Lower threshold → more YES (more mistakes possible)  
- Higher threshold → fewer YES (may miss real cases)  

---

### Prediction Outcomes

Every prediction is one of these:

- True Positive → Correct YES  
- False Positive → Wrong YES  
- True Negative → Correct NO  
- False Negative → Wrong NO  

**Just remember:**
- True = correct  
- False = wrong  

---

### Precision vs Recall

- Precision → Out of predicted YES, how many are correct  
- Recall → Out of actual YES, how many you found  

**Simple:**
- Precision = accuracy of YES  
- Recall = coverage of YES  

---

### Other Metrics (Basic Idea)

- Accuracy → overall correct predictions  
- F1 Score → balance of precision & recall  
- AUC → overall model quality  
- Log Loss → error (lower is better)  

---

### For Numeric Predictions

- MAE / RMSE → how far predictions are from actual values  

**Lower = better**

---
