# Session 03: Understanding Data in AI

**Week 1 | Duration: 2-3 hours**

## 🎯 Learning Objectives

By the end of this session, you will:
- Understand what makes "good" data for AI/ML
- Learn about different types of data and their AI applications
- Recognize data quality issues and solutions
- Understand data collection, labeling, and preparation processes
- Know key data-related challenges in AI projects

---

## 📚 Why Data is the Fuel for AI

### The Data-AI Relationship

```
Better Data → Better Models → Better Products
```

**Key Insight**: In most AI projects, improving data quality has more impact than improving algorithms.

### Andrew Ng's Data-Centric AI

Recent shift in AI development:
- **Model-Centric**: Keep data fixed, improve the algorithm
- **Data-Centric**: Keep algorithm fixed, systematically improve data quality

For most business applications, data-centric approach wins!

---

## 🔍 Types of Data

### 1. Structured Data

**Definition**: Organized in tables with rows and columns

**Examples:**
- Spreadsheets (CSV, Excel)
- Relational databases (SQL)
- Data warehouses

**Characteristics:**
- Easy to search and analyze
- Fits in predefined schema
- Each column has specific data type

**AI Use Cases:**
- Fraud detection (transaction data)
- Customer churn prediction
- Sales forecasting
- Recommendation systems (user-item matrices)

**Example:**
```
| User_ID | Age | Location    | Purchase_Amount | Churn |
|---------|-----|-------------|-----------------|-------|
| 001     | 25  | New York    | 150.00         | No    |
| 002     | 34  | San Francisco| 320.50         | Yes   |
```

---

### 2. Unstructured Data

**Definition**: Data without predefined format or organization

**Examples:**
- Text documents
- Images and videos
- Audio files
- Social media posts
- Emails

**Characteristics:**
- Makes up ~80% of enterprise data
- Harder to process with traditional tools
- Rich with insights

**AI Use Cases:**
- Image recognition (photos, medical scans)
- Natural language processing (customer reviews, support tickets)
- Voice assistants (speech to text)
- Video analysis (content moderation, security)

---

### 3. Semi-Structured Data

**Definition**: Mix of structured and unstructured

**Examples:**
- JSON files
- XML documents
- HTML pages
- Log files

**Characteristics:**
- Has some organizational properties
- Doesn't fit strict database schemas
- Common in APIs and web data

**Example (JSON):**
```json
{
  "user_id": "001",
  "name": "Alice",
  "orders": [
    {"product": "Laptop", "price": 999.99},
    {"product": "Mouse", "price": 25.99}
  ],
  "feedback": "Great products! Fast shipping."
}
```

---

### 4. Time-Series Data

**Definition**: Data points indexed by time

**Examples:**
- Stock prices
- Weather data
- IoT sensor readings
- User activity logs

**AI Use Cases:**
- Demand forecasting
- Anomaly detection
- Predictive maintenance
- Financial trading

---

## 📊 What Makes Good AI Data?

### The 5 Qualities of Good Data

#### 1. **Relevant**
- Data must be related to the problem you're solving
- **Bad Example**: Using shoe size to predict job performance
- **Good Example**: Using work history and skills to predict job performance

#### 2. **Accurate**
- Data correctly represents reality
- Free from errors and inconsistencies
- **Issues**: Typos, outdated info, measurement errors
- **Solution**: Validation rules, data cleaning pipelines

#### 3. **Complete**
- All necessary information is captured
- Minimal missing values
- **Issues**: Incomplete forms, sensor failures, integration gaps
- **Solution**: Required fields, fallback values, imputation techniques

#### 4. **Consistent**
- Same format and meaning across the dataset
- **Issues**: Different date formats (MM/DD vs DD/MM), varying units (miles vs km)
- **Solution**: Standardization, normalization, data schemas

#### 5. **Timely**
- Data is current and up-to-date
- **Issues**: Outdated customer preferences, stale inventory data
- **Solution**: Regular updates, real-time pipelines, data expiration policies

---

## 🛠️ The Data Pipeline

### Stage 1: Data Collection

**Sources:**
- **First-party**: Your own systems (app events, transactions, logs)
- **Second-party**: Partner data
- **Third-party**: Purchased or public datasets

**Methods:**
- User interactions (clicks, views, purchases)
- Surveys and forms
- IoT sensors
- Web scraping
- APIs
- Manual entry

**PM Considerations:**
- What data do we need vs. what do we have?
- Privacy and consent (GDPR, CCPA compliance)
- Data ownership and licensing
- Storage and infrastructure costs

---

### Stage 2: Data Labeling

For supervised learning, you need labeled data (inputs with correct outputs).

**Labeling Methods:**

