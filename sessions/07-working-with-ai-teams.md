# Session 07: Working with AI Teams

**Week 2 | Duration: 2-3 hours**

## 🎯 Learning Objectives

- Understand the roles in an AI/ML team
- Learn how to effectively collaborate with data scientists and ML engineers
- Master communication between technical and business stakeholders
- Navigate common challenges in cross-functional AI teams

---

## 👥 Key Roles in AI Teams

### 1. Machine Learning Engineer
**Focus:** Building and deploying ML systems into production

**Responsibilities:**
- Train and optimize ML models
- Build ML pipelines
- Deploy models to production
- Monitor model performance
- Scale ML infrastructure

**Skills:** Python, ML frameworks (TensorFlow, PyTorch), MLOps, cloud platforms

**PM Collaboration:**
- Define technical requirements and constraints
- Prioritize model improvements vs. new features
- Plan deployment strategies and timelines

---

### 2. Data Scientist
**Focus:** Extracting insights from data, prototyping ML solutions

**Responsibilities:**
- Exploratory data analysis
- Build prototype models
- Statistical analysis
- A/B test design and analysis
- Generate business insights

**Skills:** Statistics, Python/R, SQL, data visualization, experimentation

**PM Collaboration:**
- Frame business questions as data problems
- Interpret experiment results
- Validate assumptions and hypotheses

---

### 3. Data Engineer
**Focus:** Building and maintaining data infrastructure

**Responsibilities:**
- Design data pipelines
- Ensure data quality and reliability
- Build data warehouses/lakes
- Optimize data storage and retrieval
- Create data access tools

**Skills:** SQL, ETL tools, distributed systems (Spark, Kafka), cloud platforms

**PM Collaboration:**
- Define data requirements for features
- Understand data availability and limitations
- Plan data collection strategies

---

### 4. ML/AI Product Manager (You!)
**Focus:** Product strategy and execution for AI features

**Responsibilities:**
- Define product vision and roadmap
- Prioritize features and improvements
- Bridge business and technical teams
- Define success metrics
- Go-to-market planning

**Skills:** Product management + AI/ML literacy + data fluency

---

### 5. MLOps Engineer
**Focus:** ML deployment and operations

**Responsibilities:**
- Build ML deployment pipelines
- Monitor models in production
- Version control for models and data
- Automate retraining
- Ensure model governance

**Skills:** DevOps, ML platforms, monitoring tools, cloud infrastructure

---

### 6. Research Scientist (in some orgs)
**Focus:** Advancing state-of-the-art ML techniques

**Responsibilities:**
- Explore novel ML approaches
- Publish research papers
- Prototype cutting-edge techniques
- Advise on technical direction

**Skills:** Deep ML expertise, research methodology, mathematics

---

## 🤝 Effective PM-Data Scientist Collaboration

### Common Challenges

**1. Different Languages**
- **Problem:** PMs speak "business", DS speak "technical"
- **Solution:** Learn each other's vocabulary, use visual aids

**2. Misaligned Expectations**
- **Problem:** PM wants 99% accuracy, DS says 80% is realistic
- **Solution:** Discuss feasibility early, set realistic goals together

**3. Prototype vs. Production Gap**
- **Problem:** DS prototype works on laptop, production deployment complex
- **Solution:** Involve ML engineers early, discuss deployment constraints

**4. Unclear Success Criteria**
- **Problem:** "Make it better" is too vague
- **Solution:** Define specific, measurable success metrics upfront

---

### Best Practices

**1. Joint Problem Framing**
```
Weekly Collaboration:
- PM brings business problem
- DS helps formulate as ML problem
- Together define success metrics
- Agree on timeline and scope
```

**2. Regular Check-ins**
- Weekly sync on progress
- Review model performance together
- Discuss blockers and trade-offs
- Iterate on approach

**3. Shared Documentation**
- Project brief accessible to all
- Experiment log (what was tried, results)
- Model documentation (how it works, limitations)
- Decision log (why choices were made)

**4. Data-Driven Decisions**
- Use A/B tests to validate impact
- Review metrics together
- Let data inform prioritization

---

## 💬 Communication Framework

### Translating Business to Technical

**Business Request → Technical Specification**

**Example 1:**
- **Business:** "We need to reduce churn"
- **Better:** "Predict which users will churn in next 30 days, so we can intervene"
- **Even Better:** "Build classifier to predict 30-day churn with 70%+ recall, <10% FP rate, latency <100ms"

**Example 2:**
- **Business:** "Improve recommendations"
- **Better:** "Increase recommendation click-through rate by 15%"
- **Even Better:** "Optimize for engagement (CTR + watch time) while maintaining content diversity"

---

### Translating Technical to Business

**Technical Metric → Business Impact**

**Example:**
- **Technical:** "Improved model accuracy from 85% to 90%"
- **Business:** "Reduced false alarms by 33%, saving support team 10 hours/week"

**Key:** Always connect technical metrics to business value!

