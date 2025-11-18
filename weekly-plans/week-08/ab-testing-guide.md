# A/B Testing Guide for AI Products

**Created:** [Date]
**Week 8 Supporting Resource**
**Product:** [Your AI Product Name]

---

## Overview

**Why A/B Testing AI is Different:**
- Models change continuously
- User adaptation effects
- Long-term vs. short-term metrics diverge
- Network effects complicate interpretation
- Cost implications of running experiments

**Goal:** Rigorously measure impact of AI improvements while accounting for AI-specific challenges

---

## Quick Reference: A/B Test Checklist

**Before Launch:**
- [ ] Hypothesis clearly defined
- [ ] Primary metric selected
- [ ] Guardrail metrics defined
- [ ] Sample size calculated
- [ ] Duration planned (accounting for weekly cycles)
- [ ] Randomization strategy chosen
- [ ] Holdout group included (optional but recommended)
- [ ] Success/failure criteria documented
- [ ] Rollback plan ready

**During Experiment:**
- [ ] Monitor metrics daily
- [ ] Check for statistical significance
- [ ] Watch guardrails (no degradation)
- [ ] Review qualitative feedback
- [ ] Document anomalies

**After Experiment:**
- [ ] Statistical significance achieved
- [ ] Primary metric improved
- [ ] No guardrail violations
- [ ] Qualitative feedback positive
- [ ] Documented learnings
- [ ] Decision: Ship / Iterate / Kill

---

## Part 1: Hypothesis Formation

### SMART Hypothesis Template

**Template:**
```
IF we [specific change]
THEN we expect [metric] to [improve/decrease] by [X]%
BECAUSE [reasoning based on user insight]
MEASURED BY [how we'll measure success]
WITHIN [timeframe]
```

**Example:**
```
IF we improve prompt quality by adding few-shot examples
THEN we expect acceptance rate to increase by 10 percentage points
BECAUSE outputs will be more relevant and better formatted
MEASURED BY (acceptances / total outputs) over 2 weeks
WITHIN 2 weeks of launch
```

**Bad Example:**
```
"Let's try the new model and see if users like it better"
→ Too vague, no specific metric, no expected magnitude
```

---

### Hypothesis Categories for AI Products

**1. Model Improvement**
```
IF we upgrade from GPT-3.5 to GPT-4
THEN we expect acceptance rate to increase by 15%
BECAUSE output quality will be higher
```

**2. Prompt Optimization**
```
IF we add chain-of-thought prompting
THEN we expect accuracy on complex queries to increase by 20%
BECAUSE model will show its reasoning
```

**3. UX Changes**
```
IF we show confidence scores
THEN we expect user trust to increase (measured by thumbs-up rate +5%)
BECAUSE users will know when to verify outputs
```

**4. Feature Addition**
```
IF we add "Refine" button
THEN we expect regeneration rate to decrease by 30%
BECAUSE users can iterate instead of regenerating from scratch
```

**5. Parameter Tuning**
```
IF we lower temperature from 0.8 to 0.6
THEN we expect output consistency to improve (fewer regenerations, -10%)
BECAUSE outputs will be more deterministic
```

---

## Part 2: Metric Selection

### Primary Metric

**Characteristics of Good Primary Metric:**
- ✅ Directly measures user value
- ✅ Sensitive to changes (will move if treatment works)
- ✅ Measurable in reasonable timeframe
- ✅ Single metric (not a composite)

**Examples by Product Type:**

**Content Generation:**
- Acceptance rate (% outputs accepted without editing)
- Edit rate (% accepted outputs that were edited)
- Satisfaction rating (explicit user rating)

**Recommendation System:**
- Click-through rate (CTR)
- Conversion rate
- Time spent with recommended content

**Classification:**
- Accuracy (when ground truth available)
- False positive rate
- False negative rate

**Chatbot/Assistant:**
- Task completion rate
- Conversation satisfaction
- Queries per session

---

### Guardrail Metrics

**Purpose:** Ensure we don't break other things while improving primary metric

**Must-Have Guardrails:**

