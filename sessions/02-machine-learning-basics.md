# Session 02: Machine Learning Basics

**Week 1 | Duration: 3-4 hours**

## 🎯 Learning Objectives

By the end of this session, you will:
- Understand the three main types of machine learning
- Learn how ML models are trained and evaluated
- Recognize common ML algorithms and their use cases
- Understand the concept of model performance and accuracy

---

## 📚 What is Machine Learning?

**Machine Learning** is a method of data analysis that automates analytical model building. It enables computers to find hidden insights without being explicitly programmed where to look.

### The Core Idea

Instead of programming rules explicitly, we:
1. Provide data (examples)
2. Let the algorithm find patterns
3. Use those patterns to make predictions

---

## 🔍 Three Types of Machine Learning

### 1. Supervised Learning

**Definition**: Learning from labeled data (input-output pairs)

**How it works:**
```
Training Data: (Input, Correct Output)
Goal: Learn a function that maps inputs to outputs
```

**Common Algorithms:**
- Linear Regression (predict continuous values)
- Logistic Regression (classify into categories)
- Decision Trees
- Random Forests
- Support Vector Machines (SVM)
- Neural Networks

**Real-World Examples:**

| Use Case | Input | Output (Label) |
|----------|-------|----------------|
| Email Spam Detection | Email text | Spam / Not Spam |
| House Price Prediction | Size, location, bedrooms | Price |
| Image Classification | Image pixels | Cat / Dog / Bird |
| Credit Scoring | Financial history | Approve / Deny |

**When to use:**
- You have labeled training data
- You know what you're predicting
- Historical examples exist

---

### 2. Unsupervised Learning

**Definition**: Learning from unlabeled data (find hidden patterns)

**How it works:**
```
Training Data: Input only (no labels)
Goal: Discover structure or patterns in data
```

**Common Algorithms:**
- K-Means Clustering
- Hierarchical Clustering
- Principal Component Analysis (PCA)
- Anomaly Detection

**Real-World Examples:**

| Use Case | Input | What It Finds |
|----------|-------|---------------|
| Customer Segmentation | Purchase history | Groups of similar customers |
| Anomaly Detection | Transaction data | Unusual/fraudulent patterns |
| Recommendation Systems | User behavior | Similar items/users |
| Document Clustering | Text documents | Topics or themes |

**When to use:**
- No labeled data available
- Want to explore data structure
- Looking for hidden patterns
- Customer segmentation

---

### 3. Reinforcement Learning

**Definition**: Learning through trial and error with rewards/penalties

**How it works:**
```
Agent takes actions in environment
Receives rewards (positive) or penalties (negative)
Learns to maximize cumulative reward
```

**Key Concepts:**
- **Agent**: The learner/decision maker
- **Environment**: What the agent interacts with
- **Action**: What the agent can do
- **Reward**: Feedback from environment
- **Policy**: Strategy for choosing actions

**Real-World Examples:**

| Use Case | Agent | Actions | Reward |
|----------|-------|---------|--------|
| Game Playing (AlphaGo) | AI player | Game moves | Win/loss |
| Robotics | Robot | Movements | Task completion |
| Recommendation Systems | System | Content to show | User engagement |
| Autonomous Driving | Car | Steering, speed | Safe arrival |

**When to use:**
- Sequential decision-making
- Long-term optimization
- Gaming, robotics, control systems
- Dynamic environments

---

## 🛠️ The Machine Learning Workflow

### Step 1: Define the Problem
- What are you trying to predict or optimize?
- What type of ML is appropriate?
- What does success look like?

### Step 2: Collect and Prepare Data
- Gather relevant data
- Clean and preprocess
- Handle missing values
- Feature engineering

### Step 3: Split the Data
```
All Data (100%)
├── Training Set (70-80%): Train the model
├── Validation Set (10-15%): Tune hyperparameters
└── Test Set (10-15%): Final evaluation
```

**Why split?**
- Prevent overfitting
- Get unbiased performance estimates
- Tune model without cheating

### Step 4: Choose and Train Model
- Select appropriate algorithm
- Train on training data
- Adjust hyperparameters using validation set

### Step 5: Evaluate Performance
- Test on unseen test data
- Measure accuracy, precision, recall, etc.
- Compare to baseline

### Step 6: Deploy and Monitor
- Put model into production
- Monitor performance over time
- Retrain as needed

---

## 📊 Evaluating ML Models