---

## ⚙️ Technical Tools You Should Know (PM Level)

### 1. Jupyter Notebooks
**What:** Interactive coding environment
**Why PMs care:** Where DS do exploratory work, share analyses
**Your use:** Review experiment results, understand approach

### 2. Git / GitHub
**What:** Version control for code
**Why PMs care:** Track changes, collaborate on code
**Your use:** Review code commits, understand what changed

### 3. SQL
**What:** Database query language
**Why PMs care:** Access and analyze product data
**Your use:** Self-serve simple analyses, understand data availability

### 4. Python (basic reading)
**What:** Programming language for ML/DS
**Why PMs care:** Understand what team is building
**Your use:** Review code at high level, follow logic

### 5. Experiment Platforms (e.g., Optimizely, LaunchDarkly)
**What:** A/B testing tools
**Why PMs care:** Validate product changes
**Your use:** Design experiments, interpret results

### 6. Analytics Tools (Mixpanel, Amplitude, Google Analytics)
**What:** Product analytics platforms
**Why PMs care:** Understand user behavior and product performance
**Your use:** Define metrics, build dashboards, analyze trends

### 7. ML Platforms (e.g., Weights & Biases, MLflow)
**What:** Experiment tracking and model management
**Why PMs care:** See what DS team has tried, compare model versions
**Your use:** Review experiment history, understand model lineage

---

## 📋 Running Effective AI Team Meetings

### Weekly Planning Meeting

**Attendees:** PM, ML Engineer, Data Scientist, (Data Engineer as needed)

**Agenda:**
1. **Review last week** (10 min)
   - What shipped?
   - What experiments ran?
   - Results and learnings

2. **Discuss current sprint** (15 min)
   - Progress on active work
   - Blockers and help needed
   - Adjust plans if needed

3. **Plan next steps** (20 min)
   - Prioritize upcoming work
   - Assign ownership
   - Clarify requirements

4. **Technical deep dive** (15 min, rotating topic)
   - Team member shares approach/results
   - Discuss trade-offs and alternatives
   - Knowledge sharing

---

### Model Review Meeting

**When:** Before deploying new model or major changes

**Attendees:** PM, ML team, stakeholders

**Cover:**
1. **Business context**
   - Problem being solved
   - Expected impact

2. **Model approach**
   - High-level how it works
   - Data used
   - Key features

3. **Performance**
   - Offline metrics
   - A/B test results (if applicable)
   - Error analysis

4. **Trade-offs**
   - Accuracy vs. latency
   - Complexity vs. interpretability
   - Cost vs. performance

5. **Risks and mitigations**
   - What could go wrong?
   - Fallback plans
   - Monitoring strategy

6. **Go/No-Go decision**

---

## ✅ Practical Exercises

### Exercise 1: Role-Play Scenarios (30 min)

Practice these PM-DS conversations:

**Scenario A:**
Data scientist says model is "80% accurate." You need to understand what that means for the product.
- What questions do you ask?
- How do you connect to business impact?

**Scenario B:**
You want a feature shipped in 2 weeks. DS says they need 2 months.
- How do you understand the gap?
- What's negotiable vs. not?

**Scenario C:**
Model is performing poorly in production vs. offline testing.
- What do you ask the team?
- How do you decide: fix vs. rollback vs. continue?

---

### Exercise 2: Requirements Translation (45 min)

Translate these business requests into technical ML specs:

**1. "Make search better"**
Create:
- Clear problem statement
- Success metrics
- Technical requirements
- Data needed

**2. "Detect fake accounts"**
Define:
- What are you predicting?
- What data signals would you use?
- What's acceptable error rate?
- What happens with detected accounts?

---

### Exercise 3: Team Charter (30 min)

Create a working agreement for your AI team covering:
- Communication norms (meetings, updates, tools)
- Decision-making process
- Success metrics and reviews
- Handling disagreements
- Documentation standards

---

## 🤔 Critical Thinking Questions

1. **How do you balance DS desire to experiment with business need for shipping?**

2. **When should PM defer to DS expertise vs. push back?**

3. **How do you build trust with a technical team as a non-technical PM?**

4. **What decisions should PM own vs. DS vs. together?**

---

## 📖 Further Reading

- [ ] "The AI Product Manager's Handbook" by Irene Bratsis
- [ ] Articles on PM-DS collaboration from Airbnb, Netflix, Spotify
- [ ] "Working Backwards" (Amazon's approach to product development)

---

## 🎯 Key Takeaways

1. **Learn the language:** Understand enough ML to have informed conversations
2. **Define success together:** Co-create metrics with DS team
3. **Communicate bidirectionally:** Business to technical AND technical to business
4. **Respect expertise:** Trust DS on technical approach, share business context
5. **Document everything:** Shared understanding requires shared documentation

---

## 🔗 Next Session

[Session 08: AI Product Case Studies →](./08-ai-product-case-studies.md)

---

*Last Updated: 2025*