1. **Manual Labeling**
   - Humans label each example
   - **Pros**: High quality for complex tasks
   - **Cons**: Expensive, time-consuming
   - **Tools**: Labelbox, Scale AI, Amazon Mechanical Turk

2. **Programmatic Labeling**
   - Use rules or heuristics
   - **Example**: Emails with "unsubscribe" likely marketing
   - **Pros**: Fast, cheap
   - **Cons**: Less accurate, only works for simple patterns

3. **Semi-Supervised / Active Learning**
   - Label small amount manually
   - Model labels rest, humans verify uncertain cases
   - **Pros**: Balance of cost and quality
   - **Cons**: Requires ML expertise

4. **User-Generated Labels**
   - Users label through normal interaction
   - **Example**: YouTube likes/dislikes, Spotify skips
   - **Pros**: Free, continuous
   - **Cons**: Implicit, potentially biased

**Labeling Best Practices:**
- Clear labeling guidelines
- Multiple labelers for quality
- Inter-annotator agreement metrics
- Regular calibration sessions
- Version control for labels

---

### Stage 3: Data Cleaning

**Common Issues:**

1. **Missing Values**
   - **Solutions**:
     - Remove rows (if small %)
     - Fill with mean/median/mode
     - Predict using other features
     - Use algorithms that handle missing data

2. **Duplicates**
   - **Solutions**: De-duplication logic, unique identifiers

3. **Outliers**
   - **Example**: Age = 999, Price = -$50
   - **Solutions**: Remove, cap, or investigate if real

4. **Inconsistent Formats**
   - **Example**: "New York", "NY", "new york"
   - **Solutions**: Standardization, lookup tables

5. **Invalid Data**
   - **Example**: Dates in the future, negative quantities
   - **Solutions**: Validation rules, constraints

---

### Stage 4: Feature Engineering

Transform raw data into features ML algorithms can use.

**Common Transformations:**

1. **Numerical Features**
   - Normalization (scale to 0-1)
   - Standardization (mean=0, std=1)
   - Binning (age → age groups)

2. **Categorical Features**
   - One-hot encoding (Color: Red/Blue → Red:1/0, Blue:0/1)
   - Label encoding (Small/Medium/Large → 0/1/2)
   - Embeddings (for high-cardinality categories)

3. **Text Features**
   - Tokenization (split into words)
   - TF-IDF (term frequency-inverse document frequency)
   - Word embeddings (Word2Vec, BERT)

4. **Date/Time Features**
   - Extract: hour, day_of_week, month, is_weekend
   - Time since event
   - Cyclical encoding (hour 23 close to hour 0)

5. **Derived Features**
   - Ratios: price_per_sqft = price / sqft
   - Aggregations: avg_purchase_last_30days
   - Interactions: age × income

**Example:**
```
Raw: User visited site on "2025-01-15 14:30:00"
Features:
  - hour: 14
  - day_of_week: Wednesday
  - is_business_hours: True
  - is_weekend: False
  - hour_sin, hour_cos: (cyclical encoding)
```

---

### Stage 5: Data Splitting

Split data for training, validation, and testing:

```
Dataset (100%)
├── Training (70-80%): Model learns from this
├── Validation (10-15%): Tune hyperparameters
└── Test (10-15%): Final evaluation (never seen by model)
```

**Important:**
- **Random split**: For independent data
- **Time-based split**: For time-series (train on past, test on future)
- **Stratified split**: Maintain class distribution in imbalanced datasets

---

## ⚠️ Common Data Challenges in AI

### 1. Insufficient Data

**Problem**: Not enough examples to train a good model

**How much is enough?**
- Simple problems: Hundreds to thousands
- Complex problems (deep learning): Millions
- Rule of thumb: 10x examples per feature (traditional ML)

**Solutions:**
- Data augmentation (flip/rotate images, rephrase text)
- Transfer learning (use pre-trained models)
- Synthetic data generation
- Few-shot learning techniques

---

### 2. Imbalanced Data

**Problem**: One class has far more examples than others

**Example:** Fraud detection
- 99.9% normal transactions
- 0.1% fraud

**Why it's a problem:**
- Model learns to always predict majority class
- High accuracy but useless (99.9% accurate by always saying "not fraud")

**Solutions:**
- Collect more minority class data
- Undersample majority class
- Oversample minority class (SMOTE)
- Use appropriate metrics (precision/recall, not accuracy)
- Cost-sensitive learning
- Anomaly detection approaches

---

### 3. Data Bias

**Problem**: Data doesn't represent reality or reflects historical biases

**Examples:**
- Hiring AI trained on past (biased) hiring decisions
- Facial recognition performs worse on underrepresented groups
- Language models reflect stereotypes from training text

**Solutions:**
- Diverse data collection
- Bias auditing and testing
- Fairness constraints
- Regular model monitoring
- Human oversight

---

### 4. Data Drift