### Classification Metrics

**Confusion Matrix:**
```
                Predicted
              Positive  Negative
Actual Positive   TP       FN
       Negative   FP       TN
```

- **TP (True Positive)**: Correctly predicted positive
- **TN (True Negative)**: Correctly predicted negative
- **FP (False Positive)**: Incorrectly predicted positive (Type I error)
- **FN (False Negative)**: Incorrectly predicted negative (Type II error)

**Key Metrics:**

1. **Accuracy** = (TP + TN) / Total
   - Overall correctness
   - Can be misleading with imbalanced data

2. **Precision** = TP / (TP + FP)
   - Of all positive predictions, how many were correct?
   - Important when false positives are costly

3. **Recall (Sensitivity)** = TP / (TP + FN)
   - Of all actual positives, how many did we catch?
   - Important when false negatives are costly

4. **F1 Score** = 2 × (Precision × Recall) / (Precision + Recall)
   - Harmonic mean of precision and recall
   - Good for imbalanced datasets

**Example: Medical Diagnosis**
- High Recall needed: Don't miss cancer cases (minimize FN)
- High Precision needed: Don't cause unnecessary panic (minimize FP)

### Regression Metrics

For predicting continuous values:

1. **Mean Absolute Error (MAE)**: Average absolute difference
2. **Mean Squared Error (MSE)**: Average squared difference
3. **R² Score**: How well model explains variance (0-1, higher is better)

---

## 🧩 Common ML Algorithms (Product Manager View)

### Linear Regression
- **What**: Predicts continuous values with linear relationship
- **Use Cases**: Sales forecasting, price prediction
- **Pros**: Simple, interpretable, fast
- **Cons**: Assumes linear relationship

### Logistic Regression
- **What**: Binary classification (yes/no, 0/1)
- **Use Cases**: Email spam, loan approval, churn prediction
- **Pros**: Fast, interpretable, works well with less data
- **Cons**: Limited to linear decision boundaries

### Decision Trees
- **What**: Tree-like model of decisions
- **Use Cases**: Credit approval, diagnosis
- **Pros**: Easy to understand, handles non-linear data
- **Cons**: Can overfit easily

### Random Forests
- **What**: Many decision trees voting together
- **Use Cases**: Fraud detection, recommendation
- **Pros**: More accurate, less overfitting
- **Cons**: Less interpretable, slower

### Neural Networks
- **What**: Layers of interconnected nodes mimicking brain
- **Use Cases**: Image recognition, NLP, complex patterns
- **Pros**: Can learn complex patterns
- **Cons**: Needs lots of data, computationally expensive, "black box"

### K-Means Clustering
- **What**: Groups similar data points
- **Use Cases**: Customer segmentation, document clustering
- **Pros**: Simple, fast
- **Cons**: Need to specify number of clusters

---

## 💡 Key Concepts for PMs

### 1. Overfitting vs. Underfitting

**Underfitting:**
- Model is too simple
- Poor performance on training and test data
- Solution: More complex model, more features

**Overfitting:**
- Model memorizes training data
- Great on training, poor on test data
- Solution: More data, simpler model, regularization

**Sweet Spot:**
- Generalizes well to new data
- Balance between bias and variance

### 2. Feature Engineering

**Features** are the input variables used for prediction.

**Feature engineering** is creating new features from raw data:
- Combining existing features
- Extracting parts of data (e.g., day from date)
- Encoding categorical variables
- Normalizing numerical values

**Example:**
- Raw: "2025-01-15 14:30:00"
- Engineered features: hour, day_of_week, is_weekend, is_business_hours

Good features often matter more than complex algorithms!

### 3. Model Complexity vs. Data Size

```
Small Data → Use simpler models (logistic regression, small trees)
Large Data → Can use complex models (deep neural networks)
```

### 4. Interpretability vs. Accuracy Trade-off

```
More Interpretable    →    More Accurate
Linear Regression         Random Forests
Decision Trees           Neural Networks
                        Deep Learning
```

As a PM, you need to balance:
- **Regulated industries**: May require interpretability (finance, healthcare)
- **User-facing**: May prioritize accuracy (recommendations, search)

---

## ✅ Practical Exercises

### Exercise 1: ML Type Classification (20 minutes)

For each scenario, identify the type of ML and why:

