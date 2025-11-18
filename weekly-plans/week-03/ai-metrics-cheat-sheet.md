# AI Metrics Cheat Sheet

**Week 3 Optional Deliverable**
**Quick Reference Guide for AI Product Metrics**

---

## 📊 Metrics Categories

All AI product metrics fall into these categories:

1. **Model Metrics** - How good is the AI?
2. **Product Metrics** - Are users getting value?
3. **Operational Metrics** - Can we serve it reliably?
4. **Business Metrics** - Is it driving business goals?
5. **Data Quality Metrics** - Is our data good?

---

## 1. Model Metrics (Offline Evaluation)

### Classification Metrics

| Metric | Formula | When to Use | Good Value |
|--------|---------|-------------|------------|
| **Accuracy** | (TP + TN) / Total | Balanced classes | >90% (context dependent) |
| **Precision** | TP / (TP + FP) | When false positives are costly | >80% |
| **Recall** | TP / (TP + FN) | When false negatives are costly | >80% |
| **F1 Score** | 2 × (Precision × Recall) / (Precision + Recall) | Balance precision & recall | >0.8 |
| **AUC-ROC** | Area under ROC curve | Overall model quality | >0.8 |
| **Confusion Matrix** | Visual grid of predictions | Understanding error types | Visual analysis |

**When to use which:**
- **Spam detection:** High precision (few false positives)
- **Disease screening:** High recall (catch all cases)
- **General classification:** F1 score (balanced)

---

### Regression Metrics

| Metric | Formula | When to Use | Good Value |
|--------|---------|-------------|------------|
| **MAE** | Mean Absolute Error | Easy interpretation | Context dependent |
| **RMSE** | Root Mean Squared Error | Penalize large errors | Context dependent |
| **R²** | Coefficient of determination | % variance explained | >0.7 |
| **MAPE** | Mean Absolute Percentage Error | Relative error | <10% |

**Use cases:**
- Price prediction, demand forecasting, time series

---

### Ranking/Recommendation Metrics

| Metric | When to Use | Good Value |
|--------|-------------|------------|
| **Precision@K** | Top K recommendations | >30% |
| **Recall@K** | Coverage in top K | >50% |
| **NDCG** | Normalized Discounted Cumulative Gain | >0.7 |
| **MAP** | Mean Average Precision | >0.5 |
| **MRR** | Mean Reciprocal Rank | >0.6 |
| **Hit Rate@K** | % of users with ≥1 relevant item in top K | >60% |

**Use cases:**
- Search results, product recommendations, content feeds

---

### Generation Metrics (Text/Image)

**Text Generation:**

| Metric | What It Measures | Limitations |
|--------|------------------|-------------|
| **BLEU** | N-gram overlap with reference | Doesn't capture meaning |
| **ROUGE** | Recall-oriented overlap | Good for summaries |
| **Perplexity** | Model confidence/uncertainty | Lower is better |
| **Human Eval** | Quality, coherence, factuality | Expensive, slow |

**Image Generation:**

| Metric | What It Measures |
|--------|------------------|
| **FID** | Frechet Inception Distance (quality) |
| **IS** | Inception Score (diversity + quality) |
| **Human Eval** | Aesthetic quality, prompt adherence |

**LLM-Specific:**

| Metric | What It Measures |
|--------|------------------|
| **Hallucination Rate** | % of factually incorrect statements |
| **Toxicity Score** | Harmful content percentage |
| **Helpfulness** | User rating of response quality |
| **Groundedness** | % of claims backed by sources |

---

## 2. Product Metrics (Online Evaluation)

### User Engagement

| Metric | Formula | Why It Matters | Target |
|--------|---------|----------------|--------|
| **Acceptance Rate** | (Accepted suggestions / Total suggestions) × 100 | AI usefulness | >50% |
| **CTR** | (Clicks / Impressions) × 100 | Recommendation relevance | >5% |
| **Time on Task** | Avg time to complete task | Efficiency gain | 50% reduction |
| **Task Completion** | (Completed / Started) × 100 | Success rate | >80% |
| **Interaction Depth** | Avg interactions per session | Engagement level | Context dependent |

### User Satisfaction

| Metric | How to Measure | Target |
|--------|----------------|--------|
| **Thumbs Up/Down** | Explicit feedback ratio | >80% positive |
| **NPS** | Net Promoter Score | >40 |
| **CSAT** | Customer Satisfaction Score | >4/5 |
| **Edit Rate** | % of AI outputs edited | <30% |
| **Regeneration Rate** | % of outputs regenerated | <20% |

### Retention & Habit

