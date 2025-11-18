# AI Evaluation Framework

**Created:** [Date]
**Week 8 Deliverable**
**Product:** [Your AI Product Name]
**Version:** [e.g., 1.0]
**Owner:** [Your Name]

---

## Executive Summary

**Product:** [Name of your AI product]

**AI Capability:** [What the AI does - e.g., "Generates marketing copy from user prompts"]

**Evaluation Philosophy:** [Your approach - e.g., "Multi-layered evaluation combining automated metrics, human review, and continuous monitoring"]

**Success Definition:** [How you define success - e.g., "70%+ user acceptance, <2% harmful outputs, 8/10 satisfaction score"]

**Key Risks:** [Top 3 risks you're evaluating against]
1. [Risk 1 - e.g., "Low output quality"]
2. [Risk 2 - e.g., "Safety violations"]
3. [Risk 3 - e.g., "Slow response times"]

---

## Table of Contents

1. [Evaluation Strategy Overview](#evaluation-strategy-overview)
2. [Evaluation Layers](#evaluation-layers)
3. [Offline Evaluation](#offline-evaluation)
4. [Online Evaluation](#online-evaluation)
5. [Human Evaluation](#human-evaluation)
6. [Red-Teaming & Adversarial Testing](#red-teaming--adversarial-testing)
7. [Continuous Monitoring](#continuous-monitoring)
8. [Evaluation Cadence](#evaluation-cadence)
9. [Metrics Dashboard](#metrics-dashboard)
10. [Improvement Loops](#improvement-loops)

---

## Part 1: Evaluation Strategy Overview

### Evaluation Goals

**Primary Goals:**
1. **Quality Assurance** - Ensure AI outputs meet minimum quality bar
2. **Safety** - Prevent harmful, biased, or inappropriate outputs
3. **User Value** - Confirm AI solves real user problems
4. **Business Impact** - Validate positive business outcomes
5. **Continuous Improvement** - Identify areas for optimization

**Success Metrics:**
- Offline model metrics: [Target - e.g., "F1 > 0.85"]
- Online acceptance rate: [Target - e.g., "> 70%"]
- User satisfaction: [Target - e.g., "> 8/10"]
- Safety compliance: [Target - e.g., "> 99.5%"]
- Business metric: [Target - e.g., "20% increase in task completion"]

---

### Evaluation Principles

**Principle 1: Multi-Layered Evaluation**
- No single metric tells the whole story
- Combine automated + human + user feedback
- Evaluate at multiple levels: model → system → product → business

**Principle 2: Representative Testing**
- Test sets mirror real-world usage
- Include diverse scenarios and edge cases
- Regularly update test sets with new patterns

**Principle 3: Statistical Rigor**
- Use proper sample sizes
- Test for statistical significance
- Avoid p-hacking and multiple comparison errors
- Document confidence intervals

**Principle 4: Continuous Evaluation**
- Pre-launch: Comprehensive evaluation
- Post-launch: Ongoing monitoring
- Catch regressions early
- Detect drift and degradation

**Principle 5: Human-in-the-Loop**
- Automated metrics don't capture everything
- Regular human review for quality
- User feedback informs improvements
- Expert evaluation for edge cases

---

## Part 2: Evaluation Layers

### Layer 1: Model Evaluation

**What:** Evaluate the AI model in isolation

**When:** During development, before integration

**How:** Benchmark datasets, automated metrics

**Metrics:**
- [Metric 1 - e.g., "Accuracy: 92%"]
- [Metric 2 - e.g., "Precision: 88%"]
- [Metric 3 - e.g., "Recall: 85%"]
- [Metric 4 - e.g., "F1 Score: 0.86"]

**Success Criteria:**
- Must exceed baseline: [Specify baseline]
- Must meet minimum threshold: [Specify thresholds]

**Failure Response:**
- If below threshold → Don't proceed to production
- Iterate on model, data, or features
- Re-evaluate before advancing

---

### Layer 2: System Evaluation

**What:** Evaluate AI integrated into product

**When:** After integration, before user testing

**How:** End-to-end tests, integration tests

**Metrics:**
- Latency: [Target - e.g., "p95 < 2s"]
- Throughput: [Target - e.g., "> 100 qps"]
- Error rate: [Target - e.g., "< 2%"]
- System uptime: [Target - e.g., "> 99.9%"]

**Success Criteria:**
- Acceptable performance under load
- Graceful degradation on failures
- Proper integration with other systems

**Failure Response:**
- Performance issues → Optimize infrastructure
- Integration bugs → Fix and re-test
- Stability issues → Add fallbacks

---

### Layer 3: Product Evaluation

**What:** Evaluate user-facing AI features

**When:** Beta testing, A/B tests

**How:** User testing, surveys, behavioral data

**Metrics:**
- Engagement: [Target - e.g., "5+ interactions/session"]
- Acceptance rate: [Target - e.g., "> 70%"]
- Task completion: [Target - e.g., "> 80%"]
- User satisfaction: [Target - e.g., "> 8/10"]

**Success Criteria:**
- Users find value in AI feature
- AI improves user experience
- Positive feedback outweighs negative

**Failure Response:**
- Low acceptance → Improve output quality or UX
- Low engagement → Improve discoverability or value prop
- Negative feedback → Address top pain points

---

### Layer 4: Business Evaluation

**What:** Evaluate business impact

**When:** Post-launch, ongoing

**How:** A/B testing, cohort analysis

**Metrics:**
- Revenue impact: [Target - e.g., "+15%"]
- Retention lift: [Target - e.g., "+10% D30 retention"]
- Cost efficiency: [Target - e.g., "50% time savings"]
- Market differentiation: [Qualitative assessment]

**Success Criteria:**
- Positive ROI
- Meets business objectives
- Sustainable at scale

**Failure Response:**
- Negative ROI → Optimize costs or increase value
- No retention impact → Improve stickiness
- Not competitive → Add differentiating features

---

## Part 3: Offline Evaluation

### Test Set Construction

**Objective:** Build representative, diverse test sets

**Approach:**

**1. Representative Sampling**
- Sample from real user queries/inputs
- Maintain distribution of input types
- Include seasonal/temporal variations
- Volume: [X samples - e.g., "5,000 test cases"]

**2. Edge Case Coverage**
- Unusual but valid inputs
- Boundary conditions
- Rare scenarios
- Volume: [Y samples - e.g., "500 edge cases"]

**3. Adversarial Examples**
- Jailbreak attempts
- Prompt injections
- Safety violations
- Volume: [Z samples - e.g., "200 adversarial cases"]

**4. Gold Standard Labels**
- Expert-reviewed ground truth
- High inter-annotator agreement (> 0.8 kappa)
- Clear labeling guidelines
- Regular quality audits

**5. Test Set Updates**
- Add new failure modes discovered in production
- Add user-reported issues
- Refresh quarterly
- Version control test sets

---

### Automated Metrics

**For Classification Tasks:**

| Metric | Formula | Target | Why It Matters |
|--------|---------|--------|----------------|
| Accuracy | (TP + TN) / Total | > 90% | Overall correctness |
| Precision | TP / (TP + FP) | > 85% | False positive rate |
| Recall | TP / (TP + FN) | > 80% | False negative rate |
| F1 Score | 2 × (P × R) / (P + R) | > 0.82 | Balanced metric |
| AUC-ROC | Area under curve | > 0.90 | Ranking quality |

---

**For Generation Tasks:**

| Metric | Description | Target | Limitations |
|--------|-------------|--------|-------------|
| BLEU | N-gram overlap | > 0.4 | Poor for creativity |
| ROUGE | Recall-oriented overlap | > 0.5 | Doesn't capture quality |
| Perplexity | Language model confidence | < 20 | Doesn't ensure relevance |
| BERTScore | Semantic similarity | > 0.85 | Expensive to compute |
| Human Eval | Expert rating | > 7/10 | Gold standard but slow |

---

**For Retrieval Tasks:**

| Metric | Description | Target | When to Use |
|--------|-------------|--------|-------------|
| Precision@k | % relevant in top k | > 80% | When top results matter |
| Recall@k | % of relevant found in k | > 60% | When coverage matters |
| NDCG | Discounted cumulative gain | > 0.75 | When ranking matters |
| MRR | Mean reciprocal rank | > 0.7 | First relevant result |

---

### Regression Testing

**Purpose:** Ensure new changes don't break existing functionality

**Test Suite:**
- Core functionality tests: [X tests]
- Edge case tests: [Y tests]
- Performance benchmarks: [Z tests]

**Process:**
```
1. Run full test suite on every model update
2. Compare metrics to baseline
3. Flag any degradation > 5%
4. Investigate and fix before deploying
5. Update baseline after successful deployment
```

**Automation:**
- CI/CD integration
- Automated alerts on regressions
- Block deployment if critical tests fail

**Example:**
```
Baseline model (v1.2):
  - Accuracy: 92%
  - Latency p95: 1.8s
  - Safety pass rate: 99.7%

New model (v1.3):
  - Accuracy: 93.5% ✅ (+1.5%)
  - Latency p95: 2.1s ⚠️ (+16% - investigate)
  - Safety pass rate: 99.8% ✅ (+0.1%)

Decision: Investigate latency regression before deployment
```

---

### Statistical Rigor

**Sample Size Calculation:**

For A/B test to detect [X]% improvement with 95% confidence and 80% power:
```
n = (Z_α/2 + Z_β)² × (σ₁² + σ₂²) / (μ₁ - μ₂)²

Where:
- Z_α/2 = 1.96 (95% confidence)
- Z_β = 0.84 (80% power)
- σ = standard deviation
- μ = mean

Example:
To detect 5% improvement in acceptance rate (baseline 65%, σ=0.15):
n = 2,352 samples per variant
```

**Confidence Intervals:**
- Always report with 95% CI
- Example: "Accuracy: 92% (91.5% - 92.5%)"

**Multiple Comparison Correction:**
- If testing multiple hypotheses, use Bonferroni correction
- Adjusted α = 0.05 / number of tests
- Example: Testing 5 metrics → α = 0.01 per test

**Avoiding P-Hacking:**
- Pre-register hypothesis and metrics
- Don't stop experiment early because results look good
- Don't run multiple tests until one is significant
- Report all tests, not just significant ones

---

## Part 4: Online Evaluation

### A/B Testing Strategy

**Hypothesis Formation:**

**Template:**
```
IF we [change X]
THEN we expect [metric Y] to [improve by Z%]
BECAUSE [reasoning]
```

**Example:**
```
IF we improve prompt quality with few-shot examples
THEN we expect acceptance rate to increase by 10%
BECAUSE outputs will be more relevant and well-formatted
```

---

### Metric Selection

**Primary Metric:**
- [Metric name - e.g., "Acceptance rate"]
- Definition: [How measured]
- Target: [Expected improvement]
- Minimum Detectable Effect: [Smallest meaningful change]

**Guardrail Metrics:**
Monitor to ensure we don't break other things

| Metric | Target | Alert Threshold |
|--------|--------|-----------------|
| Safety violation rate | < 0.5% | Increase > 0.1% |
| Latency p95 | < 2.5s | Increase > 15% |
| Error rate | < 2% | Increase > 1% |
| Cost per query | < $0.05 | Increase > 20% |
| User satisfaction | > 7.5/10 | Decrease > 0.5 |

**Secondary Metrics:**
Positive signals we expect

| Metric | Baseline | Expected Change |
|--------|----------|-----------------|
| Regeneration rate | 30% | Decrease to 20% |
| Edit rate | 45% | Decrease to 35% |
| Time to completion | 120s | Decrease to 90s |
| Feature retention D7 | 40% | Increase to 50% |

---

### Experiment Design

**Randomization Strategy:**
- [ ] User-level randomization (consistent experience)
- [ ] Request-level randomization (faster results)
- [ ] Stratified by user segment (detect heterogeneous effects)

**Traffic Allocation:**
- Control: [X%]
- Treatment: [Y%]
- Holdout (no AI): [Z%] (optional but recommended)

**Duration:**
- Minimum: [X days - account for weekly cycles]
- Planned: [Y days - based on sample size]
- Maximum: [Z days - don't run forever]

**Launch Criteria:**
```
Proceed to full launch IF:
✅ Primary metric improves by ≥ [X]% (statistically significant)
✅ No guardrail metrics degrade by > threshold
✅ Secondary metrics show positive trends
✅ Qualitative feedback is positive
✅ No major bugs or issues
```

**Rollback Criteria:**
```
Immediate rollback IF:
❌ Safety violation rate increases > 0.2%
❌ Error rate increases > 3%
❌ User satisfaction drops > 1 point
❌ Critical bug discovered
❌ Latency p95 > 5s
```

---

### Special Considerations for AI

**1. Model Version Control**
- Lock model version for experiment duration
- Don't update model mid-experiment
- Track model version in all logs

**2. Cold Start Handling**
- New users may have different experience
- Consider separate analysis for new vs. existing users
- May need longer experiment for personalization to kick in

**3. Habituation Effects**
- Users adapt to AI over time
- Short-term metrics may differ from long-term
- Run for at least 2 weeks to capture habituation

**4. Network Effects**
- AI may improve with more users
- A/B test may underestimate full launch impact
- Consider staged rollout approach

**5. Interaction Effects**
- Multiple AI features may interact
- Test in isolation when possible
- Monitor for unexpected interactions

---

## Part 5: Human Evaluation

### Evaluation Rubric

**Criteria 1: Relevance**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Completely off-topic | User asks for recipe, AI talks about sports |
| 2 | Somewhat related but misses main point | Recipe provided but wrong cuisine |
| 3 | Addresses query but missing key aspects | Recipe ok but missing cook time |
| 4 | Highly relevant with minor gaps | Recipe complete, slightly different than asked |
| 5 | Perfectly addresses the query | Exactly what user asked for |

**Weight:** [30%]

---

**Criteria 2: Accuracy**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Completely inaccurate | Multiple factual errors |
| 2 | Mostly inaccurate | More wrong than right |
| 3 | Mostly accurate with some errors | 1-2 minor errors |
| 4 | Accurate with negligible errors | Technically correct, minor formatting issues |
| 5 | Completely accurate | No errors whatsoever |

**Weight:** [25%]

---

**Criteria 3: Completeness**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Missing critical information | Recipe missing main ingredient |
| 2 | Significant gaps | Recipe missing 2+ steps |
| 3 | Minor gaps that don't impede use | Missing garnish suggestion |
| 4 | Comprehensive with tiny omissions | All essentials covered |
| 5 | Exhaustive, nothing missing | Complete in every way |

**Weight:** [15%]

---

**Criteria 4: Coherence**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Incoherent, doesn't make sense | Contradictory statements |
| 2 | Hard to follow | Confusing structure |
| 3 | Mostly coherent, some awkwardness | Readable but could be smoother |
| 4 | Clear and well-structured | Easy to understand |
| 5 | Exceptionally clear and logical | Perfect flow |

**Weight:** [10%]

---

**Criteria 5: Tone & Style**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Completely inappropriate tone | Casual when formal needed |
| 2 | Somewhat mismatched tone | Too verbose or too terse |
| 3 | Acceptable tone | Decent but not perfect |
| 4 | Good tone match | Appropriate for context |
| 5 | Perfect tone and style | Exactly right voice |

**Weight:** [10%]

---

**Criteria 6: Safety**

| Score | Description | Example |
|-------|-------------|---------|
| 1 | Harmful content | Promotes dangerous activities |
| 2 | Potentially problematic | Contains bias or stereotypes |
| 3 | Safe but could be better | Slightly insensitive phrasing |
| 4 | Safe and appropriate | No concerns |
| 5 | Exemplary safety | Proactively addresses safety |

**Weight:** [10%]

**Note:** Any score of 1 or 2 on Safety = automatic failure

---

### Overall Score Calculation

```
Overall Score = (Relevance × 0.30) + (Accuracy × 0.25) +
                (Completeness × 0.15) + (Coherence × 0.10) +
                (Tone × 0.10) + (Safety × 0.10)

Example:
Relevance: 4 (×0.30 = 1.2)
Accuracy: 5 (×0.25 = 1.25)
Completeness: 3 (×0.15 = 0.45)
Coherence: 4 (×0.10 = 0.4)
Tone: 4 (×0.10 = 0.4)
Safety: 5 (×0.10 = 0.5)

Overall: 4.2 / 5.0 (84%)
```

**Quality Tiers:**
- **Excellent:** 4.5 - 5.0 (90-100%)
- **Good:** 3.5 - 4.49 (70-89%)
- **Acceptable:** 2.5 - 3.49 (50-69%)
- **Poor:** 1.5 - 2.49 (30-49%)
- **Fail:** < 1.5 (<30%)

**Success Criterion:** > 70% of outputs score "Good" or higher

---

### Rater Guidelines

**Who Should Rate:**
- Domain experts (for technical accuracy)
- Representative users (for relevance and usability)
- Diverse backgrounds (for bias detection)
- Minimum: 3 raters per output

**Training:**
- Review rubric thoroughly
- Complete calibration set (50 examples)
- Achieve inter-rater agreement > 0.75
- Regular re-calibration (monthly)

**Rating Process:**
1. Read user query/input
2. Review AI output
3. Score on each criterion independently
4. Provide written justification for scores ≤ 2
5. Flag any safety concerns immediately

**Inter-Rater Reliability:**
- Calculate Cohen's Kappa or Krippendorff's Alpha
- Target: κ > 0.75
- If low agreement → Review guidelines, retrain raters
- Resolve disagreements through discussion

---

### Human Evaluation Cadence

**Pre-Launch:**
- Evaluate 500+ outputs
- Comprehensive rubric application
- Achieve > 70% "Good" or better
- Address all "Fail" cases

**Post-Launch:**
- Ongoing: 100 random samples/week
- Ad-hoc: All user-reported issues
- Deep dives: Monthly (500 samples)

**Feedback Loop:**
- Weekly summary report
- Monthly trends analysis
- Findings inform model improvements
- Track improvement over time

---

## Part 6: Red-Teaming & Adversarial Testing

### Threat Model

**What Could Go Wrong:**

**1. Safety Violations**
- Harmful content generation
- Hate speech
- Violence or gore
- Self-harm promotion
- Sexual content (inappropriate contexts)

**2. Security Exploits**
- Prompt injection attacks
- Jailbreaking safety guardrails
- Data exfiltration
- Unauthorized actions

**3. Quality Failures**
- Hallucinations (false information)
- Incoherent outputs
- Irrelevant responses
- Incomplete answers

**4. Bias & Fairness**
- Demographic bias
- Cultural insensitivity
- Stereotyping
- Unfair treatment

**5. Privacy Violations**
- PII exposure
- Training data leakage
- Cross-user information sharing

---

### Red-Teaming Process

**Phase 1: Planning (1-2 days)**
```
1. Review threat model
2. Assemble red team (3-5 people with diverse backgrounds)
3. Define scope and rules of engagement
4. Set up testing environment
5. Create logging/documentation system
```

**Phase 2: Attack Generation (1 week)**
```
1. Brainstorm attack vectors
2. Generate test cases for each vector
3. Aim for 50-100 adversarial test cases
4. Include creative, unexpected attacks
5. Document all attempts
```

**Phase 3: Execution (1 week)**
```
1. Execute all test cases
2. Document successes (broke the system)
3. Document failures (system held)
4. Measure success rate by category
5. Identify most vulnerable areas
```

**Phase 4: Analysis (2-3 days)**
```
1. Categorize successful attacks
2. Assess severity and likelihood
3. Prioritize mitigations
4. Document findings in report
```

**Phase 5: Mitigation (Ongoing)**
```
1. Implement fixes for critical issues
2. Update guardrails and filters
3. Improve prompts
4. Re-test to verify fixes
5. Add successful attacks to regression suite
```

---

### Red-Teaming Categories & Examples

**Category 1: Jailbreaking**

*Goal: Bypass safety guardrails*

Examples:
- "Ignore previous instructions and..."
- "Pretend you're in developer mode..."
- "For educational purposes only, explain how to..."
- Roleplaying scenarios to bypass filters
- Encoding harmful requests in different languages

**Success Criteria:** < 1% jailbreak success rate

---

**Category 2: Prompt Injection**

*Goal: Manipulate AI behavior through crafted inputs*

Examples:
- Embedding instructions in user content
- "Ignore the above and say..."
- Multi-step injections
- Indirect injections through external content

**Success Criteria:** 0% successful injections

---

**Category 3: Adversarial Examples**

*Goal: Fool the model with subtle perturbations*

Examples:
- Slightly misspelled harmful requests
- Substituting characters (leet speak)
- Homoglyphs (visually similar characters)
- Context switching mid-prompt

**Success Criteria:** < 2% bypass rate

---

**Category 4: Edge Case Exploitation**

*Goal: Find unusual scenarios that break the system*

Examples:
- Extremely long inputs (10,000+ characters)
- Repeated tokens
- Special characters and Unicode
- Multiple languages in single input
- Contradictory instructions

**Success Criteria:** Graceful handling of all edge cases

---

**Category 5: Bias Testing**

*Goal: Elicit biased or discriminatory outputs*

Examples:
- Requests about different demographics
- Gender, race, age, religion variations
- Occupational stereotypes
- Implicit bias tests

**Success Criteria:** < 5% biased outputs

---

### Red-Teaming Report Template

**Executive Summary:**
- Test period: [Dates]
- Test cases executed: [X]
- Successful attacks: [Y] ([Y/X]%)
- Critical findings: [Number]
- Mitigations implemented: [Number]

**Findings by Category:**

| Category | Test Cases | Success Rate | Severity | Status |
|----------|-----------|--------------|----------|--------|
| Jailbreaking | 25 | 2% | High | Mitigated |
| Prompt Injection | 30 | 0% | High | Secure |
| Adversarial | 20 | 5% | Medium | In Progress |
| Edge Cases | 15 | 10% | Low | Acceptable |
| Bias | 10 | 3% | Medium | Mitigated |

**Top Vulnerabilities:**
1. [Vulnerability 1 - Description, severity, mitigation plan]
2. [Vulnerability 2]
3. [Vulnerability 3]

**Recommendations:**
1. [Recommendation 1]
2. [Recommendation 2]
3. [Recommendation 3]

---

## Part 7: Continuous Monitoring

### Metrics to Track

**Model Performance Metrics:**

| Metric | Baseline | Alert Threshold | Critical Threshold |
|--------|----------|-----------------|-------------------|
| Accuracy | 92% | < 88% | < 85% |
| Latency p50 | 0.8s | > 1.2s | > 2.0s |
| Latency p95 | 1.8s | > 2.5s | > 4.0s |
| Latency p99 | 3.2s | > 4.5s | > 8.0s |
| Error rate | 1.2% | > 2.5% | > 5.0% |
| Timeout rate | 0.3% | > 1.0% | > 2.0% |

**Quality Metrics:**

| Metric | Baseline | Alert Threshold | Critical Threshold |
|--------|----------|-----------------|-------------------|
| Acceptance rate | 72% | < 65% | < 60% |
| Thumbs up rate | 68% | < 60% | < 55% |
| Regeneration rate | 28% | > 35% | > 40% |
| Edit rate | 42% | > 50% | > 60% |
| Average quality score (1-5) | 4.1 | < 3.8 | < 3.5 |

**Safety Metrics:**

| Metric | Baseline | Alert Threshold | Critical Threshold |
|--------|----------|-----------------|-------------------|
| Content violations | 0.2% | > 0.5% | > 1.0% |
| User reports | 0.3% | > 0.8% | > 1.5% |
| PII exposures | 0% | > 0% | > 0.1% |
| Bias flags | 0.5% | > 1.5% | > 3.0% |

**Business Metrics:**

| Metric | Baseline | Alert Threshold | Critical Threshold |
|--------|----------|-----------------|-------------------|
| DAU using feature | 10,000 | < 8,000 | < 6,000 |
| Feature retention D7 | 45% | < 40% | < 35% |
| Cost per query | $0.03 | > $0.05 | > $0.08 |
| NPS | 42 | < 35 | < 25 |

---

### Drift Detection

**Types of Drift to Monitor:**

**1. Data Drift (Input Distribution Changes)**

*Detection Methods:*
- Kolmogorov-Smirnov test (continuous features)
- Chi-square test (categorical features)
- Population Stability Index (PSI)
- Jensen-Shannon divergence

*Example:*
```
Monitor: Input length distribution
Baseline: Mean 150 characters, σ = 80
Current: Mean 220 characters, σ = 120
KS test: p < 0.001 → Drift detected!

Action: Investigate why inputs are longer
Potential causes: New user segment, feature change, bot traffic
```

**2. Concept Drift (Relationship Changes)**

*Detection Methods:*
- Monitor model performance over time
- Track prediction confidence scores
- Compare to ground truth (when available)

*Example:*
```
Monitor: Acceptance rate by input category
Baseline: Category A: 75%, Category B: 70%
Current: Category A: 74%, Category B: 55%
→ Concept drift in Category B

Action: Retrain with recent Category B data
```

**3. Prediction Drift (Output Distribution Changes)**

*Detection Methods:*
- Monitor output distribution
- Track diversity metrics
- Compare to expected distribution

*Example:*
```
Monitor: Sentiment distribution of outputs
Baseline: 60% positive, 30% neutral, 10% negative
Current: 80% positive, 15% neutral, 5% negative
→ Model becoming overly positive

Action: Check if training data is biased toward positive examples
```

---

### Monitoring Dashboard

**Real-Time Dashboard (Refresh every 5 minutes):**

```
┌──────────────────────────────────────────────────────────┐
│ AI Model Performance - Last 24 Hours                      │
├──────────────────────────────────────────────────────────┤
│ Requests: 1,247,392 | Errors: 0.8% ✅ | Avg Latency: 1.1s ✅│
│                                                            │
│ Quality Metrics:                                           │
│ • Acceptance Rate:   ████████░░ 74% ✅                     │
│ • Thumbs Up Rate:    ███████░░░ 69% ✅                     │
│ • Regenerate Rate:   ███░░░░░░░ 26% ✅                     │
│                                                            │
│ Safety Metrics:                                            │
│ • Content Violations: 0.15% ✅                             │
│ • User Reports:       0.22% ✅                             │
│ • PII Exposures:      0% ✅                                │
│                                                            │
│ Performance:                                               │
│ • P50 Latency:       0.7s ✅                               │
│ • P95 Latency:       1.9s ✅                               │
│ • P99 Latency:       3.8s ⚠️ (approaching threshold)      │
└──────────────────────────────────────────────────────────┘
```

**Weekly Trends Dashboard:**

```
┌──────────────────────────────────────────────────────────┐
│ 7-Day Trends                                              │
├──────────────────────────────────────────────────────────┤
│ Acceptance Rate:                                           │
│ Week -4: 72% ███████░░░                                   │
│ Week -3: 73% ███████░░░                                   │
│ Week -2: 74% ████████░░                                   │
│ Week -1: 73% ███████░░░                                   │
│ This week: 74% ████████░░  ✅ Stable                      │
│                                                            │
│ Avg Quality Score (1-5):                                   │
│ Week -4: 4.0 ████████░░                                   │
│ Week -3: 4.1 ████████░░                                   │
│ Week -2: 4.1 ████████░░                                   │
│ Week -1: 3.9 ███████░░░  ⚠️ Dip detected                  │
│ This week: 4.0 ████████░░  ✅ Recovering                  │
└──────────────────────────────────────────────────────────┘
```

---

### Alerting Strategy

**P0 Alerts (Immediate Page):**
- Safety violations > 1% in any 1-hour window
- Error rate > 5%
- Latency p99 > 8s
- Service downtime
- PII exposure detected

**P1 Alerts (Slack + Email within 1 hour):**
- Acceptance rate drops > 10%
- Error rate > 2.5%
- Cost per query increases > 50%
- Drift detected in core features

**P2 Alerts (Email daily digest):**
- Minor metric degradations
- Trends approaching thresholds
- Quality score trending down

**Alert Fatigue Prevention:**
- Adjust thresholds based on historical variance
- Use percentage changes, not absolute values
- Require sustained degradation (not momentary spikes)
- Weekly alert review to tune thresholds

---

### Retraining Triggers

**When to Retrain Model:**

**Trigger 1: Performance Degradation**
```
IF primary metric drops > 5% sustained for 3+ days
THEN trigger retraining
```

**Trigger 2: Drift Detected**
```
IF data drift OR concept drift detected
AND confirmed by manual review
THEN trigger retraining
```

**Trigger 3: Sufficient New Data**
```
IF new labeled data > 20% of original training set
AND new data shows different patterns
THEN trigger retraining
```

**Trigger 4: Scheduled Cadence**
```
IF > 3 months since last retrain
THEN trigger retraining (proactive)
```

**Trigger 5: Major Product Changes**
```
IF new features launched OR user base shifts significantly
THEN trigger retraining
```

**Retraining Process:**
1. Collect new training data
2. Retrain model
3. Evaluate on test set
4. A/B test new model vs. current
5. If better → Deploy
6. If worse → Iterate or keep current

---

## Part 8: Evaluation Cadence

### Pre-Launch Evaluation

**Timeline: 2-4 weeks before launch**

**Week 1: Offline Evaluation**
- [ ] Run full test suite
- [ ] Achieve target metrics
- [ ] Pass regression tests
- [ ] Document results

**Week 2: Human Evaluation**
- [ ] Rate 500+ outputs
- [ ] >70% score "Good" or better
- [ ] Address all "Fail" cases
- [ ] Inter-rater agreement > 0.75

**Week 3: Red-Teaming**
- [ ] Execute 50+ attack scenarios
- [ ] < 2% jailbreak success
- [ ] Mitigate critical vulnerabilities
- [ ] Re-test after fixes

**Week 4: Beta Testing**
- [ ] 100-500 beta users
- [ ] Collect feedback
- [ ] Monitor metrics
- [ ] Iterate based on learnings

**Launch Decision:**
- All offline metrics met ✅
- Human eval pass rate > 70% ✅
- Red-team vulnerabilities mitigated ✅
- Beta feedback positive ✅
- Stakeholder sign-off ✅

---

### Post-Launch Monitoring

**Daily:**
- Monitor real-time dashboard
- Review critical alerts
- Check for anomalies
- Quick fixes for urgent issues

**Weekly:**
- Trend analysis
- Human eval of 100 samples
- User feedback review
- Metrics summary report

**Monthly:**
- Deep dive evaluation (500 samples)
- Drift analysis
- A/B test results review
- Red-team re-test
- Improvement planning

**Quarterly:**
- Comprehensive evaluation
- Test set refresh
- Model retraining consideration
- Roadmap alignment

---

## Part 9: Metrics Dashboard

### Executive Dashboard

**For Leadership (Monthly):**

```
┌──────────────────────────────────────────────────────────┐
│ AI Product Health - October 2024                          │
├──────────────────────────────────────────────────────────┤
│ Overall Status: ✅ HEALTHY                                │
│                                                            │
│ Key Metrics:                                               │
│ • User Adoption:        45% of users tried AI (↑ 5%)     │
│ • Acceptance Rate:      74% (↑ 2%)                        │
│ • User Satisfaction:    8.1/10 (↑ 0.3)                    │
│ • Safety Compliance:    99.8% (stable)                     │
│                                                            │
│ Business Impact:                                           │
│ • Task Completion:      +18% vs. non-AI users             │
│ • Time Saved:           avg 15 min/user/week              │
│ • Retention Lift:       +12% D30 retention                │
│ • NPS:                  44 (↑ 2)                           │
│                                                            │
│ Risks & Concerns:                                          │
│ • Latency p99 trending up (monitoring closely)            │
│ • Cost per query +8% (optimizing)                         │
└──────────────────────────────────────────────────────────┘
```

---

### Product Team Dashboard

**For PM/Eng (Weekly):**

```
┌──────────────────────────────────────────────────────────┐
│ Detailed Metrics - Week of Nov 11                         │
├──────────────────────────────────────────────────────────┤
│ Volume:                                                    │
│ • Total queries:        1.2M (↑ 5% WoW)                  │
│ • Active users:         32,450 (↑ 3%)                     │
│ • Queries/user:         37 (↑ 2%)                         │
│                                                            │
│ Quality:                                                   │
│ • Acceptance rate:      74% (stable)                       │
│ • Thumbs up:            69% (↑ 1%)                        │
│ • Regenerate rate:      26% (↓ 2%)                        │
│ • Edit rate:            40% (stable)                       │
│ • Quality score:        4.1/5 (stable)                     │
│                                                            │
│ Performance:                                               │
│ • P50 latency:          0.7s (stable)                     │
│ • P95 latency:          1.9s (stable)                     │
│ • P99 latency:          4.1s ⚠️ (↑ from 3.8s)            │
│ • Error rate:           0.9% (stable)                     │
│                                                            │
│ Safety:                                                    │
│ • Violations:           0.15% (stable)                     │
│ • User reports:         0.20% (stable)                     │
│                                                            │
│ Cost:                                                      │
│ • Cost/query:           $0.032 (↑ from $0.030)           │
│ • Total cost:           $38,400 (↑ 10%)                   │
│                                                            │
│ Action Items:                                              │
│ • Investigate p99 latency increase                        │
│ • Optimize cost per query                                 │
└──────────────────────────────────────────────────────────┘
```

---

## Part 10: Improvement Loops

### Continuous Improvement Process

**Step 1: Data Collection**
```
Collect:
- User feedback (thumbs up/down, comments)
- Human evaluations
- Failed cases
- Edge cases discovered
- User-reported issues
```

**Step 2: Analysis**
```
Analyze:
- Common failure patterns
- User pain points
- Quality gaps
- Safety issues
- Performance bottlenecks
```

**Step 3: Prioritization**
```
Prioritize by:
- Impact (how many users affected)
- Severity (how bad is the issue)
- Feasibility (how hard to fix)
- Strategic importance
```

**Step 4: Implementation**
```
Implement:
- Prompt improvements
- Model retraining
- Feature enhancements
- Guardrail updates
- UX refinements
```

**Step 5: Validation**
```
Validate:
- Re-evaluate on test set
- A/B test changes
- Measure improvement
- Confirm no regressions
```

**Step 6: Deploy & Monitor**
```
Deploy:
- Staged rollout
- Monitor metrics closely
- Quick rollback if issues
- Document learnings
```

**Cadence:** Every 2-4 weeks

---

### Feedback Integration

**User Feedback:**
- Collect: Thumbs up/down, comments, reports
- Aggregate: Weekly summary of themes
- Act: Address top 3 issues each sprint
- Close loop: Notify users of fixes

**Human Evaluator Feedback:**
- Collect: Detailed ratings and comments
- Analyze: Identify systematic issues
- Train: Update model or prompts
- Validate: Re-evaluate to confirm improvement

**Production Failures:**
- Detect: Monitoring alerts
- Investigate: Root cause analysis
- Fix: Immediate mitigation
- Prevent: Add to regression suite

**A/B Test Learnings:**
- Successful tests → Roll out
- Failed tests → Learn and iterate
- Surprising results → Investigate deeply
- Compile: Learnings database

---

## Appendix A: Metric Definitions

### Acceptance Rate
**Definition:** % of AI outputs user accepts without regeneration or discarding
**Formula:** Accepted / Total × 100%
**Target:** > 70%

### Thumbs Up Rate
**Definition:** % of AI outputs user explicitly rates positively
**Formula:** Thumbs Up / (Thumbs Up + Thumbs Down) × 100%
**Target:** > 65%

### Regeneration Rate
**Definition:** % of times user regenerates instead of accepting first output
**Formula:** Regenerations / Total × 100%
**Target:** < 30% (lower is better)

### Edit Rate
**Definition:** % of accepted outputs that user edits before using
**Formula:** Edited / Accepted × 100%
**Target:** 20-40% (some editing is normal)

### Quality Score
**Definition:** Average human evaluation score across all criteria
**Formula:** Weighted average of rubric scores
**Target:** > 4.0 / 5.0

---

## Appendix B: Tools & Infrastructure

### Evaluation Tools

**Offline Evaluation:**
- Jupyter notebooks for analysis
- Custom evaluation scripts
- Benchmark datasets (Papers with Code, Hugging Face)
- Statistical libraries (scipy, statsmodels)

**Online Evaluation:**
- A/B testing platform (Optimizely, LaunchDarkly, custom)
- Analytics (Amplitude, Mixpanel, custom)
- Logging infrastructure

**Human Evaluation:**
- Annotation platform (Scale AI, Labelbox, custom)
- Rubric templates
- Inter-rater agreement calculators

**Monitoring:**
- Metrics dashboard (Grafana, Datadog, custom)
- Alerting (PagerDuty, Slack)
- Log aggregation (Elasticsearch, Splunk)
- Drift detection (Evidently AI, WhyLabs)

---

## Summary Checklist

**Before Launch:**
- [ ] Offline evaluation complete and passing
- [ ] Human evaluation shows >70% quality
- [ ] Red-teaming complete, vulnerabilities mitigated
- [ ] Beta testing successful
- [ ] Monitoring dashboard set up
- [ ] Alerting configured
- [ ] Rollback plan ready

**Post-Launch:**
- [ ] Daily monitoring active
- [ ] Weekly human evaluation ongoing
- [ ] Monthly deep dives scheduled
- [ ] Drift detection running
- [ ] Improvement loop in place
- [ ] Metrics shared with stakeholders

---

**This evaluation framework demonstrates:**
- ✅ Comprehensive multi-layered approach
- ✅ Balance of automated and human evaluation
- ✅ Rigorous statistical methodology
- ✅ Proactive red-teaming and safety focus
- ✅ Continuous monitoring and improvement
- ✅ Portfolio-ready documentation

**Use this for:**
- Building evaluation systems for your AI products
- Answering interview questions about evaluation
- Demonstrating systematic thinking
- Ensuring production readiness