| Metric | Why Monitor | Acceptable Change |
|--------|-------------|-------------------|
| Error rate | System stability | No increase >1% |
| Latency (p95, p99) | User experience | No increase >15% |
| Cost per query | Business viability | No increase >20% |
| Safety violations | User safety | No increase at all |
| User satisfaction | Overall experience | No decrease >0.5 points |

**Example Guardrail Setup:**
```
Primary Metric: Acceptance rate
Target: +10%

Guardrails:
- Error rate: Must stay <2% (currently 1.2%)
- p95 latency: Must stay <2.5s (currently 1.8s)
- Cost/query: Must stay <$0.05 (currently $0.03)
- Safety violations: Must stay <0.2% (currently 0.15%)
- NPS: Must not drop >5 points (currently 42)
```

---

### Secondary Metrics

**Purpose:** Additional positive signals we expect

**Examples:**
- Time to task completion (expect decrease)
- Feature retention D7 (expect increase)
- Share rate (expect increase)
- Queries per user (could increase if feature is valuable)

**Don't Let Secondary Metrics Derail:**
- Focus on primary metric for launch decision
- Use secondary metrics for insights
- Document unexpected secondary metric movements

---

## Part 3: Experiment Design

### Randomization Strategies

#### User-Level Randomization

**When to Use:**
- Most AI products
- When consistency matters (same user always sees same variant)
- When learning effects are important

**How It Works:**
```
Hash(user_id) % 100 < 50 → Control
Hash(user_id) % 100 >= 50 → Treatment
```

**Pros:**
- Consistent user experience
- Captures learning/adaptation effects
- Easier to analyze

**Cons:**
- Slower (need more time to reach significance)
- Network effects may leak between groups

---

#### Request-Level Randomization

**When to Use:**
- Quick experiments
- When immediate feedback available
- Low risk of confusion

**How It Works:**
```
Random() < 0.5 → Control
Random() >= 0.5 → Treatment
```

**Pros:**
- Faster results
- More statistical power with same users

**Cons:**
- Inconsistent user experience
- May confuse users (AI behaves differently each time)
- Misses adaptation effects

**Best Practice:** Use user-level for most AI experiments

---

#### Stratified Randomization

**When to Use:**
- When user segments differ significantly
- To ensure balanced groups

**How It Works:**
```
For each segment (e.g., new vs. power users):
  Randomize within segment 50/50
```

**Pros:**
- Ensures balanced representation
- Can analyze heterogeneous effects

**Cons:**
- More complex to implement
- Requires pre-defined segments

---

### Traffic Allocation

**Standard Allocation:**
```
Control: 50%
Treatment: 50%
```

**Conservative Allocation (Risky Changes):**
```
Control: 90%
Treatment: 10%
(Expand to 50% if early results positive)
```

**With Holdout (Recommended for AI):**
```
Control (Current AI): 45%
Treatment (New AI): 45%
Holdout (No AI): 10%
```

**Why Holdout?**
- Measures absolute value of AI (not just improvement)
- Detects if both variants degraded
- Useful for long-term analysis

---

### Sample Size Calculation

**Formula:**
```
n = (Z_α/2 + Z_β)² × (σ₁² + σ₂²) / (μ₁ - μ₂)²

Where:
- Z_α/2 = 1.96 (for 95% confidence, two-tailed)
- Z_β = 0.84 (for 80% power)
- σ = standard deviation
- μ = mean
- μ₁ - μ₂ = minimum detectable effect
```

**Simplified Calculator:**

```python
from scipy import stats
import numpy as np

def calculate_sample_size(baseline_mean, expected_lift, baseline_std,
                         alpha=0.05, power=0.8):
    """
    Calculate required sample size per variant

    Args:
        baseline_mean: Current metric value (e.g., 0.70 for 70% acceptance)
        expected_lift: Expected improvement (e.g., 0.05 for 5pp increase)
        baseline_std: Standard deviation of metric
        alpha: Significance level (default 0.05 for 95% confidence)
        power: Statistical power (default 0.8 for 80% power)

    Returns:
        n_per_variant: Required sample size per variant
    """
    # Z-scores
    z_alpha = stats.norm.ppf(1 - alpha/2)  # Two-tailed
    z_beta = stats.norm.ppf(power)

    # Effect size
    effect_size = expected_lift

    # Sample size calculation
    n = (z_alpha + z_beta)**2 * (2 * baseline_std**2) / effect_size**2

    return int(np.ceil(n))

# Example usage
baseline_acceptance = 0.70
expected_improvement = 0.05  # 5 percentage point lift
std_dev = 0.45  # Typical for binary metrics

n = calculate_sample_size(baseline_acceptance, expected_improvement, std_dev)
print(f"Required sample size per variant: {n}")

# If you have 10,000 users/day
days_needed = n / (10000 * 0.5)  # 0.5 because only half in each variant
print(f"Experiment duration: {days_needed:.1f} days")
```