| Metric | Formula | Why It Matters | Target |
|--------|---------|----------------|--------|
| **D1/D7/D30 Retention** | % still active after X days | Stickiness | D7 >40% |
| **Weekly Active Users** | Users active in past 7 days | Growth | Increasing |
| **Usage Frequency** | Sessions per user per week | Habit formation | >3 |
| **Feature Adoption** | % of users using AI feature | Penetration | >60% |

---

## 3. Operational Metrics

### Performance

| Metric | Definition | Target | Impact |
|--------|------------|--------|--------|
| **Latency (p50)** | 50th percentile response time | <500ms | User experience |
| **Latency (p95)** | 95th percentile response time | <2s | Acceptable UX |
| **Latency (p99)** | 99th percentile response time | <5s | Edge cases |
| **Throughput** | Requests per second | Based on load | Scalability |
| **Error Rate** | % of failed requests | <1% | Reliability |
| **Uptime** | % availability | >99.9% | SLA compliance |

**Why percentiles matter:**
- p50 (median) = typical experience
- p95 = most users' worst case
- p99 = edge cases that still matter

### Cost

| Metric | Formula | Why It Matters | Target |
|--------|---------|----------------|--------|
| **Cost per Inference** | Total cost / # of inferences | Unit economics | Decreasing |
| **Cost per User** | Total cost / # of active users | Profitability | <Revenue per user |
| **Infrastructure Cost** | Monthly AI infrastructure spend | Budget | Within limits |
| **Cost per Token** | For LLMs: cost / # of tokens | Efficiency | Optimize over time |

**Cost Breakdown:**
- Model inference (API calls, GPU time)
- Data storage (vectors, embeddings, logs)
- Compute (training, fine-tuning)
- Monitoring and logging

---

## 4. Business Metrics

### Revenue Impact

| Metric | How AI Drives It | Measurement |
|--------|------------------|-------------|
| **Conversion Rate** | AI recommendations increase purchases | Before/after comparison |
| **ARPU** | Premium AI features drive upgrades | AI users vs. non-AI users |
| **LTV** | Better experience = longer retention | Cohort analysis |
| **Revenue per Session** | AI upsells, cross-sells | Track AI-attributed revenue |

### Efficiency Gains

| Metric | AI Impact | Measurement |
|--------|-----------|-------------|
| **Time Saved** | Automation, assistance | Hours saved × hourly rate |
| **Cost Reduction** | Process automation | Before/after operational cost |
| **Productivity** | Output per person | Tasks completed per hour |
| **Support Tickets** | AI handles common issues | Ticket volume reduction |

### Strategic

| Metric | What It Shows | How to Track |
|--------|---------------|--------------|
| **Competitive NPS** | AI as differentiator | Survey: "Why choose us?" |
| **Churn Prevention** | AI feature usage vs. churn | Cohort analysis |
| **Viral Coefficient** | AI drives sharing | Invites per user |
| **Market Share** | AI competitive advantage | Industry data |

---

## 5. Data Quality Metrics

### Data Health

| Metric | Definition | Target | Impact |
|--------|------------|--------|--------|
| **Completeness** | % of expected fields populated | >95% | Model accuracy |
| **Accuracy** | % of correct data points | >98% | Model quality |
| **Consistency** | % of data following schema | >99% | System reliability |
| **Freshness** | Time since last update | <24hrs | Relevance |
| **Coverage** | % of use cases represented | >90% | Model generalization |

### Drift Detection

| Metric | What It Detects | Alert Threshold |
|--------|-----------------|-----------------|
| **Data Drift** | Input distribution change | >10% KS statistic |
| **Concept Drift** | Relationship change | >15% accuracy drop |
| **Prediction Drift** | Output distribution change | >20% shift |
| **Feature Drift** | Individual feature change | >25% shift |

**When to retrain:**
- Performance drops >5%
- Drift metric exceeds threshold
- New data available (scheduled)
- Business context changes

---

## 🎯 Metrics Selection Framework

### Choose Metrics Based on ML Task:

**Classification:**
- Primary: F1 score
- Secondary: Precision, Recall (based on cost of errors)
- Business: Conversion rate, cost savings

**Recommendation:**
- Primary: Precision@K, NDCG
- Secondary: Diversity, coverage
- Business: Click-through rate, revenue

**Generation (Text/Image):**
- Primary: Human evaluation
- Secondary: BLEU/ROUGE (text), FID (image)
- Business: Acceptance rate, time saved

**Regression:**
- Primary: RMSE or MAE
- Secondary: R²
- Business: Accuracy of predictions → business impact

---

## 📐 Metrics Hierarchy Template

