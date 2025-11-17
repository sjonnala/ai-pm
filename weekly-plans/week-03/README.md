# Week 3: Metrics + AI in Companies

## 🎯 Week Overview

**Focus Areas:**
- Core PM metrics (AARRR, retention, engagement)
- AI-specific metrics (latency, cost, quality, drift)
- Model evaluation and monitoring
- Real-world AI case studies from top companies

**Deliverables:**
- Metrics dashboard template for AI products
- 2 in-depth AI case study analyses
- AI metrics cheat sheet

---

## 📚 Learning Objectives

By the end of this week, you will:

1. ✅ Master core PM metrics frameworks (AARRR, HEART, retention cohorts)
2. ✅ Understand AI-specific metrics (latency, cost per inference, model accuracy, drift)
3. ✅ Know how to balance ML metrics vs. product metrics
4. ✅ Build comprehensive metrics dashboards for AI products
5. ✅ Analyze real-world AI product case studies

---

## 🗓️ Daily Breakdown

### **Day 1 (Monday): Core PM Metrics Foundations**

**Morning Session (2 hours)**
- **Topic:** AARRR (Pirate Metrics) Framework
- **Learning:**
  - Acquisition: How users find you
  - Activation: First value experience
  - Retention: Users coming back
  - Revenue: Monetization
  - Referral: Viral growth