**Example Calculation:**
```
Baseline acceptance rate: 70%
Target improvement: +5pp (to 75%)
Standard deviation: 0.45

Result: Need ~3,100 samples per variant
If you have 5,000 users/day → 1.2 days minimum

But add buffer for:
- Weekly cycles (run full week)
- Weekday vs weekend effects
- Statistical variance

Recommended duration: 2 weeks
```

---

### Duration Planning

**Minimum Duration Considerations:**

**1. Statistical Significance**
- Run until p < 0.05 AND minimum sample size reached
- Don't stop early just because trending positive

**2. Weekly Cycles**
- Always run complete weeks (7, 14, 21 days)
- Weekday vs weekend behavior differs

**3. User Adaptation**
- New AI features: Users need time to learn → 2+ weeks
- Minor changes: 1 week may suffice

**4. Seasonality**
- Avoid holiday weeks (Black Friday, Christmas)
- Account for monthly cycles (end of month behavior)

**Recommended Durations:**
- Minor changes (UI, parameters): 1-2 weeks
- Model upgrades: 2-3 weeks
- Major features: 3-4 weeks
- Structural changes: 4-6 weeks

---

## Part 4: Running the Experiment

### Pre-Launch Checklist

**Technical Setup:**
- [ ] Randomization code tested
- [ ] Logging captures variant assignment
- [ ] Metrics dashboard shows both variants
- [ ] Alerts configured for crashes/errors
- [ ] Rollback mechanism tested

**Stakeholder Alignment:**
- [ ] Hypothesis documented and shared
- [ ] Success criteria agreed upon
- [ ] Timeline communicated
- [ ] Launch approved by stakeholders

**Baseline Capture:**
- [ ] Pre-experiment baseline established
- [ ] Historical variance documented
- [ ] Seasonality accounted for

---

### Daily Monitoring

**What to Check:**

```
┌────────────────────────────────────────────────────────────┐
│ A/B Test Dashboard - Day 5 of 14                          │
├────────────────────────────────────────────────────────────┤
│ Hypothesis: New prompt → +10% acceptance rate             │
│                                                             │
│ PRIMARY METRIC: Acceptance Rate                            │
│ Control:   72.3% (n=12,450)                                │
│ Treatment: 74.8% (n=12,380)                                │
│ Lift:      +2.5pp (+3.5%)                                  │
│ P-value:   0.12 (not yet significant)                      │
│ On Track:  ⚠️ Trending positive but needs more data       │
│                                                             │
│ GUARDRAILS:                                                 │
│ Error Rate:    1.2% vs 1.3% ✅ (no change)                 │
│ P95 Latency:   1.9s vs 2.1s ⚠️ (+10%, watch closely)      │
│ Cost/query:    $0.031 vs $0.045 ⚠️ (+45%, concerning)     │
│ Safety:        0.15% vs 0.14% ✅ (no change)               │
│                                                             │
│ SECONDARY METRICS:                                          │
│ Regenerations: 28% vs 25% ✅ (-3pp)                        │
│ Edit Rate:     42% vs 40% ✅ (-2pp)                        │
│                                                             │
│ CONCERNS:                                                   │
│ • Cost increased significantly - investigate               │
│ • Latency trending up - monitor                            │
│                                                             │
│ [View Detailed Analysis] [Add Note] [Pause Experiment]    │
└────────────────────────────────────────────────────────────┘
```

**Daily Actions:**
1. Check primary metric progress
2. Verify no guardrail violations
3. Review error logs
4. Read user feedback/reports
5. Document any anomalies
6. Update stakeholders (weekly)

---

### Common Pitfalls to Avoid

