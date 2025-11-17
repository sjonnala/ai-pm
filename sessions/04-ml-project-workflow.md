# Session 04: ML Project Workflow

**Week 2 | Duration: 3 hours**

## 🎯 Learning Objectives

- Understand the end-to-end ML project lifecycle
- Learn the key stages from problem definition to deployment
- Recognize common pitfalls and how to avoid them
- Develop a framework for scoping and executing ML projects

---

## 📚 The ML Project Lifecycle

```
1. Problem Definition
   ↓
2. Data Collection & Preparation
   ↓
3. Model Development
   ↓
4. Model Evaluation
   ↓
5. Deployment
   ↓
6. Monitoring & Maintenance
```

---

## 🎯 Stage 1: Problem Definition

### Key Questions

**1. Is this an ML problem?**
- Does it require pattern recognition from data?
- Can rules-based approach work instead?
- Is there enough data available?

**2. What exactly are we predicting?**
- Define the target variable clearly
- Supervised, unsupervised, or reinforcement learning?

**3. What does success look like?**
- Business metrics (revenue, retention, satisfaction)
- Technical metrics (accuracy, precision, recall)
- How will model impact users?

**4. What are the constraints?**
- Latency requirements (real-time vs. batch)
- Cost limitations (compute, storage, labor)
- Regulatory compliance (GDPR, fairness)
- Interpretability needs

### ML Project Canvas Template

```
PROJECT NAME: _______________________

Business Problem:
- What problem are we solving?
- Who is impacted?
- What's the current solution?

ML Formulation:
- Input (X): What features?
- Output (Y): What are we predicting?
- Type: Classification / Regression / Clustering / Other

Success Metrics:
- Business: ___________
- Technical: ___________

Constraints:
- Latency: ___________
- Budget: ___________
- Compliance: ___________

Timeline:
- Discovery: ___ weeks
- Development: ___ weeks
- Deployment: ___ weeks

Resources Needed:
- Data: ___________
- Team: ___________
- Infrastructure: ___________
```

---

## 📊 Stage 2: Data Collection & Preparation

### 2.1 Data Discovery
- What data exists?
- Where is it stored?
- What's the quality?
- What's missing?

### 2.2 Data Collection
- Gather from existing sources
- Set up new data collection (instrumentation)
- Consider third-party data
- Ensure legal/ethical compliance

### 2.3 Exploratory Data Analysis (EDA)
```
- Understand distributions
- Identify correlations
- Spot anomalies
- Visualize patterns
- Generate hypotheses
```

### 2.4 Data Preparation
- Cleaning (handle missing, outliers, duplicates)
- Feature engineering
- Data splitting (train/val/test)
- Documentation

**Time Allocation:** Often 60-80% of project effort!

---

## 🧪 Stage 3: Model Development

### 3.1 Baseline Model

**Always start with a simple baseline:**
- Simple heuristic (e.g., predict most common class)
- Basic algorithm (logistic regression, decision tree)
- Existing solution performance

**Why?**
- Know if ML adds value
- Benchmark for comparison
- Fast to implement

### 3.2 Model Selection

**Start simple, add complexity as needed:**

```
1. Try simple algorithms first
   ↓
2. If insufficient, try ensemble methods
   ↓
3. If still insufficient, try deep learning
```

**Factors to consider:**
- Data size (small = simple models, large = can try complex)
- Feature types (structured = traditional ML, images/text = deep learning)
- Interpretability needs
- Latency requirements
- Team expertise

### 3.3 Hyperparameter Tuning

- Grid search (try all combinations)
- Random search (sample randomly)
- Bayesian optimization (smart search)
- Cross-validation for robust estimates

### 3.4 Feature Iteration

- Add new features
- Remove unhelpful features
- Transform existing features
- Domain expert collaboration

---

## ✅ Stage 4: Model Evaluation

### 4.1 Offline Evaluation

**Test set performance:**
- Use held-out test data
- Measure relevant metrics
- Compare to baseline
- Error analysis (where does it fail?)

**Evaluation checklist:**
- [ ] Overall performance meets requirements
- [ ] Performance across different segments (fairness)
- [ ] Edge cases handled appropriately
- [ ] Confidence calibration (if using probabilities)
- [ ] Interpretability and explainability

### 4.2 Error Analysis

**Systematically analyze mistakes:**

1. **Categorize errors**
   - What types of examples fail?
   - Are there patterns?

2. **Prioritize fixes**
   - Which errors are most costly?
   - Which are most common?
   - Which are fixable?

3. **Iterate**
   - Collect more data for error cases
   - Engineer new features
   - Try different algorithms

**Example error analysis:**
```
Email spam classifier errors:
- 40% marketing emails misclassified (data issue - need more examples)
- 30% promotional but useful (ambiguous - need better features)
- 20% foreign language (coverage issue - expand training data)
- 10% adversarial (evolving problem - need continuous updates)
```

### 4.3 Pre-Production Validation

- [ ] Model performance on recent data
- [ ] Latency and resource usage acceptable
- [ ] Model serialization and loading works
- [ ] Integration with existing systems tested
- [ ] Failure modes and fallbacks defined

---