- **Resources:**
  - 📚 [Dave McClure - Pirate Metrics](https://www.youtube.com/watch?v=irjgfW0BIrw) ⭐
  - 📖 [Reforge - Retention Guide](https://www.reforge.com/blog/retention)
  - 📖 [Amplitude - North Star Playbook](https://amplitude.com/north-star)

**Evening Session (2 hours)**
- **Topic:** Retention & Engagement Metrics
- **Learning:**
  - Cohort analysis
  - DAU/MAU ratio
  - Stickiness metrics
  - L7/L30 (Lending Club metric)
  - Power user curves
- **Activity:**
  - Pick 3 products (one AI product)
  - Identify their likely AARRR metrics
  - Sketch retention cohort for AI product
- **Resources:**
  - 📖 [Lenny's Newsletter - Retention](https://www.lennysnewsletter.com/p/what-is-good-retention-issue-29)
  - 📖 [Sequoia - Data-Driven Approach](https://www.sequoiacap.com/article/data-driven-pitfalls/)

**Interview Prep:**
- "How do you measure product success?"
- "What metrics would you track for [product]?"

---

### **Day 2 (Tuesday): AI-Specific Metrics - Part 1**

**Morning Session (2 hours)**
- **Topic:** Model Performance Metrics
- **Learning:**
  - Accuracy, Precision, Recall, F1-Score
  - Confusion matrices
  - ROC curves and AUC
  - Mean Absolute Error (MAE), RMSE
  - When to use which metric
- **Resources:**
  - 📚 [Google ML Crash Course - Classification Metrics](https://developers.google.com/machine-learning/crash-course/classification)
  - 📖 [Towards Data Science - Model Metrics](https://towardsdatascience.com/the-5-classification-evaluation-metrics-you-must-know-aa97784ff226)
  - 🎥 [StatQuest - ROC and AUC](https://www.youtube.com/watch?v=4jRBRDbJemM)

**Evening Session (2 hours)**
- **Topic:** Quality & Relevance Metrics for AI Products
- **Learning:**
  - Task-specific metrics (BLEU for translation, etc.)
  - Relevance scoring
  - User satisfaction metrics
  - Ground truth evaluation
  - Human evaluation frameworks
- **Resources:**
  - 📖 [Eugene Yan - Patterns for ML Systems](https://eugeneyan.com/writing/patterns-for-personalization/)
  - 📖 [Spotify - Bandits for Recommendations](https://engineering.atspotify.com/2023/05/introducing-the-spotify-bandits-library/)

**Activity:**
- For your Week 1 AI opportunity, identify:
  - Appropriate model performance metrics
  - Product success metrics
  - How they connect

**Interview Prep:**
- "How do you evaluate an ML model?"
- "What's the difference between accuracy and precision?"

---

### **Day 3 (Wednesday): AI-Specific Metrics - Part 2**

**Morning Session (2 hours)**
- **Topic:** Operational AI Metrics
- **Learning:**
  - **Latency:** p50, p95, p99 response times
  - **Cost:** Cost per inference, compute costs
  - **Throughput:** Requests per second
  - **Availability:** Uptime, error rates
  - Latency-quality trade-offs
- **Resources:**
  - 📖 [AWS ML Lens - Operational Metrics](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/)
  - 📖 [Google Cloud - AI Monitoring](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning)
  - 📖 [Chip Huyen - ML Monitoring](https://huyenchip.com/2022/02/07/data-distribution-shifts-and-monitoring.html) ⭐

**Evening Session (2 hours)**
- **Topic:** Model Drift & Data Quality
- **Learning:**
  - **Data Drift:** Input distribution changes
  - **Concept Drift:** Relationship changes
  - **Prediction Drift:** Output distribution changes
  - Detecting drift
  - Retraining triggers
- **Resources:**
  - 📚 [Evidently AI - ML Monitoring](https://www.evidentlyai.com/blog/ml-monitoring-101)
  - 📖 [Neptune.ai - Model Drift](https://neptune.ai/blog/concept-drift-best-practices)
  - 📖 [Uber - ML Observability](https://www.uber.com/blog/monitoring-machine-learning-models/)

**Activity:**
- Create "AI Metrics Cheat Sheet"
- Map metrics to ML lifecycle phases

**Interview Prep:**
- "How do you monitor ML models in production?"
- "What would you do if model performance degrades?"

---

### **Day 4 (Thursday): Metrics Dashboards & Trade-offs**

**Morning Session (2 hours)**
- **Topic:** Building Metrics Dashboards for AI Products
- **Learning:**
  - Hierarchy of metrics (North Star → Input → Counter)
  - Leading vs. lagging indicators
  - Dashboard design principles
  - Choosing the right visualization
- **Resources:**
  - 📖 [Amplitude - Metrics Hierarchy](https://amplitude.com/blog/product-metrics)
  - 📖 [Mixpanel - Dashboard Best Practices](https://mixpanel.com/blog/product-analytics-dashboards/)
  - 📚 [Lean Analytics](https://leananalyticsbook.com/) - Key chapters

**Evening Session (2 hours)**
- **Topic:** Balancing Competing Metrics
- **Learning:**
  - Precision vs. Recall trade-offs
  - Latency vs. Quality
  - Cost vs. Performance
  - Short-term vs. Long-term metrics
  - Guard rail metrics
- **Activity:**
  - Design metrics dashboard for your AI opportunity
  - Include: North Star, Input Metrics, ML Metrics, Guardrails
- **Resources:**
  - 📖 [Spotify - Metrics Trade-offs](https://engineering.atspotify.com/2020/02/measuring-the-quality-of-recommendations/)
  - 📖 [Netflix - Experimentation](https://netflixtechblog.com/its-all-a-bout-testing-the-netflix-experimentation-platform-4e1ca458c15)

**Deliverable:** Start metrics dashboard template

**Interview Prep:**
- "How would you measure success for an AI recommendation system?"
- "What trade-offs would you consider?"

---

### **Day 5 (Friday): Real-World AI Case Studies**

**Morning Session (2 hours)**
- **Topic:** Case Study Deep Dive #1
- **Select one major AI product:**
  - **Option A:** Netflix Recommendations
  - **Option B:** Spotify Discover Weekly
  - **Option C:** YouTube Algorithm
  - **Option D:** LinkedIn Feed Ranking

**Analysis Framework:**
1. **Product Overview:** What problem does it solve?
2. **ML Approach:** What type of ML? (collaborative filtering, deep learning, etc.)
3. **Metrics:** What do they optimize for?
4. **Trade-offs:** What did they sacrifice?
5. **Evolution:** How did it improve over time?
6. **Lessons:** What can we learn?

- **Resources:**
  - 📖 [Netflix Tech Blog](https://netflixtechblog.com/) - Recommendation articles
  - 📖 [Spotify Engineering](https://engineering.atspotify.com/) - Search "discover weekly"
  - 📖 [YouTube Recommendation Paper](https://research.google/pubs/pub45530/)
  - 📖 [LinkedIn ML Blog](https://engineering.linkedin.com/blog/topic/machine-learning)

**Evening Session (2 hours)**
- **Topic:** Case Study Deep Dive #2
- **Select one emerging AI product:**
  - **Option A:** Notion AI
  - **Option B:** GitHub Copilot
  - **Option C:** Midjourney
  - **Option D:** Perplexity AI

**Analysis Framework:** (same as above)

- **Resources:**
  - 📖 [GitHub Copilot Research](https://github.blog/2022-09-07-research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)
  - 📖 [OpenAI - GPT Best Practices](https://platform.openai.com/docs/guides/gpt-best-practices)
  - 📖 [Lenny's Podcast - AI PM Interviews](https://www.lennyspodcast.com/)

**Deliverable:** Complete 2 case study analyses

---

### **Day 6-7 (Weekend): Metrics Dashboard & Case Study Polish**

**Saturday (3 hours)**
- **Activity:** Complete Metrics Dashboard Template
- **Include:**
  - North Star Metric
  - AARRR breakdown
  - ML-specific metrics (accuracy, latency, cost, drift)
  - Input metrics (what drives North Star)
  - Counter metrics (what could go wrong)
  - Guardrail metrics
  - Cohort retention template
- **Make it reusable** for any AI product

**Sunday (2 hours)**
- **Activity:** Polish & Connect Learnings
  - Refine both case study analyses
  - Extract patterns: What do successful AI products have in common?
  - Create "AI Product Success Patterns" 1-pager
  - Add metrics examples to your interview prep doc
- **Reflection:**
  - What surprised you about these case studies?
  - How would you apply these insights to your opportunity?
  - What metrics would be most critical for your portfolio project?

---

## 📝 Deliverables Checklist

### Required Deliverables:

- [ ] **Metrics Dashboard Template** (`metrics-dashboard.md`)
  - North Star Metric definition
  - AARRR framework applied to AI product
  - ML-specific metrics (model, operational, drift)
  - Metrics hierarchy diagram
  - Cohort retention template
  - Trade-offs documentation

- [ ] **AI Case Study #1** (`case-study-1.md`)
  - Product overview
  - ML approach
  - Key metrics
  - Trade-offs made
  - Evolution over time
  - Lessons learned

- [ ] **AI Case Study #2** (`case-study-2.md`)
  - Same structure as above

### Optional Deliverables:

- [ ] **AI Metrics Cheat Sheet** (`ai-metrics-cheat-sheet.md`)
  - Quick reference for all AI metrics
  - When to use which metric
  - Typical ranges/benchmarks

- [ ] **AI Product Success Patterns** (`success-patterns.md`)
  - Common patterns from case studies
  - Anti-patterns to avoid

---

## 📖 Recommended Resources (Comprehensive List)

### Core PM Metrics:
- **Books:**
  - 📚 *Lean Analytics* - Alistair Croll & Benjamin Yoskovitz ⭐ MUST READ
  - 📚 *Measure What Matters* - John Doerr (OKRs)

- **Articles & Guides:**
  - [Lenny's Newsletter - Metrics Collection](https://www.lennysnewsletter.com/)
  - [Reforge - Retention Engagement](https://www.reforge.com/blog)
  - [Amplitude - Product Metrics](https://amplitude.com/blog)
  - [Sequoia - Metrics Guide](https://www.sequoiacap.com/article/business-metrics/)

- **Tools:**
  - [Mixpanel](https://mixpanel.com/)
  - [Amplitude](https://amplitude.com/)
  - [Segment](https://segment.com/)

### AI Metrics:
- **Deep Dives:**
  - 📚 *Designing Machine Learning Systems* - Chip Huyen (Chapter on Monitoring) ⭐
  - 📖 [Chip Huyen - ML Monitoring](https://huyenchip.com/2022/02/07/data-distribution-shifts-and-monitoring.html) ⭐
  - 📖 [Eugene Yan - Applied ML Patterns](https://applyingml.com/) ⭐
  - 📖 [Google - ML Rules #3-7](https://developers.google.com/machine-learning/guides/rules-of-ml) (First wave metrics)

- **Company Engineering Blogs:**
  - [Netflix Tech Blog](https://netflixtechblog.com/) ⭐
  - [Spotify Engineering](https://engineering.atspotify.com/) ⭐
  - [Uber Engineering](https://www.uber.com/blog/engineering/)
  - [Meta AI](https://ai.meta.com/blog/)
  - [LinkedIn Engineering](https://engineering.linkedin.com/blog/topic/machine-learning)
  - [Airbnb Tech](https://medium.com/airbnb-engineering)

- **ML Monitoring Tools:**
  - [Evidently AI](https://www.evidentlyai.com/)
  - [WhyLabs](https://whylabs.ai/)
  - [Arize AI](https://arize.com/)

### Case Study Sources:
- 📖 [Lenny's Podcast](https://www.lennyspodcast.com/) - PM interviews
- 📖 [a16z Podcast](https://a16z.com/podcasts/) - AI deep dives
- 📖 [High Growth Handbook](https://growth.eladgil.com/)
- 📖 [Product Coalition](https://productcoalition.com/)

---

## 🎓 Key Concepts to Master

### Core PM Metrics:
- **North Star Metric:** Single metric capturing core value
- **AARRR:** Acquisition → Activation → Retention → Revenue → Referral
- **Cohort Analysis:** Tracking groups of users over time
- **Retention Curves:** Flattening = product-market fit
- **DAU/MAU:** Stickiness ratio (good > 20%)
- **Counter Metrics:** Metrics that prevent gaming the system

### AI Metrics:
- **Offline Metrics:** Evaluated on historical data (accuracy, RMSE, etc.)
- **Online Metrics:** Evaluated with real users (CTR, engagement, etc.)
- **Model Metrics:** How good is the model? (precision, recall, F1)
- **Product Metrics:** Is it driving business outcomes?
- **Operational Metrics:** Can we serve it at scale? (latency, cost)
- **Data Quality:** Is our input data good? (completeness, freshness)
- **Drift:** Is the world changing? (distribution shifts)

### Metric Trade-offs:
- **Precision vs. Recall:** Strictness vs. coverage
- **Latency vs. Quality:** Speed vs. accuracy
- **Cost vs. Performance:** Budget vs. capability
- **Short-term vs. Long-term:** Engagement now vs. value later
- **Local vs. Global:** Individual optimization vs. ecosystem health

---

## 💡 Interview Questions You Should Be Able to Answer

### Metrics Questions:
1. "How would you measure success for [AI product]?"
   - **Framework:** North Star → Input metrics → ML metrics → Guardrails

2. "What's the difference between offline and online metrics?"
   - **Answer:** Offline = historical data evaluation, Online = real user impact

3. "How do you know if your recommendation system is working?"
   - **Answer:** Layered approach - ML metrics (precision@k) + Product metrics (engagement, retention) + Business metrics (revenue)

4. "Your model has 95% accuracy. Is that good?"
   - **Answer:** Depends on context! Baseline? Class imbalance? What's the cost of errors?

5. "You notice model performance degrading. What do you do?"
   - **Framework:** Investigate (drift? data quality? model issue?) → Diagnose → Fix (retrain? update features? change model?)

6. "How would you trade off latency vs. accuracy?"
   - **Answer:** Understand user needs + use case criticality + competitive landscape + cost. May use hybrid approach (fast simple model → slow complex model for edge cases)

### Case Study Questions:
7. "Tell me about an AI product you admire. Why?"
   - **Use your case studies!**

8. "How would you improve YouTube recommendations?"
   - **Framework:** Current state → Opportunities → Solutions → Metrics → Trade-offs

9. "What's an example of an AI product that failed? Why?"
   - **Have examples ready from research**

---

## 🎯 Tips for Success

1. **Think in systems** - Metrics don't exist in isolation
2. **Balance is key** - Optimize for North Star, monitor guardrails
3. **Learn from best** - Study how top companies measure AI products
4. **Be specific** - "Engagement" is vague; "DAU/MAU ratio" is precise
5. **Connect ML to business** - Always link model metrics to product outcomes

---

## 🔗 Connections to Interview Success

This week builds critical skills for:
- **Metrics Interviews:** Defining and tracking product success
- **Execution Interviews:** Making data-driven decisions
- **Product Sense:** Understanding what to measure
- **Technical Collaboration:** Speaking ML engineer language

**Common Interview Scenario:**
"We're building an AI writing assistant. How would you measure success?"

**Your Approach (using this week's learning):**
1. **North Star:** Time saved on writing tasks (leading to more content created)
2. **AARRR Breakdown:**
   - Acquisition: # of sign-ups
   - Activation: Used AI suggestion ≥ 3 times in first session
   - Retention: Used AI ≥ 2 days in first week
   - Revenue: Conversion to paid
   - Referral: Invite rate
3. **ML Metrics:**
   - Acceptance rate (% of AI suggestions accepted)
   - Precision@k for suggestions
   - Latency (< 500ms for good UX)
4. **Product Metrics:**
   - Content completion rate (% of started docs finished)
   - Words per session (productivity)
   - User satisfaction score
5. **Guardrails:**
   - Hallucination rate (quality control)
   - Cost per user (sustainability)
   - Churn rate (are we adding value?)
6. **Trade-offs:**
   - Fast suggestions vs. highest quality
   - Proactive vs. on-demand
   - Cost vs. model sophistication

---

## ⏭️ Coming Up in Week 4

**Focus:** PM Roadmaps + AI Transformation
- Building 6-month AI product roadmaps
- Prioritization frameworks (RICE, value vs. effort)
- AI transformation playbook
- **Deliverable:** 6-month roadmap + AI transformation doc

---

## 📊 Progress Tracking

| Day | Topic | Hours Completed | Status |
|-----|-------|----------------|--------|
| Mon | Core PM Metrics | __ / 4 | ⬜ |
| Tue | AI Metrics - Part 1 | __ / 4 | ⬜ |
| Wed | AI Metrics - Part 2 | __ / 4 | ⬜ |
| Thu | Dashboards & Trade-offs | __ / 4 | ⬜ |
| Fri | Case Studies | __ / 4 | ⬜ |
| Sat-Sun | Dashboard & Polish | __ / 5 | ⬜ |

**Total Target Hours:** 25 hours
**Actual Hours:** ___ hours

---

**Week 3 Success Criteria:**
✅ You can define metrics for any AI product
✅ You understand the full metrics stack (model → product → business)
✅ You can analyze trade-offs between competing metrics
✅ You have 2 detailed case studies to discuss in interviews
✅ You can explain how to monitor ML models in production

Master metrics, master PM! 📊🚀