**Pitfall 1: Peeking**
- Checking results every hour and stopping when "significant"
- **Solution:** Pre-commit to duration, only check daily for disasters

**Pitfall 2: P-Hacking**
- Trying different metrics until one is significant
- **Solution:** Pre-register primary metric, stick to it

**Pitfall 3: Ignoring Guardrails**
- Primary metric up but cost tripled
- **Solution:** Check guardrails daily, halt if violated

**Pitfall 4: Stopping Too Early**
- Significance reached after 2 days of planned 2-week test
- **Solution:** Run full duration to account for novelty effects

**Pitfall 5: Not Checking A/A**
- Assuming randomization worked correctly
- **Solution:** Occasionally run A/A test (same variant, split traffic) to verify no systematic bias

---

## Part 5: Special AI Considerations

### Controlling for Model Version

**Problem:** Models update during experiment

**Solution:**
```python
# Lock model version at experiment start
experiment_config = {
    'control': {
        'model': 'gpt-4-0613',  # Specific version
        'locked': True
    },
    'treatment': {
        'model': 'gpt-4-1106-preview',
        'locked': True
    }
}

# Don't allow model to auto-update during experiment
```

---

### Handling Cold Start

**Problem:** New users have no personalization data

**Solution 1: Separate Analysis**
```
Analyze separately:
- New users (first session)
- Returning users (2+ sessions)

May see different effects:
- New users: +5% acceptance
- Returning users: +15% acceptance (personalization kicking in)
```

**Solution 2: Cohort by Tenure**
```
Stratify results:
- Day 1 users
- Day 2-7 users
- Week 2+ users
```

---

### Measuring Habituation

**Problem:** Users adapt to AI over time

**Method: Cohort Analysis**
```
Track acceptance rate by days since first exposure:

Day 1:  Control 70% | Treatment 75% | Lift +5pp
Day 3:  Control 71% | Treatment 76% | Lift +5pp
Week 1: Control 72% | Treatment 78% | Lift +6pp  ← Growing
Week 2: Control 72% | Treatment 79% | Lift +7pp  ← Growing
Week 3: Control 72% | Treatment 79% | Lift +7pp  ← Stable

Interpretation: Treatment effect grows as users learn new feature
```

**Implication:** Short tests may underestimate long-term value

---

### Network Effects

**Problem:** Users in treatment may influence users in control

**Example:**
- User A (treatment) shares AI-generated content
- User B (control) sees it, expectations change
- Contamination of control group

**Solutions:**

**1. Cluster Randomization**
```
Instead of randomizing individuals, randomize clusters:
- Geography (all users in SF = treatment)
- Time (all users who join in January = treatment)
- Social network (friends grouped together)
```

**2. Holdout Analysis**
```
Compare:
- Control vs Treatment (may be contaminated)
- Pre-period vs Post-period (everyone eventually gets treatment)
```

**3. Accept Limitation**
```
Acknowledge in analysis:
"Results may be understated due to network effects"
```

---

## Part 6: Statistical Analysis

### Calculating Statistical Significance

**For Binary Metrics (e.g., acceptance rate):**

```python
from scipy import stats

def calculate_significance(control_successes, control_total,
                          treatment_successes, treatment_total):
    """
    Two-proportion z-test

    Returns:
        p_value: Probability difference is due to chance
        lift: Percentage point difference
        relative_lift: Percent improvement
    """
    # Proportions
    p_control = control_successes / control_total
    p_treatment = treatment_successes / treatment_total

    # Pooled proportion
    p_pooled = (control_successes + treatment_successes) / (control_total + treatment_total)

    # Standard error
    se = np.sqrt(p_pooled * (1 - p_pooled) * (1/control_total + 1/treatment_total))

    # Z-score
    z = (p_treatment - p_control) / se

    # P-value (two-tailed)
    p_value = 2 * (1 - stats.norm.cdf(abs(z)))

    # Lifts
    lift = p_treatment - p_control
    relative_lift = (p_treatment / p_control - 1) * 100

    return p_value, lift, relative_lift

# Example
control_accepted = 9000
control_total = 12500

treatment_accepted = 9800
treatment_total = 12500

p_val, abs_lift, rel_lift = calculate_significance(
    control_accepted, control_total,
    treatment_accepted, treatment_total
)

print(f"P-value: {p_val:.4f}")
print(f"Absolute lift: {abs_lift:.3f} ({abs_lift*100:.1f}pp)")
print(f"Relative lift: {rel_lift:.1f}%")
print(f"Significant: {'Yes' if p_val < 0.05 else 'No'}")
```

