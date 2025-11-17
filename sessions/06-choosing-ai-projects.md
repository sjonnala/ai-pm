# Session 06: Choosing AI Projects

**Week 2 | Duration: 3-4 hours**

## 🎯 Learning Objectives

- Develop framework for evaluating AI project opportunities
- Assess feasibility, value, and cost of AI initiatives
- Prioritize AI projects for maximum business impact
- Understand when NOT to use AI

---

## 📊 AI Project Evaluation Framework

### Andrew Ng's Framework: Feasibility + Value

#### Technical Feasibility

**Can AI solve this problem?**

Questions to ask:
1. Can a human do this task given the same information?
   - If yes → likely feasible for ML
   - If no → likely not feasible

2. Do we have (or can we get) enough quality data?
   - Supervised learning: labeled examples
   - Quantity: thousands to millions depending on complexity

3. Is it pattern recognition vs. rule-based?
   - Pattern recognition → ML
   - Clear rules → traditional programming

4. Can we tolerate some errors?
   - ML is probabilistic, not perfect
   - Critical systems may need guarantees

**Feasibility Checklist:**
- [ ] Human can perform task with given information
- [ ] Sufficient training data available or obtainable
- [ ] Data quality meets requirements
- [ ] Acceptable error rate defined
- [ ] No deterministic solution required

---

#### Business Value

**Will this create significant impact?**

**Value Assessment:**

1. **Revenue Impact**
   - Increase sales (recommendations, personalization)
   - New revenue streams (AI-powered features)
   - Pricing optimization

2. **Cost Reduction**
   - Automate manual tasks
   - Reduce errors and waste
   - Optimize resource allocation

3. **User Experience**
   - Personalization
   - Faster/better service
   - New capabilities

4. **Strategic Value**
   - Competitive differentiation
   - Data moat (network effects)
   - Platform for future capabilities

**Value Calculation Template:**
```
Annual Value Estimate:

Revenue Impact:
- Increase in conversion: ___% × $_____ = $_____
- New customers: _____ × $_____ LTV = $_____

Cost Savings:
- Labor hours saved: _____ × $_____ = $_____
- Error reduction: ___% × $_____ = $_____

Total Annual Value: $_____
```

---

### The AI Project Prioritization Matrix

```
          High Value
               ↑
    Quick Wins │ Strategic Bets
               │
    ───────────┼───────────
               │
    Low Hanging│ Money Pits
      Fruit    │
               ↓
          Low Value

    Low ← Feasibility → High
```

**1. Quick Wins (High Value, High Feasibility)**
- **Do First!**
- Examples: Product recommendations, email personalization
- Build momentum and demonstrate AI value

**2. Strategic Bets (High Value, Low Feasibility)**
- **Long-term investments**
- Examples: Autonomous vehicles, AGI
- Require research, significant resources
- High risk, high reward

**3. Low Hanging Fruit (Low Value, High Feasibility)**
- **Do if resources available**
- Examples: Simple automations
- Good for learning, building capabilities
- Don't over-invest

**4. Money Pits (Low Value, Low Feasibility)**
- **Avoid!**
- Not worth the effort

---

## 🎯 Choosing Your First AI Projects

### Criteria for Early AI Projects

1. **Start with High Feasibility**
   - Build confidence and expertise
   - Demonstrate value quickly
   - Learn organizational challenges

2. **Clear Success Metrics**
   - Easy to measure impact
   - Short feedback loop
   - Visible to stakeholders

3. **Contained Scope**
   - Specific use case
   - Limited dependencies
   - Fast to iterate

4. **Low Risk**
   - Non-critical systems
   - Errors not catastrophic
   - Easy to rollback

5. **Data Available**
   - Existing data or easy to collect
   - Good quality
   - Sufficient volume

---

## ❌ When NOT to Use AI

### Red Flags

**1. Simple Rules Work Fine**
- Example: If temperature > 75°F, turn on AC
- Don't use ML for what if-else can handle

**2. Insufficient or Poor Data**
- Can't get enough training data
- Data quality too low
- Bias concerns can't be mitigated

**3. Determinism Required**
- Safety-critical without fallbacks
- Legal/regulatory mandates exact logic
- Need to guarantee specific outcomes

**4. Explainability Critical**
- Can't use black-box models
- Need to justify every decision legally
- Stakeholders won't trust unexplainable system

**5. Not Worth the Cost**
- ML infrastructure and maintenance expensive
- Traditional solution much cheaper
- Value doesn't justify investment

**6. Problem is Unclear**
- Don't know what you're optimizing for
- Requirements constantly changing
- No way to measure success

---

## 💡 AI Project Ideation

### Finding AI Opportunities

**1. Task Automation**
- What manual, repetitive tasks exist?
- What do humans do that's pattern recognition?
- Examples: Data entry, image tagging, email routing

**2. Optimization**
- What decisions involve tradeoffs?
- What resources could be allocated better?
- Examples: Pricing, inventory, scheduling

**3. Personalization**
- What should be different for each user?
- What preferences can we learn?
- Examples: Content, recommendations, UX

