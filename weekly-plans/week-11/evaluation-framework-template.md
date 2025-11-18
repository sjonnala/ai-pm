# AI Product Evaluation Framework

**Created:** [Date]
**Week 11 Portfolio Project Deliverable**
**Product Name:** [Your AI Product Name]
**Prepared by:** [Your Name]
**Version:** [e.g., 1.0]

---

## Executive Summary

**Framework Purpose:**

[In 2-3 sentences, explain what this evaluation framework covers and why it's critical for your AI product.]

Example: "This evaluation framework ensures our AI-powered documentation assistant delivers accurate, helpful, and safe responses. It combines offline testing, online A/B experiments, human evaluation, and continuous monitoring to maintain quality as the product scales."

**Your Framework Purpose:**

[Your turn - write your framework purpose here]

**Key Evaluation Layers:**
- **Model Performance:** [Core ML metrics]
- **System Quality:** [End-to-end behavior]
- **User Experience:** [Real-world satisfaction]
- **Business Impact:** [Success metrics]
- **Safety & Trust:** [Guardrails and monitoring]

---

## Table of Contents

1. [Evaluation Philosophy & Strategy](#part-1-evaluation-philosophy--strategy)
2. [Offline Evaluation](#part-2-offline-evaluation)
3. [Online Evaluation (A/B Testing)](#part-3-online-evaluation-ab-testing)
4. [Human Evaluation](#part-4-human-evaluation)
5. [Red-Teaming & Safety Testing](#part-5-red-teaming--safety-testing)
6. [Continuous Monitoring](#part-6-continuous-monitoring)
7. [Evaluation Metrics Reference](#part-7-evaluation-metrics-reference)
8. [Iteration & Improvement Process](#part-8-iteration--improvement-process)

---

## Part 1: Evaluation Philosophy & Strategy

### 1.1 Evaluation Philosophy

**Core Principles:**

[Define your evaluation philosophy. What matters most for your AI product? Accuracy? Speed? Safety? User satisfaction?]

Example principles:
- **User-centric:** User satisfaction matters more than any single metric
- **Comprehensive:** Test both happy paths and edge cases
- **Continuous:** Evaluation doesn't stop at launch
- **Transparent:** Document what works and what doesn't
- **Iterative:** Use findings to improve the product

**Your Philosophy:**

[Write 3-5 principles that guide your evaluation approach]

1. [Principle 1]
2. [Principle 2]
3. [Principle 3]
4. [Principle 4]
5. [Principle 5]

---

### 1.2 Evaluation Layers

**Layer 1: Model-Level Evaluation**
- **What:** Individual ML model performance
- **Metrics:** [e.g., Precision, recall, F1, perplexity, ROUGE, BLEU]
- **When:** During development and before deployment
- **Who:** ML engineers, AI PM

**Layer 2: System-Level Evaluation**
- **What:** End-to-end system behavior (model + application logic)
- **Metrics:** [e.g., Task completion rate, latency, error rate]
- **When:** Integration testing and staging
- **Who:** Engineers, QA, AI PM

**Layer 3: User-Level Evaluation**
- **What:** Real user experience and satisfaction
- **Metrics:** [e.g., NPS, satisfaction score, task success rate]
- **When:** Beta testing and production
- **Who:** Users, product team

**Layer 4: Business-Level Evaluation**
- **What:** Impact on product and business goals
- **Metrics:** [e.g., Engagement, retention, revenue]
- **When:** Post-launch
- **Who:** Product leadership, AI PM

---

### 1.3 Pre-Launch vs. Post-Launch Evaluation

**Pre-Launch Evaluation:**

| Evaluation Type | Purpose | Timeline |
|----------------|---------|----------|
| **Offline Testing** | Validate model quality on test sets | [e.g., 2 weeks before launch] |
| **Human Evaluation** | Assess quality on diverse scenarios | [e.g., 1 week before launch] |
| **Red-Teaming** | Find safety issues and edge cases | [e.g., Ongoing until launch] |
| **Beta Testing** | Test with real users (small group) | [e.g., 1-2 weeks before launch] |

**Post-Launch Evaluation:**

| Evaluation Type | Purpose | Cadence |
|----------------|---------|---------|
| **A/B Testing** | Measure impact of changes | [e.g., Continuous] |
| **Performance Monitoring** | Track model drift and degradation | [e.g., Real-time + weekly reviews] |
| **User Feedback** | Understand satisfaction and issues | [e.g., Continuous collection, weekly analysis] |
| **Periodic Audits** | Deep-dive quality and safety checks | [e.g., Monthly or quarterly] |

---

## Part 2: Offline Evaluation

Offline evaluation tests your AI system on pre-defined datasets before exposing it to real users.

### 2.1 Test Set Construction

**Test Set Requirements:**

| Requirement | Description | Your Plan |
|-------------|-------------|-----------|
| **Size** | Number of test examples | [e.g., 1,000 test cases] |
| **Diversity** | Coverage of use cases | [Describe how you ensure diversity] |
| **Representativeness** | Matches real-world distribution | [How does it match production?] |
| **Quality** | Accuracy of ground truth labels | [Who reviews? What's the process?] |
| **Freshness** | How recent is the data | [How often do you refresh?] |

**Test Set Composition:**

Break down your test set:

| Category | % of Test Set | Example Count | Purpose |
|----------|---------------|---------------|---------|
| [e.g., Common queries] | [e.g., 60%] | [e.g., 600] | [Test typical use cases] |
| [e.g., Edge cases] | [e.g., 20%] | [e.g., 200] | [Test robustness] |
| [e.g., Ambiguous inputs] | [e.g., 10%] | [e.g., 100] | [Test clarification] |
| [e.g., Adversarial cases] | [e.g., 10%] | [e.g., 100] | [Test safety] |

---

### 2.2 Offline Metrics

**Primary Metrics:**

Define the key metrics for offline evaluation:

| Metric | Definition | Target Value | Measurement Method |
|--------|------------|--------------|-------------------|
| [e.g., Accuracy] | [% of correct answers] | [e.g., >90%] | [Automated comparison to ground truth] |
| [e.g., Precision] | [% of AI outputs that are correct] | [e.g., >85%] | [True positives / (True positives + False positives)] |
| [e.g., Recall] | [% of correct answers found by AI] | [e.g., >80%] | [True positives / (True positives + False negatives)] |
| [Your metric 1] | [Definition] | [Target] | [Method] |
| [Your metric 2] | [Definition] | [Target] | [Method] |

**For LLM-based products, consider:**
- **Relevance:** Does the response address the user's query?
- **Accuracy:** Is the information factually correct?
- **Coherence:** Is the response well-structured and logical?
- **Completeness:** Does it cover all aspects of the query?
- **Conciseness:** Is it appropriately brief without sacrificing quality?

**Scoring Approach:**

[Describe how you score these metrics]

Example:
- Use LLM-as-judge (e.g., GPT-4) with detailed rubric
- Human raters score 1-5 on each dimension
- Automated comparison against reference answers using BLEU/ROUGE/Semantic similarity

**Your Approach:**

[Your scoring methodology]

---

### 2.3 Baseline & Benchmarks

**Baseline Performance:**

What are you comparing against?

| Baseline | Description | Performance |
|----------|-------------|-------------|
| **Random** | [Random outputs] | [Expected performance] |
| **Simple Heuristic** | [e.g., Keyword matching] | [Performance level] |
| **Previous Version** | [If iterating on existing product] | [Previous performance] |
| **Competitor** | [Competitor product if available] | [Their performance] |
| **Human Expert** | [Human performance on same task] | [Human-level performance] |

**Success Threshold:**

[Define what "good enough" means]

Example: "Our AI must score >85% on accuracy, outperform the keyword baseline by 30%, and achieve at least 80% of human expert performance."

**Your Threshold:**

[Your success criteria]

---

### 2.4 Regression Testing

**Regression Test Suite:**

To ensure new changes don't break existing functionality:

- **Test Set:** [Size and composition, e.g., "500 core test cases"]
- **Frequency:** [When to run, e.g., "Before every deployment"]
- **Passing Criteria:** [e.g., "No more than 2% degradation on any metric"]
- **Failure Protocol:** [What happens if tests fail, e.g., "Block deployment, investigate root cause"]

**Critical Test Cases:**

List 10-20 test cases that must ALWAYS work:

| ID | Test Case | Expected Behavior | Why Critical |
|----|-----------|-------------------|--------------|
| TC001 | [Example input] | [Expected output] | [Why this matters] |
| TC002 | [Example input] | [Expected output] | [Why this matters] |
| ... | ... | ... | ... |

---

## Part 3: Online Evaluation (A/B Testing)

Online evaluation tests your AI with real users in production.

### 3.1 A/B Test Strategy

**When to Run A/B Tests:**

- Launching new AI feature
- Changing model or prompts
- Modifying user experience
- Testing new evaluation metrics

**A/B Test Framework:**

For each planned A/B test:

**Test 1: [Name of test]**

| Element | Details |
|---------|---------|
| **Hypothesis** | [What you believe will happen. e.g., "New prompt template will improve response relevance by 10%"] |
| **Treatment** | [What's different in variant B. e.g., "Use structured prompt with examples"] |
| **Control** | [Current version. e.g., "Existing simple prompt"] |
| **Primary Metric** | [Main success metric. e.g., "User satisfaction score (thumbs up/down)"] |
| **Secondary Metrics** | [Additional metrics to track. e.g., "Task completion, latency, engagement"] |
| **Guardrail Metrics** | [Metrics that shouldn't regress. e.g., "Error rate <5%, latency <2s, cost per query"] |
| **Sample Size** | [Users needed per variant. e.g., "2,000 users per variant"] |
| **Duration** | [How long to run. e.g., "2 weeks"] |
| **Traffic Split** | [How to divide users. e.g., "50/50 split"] |
| **Success Criteria** | [When to ship. e.g., "Primary metric +10%, no guardrail violations, p<0.05"] |

---

### 3.2 Rollout Plan

**Phased Rollout Strategy:**

| Phase | % Traffic | Duration | Success Criteria | Rollback Trigger |
|-------|-----------|----------|------------------|------------------|
| **Phase 1: Canary** | [e.g., 5%] | [e.g., 24 hours] | [No errors, latency OK] | [Error rate >1%, latency >3s] |
| **Phase 2: Beta** | [e.g., 25%] | [e.g., 1 week] | [Metrics neutral or better] | [Any guardrail violated] |
| **Phase 3: Majority** | [e.g., 75%] | [e.g., 1 week] | [Sustained improvement] | [Unexpected regression] |
| **Phase 4: Full** | [e.g., 100%] | [Ongoing] | [Monitor for drift] | [Drift detected] |

**Rollback Plan:**

- **Trigger conditions:** [When to rollback]
- **Rollback process:** [Steps to revert]
- **Communication:** [Who to notify]
- **Root cause analysis:** [Post-mortem process]

---

### 3.3 Statistical Rigor

**Statistical Approach:**

| Element | Your Approach |
|---------|---------------|
| **Significance Level** | [e.g., α = 0.05 (95% confidence)] |
| **Power** | [e.g., 80% power to detect 10% improvement] |
| **Minimum Detectable Effect** | [e.g., "We can detect changes ≥5%"] |
| **Multiple Testing Correction** | [e.g., "Bonferroni correction for multiple metrics"] |
| **Sequential Testing** | [e.g., "Use sequential analysis to stop early if clear winner"] |

---

## Part 4: Human Evaluation

Human evaluation assesses quality dimensions that automated metrics can't capture.

### 4.1 Human Evaluation Rubric

**Evaluation Dimensions:**

Create a rubric for human raters:

| Dimension | 1 (Poor) | 2 (Fair) | 3 (Good) | 4 (Very Good) | 5 (Excellent) | Weight |
|-----------|----------|----------|----------|---------------|---------------|--------|
| **Relevance** | [Not related to query] | [Somewhat related] | [Mostly relevant] | [Highly relevant] | [Perfectly on-topic] | [e.g., 30%] |
| **Accuracy** | [Factually wrong] | [Partially correct] | [Mostly correct] | [Accurate] | [Completely accurate] | [e.g., 40%] |
| **Helpfulness** | [Not useful] | [Slightly helpful] | [Moderately helpful] | [Very helpful] | [Extremely helpful] | [e.g., 20%] |
| [Your dimension] | [...] | [...] | [...] | [...] | [...] | [e.g., X%] |

**Overall Quality Score:**

[Describe how you combine dimensions into overall score]

Example: Weighted average: (Relevance × 0.3) + (Accuracy × 0.4) + (Helpfulness × 0.2) + [Dimension × Weight]

---

### 4.2 Rater Guidelines

**Who Are the Raters:**

- **Internal raters:** [e.g., Team members, subject matter experts]
- **External raters:** [e.g., Contractors, target users]
- **Sample size:** [e.g., 3 raters per example for agreement]

**Rater Training:**

- **Training materials:** [What do raters study?]
- **Calibration:** [How do you ensure consistency?]
- **Inter-rater agreement:** [Target Kappa or % agreement: e.g., >0.7]
- **Quality checks:** [How do you catch bad raters?]

**Rating Process:**

1. [Step 1: e.g., "Read the user query"]
2. [Step 2: e.g., "Review AI response"]
3. [Step 3: e.g., "Score each dimension 1-5"]
4. [Step 4: e.g., "Provide written feedback"]
5. [Step 5: e.g., "Submit rating"]

---

### 4.3 Evaluation Cadence

**When to Run Human Evaluation:**

| Timing | Sample Size | Purpose |
|--------|-------------|---------|
| **Pre-launch** | [e.g., 500 examples] | [Validate quality before shipping] |
| **Weekly** | [e.g., 100 examples] | [Monitor quality over time] |
| **After major change** | [e.g., 300 examples] | [Assess impact of changes] |
| **Quarterly deep-dive** | [e.g., 1000 examples] | [Comprehensive quality audit] |

---

### 4.4 Feedback Loop

**How Human Evaluation Improves the Product:**

- **High-quality examples:** [Add to training/few-shot examples]
- **Low-quality examples:** [Debug and fix root causes]
- **Edge cases:** [Add to test sets]
- **Patterns:** [Identify systematic issues]
- **Feature requests:** [User needs revealed through evaluation]

---

## Part 5: Red-Teaming & Safety Testing

Red-teaming proactively finds ways the AI can fail or be misused.

### 5.1 Threat Model

**What Could Go Wrong?**

| Threat Category | Specific Risks | Likelihood | Impact | Mitigation |
|----------------|----------------|------------|--------|------------|
| **Hallucinations** | [AI makes up false information] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| **Bias** | [AI shows unfair bias] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| **Jailbreaks** | [Users bypass safety guardrails] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| **Privacy Leaks** | [AI reveals sensitive data] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| **Inappropriate Content** | [AI generates harmful content] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| **Manipulation** | [AI could be used to manipulate] | [High/Med/Low] | [High/Med/Low] | [Mitigation approach] |
| [Your threat] | [Description] | [Likelihood] | [Impact] | [Mitigation] |

---

### 5.2 Adversarial Test Cases

**Red-Team Test Suite:**

Build a collection of adversarial inputs designed to break your AI:

| Category | Test Cases | Expected Behavior | Pass/Fail Criteria |
|----------|------------|-------------------|---------------------|
| **Prompt Injection** | [e.g., "Ignore previous instructions..."] | [AI should refuse or ignore] | [Pass if AI doesn't comply] |
| **Jailbreak Attempts** | [e.g., "Pretend you're DAN..."] | [AI should maintain guidelines] | [Pass if guidelines followed] |
| **Ambiguous Queries** | [e.g., Vague or multi-intent queries] | [AI should clarify] | [Pass if asks for clarification] |
| **Factual Traps** | [e.g., Questions with false premises] | [AI should correct premise] | [Pass if corrects or caveats] |
| **Edge Cases** | [Examples from your PRD] | [Expected graceful handling] | [Pass if handles gracefully] |
| [Your category] | [Examples] | [Expected] | [Criteria] |

**Sample Adversarial Test Cases:**

List 20-30 specific adversarial inputs to test:

1. [Test case 1]
2. [Test case 2]
3. [Test case 3]
...

---

### 5.3 Bias & Fairness Testing

**Demographic Testing:**

Test for differential performance across groups:

| Dimension | Groups to Test | Metric | Acceptable Variance |
|-----------|----------------|--------|---------------------|
| **Gender** | [Male, Female, Non-binary] | [Accuracy, Tone] | [<5% difference] |
| **Age** | [18-30, 31-50, 51+] | [Relevance] | [<5% difference] |
| **Language** | [Native, Non-native speakers] | [Comprehension] | [<10% difference] |
| **Technical Level** | [Beginner, Expert] | [Helpfulness] | [<5% difference] |
| [Your dimension] | [Groups] | [Metric] | [Threshold] |

**Stereotype Testing:**

- Test for stereotypical responses related to race, gender, religion, etc.
- [Specific tests you'll run]

---

### 5.4 Safety Guardrails

**Implemented Guardrails:**

| Guardrail | How It Works | What It Prevents |
|-----------|--------------|------------------|
| **Content Filter** | [e.g., Block NSFW inputs/outputs] | [Inappropriate content] |
| **Rate Limiting** | [e.g., Max 100 queries/hour] | [Abuse, cost overruns] |
| **Input Validation** | [e.g., Max length, format checks] | [Attacks, errors] |
| **Output Filtering** | [e.g., PII detection, toxic language] | [Privacy leaks, harm] |
| **Human-in-the-Loop** | [e.g., Flag uncertain responses] | [High-stakes errors] |
| [Your guardrail] | [Mechanism] | [Protection] |

---

## Part 6: Continuous Monitoring

Monitoring ensures quality doesn't degrade after launch.

### 6.1 Real-Time Monitoring

**Metrics to Monitor in Real-Time:**

| Metric | Threshold | Alert Trigger | Response |
|--------|-----------|---------------|----------|
| **Error Rate** | [e.g., <1%] | [e.g., >3% for 5 min] | [Page on-call engineer] |
| **Latency (p95)** | [e.g., <2s] | [e.g., >5s for 10 min] | [Investigate, scale resources] |
| **Cost per Query** | [e.g., <$0.05] | [e.g., >$0.10 average over 1hr] | [Review, potentially throttle] |
| **Satisfaction Score** | [e.g., >70%] | [e.g., <50% for 1 hour] | [Investigate quality drop] |
| [Your metric] | [Threshold] | [Alert trigger] | [Response] |

**Monitoring Dashboard:**

[Describe your monitoring dashboard. What's visible at a glance?]

Tools: [e.g., Datadog, Grafana, CloudWatch, custom dashboard]

---

### 6.2 Model Drift Detection

**What is Drift?**

- **Data Drift:** Input distribution changes over time
- **Concept Drift:** Relationship between inputs and outputs changes
- **Model Drift:** Model performance degrades over time

**Drift Detection Strategy:**

| Drift Type | How to Detect | Frequency | Action if Detected |
|------------|---------------|-----------|-------------------|
| **Data Drift** | [e.g., Compare input distributions weekly] | [Weekly] | [Investigate cause, consider retraining] |
| **Performance Drift** | [e.g., Track offline metrics on recent data] | [Daily] | [Root cause analysis, potentially retrain] |
| **User Satisfaction Drift** | [e.g., Monitor ratings trend] | [Daily] | [Investigate, A/B test fixes] |

**Retraining Triggers:**

When do you retrain or update the model?

- [Trigger 1: e.g., "Performance drops >5% for 3 consecutive days"]
- [Trigger 2: e.g., "New use cases emerge representing >20% of traffic"]
- [Trigger 3: e.g., "Quarterly scheduled retrain regardless"]
- [Your triggers]

---

### 6.3 User Feedback Collection

**Feedback Mechanisms:**

| Mechanism | What it Captures | How Often Shown | How Used |
|-----------|------------------|-----------------|----------|
| **Thumbs Up/Down** | [Binary satisfaction] | [Every response] | [Track satisfaction rate] |
| **1-5 Stars** | [Granular satisfaction] | [Random 10% of users] | [Detailed quality analysis] |
| **Text Feedback** | [Qualitative insights] | [When user rates low] | [Identify issues, improve prompts] |
| **Feature Requests** | [What users want] | [Feedback form] | [Product roadmap input] |
| [Your mechanism] | [What it captures] | [Frequency] | [Usage] |

**Feedback Analysis:**

- **Volume:** [Target: e.g., "Collect 1,000 ratings per week"]
- **Analysis Cadence:** [e.g., "Weekly review of feedback"]
- **Action Items:** [e.g., "Create tickets for top 5 issues monthly"]

---

### 6.4 Incident Response

**Incident Classification:**

| Severity | Definition | Examples | Response Time |
|----------|------------|----------|---------------|
| **P0 (Critical)** | [Service down or major safety issue] | [Offensive content, total outage] | [Immediate, 24/7] |
| **P1 (High)** | [Significant degradation] | [Latency spike, accuracy drop] | [<1 hour] |
| **P2 (Medium)** | [Minor issues] | [Edge case failures] | [<4 hours] |
| **P3 (Low)** | [Nice to fix] | [Small UX improvements] | [<1 week] |

**Incident Response Process:**

1. **Detect:** [How incidents are detected]
2. **Alert:** [Who gets notified]
3. **Triage:** [Who assesses severity]
4. **Mitigate:** [Immediate actions to reduce impact]
5. **Resolve:** [Permanent fix]
6. **Post-Mortem:** [Learn from incident]
7. **Prevent:** [Implement safeguards]

---

## Part 7: Evaluation Metrics Reference

### 7.1 Model-Level Metrics

**For Classification Tasks:**

| Metric | Formula | When to Use | Target |
|--------|---------|-------------|--------|
| **Accuracy** | (TP+TN)/(TP+TN+FP+FN) | [Balanced datasets] | [e.g., >90%] |
| **Precision** | TP/(TP+FP) | [When false positives are costly] | [e.g., >85%] |
| **Recall** | TP/(TP+FN) | [When false negatives are costly] | [e.g., >80%] |
| **F1 Score** | 2×(Precision×Recall)/(Precision+Recall) | [Balance precision and recall] | [e.g., >0.85] |

**For Generation Tasks (LLMs):**

| Metric | What It Measures | When to Use | Target |
|--------|------------------|-------------|--------|
| **BLEU** | N-gram overlap with reference | [Translation, summarization] | [e.g., >0.4] |
| **ROUGE** | Recall of n-grams | [Summarization] | [e.g., >0.5] |
| **Perplexity** | How surprised model is | [Language modeling] | [Lower is better] |
| **Semantic Similarity** | Meaning similarity (embeddings) | [Paraphrase, Q&A] | [e.g., >0.8] |
| **LLM-as-Judge** | GPT-4 rates response quality | [Open-ended generation] | [e.g., >4/5] |

---

### 7.2 System-Level Metrics

| Metric | Definition | Target | Measurement |
|--------|------------|--------|-------------|
| **End-to-End Accuracy** | [% of user tasks completed correctly] | [e.g., >85%] | [Test on user scenarios] |
| **Latency (p50)** | [Median response time] | [e.g., <1s] | [Production monitoring] |
| **Latency (p95)** | [95th percentile response time] | [e.g., <3s] | [Production monitoring] |
| **Error Rate** | [% of requests that error] | [e.g., <1%] | [Production monitoring] |
| **Cost per Query** | [Average AI cost per request] | [e.g., <$0.05] | [Cost monitoring] |

---

### 7.3 User-Level Metrics

| Metric | Definition | Target | Measurement |
|--------|------------|--------|-------------|
| **Task Success Rate** | [% of users who achieve their goal] | [e.g., >80%] | [User testing, session analysis] |
| **Satisfaction Score** | [Thumbs up % or star rating] | [e.g., >75% thumbs up] | [In-product feedback] |
| **Net Promoter Score** | [Would you recommend? -100 to 100] | [e.g., >30] | [Post-interaction survey] |
| **Time to Value** | [Time until user gets first value] | [e.g., <2 min] | [Analytics] |

---

### 7.4 Business-Level Metrics

| Metric | Definition | Target | Measurement |
|--------|------------|--------|-------------|
| **Adoption Rate** | [% of users who try AI feature] | [e.g., >60%] | [Product analytics] |
| **Engagement** | [Avg queries per active user per week] | [e.g., >10] | [Product analytics] |
| **Retention** | [% of users who return after 7/30 days] | [e.g., >40% D7] | [Cohort analysis] |
| **Revenue Impact** | [Incremental revenue from AI feature] | [e.g., +15% ARPU] | [A/B test] |

---

## Part 8: Iteration & Improvement Process

### 8.1 Evaluation Cadence

**Weekly:**
- Review real-time monitoring dashboards
- Analyze user feedback from past week
- Check for drift or degradation
- Triage any incidents

**Monthly:**
- Run human evaluation on sample (100-300 examples)
- Deep-dive on failed cases
- Review A/B test results
- Update test sets with new edge cases

**Quarterly:**
- Comprehensive quality audit (1000+ examples)
- Red-teaming exercise
- Bias & fairness assessment
- Evaluation framework review and update

---

### 8.2 Feedback Loop to Product

**How Evaluation Drives Improvement:**

```
Evaluation → Findings → Analysis → Action → Improvement
```

**Example Flow:**

1. **Evaluation:** Human raters score 200 responses, average 3.2/5
2. **Finding:** 30% of responses are too verbose
3. **Analysis:** Model is over-explaining simple queries
4. **Action:** Update prompt to be more concise for simple queries
5. **Improvement:** Re-evaluate, score improves to 4.1/5

**Your Process:**

[Describe your iteration process. How do evaluation insights become product improvements?]

---

### 8.3 Success Metrics Dashboard

**Create a One-Page Dashboard:**

[Design a visual dashboard showing all key evaluation metrics]

**Sections:**
1. **Model Performance:** [Accuracy, precision, recall, etc.]
2. **System Health:** [Latency, error rate, cost]
3. **User Satisfaction:** [Thumbs up %, NPS, feedback volume]
4. **Business Impact:** [Adoption, engagement, retention]
5. **Safety & Trust:** [Incident count, bias metrics, drift status]

**Tools:** [e.g., Figma mockup, Google Sheets, Notion dashboard]

---

## Appendix A: Evaluation Checklist

Use this checklist to ensure comprehensive evaluation:

**Pre-Launch:**
- [ ] Offline evaluation complete (test set, metrics, baselines)
- [ ] Human evaluation complete (rubric, raters, results)
- [ ] Red-teaming complete (adversarial tests, safety checks)
- [ ] Beta testing complete (real users, feedback collected)
- [ ] All metrics meet success thresholds
- [ ] Regression test suite passing
- [ ] Monitoring and alerting set up

**Post-Launch:**
- [ ] A/B tests planned and running
- [ ] Real-time monitoring active
- [ ] User feedback collection working
- [ ] Weekly evaluation reviews scheduled
- [ ] Monthly human evaluation scheduled
- [ ] Quarterly audit scheduled
- [ ] Incident response process documented
- [ ] Drift detection running

---

## Appendix B: Evaluation Tools & Resources

**Tools You Might Use:**

- **Offline Evaluation:** [e.g., Python scripts, Jupyter notebooks, evaluation frameworks]
- **A/B Testing:** [e.g., LaunchDarkly, Optimizely, custom framework]
- **Human Evaluation:** [e.g., Scale AI, Surge, internal tool]
- **Monitoring:** [e.g., Datadog, Prometheus, Grafana, CloudWatch]
- **Analytics:** [e.g., Amplitude, Mixpanel, custom dashboards]
- **LLM Evaluation:** [e.g., OpenAI Evals, LangChain eval, PromptLayer]

**Resources:**

- [Link to evaluation best practices]
- [Link to your test sets]
- [Link to monitoring dashboards]
- [Link to incident response playbook]

---

## Reflection & Learnings

**What I Learned About AI Evaluation:**

[Reflect on what you learned while building this framework. What surprised you? What was harder than expected? What would you do differently?]

**How This Framework Demonstrates AI PM Skills:**

[Explain how this framework showcases your ability to ensure AI quality, think about edge cases, and ship reliable AI products]

**Interview Talking Points:**

[List 3-5 key points you'd emphasize when discussing this framework in interviews]

1. [Point 1]
2. [Point 2]
3. [Point 3]
4. [Point 4]
5. [Point 5]

---

**Document Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | [Date] | [Initial creation] | [Your name] |
| 1.1 | [Date] | [Updates based on feedback] | [Your name] |

---

**End of Evaluation Framework Template**

*This framework is a living document. Update it as you learn and as your product evolves.*