## 🚀 Stage 5: Deployment

### 5.1 Deployment Strategies

**1. Shadow Deployment**
- Run new model alongside existing system
- Don't serve predictions to users yet
- Compare performance
- **Pros:** Safe, can test with real data
- **Cons:** Doesn't test user impact

**2. A/B Testing**
- Serve new model to small % of users
- Compare metrics vs. control
- Gradually increase if successful
- **Pros:** Measures real impact
- **Cons:** Some users get worse experience if model fails

**3. Canary Deployment**
- Deploy to small segment first
- Monitor closely
- Expand if stable
- **Pros:** Limits blast radius
- **Cons:** Requires good monitoring

**4. Blue-Green Deployment**
- Two identical production environments
- Switch traffic between them
- Easy rollback
- **Pros:** Fast rollback
- **Cons:** Resource intensive

### 5.2 Deployment Checklist

**Technical:**
- [ ] Model exported and versioned
- [ ] Serving infrastructure set up
- [ ] API endpoints defined and tested
- [ ] Latency requirements met
- [ ] Resource limits configured
- [ ] Logging and monitoring in place

**Operational:**
- [ ] Rollback plan documented
- [ ] On-call rotation assigned
- [ ] Stakeholders informed
- [ ] Documentation updated
- [ ] Training for support team

**Compliance:**
- [ ] Privacy review completed
- [ ] Security scan passed
- [ ] Fairness audit done
- [ ] Regulatory requirements met

---

## 📈 Stage 6: Monitoring & Maintenance

### 6.1 What to Monitor

**Model Performance:**
- Prediction accuracy/error rates
- Distribution of predictions
- Confidence scores

**Data Quality:**
- Feature distributions (detect drift)
- Missing data rates
- Data pipeline health

**System Performance:**
- Latency (p50, p95, p99)
- Throughput (requests/second)
- Resource usage (CPU, memory)
- Error rates

**Business Metrics:**
- User engagement
- Conversion rates
- Revenue impact
- Customer satisfaction

### 6.2 When to Retrain

**Triggers:**
- Scheduled (e.g., weekly, monthly)
- Performance degradation detected
- Significant data drift
- New data available
- Business requirements change

**Retraining workflow:**
```
1. Collect new data
2. Validate data quality
3. Retrain model
4. Evaluate on test set
5. A/B test vs. current model
6. Deploy if better
7. Archive old model version
```

### 6.3 Model Governance

- **Version control:** Track model versions and code
- **Experiment tracking:** Log all experiments and results
- **Model registry:** Central repository for models
- **Lineage tracking:** Know what data trained which model
- **Audit trail:** Who deployed what, when, and why

---

## ⚠️ Common Pitfalls & How to Avoid Them

### 1. Jumping to Models Too Quickly
**Problem:** Starting with model before understanding data/problem
**Solution:** Spend time on problem definition and EDA

### 2. Data Leakage
**Problem:** Test data information leaks into training
**Example:** Using future information to predict the past
**Solution:** Strict train/test separation, time-based splits

### 3. Overfitting to Test Set
**Problem:** Tuning model based on test performance
**Solution:** Use validation set for tuning, test only for final evaluation

### 4. Ignoring Baseline
**Problem:** Don't know if ML adds value
**Solution:** Always establish simple baseline first

### 5. Not Monitoring in Production
**Problem:** Model degrades silently
**Solution:** Comprehensive monitoring and alerting

### 6. Poor Communication
**Problem:** Technical team and business team misaligned
**Solution:** Regular check-ins, shared metrics, clear documentation

---

## ✅ Practical Exercises

### Exercise 1: Project Scoping (45 min)

Scope an ML project using the ML Project Canvas:

**Scenario:** E-commerce company wants to reduce customer support costs

Fill out complete ML Project Canvas considering:
- Is ML the right solution?
- What would you predict?
- What data exists?
- What does success look like?
- What are the constraints?

### Exercise 2: Deployment Strategy (30 min)

**Scenario:** Launching new recommendation algorithm for homepage

Choose deployment strategy and justify:
1. What strategy would you use?
2. What metrics would you monitor?
3. What's your rollback criteria?
4. What's your expansion plan?

### Exercise 3: Error Analysis (45 min)

**Given:** Spam classifier with 95% accuracy, but users complaining

**Error breakdown:**
- 3% false positives (good email marked spam)
- 2% false negatives (spam not caught)

**Questions:**
1. Which error type is worse? Why?
2. How would you investigate false positives?
3. What data would you collect?
4. How would you measure improvement?

---

## 📖 Further Reading

- [ ] "Building Machine Learning Powered Applications" by Genevieve Huygen
- [ ] "Reliable Machine Learning" by Cathy Chen et al.
- [ ] [Google's ML Handbook](https://developers.google.com/machine-learning)

---

## 📝 Deliverable

**ML Project Proposal Template:**
Create a reusable template for proposing ML projects including:
- Problem statement
- ML formulation
- Data requirements
- Success metrics
- Timeline and resources
- Risks and mitigation

---

## 🔗 Next Session

[Session 05: Data Science Project Lifecycle →](./05-data-science-lifecycle.md)

---

*Last Updated: 2025*
