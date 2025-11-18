# Week 8: AI Evaluation Framework

## 🎯 Week Overview

**Focus Areas:**
- Building comprehensive AI evaluation systems
- Quantitative evaluation (metrics, benchmarks, tests)
- Qualitative evaluation (human review, user feedback)
- Red-teaming and adversarial testing
- A/B testing for AI products
- Continuous monitoring and drift detection

**Deliverables:**
- Complete AI evaluation framework document
- Edge case catalog (50+ cases)
- Drift monitoring strategy
- Evaluation rubric with scoring

## 🧠 Deep Dive Resources

- [Evaluation Ops Deep Dive](./evaluation-ops-deep-dive.md) — ownership models, test suite architecture, eval boards, red teaming, and drift alerting templates.

---

## 📚 Learning Objectives

By the end of this week, you will:

1. ✅ Build comprehensive evaluation frameworks for AI products
2. ✅ Design quantitative and qualitative evaluation systems
3. ✅ Conduct red-teaming and adversarial testing
4. ✅ Set up A/B testing for AI features
5. ✅ Monitor for model drift and performance degradation

---

## 🗓️ Daily Breakdown

### **Day 1 (Monday): Evaluation Fundamentals**

**Morning Session (2 hours)**
- **Topic:** Why AI Evaluation is Different
- **Learning:**
  - Traditional software: Deterministic, testable
  - AI software: Probabilistic, hard to test comprehensively
  - **Evaluation layers:**
    1. Model evaluation (offline)
    2. System evaluation (integration)
    3. Product evaluation (user impact)
    4. Business evaluation (outcomes)
  - Evaluation throughout ML lifecycle:
    - Development: Benchmark datasets
    - Pre-launch: Human evaluation, A/B tests
    - Post-launch: Monitoring, continuous evaluation