**4. Prediction**
- What would be valuable to forecast?
- What uncertainty creates problems?
- Examples: Demand, churn, equipment failure

**5. Insights**
- What patterns are hidden in data?
- What questions can't be answered manually?
- Examples: Customer segments, anomaly detection

### Ideation Exercise Template

```
Business Area: _____________

Current Pain Points:
1. _____________________
2. _____________________
3. _____________________

AI Opportunity Ideas:
Idea 1:
  - What: _____________
  - Who benefits: ______
  - Value: $___________
  - Feasibility: High/Med/Low
  - Data needed: _______

Idea 2: ...
```

---

## 🎯 Case Studies

### Case Study 1: Netflix Recommendations

**Problem:** Help users find content they'll enjoy
**Feasibility:**
  - ✅ Humans can recommend content
  - ✅ Massive data (viewing history, ratings)
  - ✅ Pattern recognition problem
  - ✅ Errors acceptable (bad recommendation = skip)

**Value:**
  - 80% of viewed content from recommendations
  - Reduces churn
  - Increases engagement
  - Estimated $1B+ annual value

**Result:** Quick win → continued investment

---

### Case Study 2: Fraud Detection

**Problem:** Identify fraudulent transactions

**Feasibility:**
  - ✅ Humans can spot fraud patterns (but slow)
  - ✅ Transaction data available
  - ✅ Pattern recognition with rare events
  - ⚠️  Errors costly (false positives annoy customers)

**Value:**
  - Prevent millions in losses
  - Faster than manual review
  - Scales to high volume

**Challenges:**
  - Imbalanced data (rare fraud cases)
  - Adversarial (fraudsters adapt)
  - Need high precision and recall

**Result:** High value, manageable feasibility → strategic bet

---

## ✅ Practical Exercises

### Exercise 1: Feasibility Assessment (30 min)

Assess feasibility of these AI ideas:

1. **Predict stock prices for next month**
   - Can humans do this?
   - What data is available?
   - What's different about AI approach?

2. **Diagnose diseases from medical images**
   - Can doctors do this?
   - What training data exists?
   - What are the risks?

3. **Generate creative marketing copy**
   - Can humans do this?
   - How would you measure quality?
   - What are limitations?

---

### Exercise 2: AI Project Prioritization (60 min)

You're a PM at an e-commerce company. Evaluate and prioritize these ideas:

**Idea A: Product Recommendations**
- Suggest products based on browsing/purchase history
- Data: 5 years of user data, millions of interactions
- Potential value: 10% increase in AOV = $50M/year

**Idea B: Automated Customer Support**
- Chatbot to handle common questions
- Data: 2 years of support tickets
- Potential value: Save 20 FTE = $2M/year

**Idea C: Demand Forecasting**
- Predict product demand to optimize inventory
- Data: 3 years of sales data, external factors
- Potential value: Reduce overstock 15% = $10M/year

**Idea D: Visual Search**
- Search products by uploading images
- Data: Product catalog images, limited user search data
- Potential value: Increase discovery = $5M/year (uncertain)

**Tasks:**
1. Assess feasibility (high/medium/low) for each
2. Plot on prioritization matrix
3. Recommend order of execution
4. Justify your reasoning

---

### Exercise 3: Opportunity Identification (45 min)

Pick an industry or company you're familiar with:

1. **Identify 5 AI opportunities**
   - What manual tasks exist?
   - What could be personalized?
   - What needs prediction?

2. **For each opportunity, assess:**
   - Feasibility (can it be done?)
   - Value (what's the impact?)
   - Data availability
   - Risk level

3. **Choose top 2 to pursue**
   - Why these?
   - What would you do first?
   - What resources needed?

---

## 🤔 Critical Thinking Questions

1. **Why do many AI projects fail?**
   - Consider: feasibility assessment, value calculation, data quality

2. **How do you balance "moonshot" AI projects with practical wins?**
   - Think about: portfolio approach, resource allocation, risk

3. **What's the difference between an AI project and an AI feature?**
   - Consider: scope, impact, organizational change

4. **How do you convince stakeholders to invest in AI infrastructure before specific projects?**
   - Think about: platform vs. point solutions, long-term vision

---

## 📖 Further Reading

- [ ] Andrew Ng's "AI Transformation Playbook"
- [ ] "Data Science for Business" (Chapter 2: Business Problems and Data Science Solutions)
- [ ] McKinsey reports on AI adoption and value

---

## 📝 Deliverable

**AI Project Evaluation Matrix:**

Create a reusable template for your organization:
- Feasibility assessment criteria
- Value estimation framework
- Risk evaluation
- Prioritization methodology
- Decision-making process

---

## 🎯 Key Takeaways

1. **Feasibility first**: Can AI solve this? Do we have data?
2. **Value matters**: Focus on business impact, not cool tech
3. **Start small**: Quick wins build momentum and expertise
4. **Know when to say no**: Not every problem needs AI
5. **Portfolio approach**: Mix of quick wins and strategic bets

---

## 🔗 Next Session

[Session 07: Working with AI Teams →](./07-working-with-ai-teams.md)

---

*Last Updated: 2025*