---

### Confidence Intervals

**Always Report with Confidence Intervals:**

```python
def confidence_interval(successes, total, confidence=0.95):
    """
    Calculate confidence interval for proportion

    Returns:
        lower, upper bounds
    """
    p = successes / total
    z = stats.norm.ppf(1 - (1 - confidence)/2)  # 1.96 for 95%

    se = np.sqrt(p * (1 - p) / total)
    margin = z * se

    return p - margin, p + margin

# Example
control_lower, control_upper = confidence_interval(9000, 12500)
treatment_lower, treatment_upper = confidence_interval(9800, 12500)

print(f"Control: 72.0% (95% CI: {control_lower*100:.1f}% - {control_upper*100:.1f}%)")
print(f"Treatment: 78.4% (95% CI: {treatment_lower*100:.1f}% - {treatment_upper*100:.1f}%)")
```

**Visualization:**
```
Control:    ├────────●────────┤  72% (70.8% - 73.2%)
Treatment:  ├────────────●────────────┤  78.4% (77.2% - 79.6%)
```
**Interpretation:** CIs don't overlap → Highly confident in difference

---

### Multiple Comparison Correction

**Problem:** Testing multiple metrics increases false positive rate

**Solution: Bonferroni Correction**
```
If testing K metrics, use adjusted significance level:
α_adjusted = α / K

Example:
- Testing 5 metrics
- Original α = 0.05
- Adjusted α = 0.05 / 5 = 0.01

Only declare significant if p < 0.01 for any single metric
```

**Better Solution: Pre-Register Primary Metric**
- Designate ONE primary metric
- Use α = 0.05 for that
- Report others as "exploratory" (not for decision-making)

---

## Part 7: Making the Decision

### Launch Decision Framework

**Ship the Treatment IF:**
- ✅ Primary metric improved by target amount (or more)
- ✅ Improvement is statistically significant (p < 0.05)
- ✅ No guardrail metrics degraded beyond threshold
- ✅ Secondary metrics show positive trends (or neutral)
- ✅ Qualitative feedback is positive (or neutral)
- ✅ No major bugs or issues discovered
- ✅ Cost/complexity is acceptable

**Iterate IF:**
- ⚠️ Primary metric improved but not by target amount
- ⚠️ Trending positive but not yet significant
- ⚠️ One guardrail slightly violated but fixable
- ⚠️ Mixed qualitative feedback

**Kill IF:**
- ❌ Primary metric degraded or flat
- ❌ Multiple guardrails violated
- ❌ Significant negative user feedback
- ❌ Cost increase not justified by value
- ❌ Technical issues can't be fixed

---

### Example Decision Matrix

**Scenario 1: Clear Win**
```
Primary: Acceptance +8% (target was +5%), p=0.001
Guardrails: All stable
Qualitative: Users love it

Decision: SHIP ✅
```

**Scenario 2: Mixed Results**
```
Primary: Acceptance +6% (good!), p=0.03 (significant)
Guardrails: Cost +40% (concerning)
Qualitative: Positive

Decision: ITERATE ⚠️
Action: Optimize cost, re-test
```

**Scenario 3: Failed**
```
Primary: Acceptance +1% (not meaningful), p=0.45 (not significant)
Guardrails: All stable
Qualitative: Neutral

Decision: KILL ❌
Learning: Document why it didn't work
```

**Scenario 4: Guardrail Violation**
```
Primary: Acceptance +12% (great!), p<0.001
Guardrails: Latency +50% (users complaining)
Qualitative: Mixed

Decision: ITERATE or KILL ⚠️
Action: Fix latency, re-test
If can't fix: Kill despite primary metric win
```

---

## Part 8: Post-Experiment

### Results Documentation

**Template:**