1. **Spotify Discover Weekly**: Recommends songs based on listening history
2. **Gmail spam filter**: Classifies emails as spam/not spam
3. **Google News grouping**: Groups similar news articles together
4. **AlphaGo**: Plays the game Go
5. **Credit card fraud detection**: Identifies unusual transactions
6. **House price prediction**: Estimates home values based on features
7. **Netflix content grouping**: Creates genre categories from viewing data
8. **Self-driving car**: Learns to navigate roads

**Answers:**
1. Supervised (has user feedback) or Unsupervised (collaborative filtering)
2. Supervised (labeled spam/not spam examples)
3. Unsupervised (no labels, finding patterns)
4. Reinforcement (learning from game outcomes)
5. Unsupervised (anomaly detection) or Supervised (if labeled fraud examples)
6. Supervised (has historical price labels)
7. Unsupervised (clustering)
8. Reinforcement (learning from driving outcomes)

### Exercise 2: Choose the Right Metric (30 minutes)

For each use case, determine which metric matters most and why:

1. **Cancer Screening Test**
   - Should you optimize for precision or recall?

2. **YouTube Recommendation System**
   - What success metric would you use?

3. **Email Spam Filter**
   - Precision vs. Recall trade-off?

4. **Loan Approval System**
   - What are the costs of false positives vs. false negatives?

**Discussion Points:**
- Cancer: High recall (don't miss cases), even if some false positives
- YouTube: Click-through rate, watch time, user satisfaction
- Spam: Balance - missing spam is annoying, blocking real email is worse
- Loans: FP = lose money, FN = miss opportunity

### Exercise 3: ML Problem Formulation (45 minutes)

Pick a product feature idea and formulate it as an ML problem:

**Template:**
```
Feature Idea: [Your idea]
Business Goal: [What you want to achieve]
ML Problem Type: [Supervised/Unsupervised/Reinforcement]
Input (Features): [What data you'll use]
Output (Target): [What you're predicting]
Success Metric: [How you'll measure success]
Data Sources: [Where you'll get training data]
Potential Challenges: [What could go wrong]
```

**Example:**
```
Feature Idea: Smart email reply time prediction
Business Goal: Help users prioritize urgent emails
ML Problem Type: Supervised Learning (Classification)
Input: Sender, subject, time sent, email content, user history
Output: Response urgency (immediate, today, this week, whenever)
Success Metric: Accuracy of predictions, user satisfaction
Data Sources: User email history, response times
Potential Challenges: Different users have different urgency definitions
```

---

## 🤔 Critical Thinking Questions

1. **When should you NOT use machine learning?**
   - Consider: simple rule-based solutions, lack of data, need for determinism

2. **Why does more data usually improve ML performance?**
   - Think about: patterns, edge cases, generalization

3. **How would you explain overfitting to a non-technical executive?**
   - Use analogies: memorizing vs. understanding for a test

4. **What are the risks of deploying an ML model that's 95% accurate?**
   - Consider: what happens with the 5% errors, cost of mistakes

---

## 📖 Further Reading

### Essential
- [ ] Andrew Ng's Machine Learning Course (Week 1-2)
- [ ] Google's Machine Learning Crash Course (Intro sections)
- [ ] [Visual Introduction to ML](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)

### Optional
- [ ] "Hands-On Machine Learning" by Aurélien Géron (Chapter 1-2)
- [ ] [ML Cheat Sheet](https://ml-cheatsheet.readthedocs.io/)
- [ ] [Kaggle's ML Micro-Courses](https://www.kaggle.com/learn)

---

## 📝 Self-Assessment

Before moving to Session 03, ensure you can:
- [ ] Explain supervised, unsupervised, and reinforcement learning
- [ ] Describe the ML workflow from problem to deployment
- [ ] Understand key evaluation metrics (accuracy, precision, recall)
- [ ] Explain overfitting and underfitting
- [ ] Identify which ML type to use for a given problem
- [ ] Understand the importance of train/validation/test splits

---

## 🚀 Key Takeaways for PMs

1. **Not everything needs ML**: Start with simpler solutions
2. **Data is critical**: Good data > complex algorithms
3. **Metrics matter**: Choose metrics aligned with business goals
4. **Iterate**: Start simple, improve over time
5. **Monitor in production**: Models can degrade over time

---

## 🔗 Next Session

[Session 03: Understanding Data in AI →](./03-understanding-data-in-ai.md)

Deep dive into data - the fuel for AI systems - and learn about data quality, preparation, and requirements.

---

*Last Updated: 2025*
