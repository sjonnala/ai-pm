# AI Drift Monitoring Strategy

**Created:** [Date]
**Week 8 Deliverable**
**Product:** [Your AI Product Name]
**Version:** [e.g., 1.0]
**Owner:** [Your Name]

---

## Executive Summary

**Product:** [Name of your AI product]

**Why Drift Monitoring Matters:**
- AI models degrade over time as the world changes
- Input distributions shift
- Relationships between inputs and outputs evolve
- Undetected drift leads to poor user experience

**Monitoring Approach:**
- Real-time statistical drift detection
- Performance metric tracking
- User feedback monitoring
- Automated alerting

**Retraining Cadence:**
- Reactive: When drift detected
- Proactive: Quarterly baseline
- Emergency: Critical performance drop

**Success Metric:** Detect drift before user satisfaction drops >5%

---

## Table of Contents

1. [Types of Drift](#types-of-drift)
2. [Detection Methods](#detection-methods)
3. [Metrics to Monitor](#metrics-to-monitor)
4. [Monitoring Infrastructure](#monitoring-infrastructure)
5. [Alerting Strategy](#alerting-strategy)
6. [Retraining Triggers](#retraining-triggers)
7. [Response Playbook](#response-playbook)
8. [Evaluation & Validation](#evaluation--validation)

---

## Part 1: Types of Drift

### Data Drift (Covariate Shift)

**Definition:** The distribution of input features changes over time

**Example:**
```
Baseline (Training Time):
- Average input length: 150 characters
- 80% English, 15% Spanish, 5% other languages
- Peak usage: 9am-5pm

Current (Production):
- Average input length: 220 characters (+47%)
- 70% English, 20% Spanish, 10% other (+5% other)
- Peak usage: Now 24/7 (global expansion)

→ Input distribution has shifted
```

**Impact:**
- Model may not generalize well to new inputs
- Performance degrades on shifted distribution
- Predictions less confident

**Detection:**
- Statistical tests (KS test, Chi-square)
- Distribution comparison
- Feature drift scores

**Response:**
- Collect representative new data
- Retrain on updated distribution
- Update feature engineering

---

### Concept Drift

**Definition:** The relationship between inputs and outputs changes

**Example:**
```
Baseline:
- Keyword "viral" in positive context = Marketing content
- Model learned: "viral" → Marketing classification

Current:
- Keyword "viral" in negative context = Medical/pandemic
- Relationship changed: "viral" → Medical classification

→ Same input, different meaning
```

**Impact:**
- Model predictions become incorrect
- Accuracy drops
- User trust erodes

**Detection:**
- Monitor prediction accuracy over time
- Compare to ground truth (when available)
- Track user feedback sentiment

**Response:**
- Relabel data with new context
- Retrain model
- Update training data to reflect new relationships

---

### Prediction Drift

**Definition:** The distribution of model outputs changes

**Example:**
```
Baseline:
- Sentiment: 40% positive, 40% neutral, 20% negative

Current:
- Sentiment: 60% positive, 30% neutral, 10% negative

→ Model outputting more positive predictions

Possible causes:
- Input distribution changed (users happier)
- Model degraded (everything looks positive)
- Data quality issue
```

**Impact:**
- May indicate model malfunction
- Could signal data drift
- Affects downstream systems

**Detection:**
- Track output distribution
- Compare to historical baseline
- Monitor diversity metrics

**Response:**
- Investigate root cause
- Check for data quality issues
- Validate with ground truth
- Retrain if confirmed drift

---

### Label Drift

**Definition:** The definition/meaning of labels changes over time

**Example:**
```
Baseline:
- "Spam" meant commercial promotions

Current:
- "Spam" now includes political messages, crypto scams, AI-generated content

→ Label definition expanded
```

**Impact:**
- Old labels no longer accurate
- Model misses new spam types
- User complaints increase

**Detection:**
- Review label definitions
- Analyze misclassifications
- User feedback patterns

**Response:**
- Update labeling guidelines
- Relabel historical data
- Retrain with new definitions

---

## Part 2: Detection Methods

### Statistical Tests for Data Drift

#### Kolmogorov-Smirnov (KS) Test

**Use Case:** Continuous features (e.g., age, price, length)

**How It Works:**
- Compares cumulative distributions
- Returns p-value (probability distributions are same)
- Threshold: p < 0.05 indicates significant drift

**Implementation:**
```python
from scipy import stats

def detect_drift_ks(baseline_data, current_data, threshold=0.05):
    """
    Detect drift using KS test

    Args:
        baseline_data: Historical data from training time
        current_data: Recent production data
        threshold: P-value threshold (default 0.05)

    Returns:
        is_drift: Boolean indicating if drift detected
        p_value: Statistical p-value
        drift_score: Magnitude of drift (0-1)
    """
    statistic, p_value = stats.ks_2samp(baseline_data, current_data)

    is_drift = p_value < threshold
    drift_score = statistic  # 0 = identical, 1 = completely different

    return is_drift, p_value, drift_score

# Example usage
baseline_lengths = [120, 145, 160, 155, ...]  # Training data
current_lengths = [180, 210, 195, 220, ...]   # Production data

is_drift, p_value, score = detect_drift_ks(baseline_lengths, current_lengths)

if is_drift:
    print(f"⚠️ Drift detected! p={p_value:.4f}, score={score:.2f}")
    # Trigger alert
```

**Interpretation:**
- p_value < 0.01: Strong evidence of drift (immediate attention)
- p_value 0.01-0.05: Moderate evidence (monitor closely)
- p_value > 0.05: No significant drift

---

#### Chi-Square Test

**Use Case:** Categorical features (e.g., category, language, type)

**How It Works:**
- Compares frequency distributions
- Tests if categorical distributions differ
- Threshold: p < 0.05 indicates significant drift

**Implementation:**
```python
from scipy.stats import chi2_contingency
import numpy as np

def detect_drift_chi2(baseline_counts, current_counts, threshold=0.05):
    """
    Detect drift in categorical features using Chi-square test

    Args:
        baseline_counts: Dictionary of category counts from training
        current_counts: Dictionary of category counts from production

    Returns:
        is_drift: Boolean
        p_value: Statistical p-value
        drift_score: Normalized chi-square statistic
    """
    # Ensure same categories
    all_categories = set(baseline_counts.keys()) | set(current_counts.keys())

    baseline = [baseline_counts.get(cat, 0) for cat in all_categories]
    current = [current_counts.get(cat, 0) for cat in all_categories]

    # Chi-square test
    chi2, p_value, dof, expected = chi2_contingency([baseline, current])

    is_drift = p_value < threshold

    # Normalize chi2 statistic for drift score (0-1 scale)
    n = sum(baseline) + sum(current)
    drift_score = min(1.0, chi2 / n)  # Cramér's V approximation

    return is_drift, p_value, drift_score

# Example usage
baseline_langs = {'en': 800, 'es': 150, 'fr': 50}
current_langs = {'en': 700, 'es': 200, 'fr': 100}  # ES & FR increased

is_drift, p_value, score = detect_drift_chi2(baseline_langs, current_langs)
```

---

#### Population Stability Index (PSI)

**Use Case:** Overall feature stability, commonly used in industry

**How It Works:**
- Measures distribution shift
- PSI < 0.1: No drift
- PSI 0.1-0.25: Moderate drift
- PSI > 0.25: Significant drift

**Formula:**
```
PSI = Σ (actual% - expected%) × ln(actual% / expected%)
```

**Implementation:**
```python
import numpy as np

def calculate_psi(baseline, current, bins=10):
    """
    Calculate Population Stability Index

    Args:
        baseline: Baseline feature values
        current: Current feature values
        bins: Number of bins for bucketing

    Returns:
        psi: PSI value
        interpretation: Drift level
    """
    # Create bins based on baseline
    breakpoints = np.percentile(baseline, np.linspace(0, 100, bins+1))
    breakpoints[0] = -np.inf
    breakpoints[-1] = np.inf

    # Bin both distributions
    baseline_counts = np.histogram(baseline, bins=breakpoints)[0]
    current_counts = np.histogram(current, bins=breakpoints)[0]

    # Convert to percentages
    baseline_pct = baseline_counts / len(baseline)
    current_pct = current_counts / len(current)

    # Avoid division by zero
    baseline_pct = np.where(baseline_pct == 0, 0.0001, baseline_pct)
    current_pct = np.where(current_pct == 0, 0.0001, current_pct)

    # Calculate PSI
    psi = np.sum((current_pct - baseline_pct) * np.log(current_pct / baseline_pct))

    # Interpretation
    if psi < 0.1:
        interpretation = "No drift"
    elif psi < 0.25:
        interpretation = "Moderate drift - monitor"
    else:
        interpretation = "Significant drift - retrain"

    return psi, interpretation

# Example
baseline = np.random.normal(150, 30, 1000)
current = np.random.normal(170, 35, 1000)  # Shifted distribution

psi, interpretation = calculate_psi(baseline, current)
print(f"PSI: {psi:.3f} - {interpretation}")
```

---

#### Jensen-Shannon Divergence

**Use Case:** Comparing probability distributions

**How It Works:**
- Symmetric measure of similarity
- Range: 0 (identical) to 1 (completely different)
- More robust than KL divergence (handles zeros)

**Implementation:**
```python
from scipy.spatial import distance

def js_divergence(p, q):
    """
    Calculate Jensen-Shannon divergence between two distributions

    Args:
        p: Baseline distribution (histogram)
        q: Current distribution (histogram)

    Returns:
        js_div: JS divergence (0-1, lower is better)
    """
    # Normalize to probability distributions
    p = np.array(p) / np.sum(p)
    q = np.array(q) / np.sum(q)

    # Calculate JS divergence
    js_div = distance.jensenshannon(p, q)

    return js_div

# Example
baseline_dist = [100, 200, 300, 400]  # Feature distribution
current_dist = [80, 180, 350, 390]    # Slight shift

js = js_divergence(baseline_dist, current_dist)
print(f"JS Divergence: {js:.3f}")

# Interpretation
if js < 0.1:
    print("No drift")
elif js < 0.3:
    print("Moderate drift")
else:
    print("Significant drift")
```

---

### Performance-Based Drift Detection

#### Accuracy Degradation Monitoring

**Method:** Track model accuracy over time

**Implementation:**
```python
import pandas as pd
from datetime import datetime, timedelta

def monitor_accuracy_drift(predictions_df, ground_truth_df, window_days=7):
    """
    Monitor accuracy over rolling windows

    Args:
        predictions_df: DataFrame with columns [timestamp, prediction, request_id]
        ground_truth_df: DataFrame with columns [request_id, ground_truth]
        window_days: Size of rolling window

    Returns:
        drift_detected: Boolean
        accuracy_trend: DataFrame with accuracy over time
    """
    # Join predictions with ground truth
    df = predictions_df.merge(ground_truth_df, on='request_id')
    df['correct'] = df['prediction'] == df['ground_truth']

    # Calculate rolling accuracy
    df = df.set_index('timestamp').sort_index()
    rolling_accuracy = df['correct'].rolling(f'{window_days}D').mean()

    # Detect drift (accuracy drop > 5%)
    baseline_accuracy = rolling_accuracy.iloc[:len(rolling_accuracy)//4].mean()
    current_accuracy = rolling_accuracy.iloc[-1]

    drift_detected = (baseline_accuracy - current_accuracy) > 0.05

    accuracy_trend = pd.DataFrame({
        'date': rolling_accuracy.index,
        'accuracy': rolling_accuracy.values
    })

    return drift_detected, accuracy_trend

# Alert if accuracy drops
if drift_detected:
    print(f"⚠️ Accuracy drift! Baseline: {baseline_accuracy:.2%}, Current: {current_accuracy:.2%}")
```

---

#### Confidence Score Tracking

**Method:** Monitor model confidence distribution

**Rationale:** Decreasing confidence may indicate drift

**Implementation:**
```python
def monitor_confidence_drift(baseline_confidences, current_confidences):
    """
    Monitor if model confidence is degrading

    Args:
        baseline_confidences: List of confidence scores from training/baseline
        current_confidences: List of recent confidence scores

    Returns:
        drift_detected: Boolean
        confidence_drop: Percentage point change
    """
    baseline_mean = np.mean(baseline_confidences)
    current_mean = np.mean(current_confidences)

    confidence_drop = baseline_mean - current_mean

    # Alert if average confidence drops > 10 percentage points
    drift_detected = confidence_drop > 0.10

    return drift_detected, confidence_drop

# Example
baseline_conf = [0.92, 0.88, 0.95, 0.90, ...]  # High confidence
current_conf = [0.75, 0.72, 0.80, 0.78, ...]   # Lower confidence

drift, drop = monitor_confidence_drift(baseline_conf, current_conf)
if drift:
    print(f"⚠️ Confidence drift detected! Drop: {drop:.1%}")
```

---

## Part 3: Metrics to Monitor

### Input Metrics

| Metric | Description | Monitoring Frequency | Alert Threshold |
|--------|-------------|---------------------|-----------------|
| Input length distribution | Avg, median, p95, p99 | Hourly | >15% change |
| Token count distribution | For text inputs | Hourly | >20% change |
| Language distribution | % per language | Daily | >10% change in any language |
| Category distribution | % per category | Daily | >15% change in any category |
| Feature value ranges | Min, max, mean per feature | Hourly | >2 std dev from baseline |
| Null/missing rate | % of missing values | Hourly | >5% increase |
| Special character rate | % inputs with special chars | Daily | >10% change |

---

### Output Metrics

| Metric | Description | Monitoring Frequency | Alert Threshold |
|--------|-------------|---------------------|-----------------|
| Prediction distribution | % per class/category | Hourly | >10% change |
| Confidence distribution | Mean, median confidence | Hourly | >10 pp drop |
| Output length distribution | For generated text | Daily | >15% change |
| Diversity metrics | Unique outputs / Total | Daily | >20% decrease |
| Response time | P50, P95, P99 latency | Real-time | >15% increase |
| Error rate | % of failed predictions | Real-time | >1% increase |

---

### Performance Metrics

| Metric | Description | Monitoring Frequency | Alert Threshold |
|--------|-------------|---------------------|-----------------|
| Accuracy (when GT available) | Overall accuracy | Daily | >3% drop |
| Precision | Per class | Weekly | >5% drop |
| Recall | Per class | Weekly | >5% drop |
| F1 Score | Harmonic mean | Weekly | >5% drop |
| AUC-ROC | For classification | Weekly | >0.03 drop |
| NDCG (for ranking) | Ranking quality | Daily | >5% drop |

---

### User Feedback Metrics

| Metric | Description | Monitoring Frequency | Alert Threshold |
|--------|-------------|---------------------|-----------------|
| Acceptance rate | % outputs accepted | Daily | >5% drop |
| Thumbs up rate | % positive feedback | Daily | >5% drop |
| Regeneration rate | % users regenerate | Daily | >5% increase |
| Edit rate | % users edit output | Daily | >10% increase |
| User satisfaction (1-10) | Explicit ratings | Weekly | >0.5 point drop |
| Net Promoter Score | Would recommend? | Monthly | >5 point drop |

---

## Part 4: Monitoring Infrastructure

### Data Collection

**What to Log:**

```python
# Example log entry
{
    "request_id": "req_123456",
    "timestamp": "2024-01-15T14:30:00Z",
    "user_id": "user_789",

    # Input features
    "input": {
        "text": "[user input]",
        "length": 245,
        "language": "en",
        "category": "blog_post",
        "special_chars_count": 5
    },

    # Model metadata
    "model": {
        "version": "v2.3",
        "endpoint": "gpt-4",
        "temperature": 0.7,
        "max_tokens": 1000
    },

    # Output
    "output": {
        "text": "[AI output]",
        "length": 892,
        "confidence": 0.87,
        "generation_time_ms": 1234
    },

    # User feedback (if available)
    "feedback": {
        "accepted": true,
        "edited": false,
        "thumbs_up": true,
        "regenerated": false
    },

    # Ground truth (if available later)
    "ground_truth": {
        "label": "[correct output]",
        "verified_at": "2024-01-16T10:00:00Z"
    }
}
```

---

### Monitoring Dashboard

**Real-Time Dashboard (Grafana / Datadog):**

```
┌────────────────────────────────────────────────────────────┐
│ AI Model Drift Monitoring                                  │
│ Last Updated: 2 minutes ago                                │
├────────────────────────────────────────────────────────────┤
│                                                             │
│ DATA DRIFT INDICATORS                                       │
│                                                             │
│ Input Length Distribution:                                  │
│ Baseline: 150 ± 80 chars                                   │
│ Current:  220 ± 120 chars  ⚠️ +47% DRIFT DETECTED         │
│ PSI: 0.28 (SIGNIFICANT)                                    │
│                                                             │
│ Language Distribution:                                      │
│ EN: 70% (was 80%) ⚠️                                       │
│ ES: 20% (was 15%) ⚠️                                       │
│ Other: 10% (was 5%) ⚠️                                     │
│ Chi-square p-value: 0.001 (DRIFT)                          │
│                                                             │
│ ────────────────────────────────────────────────────────── │
│                                                             │
│ PERFORMANCE DRIFT                                           │
│                                                             │
│ Accuracy (7-day rolling):                                   │
│ Week -4: 92% ████████████                                  │
│ Week -3: 91% ███████████░                                  │
│ Week -2: 90% ███████████                                   │
│ Week -1: 88% ██████████░░  ⚠️ -4% vs baseline             │
│ This week: 87% ██████████░  ⚠️ THRESHOLD BREACHED         │
│                                                             │
│ Confidence Distribution:                                    │
│ Baseline mean: 0.89                                        │
│ Current mean:  0.82  ⚠️ -7pp drop                          │
│                                                             │
│ ────────────────────────────────────────────────────────── │
│                                                             │
│ USER FEEDBACK DRIFT                                         │
│                                                             │
│ Acceptance Rate:  68% (was 74%)  ⚠️ -6%                    │
│ Thumbs Up:        65% (was 70%)  ⚠️ -5%                    │
│ Regenerations:    35% (was 28%)  ⚠️ +7%                    │
│                                                             │
│ ────────────────────────────────────────────────────────── │
│                                                             │
│ 🚨 ACTIVE ALERTS (3)                                        │
│ • Input distribution drift (PSI > 0.25)                    │
│ • Accuracy below threshold (<90%)                          │
│ • User acceptance declining                                │
│                                                             │
│ [View Detailed Metrics] [Trigger Retraining] [Dismiss]    │
└────────────────────────────────────────────────────────────┘
```

---

### Drift Detection Pipeline

**Automated Pipeline (Runs Hourly/Daily):**

```python
# Pseudocode for drift detection pipeline

def drift_detection_pipeline():
    """
    Automated drift detection and alerting
    Runs on schedule (e.g., hourly)
    """

    # 1. Collect recent data
    current_data = fetch_production_data(last_hours=24)
    baseline_data = fetch_baseline_data()  # From training time or last retrain

    # 2. Run drift tests
    drift_results = {}

    # Test each feature
    for feature in MONITORED_FEATURES:
        if is_continuous(feature):
            is_drift, p_val, score = detect_drift_ks(
                baseline_data[feature],
                current_data[feature]
            )
        else:  # Categorical
            is_drift, p_val, score = detect_drift_chi2(
                baseline_data[feature],
                current_data[feature]
            )

        drift_results[feature] = {
            'drift_detected': is_drift,
            'p_value': p_val,
            'drift_score': score
        }

    # 3. Check performance metrics
    accuracy_drift = check_accuracy_degradation(current_data)
    confidence_drift = check_confidence_degradation(current_data)

    # 4. Aggregate results
    total_drifted_features = sum(r['drift_detected'] for r in drift_results.values())
    critical_drift = total_drifted_features > 3  # More than 3 features drifting

    # 5. Alert if needed
    if critical_drift or accuracy_drift or confidence_drift:
        send_alert(
            severity='P1' if critical_drift else 'P2',
            message=f"Drift detected in {total_drifted_features} features",
            details=drift_results
        )

        # Log to monitoring system
        log_drift_event(drift_results)

        # Auto-trigger retraining if conditions met
        if should_auto_retrain(drift_results):
            trigger_retraining_workflow()

    # 6. Update dashboard
    update_monitoring_dashboard(drift_results)

    return drift_results
```

---

## Part 5: Alerting Strategy

### Alert Levels

**P0 (Critical - Page On-Call):**
- Accuracy drops > 10% in 1 hour
- Error rate > 10%
- Safety violations spike
- Complete service outage

**Action:** Immediate investigation + potential rollback

---

**P1 (High - Slack + Email within 1 hour):**
- Data drift: PSI > 0.25 or p-value < 0.01
- Accuracy drops 5-10%
- User acceptance drops > 10%
- Confidence drops > 15 pp

**Action:** Investigate within 1 hour, plan retraining

---

**P2 (Medium - Email digest):**
- Moderate drift: PSI 0.1-0.25
- Accuracy drops 3-5%
- User feedback trending negative
- Performance metrics degrading

**Action:** Monitor closely, plan investigation

---

**P3 (Low - Weekly summary):**
- Minor drift detected
- Metrics approaching thresholds
- Trends worth watching

**Action:** Include in weekly review

---

### Alert Configuration

```python
# Alert thresholds configuration

ALERT_THRESHOLDS = {
    'data_drift': {
        'psi': {
            'p2': 0.1,   # Moderate drift
            'p1': 0.25   # Significant drift
        },
        'ks_test_p_value': {
            'p2': 0.05,
            'p1': 0.01
        }
    },

    'accuracy': {
        'p3': 0.03,   # 3% drop
        'p2': 0.05,   # 5% drop
        'p1': 0.10,   # 10% drop
        'p0': 0.15    # 15% drop (critical)
    },

    'confidence': {
        'p2': 0.10,   # 10pp drop
        'p1': 0.15    # 15pp drop
    },

    'user_feedback': {
        'acceptance_rate': {
            'p2': -0.05,  # 5% drop
            'p1': -0.10   # 10% drop
        },
        'thumbs_up_rate': {
            'p2': -0.05,
            'p1': -0.10
        }
    },

    'error_rate': {
        'p2': 0.02,    # 2%
        'p1': 0.05,    # 5%
        'p0': 0.10     # 10%
    }
}
```

---

### Alert Fatigue Prevention

**Strategies:**

1. **Sustained Degradation:**
   - Require degradation to persist for X hours before alerting
   - Prevents alerts on temporary fluctuations

2. **Percentage-Based Thresholds:**
   - Use % change, not absolute values
   - Adapts to different baseline levels

3. **Multi-Signal Confirmation:**
   - Require 2+ drift indicators before P1 alert
   - Single metric drift → P2 alert

4. **Alert Aggregation:**
   - Batch related alerts
   - Send digest instead of individual alerts

5. **Regular Threshold Review:**
   - Monthly review of alert frequency
   - Adjust thresholds if too sensitive/insensitive

---

## Part 6: Retraining Triggers

### When to Retrain

**Trigger 1: Significant Drift Detected**
```
IF PSI > 0.25 for any critical feature
OR 3+ features showing drift (p < 0.01)
OR Chi-square test significant for main feature
THEN trigger retraining investigation
```

**Trigger 2: Performance Degradation**
```
IF accuracy drops > 5% sustained for 3+ days
OR acceptance rate drops > 10%
OR user satisfaction drops > 1 point (1-10 scale)
THEN trigger retraining
```

**Trigger 3: Sufficient New Data**
```
IF new labeled data > 20% of original training set
AND new data shows different patterns
THEN consider retraining
```

**Trigger 4: Scheduled Cadence**
```
IF time since last retrain > 3 months
AND new data available
THEN trigger scheduled retraining
```

**Trigger 5: Major Changes**
```
IF new feature launched
OR user base expanded to new geography/demographic
OR product pivot
THEN retrain to adapt
```

---

### Retraining Decision Matrix

| Drift Level | Performance | Data Available | Action |
|-------------|-------------|----------------|--------|
| Significant (PSI>0.25) | Good (accuracy stable) | Yes | Monitor + Plan retrain |
| Significant | Poor (<5% drop) | Yes | **Retrain immediately** |
| Significant | Poor | No | Collect data + temp fixes |
| Moderate (PSI 0.1-0.25) | Good | Yes | Schedule retrain (2 weeks) |
| Moderate | Poor | Yes | **Retrain immediately** |
| None | Poor | Yes | Investigate (may not be drift) |

---

### Retraining Process

**Step 1: Data Collection (1-2 days)**
```
1. Export recent production data
2. Filter for quality
3. Label new data (human annotators or user feedback)
4. Validate labels (inter-rater agreement > 0.75)
5. Combine with original training data
```

**Step 2: Model Retraining (1-3 days)**
```
1. Update training dataset
2. Retrain model
3. Validate on test set
4. Ensure no regressions on original test cases
```

**Step 3: Evaluation (2-3 days)**
```
1. Offline evaluation on new test set
2. Compare to current production model
3. Red-team new model
4. Human evaluation (sample 500+ outputs)
```

**Step 4: A/B Test (1-2 weeks)**
```
1. Deploy new model to 10% of traffic
2. Monitor all metrics closely
3. Compare to baseline
4. Gradually increase to 50% if successful
```

**Step 5: Full Rollout (1-2 days)**
```
1. Monitor for 24 hours at 50%
2. If stable, roll out to 100%
3. Update baseline for future drift detection
4. Document learnings
```

**Total Time:** 2-4 weeks from detection to full deployment

---

## Part 7: Response Playbook

### Drift Detected - What Now?

**Immediate Actions (Within 1 hour):**

1. **Verify the Alert**
   - Is this a real drift or monitoring glitch?
   - Check data quality
   - Review recent changes (code deploys, config changes)

2. **Assess Impact**
   - How many users affected?
   - Is performance actually degrading?
   - Are users complaining?

3. **Communicate**
   - Notify stakeholders
   - Create incident ticket
   - Start investigation log

---

**Short-Term Mitigation (Within 24 hours):**

**Option 1: Quick Fixes**
- Adjust model parameters (temperature, thresholds)
- Update prompts (for LLMs)
- Add preprocessing to handle new patterns

**Option 2: Rollback**
- If new model caused drift, roll back to previous version
- Monitor to see if drift persists

**Option 3: Hybrid Approach**
- Route drifted segment to different model
- Use rule-based fallback for problematic cases

---

**Long-Term Resolution (1-4 weeks):**

1. **Root Cause Analysis**
   - Why did drift occur?
   - What changed in the real world?
   - Is this temporary or permanent?

2. **Data Collection**
   - Gather representative samples of new distribution
   - Label with high quality
   - Validate labels

3. **Model Retraining**
   - Follow retraining process (see Part 6)
   - Update baseline
   - Deploy improved model

4. **Prevention**
   - Add new patterns to test set
   - Improve monitoring to catch earlier
   - Update alerts if needed

---

### Incident Response Template

```
DRIFT INCIDENT REPORT

Incident ID: [ID]
Detected: [Timestamp]
Severity: [P0/P1/P2/P3]
Status: [Investigating / Mitigating / Resolved]

SUMMARY:
[Brief description of drift detected]

IMPACT:
- Users affected: [X]%
- Performance impact: [Metric] dropped from [Y]% to [Z]%
- Business impact: [Revenue / retention / satisfaction]

ROOT CAUSE:
[What caused the drift? Data distribution change? Model degradation?]

TIMELINE:
- [Time]: Drift first occurred (estimated)
- [Time]: Alert triggered
- [Time]: Investigation started
- [Time]: Mitigation deployed
- [Time]: Resolved

MITIGATION:
[What we did to address it]

RESOLUTION:
[Final fix - retrained model / updated config / etc.]

PREVENTION:
[How we'll prevent this in the future]

LESSONS LEARNED:
1. [Lesson 1]
2. [Lesson 2]
3. [Lesson 3]
```

---

## Part 8: Evaluation & Validation

### Validating Drift Detection

**Test Your Drift Monitoring:**

**Synthetic Drift Test:**
```python
# Create synthetic drift to test monitoring

# Baseline data (what model was trained on)
baseline = np.random.normal(150, 30, 10000)

# Synthetic drift scenarios
drift_scenarios = {
    'no_drift': np.random.normal(150, 30, 1000),      # Same distribution
    'mild_drift': np.random.normal(160, 32, 1000),    # Slight shift
    'moderate_drift': np.random.normal(170, 35, 1000), # Clear shift
    'severe_drift': np.random.normal(200, 50, 1000)   # Major shift
}

# Test if monitoring catches each scenario correctly
for scenario, data in drift_scenarios.items():
    is_drift, p_val, score = detect_drift_ks(baseline, data)
    psi, interpretation = calculate_psi(baseline, data)

    print(f"{scenario}:")
    print(f"  KS Test: {'DRIFT' if is_drift else 'NO DRIFT'} (p={p_val:.4f})")
    print(f"  PSI: {psi:.3f} ({interpretation})")
    print()

# Verify:
# - no_drift: Should NOT trigger alerts
# - mild_drift: Should trigger P2 alert
# - moderate_drift: Should trigger P1 alert
# - severe_drift: Should trigger P0 alert
```

---

### Success Metrics for Drift Monitoring

**Effectiveness Metrics:**

| Metric | Target | Measurement |
|--------|--------|-------------|
| Early Detection Rate | >90% | % of real drifts caught before 5% perf drop |
| False Positive Rate | <10% | % of alerts that weren't real drift |
| Time to Detection | <48 hours | Time from drift start to alert |
| Time to Resolution | <2 weeks | Time from detection to retrained model live |
| Performance Recovery | >95% | % of original performance restored after retrain |

---

### Continuous Improvement

**Monthly Review:**

1. **Alert Review**
   - How many drift alerts?
   - True positives vs. false positives?
   - Missed drifts?

2. **Threshold Tuning**
   - Are thresholds too sensitive/insensitive?
   - Adjust based on historical patterns

3. **Detection Method Evaluation**
   - Which tests caught drift earliest?
   - Any tests consistently wrong?

4. **Retraining Effectiveness**
   - Did retraining resolve drift?
   - How long did benefits last?

---

## Summary Checklist

**Drift Monitoring Setup:**
- [ ] Data logging infrastructure in place
- [ ] Baseline distributions captured
- [ ] Statistical tests implemented (KS, Chi-square, PSI)
- [ ] Performance tracking automated
- [ ] User feedback collection active
- [ ] Monitoring dashboard built
- [ ] Alerts configured
- [ ] Retraining pipeline ready
- [ ] Response playbook documented

**Ongoing Operations:**
- [ ] Daily dashboard review
- [ ] Weekly drift report
- [ ] Monthly threshold review
- [ ] Quarterly comprehensive evaluation
- [ ] Retraining when triggered
- [ ] Post-retraining validation

---

**This drift monitoring strategy provides:**
- ✅ Comprehensive understanding of drift types
- ✅ Multiple detection methods
- ✅ Clear alerting thresholds
- ✅ Automated monitoring infrastructure
- ✅ Retraining decision framework
- ✅ Incident response playbook
- ✅ Portfolio-ready documentation

**Use this for:**
- Building drift monitoring systems
- Ensuring model reliability over time
- Interview discussions about ML operations
- Demonstrating MLOps expertise