```
A/B TEST RESULTS

Test ID: AB-2024-001
Experiment Name: Improved Prompt Quality
Hypothesis: Adding few-shot examples → +10% acceptance rate
Duration: Jan 15 - Jan 29, 2024 (2 weeks)

RESULTS SUMMARY:
✅ SUCCESS - Shipping to 100%

Primary Metric: Acceptance Rate
- Control: 72.3% (n=87,450)
- Treatment: 78.9% (n=87,380)
- Lift: +6.6pp (+9.1%)
- P-value: <0.001 (highly significant)
- 95% CI: +6.1pp to +7.1pp

Guardrail Metrics:
- Error rate: 1.2% → 1.3% ✅ (no change)
- P95 latency: 1.8s → 1.9s ✅ (+5%, acceptable)
- Cost/query: $0.030 → $0.033 ✅ (+10%, acceptable)
- Safety: 0.15% → 0.14% ✅ (improved)
- NPS: 42 → 44 ✅ (+2)

Secondary Metrics:
- Regenerations: 28% → 24% ✅ (-4pp)
- Edit rate: 42% → 39% ✅ (-3pp)
- Time to completion: 120s → 105s ✅ (-12%)

Qualitative Feedback:
- 87% positive sentiment in comments
- Top theme: "Outputs are more relevant now"
- 3 bugs reported, all fixed

DECISION: Ship to 100%
Rollout Plan: Gradual over 3 days (10% → 50% → 100%)
Expected Impact: +9% acceptance rate company-wide
Estimated Revenue Impact: +$2.1M/year

LEARNINGS:
1. Few-shot examples significantly improve relevance
2. No latency increase despite longer prompts
3. Cost increase acceptable given value added

NEXT STEPS:
1. Gradual rollout starting Feb 1
2. Monitor for 1 week at 100%
3. Document final results
4. Plan next iteration (chain-of-thought prompting)
```

---

### Learnings Database

**Maintain Cumulative Learnings:**

| Test # | Date | Hypothesis | Result | Lift | Key Learning |
|--------|------|-----------|---------|------|--------------|
| AB-001 | Jan 2024 | Few-shot examples | ✅ Win | +9% | Examples improve relevance |
| AB-002 | Feb 2024 | Lower temperature | ❌ Fail | -2% | Users prefer variety over consistency |
| AB-003 | Mar 2024 | Show confidence | ✅ Win | +5% | Transparency builds trust |
| AB-004 | Apr 2024 | New model (GPT-4) | ✅ Win | +15% | Quality trumps speed |

**Use for:**
- Informing future hypotheses
- Avoiding repeated mistakes
- Training new PMs
- Stakeholder education

---

### Continuous Experimentation

**Build Experimentation Culture:**

**Monthly Goals:**
- Run 2-4 A/B tests
- 1-2 product experiments
- 1-2 infrastructure experiments

**Prioritization:**
- High impact, high confidence → Test immediately
- High impact, low confidence → Test to learn
- Low impact, high confidence → Just ship
- Low impact, low confidence → Deprioritize

**Velocity:**
- Faster iterations > perfection
- Learn quickly from failures
- Ship wins quickly

---

## Summary Checklist

**Before Every A/B Test:**
- [ ] Hypothesis documented
- [ ] Primary metric selected
- [ ] Guardrails defined
- [ ] Sample size calculated
- [ ] Duration planned
- [ ] Stakeholders aligned
- [ ] Code reviewed and tested
- [ ] Logging confirmed
- [ ] Rollback plan ready

**During Test:**
- [ ] Daily monitoring
- [ ] No peeking (wait for duration)
- [ ] Guardrails checked
- [ ] Anomalies documented

**After Test:**
- [ ] Statistical significance calculated
- [ ] Guardrails validated
- [ ] Qualitative feedback reviewed
- [ ] Decision made (ship/iterate/kill)
- [ ] Results documented
- [ ] Learnings captured
- [ ] Stakeholders informed

---

**This A/B testing guide provides:**
- ✅ Complete testing framework for AI products
- ✅ Statistical rigor and calculations
- ✅ Special considerations for AI (drift, adaptation, etc.)
- ✅ Decision frameworks
- ✅ Real code examples
- ✅ Portfolio-ready documentation

**Use this for:**
- Running rigorous AI product experiments
- Interview discussions about evaluation
- Demonstrating data-driven decision making
- Building experimentation culture