```
NORTH STAR METRIC
(e.g., "Time saved per user per week")
        |
        |
   _____↓______
  |            |
INPUT       INPUT
METRIC 1    METRIC 2
  |            |
 AI           Product
Metrics      Metrics
  |            |
  ↓            ↓
Model      Engagement
Quality    Metrics
```

**Always have:**
1. North Star (one metric)
2. Input metrics (2-3 that drive North Star)
3. Guardrail metrics (prevent gaming)
4. Counter metrics (watch for negative effects)

---

## ⚖️ Common Trade-offs

### Precision vs. Recall
- **High Precision:** Fewer false positives (e.g., spam filter)
- **High Recall:** Catch all cases (e.g., fraud detection)
- **Balance:** F1 score

### Latency vs. Quality
- **Fast model:** Lower accuracy, better UX
- **Slow model:** Higher accuracy, worse UX
- **Solution:** Hybrid (fast for most, slow for critical)

### Cost vs. Performance
- **Expensive model:** Best results, high cost
- **Cheap model:** Good enough, sustainable
- **Solution:** Tiered approach, optimize over time

### Exploration vs. Exploitation
- **Explore:** Try new recommendations (discovery)
- **Exploit:** Show safe bets (satisfaction)
- **Solution:** Multi-armed bandit, epsilon-greedy

---

## 🚨 Guardrail Metrics

**Always monitor these to prevent unintended consequences:**

| Guardrail | Why It Matters | Alert Threshold |
|-----------|----------------|-----------------|
| **Safety Incidents** | Harmful outputs | >0 |
| **Bias Metrics** | Fairness across groups | >10% disparity |
| **Churn Rate** | Long-term satisfaction | >5% monthly |
| **User Complaints** | Quality issues | >10/week |
| **Cost Overruns** | Budget sustainability | >20% over budget |

---

## 📊 Metrics Dashboard Structure

**Executive View:**
- North Star + trend
- 3 key metrics (green/yellow/red)

**Product View:**
- AARRR funnel
- User satisfaction
- Feature adoption

**ML View:**
- Model performance (accuracy, latency)
- Drift detection
- A/B test results

**Operations View:**
- System health (uptime, errors)
- Cost metrics
- Scaling metrics

---

## 🎓 Interview Quick Reference

**Q: "What metrics would you track for [AI product]?"**

**Answer Framework:**
1. **North Star:** [One metric that captures core value]
2. **Product Metrics:** Engagement, satisfaction, retention
3. **ML Metrics:** [Task-specific: accuracy/precision@k/BLEU/etc.]
4. **Operational:** Latency, cost, uptime
5. **Guardrails:** Safety, fairness, churn

**Example:**
"For an AI writing assistant:
- **North Star:** Time saved per user per week
- **Product:** Acceptance rate (>50%), satisfaction (>4/5)
- **ML:** Generation quality (human eval >80%), hallucination rate (<5%)
- **Operational:** Latency p95 <2s, cost per user <$0.50
- **Guardrails:** Safety incidents (0), churn (<5%/mo)"

---

## 🔍 Metric Selection Checklist

For each metric you choose, ask:

- [ ] **Measurable:** Can we actually track this?
- [ ] **Actionable:** Can we improve it?
- [ ] **Leading:** Does it predict future success?
- [ ] **Aligned:** Does it tie to business goals?
- [ ] **Simple:** Can everyone understand it?
- [ ] **Comparable:** Can we benchmark over time?

---

## 📈 Benchmarks (Industry Estimates)

**Engagement:**
- Good acceptance rate: >50%
- Great acceptance rate: >70%
- Excellent acceptance rate: >80%

**Quality:**
- Good satisfaction: >70%
- Great satisfaction: >80%
- Excellent satisfaction: >90%

**Performance:**
- Good latency: <1s
- Great latency: <500ms
- Excellent latency: <200ms

**Retention:**
- Good D7: >40%
- Great D7: >60%
- Excellent D7: >80%

*Note: These vary wildly by product category!*

---

## 💡 Key Principles

1. **Metrics ≠ Goals:** Don't optimize metrics; optimize outcomes
2. **Leading > Lagging:** Engagement today predicts retention tomorrow
3. **Layers Matter:** Model metrics ≠ product metrics ≠ business metrics
4. **Balance:** One metric is never enough; need hierarchy
5. **Context:** "Good" depends on use case, industry, maturity
6. **Guardrails:** Always have counter-metrics to prevent gaming

---

**Use this cheat sheet for:**
- ✅ Designing metrics for your portfolio project
- ✅ Interview prep (metrics questions)
- ✅ Quick reference during problem-solving
- ✅ Evaluating real AI products

**Print or save for quick access during interviews!** 📋