**Problem**: Data distribution changes over time

**Example:**
- E-commerce model trained pre-COVID
- Shopping behavior changed during pandemic
- Model performance degrades

**Types:**
- **Concept drift**: Relationship between input and output changes
- **Data drift**: Input distribution changes

**Solutions:**
- Monitor model performance continuously
- Retrain regularly with fresh data
- Online learning (continuous updates)
- Drift detection algorithms

---

### 5. Data Privacy & Security

**Challenges:**
- GDPR, CCPA compliance
- User consent and transparency
- Right to deletion
- Data breaches
- Model inversion attacks (reverse-engineer training data from model)

**Solutions:**
- Privacy-preserving techniques (differential privacy, federated learning)
- Data anonymization and pseudonymization
- Access controls and encryption
- Data governance policies
- Ethics review boards

---

## ✅ Practical Exercises

### Exercise 1: Data Quality Assessment (30 minutes)

You're building a model to predict customer churn. Review this sample data and identify issues:

```
| CustomerID | Age | Signup_Date | Monthly_Spend | Churn |
|------------|-----|-------------|---------------|-------|
| C001       | 25  | 1/15/2023   | 50.00        | No    |
| C002       | 999 | 2023-02-20  | 75.50        | Yes   |
| C001       | 25  | 1/15/2023   | 50.00        | No    |
| C004       | 34  | 03/10/23    | -20.00       | NULL  |
| C005       |     | 2023-04-05  | 120.00       | No    |
```

**Questions:**
1. What data quality issues do you see?
2. How would you fix each issue?
3. Would you remove any rows? Which and why?

---

### Exercise 2: Feature Engineering (45 minutes)

You're building a restaurant recommendation system. Raw data includes:
- Restaurant reviews (text)
- User profile (age, location, dietary preferences)
- Visit timestamp
- Rating (1-5 stars)

**Task:** Design features for the ML model
1. List 10+ features you would engineer
2. Explain how each feature would be useful
3. Identify which features might be most predictive

---

### Exercise 3: Data Requirements Document (60 minutes)

Pick an AI product idea and create a data requirements document:

**Template:**
```
Product: [AI feature name]
ML Problem: [What you're predicting]

Data Required:
  Input Features:
    - Feature 1: [description, type, source]
    - Feature 2: [description, type, source]
    ...

  Target Label:
    - [What you're predicting, how to obtain]

Data Sources:
  - Existing: [what you have]
  - Need to collect: [what's missing]
  - Third-party: [external data needed]

Data Volume:
  - Training set size: [estimated]
  - Expected collection time: [timeline]

Labeling Strategy:
  - [How labels will be obtained]
  - [Quality assurance process]

Privacy Considerations:
  - [PII, consent, compliance]

Data Quality Plan:
  - [Validation rules]
  - [Cleaning process]
  - [Monitoring strategy]
```

---

## 🤔 Critical Thinking Questions

1. **"We have 1 million rows of data, so we have enough for any ML model." True or false? Why?**

2. **Your model is 95% accurate, but business impact is minimal. What might be wrong with your data?**

3. **When would you choose to use synthetic/augmented data vs. collecting more real data?**

4. **How would you convince stakeholders to invest in data quality improvements rather than fancier algorithms?**

---

## 📖 Further Reading

### Essential
- [ ] [Google's Data Preparation Guide](https://developers.google.com/machine-learning/data-prep)
- [ ] "Data Science for Business" by Provost & Fawcett (Chapter 2-3)
- [ ] Andrew Ng's talks on Data-Centric AI

### Optional
- [ ] "Practical Statistics for Data Scientists" (Chapter 1-2)
- [ ] [Kaggle's Data Cleaning Course](https://www.kaggle.com/learn/data-cleaning)
- [ ] Papers on data quality best practices

---

## 📝 Self-Assessment

Before moving on, ensure you can:
- [ ] Explain the difference between structured, unstructured, and semi-structured data
- [ ] List the 5 qualities of good AI data
- [ ] Describe the data pipeline stages
- [ ] Identify common data quality issues
- [ ] Understand data labeling strategies
- [ ] Explain data challenges (insufficient, imbalanced, biased, drifted)
- [ ] Create a data requirements document for an AI feature

---

## 🚀 Key Takeaways for PMs

1. **Data quality > algorithm sophistication** for most projects
2. **Budget for data work**: 60-80% of AI project time is data prep
3. **Start with data audit**: What do you have vs. what do you need?
4. **Privacy is not optional**: Build it in from day one
5. **Monitor data in production**: Data drift can silently break models

---

## 🔗 Next Session

[Session 04: ML Project Workflow →](./04-ml-project-workflow.md)

Learn the end-to-end process of building and deploying machine learning projects.

---

*Last Updated: 2025*