- **Resources:**
  - 📚 [Chip Huyen - ML Systems Design](https://huyenchip.com/machine-learning-systems-design/) (Evaluation chapter) ⭐
  - 📖 [Google - Testing ML Systems](https://developers.google.com/machine-learning/testing-debugging) ⭐
  - 📖 [Evidently AI - ML Evaluation](https://www.evidentlyai.com/blog/ml-evaluation-guide)

**Evening Session (2 hours)**
- **Topic:** Offline vs. Online Evaluation
- **Learning:**
  - **Offline Evaluation:**
    - Test on historical data
    - Metrics: Accuracy, precision, recall, RMSE, etc.
    - Pros: Fast, reproducible, cheap
    - Cons: Doesn't capture real user behavior
  - **Online Evaluation:**
    - Test with real users
    - Metrics: CTR, engagement, satisfaction
    - Pros: Measures actual impact
    - Cons: Slow, expensive, risky
  - **When to use which:**
    - Offline first (filter obviously bad models)
    - Online second (measure real impact)
    - Both continuously (detect drift)

**Activity:**
- For your AI opportunity, list:
  - 5 offline metrics
  - 5 online metrics
  - How they connect

**Interview Prep:**
- "How do you evaluate an AI model?"
- "What metrics would you track for [AI product]?"

---

### **Day 2 (Tuesday): Quantitative Evaluation**

**Morning Session (2 hours)**
- **Topic:** Building Test Sets & Benchmarks
- **Learning:**
  - **Test set construction:**
    - Representative of real usage
    - Diverse edge cases
    - Regularly updated
    - Gold-standard labels
  - **Benchmark datasets:**
    - Industry standard datasets
    - Custom domain-specific tests
    - Regression test suites
  - **Evaluation metrics by task:**
    - Classification: Accuracy, precision, recall, F1, AUC
    - Regression: MAE, RMSE, R²
    - Ranking: NDCG, MAP, MRR
    - Generation: BLEU, ROUGE, perplexity, human eval
    - Retrieval: Precision@k, recall@k
- **Resources:**
  - 📖 [Papers with Code - Benchmarks](https://paperswithcode.com/datasets)
  - 📖 [Hugging Face - Evaluation](https://huggingface.co/docs/evaluate/)
  - 📖 [Google - Model Cards](https://modelcards.withgoogle.com/)

**Evening Session (2 hours)**
- **Topic:** Statistical Rigor
- **Learning:**
  - Statistical significance testing
  - Confidence intervals
  - Sample size requirements
  - Multiple comparison corrections
  - Avoiding p-hacking
- **Activity:**
  - Design test set for your AI opportunity
  - Define success thresholds
  - Calculate required sample sizes

---

### **Day 3 (Wednesday): Qualitative Evaluation & Human Review**

**Morning Session (2 hours)**
- **Topic:** Human Evaluation Frameworks
- **Learning:**
  - **Why human evaluation:**
    - Metrics don't capture everything
    - Quality, tone, appropriateness
    - Edge cases that numbers miss
  - **Human eval methods:**
    - Expert review (domain specialists)
    - Crowdsourced evaluation (diverse raters)
    - User feedback (thumbs up/down, comments)
  - **Evaluation rubrics:**
    - Relevance: Does it answer the question?
    - Accuracy: Is information correct?
    - Completeness: Is anything missing?
    - Coherence: Does it make sense?
    - Tone: Is it appropriate?
    - Safety: Any harmful content?
  - **Inter-rater reliability:** Agreement between evaluators
- **Resources:**
  - 📖 [Anthropic - Constitutional AI Evaluation](https://www.anthropic.com/index/constitutional-ai-harmlessness-from-ai-feedback)
  - 📖 [OpenAI - Model Evals](https://github.com/openai/evals)
  - 📖 [Scale AI - Human Evaluation](https://scale.com/blog/llm-evaluation-guide)

**Evening Session (2 hours)**
- **Activity:** Build Evaluation Rubric
- **Create detailed rubric for your AI opportunity:**
  - 5-10 evaluation criteria
  - 1-5 scale for each
  - Clear descriptions for each level
  - Examples of each score
  - Weighting (which criteria matter most)
- **Example criteria:**
  - Relevance (1=off-topic, 5=perfect match)
  - Accuracy (1=wrong, 5=completely correct)
  - Helpfulness (1=useless, 5=solves problem)
  - Safety (1=harmful, 5=perfectly safe)

**Deliverable:** Evaluation rubric

---

### **Day 4 (Thursday): Red-Teaming & Edge Cases**

**Morning Session (2 hours)**
- **Topic:** Red-Teaming AI Systems
- **Learning:**
  - **What is red-teaming:**
    - Adversarial testing
    - Finding ways to break the system
    - Security, safety, robustness testing
  - **Red-teaming categories:**
    - **Jailbreaking:** Bypassing safety guardrails
    - **Prompt injection:** Malicious instructions
    - **Data poisoning:** Corrupting training data
    - **Adversarial examples:** Inputs designed to fool model
    - **Edge cases:** Unusual but valid scenarios
    - **Bias testing:** Unfair or discriminatory outputs
  - **Red-teaming process:**
    1. Define threat model (what could go wrong?)
    2. Generate test cases
    3. Execute attacks
    4. Document findings
    5. Implement mitigations
    6. Re-test
- **Resources:**
  - 📖 [Anthropic - Red Teaming LLMs](https://www.anthropic.com/index/red-teaming-language-models)
  - 📖 [Microsoft - AI Red Team](https://www.microsoft.com/en-us/security/blog/2023/08/07/microsoft-ai-red-team-building-future-of-safer-ai/)
  - 📖 [OWASP - LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

**Evening Session (2 hours)**
- **Activity:** Build Edge Case Catalog
- **Brainstorm 50+ edge cases for your AI opportunity:**

**Categories to explore:**
  1. **Input edge cases:**
     - Empty input
     - Very long input
     - Special characters
     - Multiple languages
     - Ambiguous requests
  2. **Context edge cases:**
     - New user (no history)
     - Power user (extensive history)
     - Conflicting preferences
  3. **Domain edge cases:**
     - Rare scenarios
     - Expert-level queries
     - Nonsensical requests
  4. **Adversarial cases:**
     - Trying to bypass filters
     - Requesting harmful content
     - Prompt injection attempts
  5. **Ethical edge cases:**
     - Biased requests
     - Privacy violations
     - Copyright issues

**Deliverable Start:** Edge case catalog

---

### **Day 5 (Friday): A/B Testing & Continuous Monitoring**

**Morning Session (2 hours)**
- **Topic:** A/B Testing for AI Products
- **Learning:**
  - **Why A/B testing is tricky for AI:**
    - Models change continuously
    - User adaptation effects
    - Long-term vs. short-term metrics
    - Network effects
  - **A/B test design:**
    - Hypothesis formation
    - Metric selection (primary + guardrails)
    - Sample size calculation
    - Duration determination
    - Randomization strategy
  - **Special considerations for AI:**
    - Controlling for model version
    - Handling cold start
    - Measuring habituation
    - Interaction effects
- **Resources:**
  - 📖 [Netflix - A/B Testing](https://netflixtechblog.com/its-all-a-bout-testing-the-netflix-experimentation-platform-4e1ca458c15) ⭐
  - 📖 [Spotify - A/B Testing ML](https://engineering.atspotify.com/2020/02/measuring-the-quality-of-recommendations/)
  - 📖 [Optimizely - Experimentation](https://www.optimizely.com/optimization-glossary/ab-testing/)

**Evening Session (2 hours)**
- **Topic:** Drift Detection & Monitoring
- **Learning:**
  - **Types of drift:**
    - **Data drift:** Input distribution changes
    - **Concept drift:** Relationships change
    - **Prediction drift:** Output distribution changes
  - **Monitoring strategies:**
    - Statistical tests (KS test, chi-square, etc.)
    - Distribution comparisons
    - Performance tracking over time
    - Alerting thresholds
  - **When to retrain:**
    - Performance drops below threshold
    - Drift detected
    - New data available
    - Scheduled cadence
- **Resources:**
  - 📖 [Evidently AI - Drift Detection](https://www.evidentlyai.com/blog/ml-monitoring-data-drift) ⭐
  - 📖 [Chip Huyen - Monitoring ML](https://huyenchip.com/2022/02/07/data-distribution-shifts-and-monitoring.html) ⭐

**Activity:**
- Design drift monitoring strategy for your AI opportunity
- Define alerting thresholds
- Plan retraining cadence

---

### **Day 6-7 (Weekend): Complete Evaluation Framework**

**Saturday (3-4 hours)**
- **Activity:** Build Complete Evaluation Framework Document

**Structure:**
  1. **Evaluation Strategy Overview**
     - Goals and principles
     - Evaluation layers (model → system → product → business)

  2. **Offline Evaluation**
     - Test set construction
     - Metrics and benchmarks
     - Success thresholds
     - Regression testing

  3. **Online Evaluation**
     - A/B testing plan
     - Metrics (primary + guardrails)
     - Sample size and duration
     - Success criteria

  4. **Human Evaluation**
     - Evaluation rubric
     - Rater guidelines
     - Inter-rater reliability
     - Frequency and volume

  5. **Red-Teaming**
     - Threat model
     - Edge case catalog (50+ cases)
     - Testing process
     - Mitigation strategies

  6. **Continuous Monitoring**
     - Drift detection
     - Performance tracking
     - Alerting strategy
     - Retraining triggers

  7. **Evaluation Cadence**
     - Pre-launch: Comprehensive eval
     - Post-launch: Daily/weekly/monthly monitoring
     - Major updates: Full re-evaluation

**Sunday (2 hours)**
- **Activity:** Polish Deliverables
  - Complete edge case catalog (aim for 50-100)
  - Refine evaluation rubric
  - Add visual diagrams
  - Create executive summary

- **Reflection:**
  - What are the biggest risks for your AI opportunity?
  - How confident are you in catching problems?
  - What would you monitor most closely?
  - How would you know if your AI product is succeeding?

---

## 📝 Deliverables Checklist

### Required Deliverables:

- [ ] **AI Evaluation Framework** (`evaluation-framework.md`)
  - Offline evaluation plan
  - Online evaluation (A/B testing)
  - Human evaluation rubric
  - Red-teaming strategy
  - Continuous monitoring plan
  - Evaluation cadence

- [ ] **Edge Case Catalog** (`edge-cases.md`)
  - 50+ edge cases
  - Organized by category
  - Expected behavior for each
  - Priority/severity ratings

- [ ] **Evaluation Rubric** (`evaluation-rubric.md`)
  - 5-10 criteria
  - 1-5 scoring scale
  - Clear descriptions
  - Examples for each score
  - Weighting

- [ ] **Drift Monitoring Strategy** (`drift-monitoring.md`)
  - Metrics to track
  - Detection methods
  - Alerting thresholds
  - Retraining triggers

---

## 📖 Recommended Resources

### Evaluation Fundamentals:
- 📚 [Chip Huyen - ML Systems Design](https://huyenchip.com/machine-learning-systems-design/) ⭐
- 📖 [Google - Testing ML](https://developers.google.com/machine-learning/testing-debugging) ⭐
- 📖 [Evidently AI - ML Evaluation](https://www.evidentlyai.com/blog/ml-evaluation-guide)

### Human Evaluation:
- 📖 [Scale AI - LLM Evaluation](https://scale.com/blog/llm-evaluation-guide) ⭐
- 📖 [Anthropic - Constitutional AI](https://www.anthropic.com/index/constitutional-ai-harmlessness-from-ai-feedback)
- 📖 [OpenAI - Model Evals](https://github.com/openai/evals)

### Red-Teaming:
- 📖 [Anthropic - Red Teaming](https://www.anthropic.com/index/red-teaming-language-models) ⭐
- 📖 [Microsoft - AI Red Team](https://www.microsoft.com/en-us/security/blog/2023/08/07/microsoft-ai-red-team-building-future-of-safer-ai/)
- 📖 [OWASP - LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

### A/B Testing:
- 📖 [Netflix - Experimentation](https://netflixtechblog.com/its-all-a-bout-testing-the-netflix-experimentation-platform-4e1ca458c15) ⭐
- 📖 [Spotify - ML A/B Testing](https://engineering.atspotify.com/2020/02/measuring-the-quality-of-recommendations/)
- 📖 [Uber - Experimentation Platform](https://www.uber.com/blog/experimentation-platform/)

### Drift & Monitoring:
- 📖 [Evidently AI - Drift Detection](https://www.evidentlyai.com/blog/ml-monitoring-data-drift) ⭐
- 📖 [Chip Huyen - Monitoring](https://huyenchip.com/2022/02/07/data-distribution-shifts-and-monitoring.html) ⭐
- 📖 [WhyLabs - ML Monitoring](https://whylabs.ai/blog)

---

## 🎓 Key Concepts to Master

### Evaluation Types:
- **Offline:** Historical data, fast, doesn't capture real behavior
- **Online:** Real users, slow, expensive, measures actual impact
- **Human:** Captures quality, subjective, expensive
- **Automated:** Scalable, objective, may miss nuances

### Metrics:
- **Model Metrics:** Accuracy, precision, recall, F1, RMSE, BLEU, etc.
- **Product Metrics:** Engagement, satisfaction, task completion
- **Business Metrics:** Revenue, retention, cost
- **Guardrail Metrics:** Safety, fairness, cost, latency

### Red-Teaming:
- **Jailbreaking:** Bypassing safety
- **Prompt Injection:** Malicious instructions
- **Adversarial Examples:** Fooling the model
- **Edge Cases:** Unusual scenarios
- **Bias Testing:** Fairness evaluation

### Drift:
- **Data Drift:** Inputs change
- **Concept Drift:** Relationships change
- **Prediction Drift:** Outputs change
- **Detection:** Statistical tests, monitoring
- **Response:** Retrain, update features, adjust model

---

## 💡 Interview Questions You Should Be Able to Answer

1. "How do you evaluate an AI model?"
   - **Framework:** Offline (metrics) → Online (A/B test) → Continuous (monitoring)

2. "What metrics would you track for [AI product]?"
   - **Answer:** Model metrics + Product metrics + Business metrics + Guardrails

3. "How do you know when to retrain your model?"
   - **Answer:** Performance drops, drift detected, new data, scheduled cadence

4. "Walk me through your red-teaming process"
   - **Framework:** Threat model → Generate cases → Test → Document → Mitigate → Re-test

5. "How would you A/B test an AI recommendation system?"
   - **Answer:** Primary metric, guardrails, sample size, duration, control for model version

6. "Your model's accuracy is 95% but users are unhappy. Why?"
   - **Answer:** Accuracy ≠ quality. Look at: relevance, tone, latency, failure modes, user expectations

7. "How do you prevent AI failures in production?"
   - **Answer:** Comprehensive eval (offline + online + human), red-teaming, monitoring, fallbacks

---

## ⏭️ Coming Up in Week 9 (Phase 3 Begins!)

**Focus:** Choose Your AI Product Idea
- Select portfolio project based on all learnings
- Opportunity assessment
- Feasibility validation
- Scope definition
- **Deliverable:** Complete opportunity assessment

---

## 📊 Progress Tracking

| Day | Topic | Hours Completed | Status |
|-----|-------|----------------|--------|
| Mon | Evaluation Fundamentals | __ / 4 | ⬜ |
| Tue | Quantitative Evaluation | __ / 4 | ⬜ |
| Wed | Qualitative & Human Eval | __ / 4 | ⬜ |
| Thu | Red-Teaming & Edge Cases | __ / 4 | ⬜ |
| Fri | A/B Testing & Monitoring | __ / 4 | ⬜ |
| Sat-Sun | Complete Framework | __ / 6 | ⬜ |

**Total Target Hours:** 26 hours

---

**Week 8 Success Criteria:**
✅ You can design comprehensive evaluation systems
✅ You understand all evaluation types and when to use them
✅ You can red-team AI systems effectively
✅ You know how to A/B test AI products
✅ You can monitor and detect drift

**🎉 Phase 2 Complete! You now have ALL the AI PM skills. Phase 3: Build your portfolio! 🚀**
