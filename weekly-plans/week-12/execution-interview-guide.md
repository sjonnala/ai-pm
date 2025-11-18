# Execution Interview Guide for AI PMs

## 🎯 Overview

Execution interviews evaluate your ability to deliver products, solve operational problems, and drive results. Unlike product sense (which tests strategic thinking), execution tests tactical skills: metrics, debugging, prioritization, and project management.

For AI PMs, execution questions have unique dimensions: model performance metrics, A/B testing with non-deterministic systems, drift monitoring, and cost management.

This guide covers frameworks, question types, and practice to master execution interviews.

---

## 📋 What Interviewers Are Evaluating

### Core Competencies:
1. **Metrics Fluency** - Can you define and interpret the right metrics?
2. **Analytical Thinking** - Can you diagnose problems systematically?
3. **Prioritization** - Can you decide what to work on and why?
4. **Project Management** - Can you plan and execute work streams?
5. **Stakeholder Management** - Can you align teams and communicate?
6. **Data-Driven Decision Making** - Do you use data effectively?
7. **AI Metrics Expertise** - Do you understand ML-specific metrics? ⭐
8. **Experimentation** - Can you design and interpret A/B tests? ⭐
9. **Trade-off Navigation** - Can you balance speed, quality, and cost?
10. **Operational Excellence** - Can you maintain and improve products post-launch?

---

## 🎨 Common Question Types

### Type 1: Metrics Questions
**Examples:**
- "What metrics would you track for GitHub Copilot?"
- "How would you measure success for an AI chatbot?"
- "What's the North Star metric for Spotify's Discover Weekly?"

**What they're testing:** Understanding of product and ML metrics, ability to connect metrics to business goals

---

### Type 2: Diagnosis / Investigation
**Examples:**
- "DAU dropped 10% last week. How do you investigate?"
- "Recommendation click-through rate decreased. What do you do?"
- "Users are complaining AI responses are slow. Diagnose the issue."

**What they're testing:** Structured problem-solving, hypothesis generation, root cause analysis

---

### Type 3: Prioritization
**Examples:**
- "You have 10 feature requests and 2 engineers. How do you prioritize?"
- "Engineering says AI feature will take 6 months. What do you do?"
- "CEO wants feature X, users want feature Y. How do you decide?"

**What they're testing:** Trade-off evaluation, stakeholder management, judgment

---

### Type 4: Roadmap Planning
**Examples:**
- "Build a 6-month roadmap for AI in Gmail"
- "What should we prioritize: new features vs. improving AI quality?"
- "Plan the next quarter for your AI product"

**What they're testing:** Strategic sequencing, balancing innovation and maintenance, communication

---

### Type 5: Launch / Go-to-Market
**Examples:**
- "How would you launch an AI feature?"
- "Plan the rollout for a new recommendation algorithm"
- "You're launching an AI product - what's your launch strategy?"

**What they're testing:** Launch planning, risk mitigation, phased rollouts, measurement

---

### Type 6: A/B Testing
**Examples:**
- "How would you A/B test a recommendation algorithm?"
- "Design an experiment to test AI vs. non-AI version"
- "What metrics would you track in an A/B test for AI feature X?"

**What they're testing:** Experimentation rigor, statistical thinking, AI-specific testing challenges

---

### Type 7: Trade-offs / Constraints
**Examples:**
- "You need to ship in 2 weeks but AI quality is only 70%. What do you do?"
- "Improving accuracy will double inference cost. How do you decide?"
- "Faster model or better model - which do you ship?"

**What they're testing:** Decision-making under constraints, trade-off analysis, business judgment

---

## 📊 Framework 1: Metrics Questions

### **Step 1: Clarify the Product**
Before jumping to metrics, understand what the product does.

**Questions to Ask:**
- What does this product do?
- Who are the users?
- What's the core value proposition?
- What's the business model?

**Example (GitHub Copilot):**
> "GitHub Copilot is an AI code completion tool that suggests code as developers type. Users are developers (individuals and teams). Core value: Speeds up coding by reducing boilerplate and providing context-aware suggestions. Business model: Subscription ($10/month individual, enterprise plans)."

---

### **Step 2: Define North Star Metric**
The North Star Metric (NSM) is the single metric that best captures the core value you deliver to users.

**Framework:**
```
North Star = Core Value Delivered
```

**Criteria for Good NSM:**
✅ Measures value delivered to users (not just business value)
✅ Actionable (teams can influence it)
✅ Leading indicator (predicts long-term success)
✅ Singular focus (one metric, not 5)

**Examples:**

| Product | North Star Metric |
|---------|-------------------|
| Spotify | Time spent listening per user |
| Airbnb | Nights booked |
| Slack | Messages sent per DAU |
| Netflix | Hours watched per subscriber |
| GitHub Copilot | **Code suggestions accepted per active user** |
| ChatGPT | **Engaged sessions per week** |
| Notion AI | **AI-assisted tasks completed per user** |

**For GitHub Copilot:**
> "The North Star Metric is **code suggestions accepted per active developer**. This captures the core value (helpful code suggestions) and user engagement (active usage). If this number goes up, it means developers are finding Copilot more useful."

---

### **Step 3: Product Metrics (AARRR Framework)**

**AARRR Pirate Metrics:**
- **A**cquisition - How do users discover you?
- **A**ctivation - Do they have a great first experience?
- **R**etention - Do they come back?
- **R**evenue - Do they pay?
- **R**eferral - Do they tell others?

**Example (GitHub Copilot):**

**Acquisition:**
- New sign-ups
- Trial starts
- Traffic sources (organic, paid, referral)
- Conversion rate (visitor → trial)

**Activation:**
- % of trial users who install extension
- % who accept first suggestion
- Time to first accepted suggestion
- "Aha moment": User accepts 3+ suggestions in first session

**Retention:**
- D1, D7, D30 retention (% users active after 1, 7, 30 days)
- Weekly active developers
- Churn rate (% who cancel subscription)
- Resurrection (% of churned users who return)

**Revenue:**
- Free → Paid conversion rate
- Monthly recurring revenue (MRR)
- Average revenue per user (ARPU)
- Lifetime value (LTV)
- Churn rate (revenue and user churn)

**Referral:**
- Viral coefficient (how many new users does each user bring?)
- NPS (Net Promoter Score)
- Team invites (for enterprise)
- Word-of-mouth mentions (social, forums)

---

### **Step 4: AI-Specific Metrics**

For AI products, you need metrics that track AI performance, not just product engagement.

**AI Quality Metrics:**

1. **Suggestion Acceptance Rate**
   - % of AI suggestions users accept
   - Target: >30% for Copilot (varies by product)
   - Tracks: Is the AI actually useful?

2. **Suggestion Relevance Score**
   - Human-rated quality (1-5 scale)
   - Sample-based evaluation
   - Tracks: Are suggestions contextually appropriate?

3. **Edit Distance**
   - How much users modify AI suggestions after accepting
   - Low edit distance = high quality
   - Tracks: Does AI get it right the first time?

4. **Task Completion Rate**
   - % of coding tasks completed with AI help
   - Tracks: Does AI help users finish their work?

**AI Performance Metrics:**

5. **Latency (Response Time)**
   - p50, p95, p99 latency (median, 95th percentile, 99th percentile)
   - Target: <200ms for inline suggestions (Copilot)
   - Tracks: Is AI fast enough to not disrupt flow?

6. **Inference Cost**
   - Cost per suggestion generated
   - Total inference cost per user per month
   - Tracks: Is the AI economically sustainable?

7. **Model Accuracy** (if applicable)
   - Precision, recall, F1 score
   - For classification/prediction tasks
   - Tracks: Model performance on test set

**AI Health Metrics:**

8. **Error Rate**
   - % of suggestions that cause errors or don't compile
   - Tracks: AI reliability

9. **Fallback Rate**
   - % of times AI can't generate suggestion
   - Tracks: Coverage

10. **Drift Detection**
    - Is model performance degrading over time?
    - Compare current accuracy to baseline
    - Tracks: Need for retraining

**User Perception Metrics:**

11. **Satisfaction Scores**
    - Thumbs up/down on suggestions
    - CSAT (Customer Satisfaction Score)
    - Tracks: User happiness

12. **Trust Indicators**
    - % users who review suggestions before accepting
    - % users who disable AI
    - Tracks: User trust in AI

---

### **Step 5: Guardrail Metrics**

Metrics that should NOT go down (or up, for negative metrics).

**Examples:**
- User churn < 5% per month
- Error rate < 1%
- Cost per user < $5/month (to maintain profitability)
- Security incidents = 0
- P99 latency < 2 seconds

**Why Guardrails Matter:**
- Prevent "gaming" the North Star (e.g., don't increase engagement by spamming users)
- Ensure product quality stays high
- Maintain business sustainability

---

### **Step 6: Connect Metrics to Strategy**

Show how metrics drive decisions.

**Example:**
> "If suggestion acceptance rate drops, we'd investigate:
> - Is it a model quality issue? (check offline metrics)
> - Is it a UX issue? (A/B test different suggestion placements)
> - Is it a latency issue? (check p95 latency)
> - Is it context-specific? (segment by language, project type)
> Based on the diagnosis, we'd prioritize improvements: retrain model, optimize prompts, or adjust UX."

---

### **Complete Answer Template:**

**Question:** "What metrics would you track for GitHub Copilot?"

**Answer:**

> "Great question. Let me start by clarifying: GitHub Copilot is an AI code completion tool that helps developers code faster by suggesting contextually relevant code. Users are individual developers and enterprise teams, and the business model is subscription-based.
>
> **North Star Metric:** I'd propose **code suggestions accepted per active developer** as the North Star. This directly measures the value we deliver - if developers accept more suggestions, it means Copilot is useful and they're getting value.
>
> **Product Metrics (AARRR):**
> - **Acquisition:** New sign-ups, trial starts, conversion rate
> - **Activation:** % trial users who accept first suggestion, time to first value
> - **Retention:** D7/D30 retention, weekly active developers, subscription renewal rate
> - **Revenue:** Trial → Paid conversion, MRR, ARPU, LTV
> - **Referral:** Team invites, NPS, word-of-mouth
>
> **AI-Specific Metrics:**
> - **Quality:** Suggestion acceptance rate (target >30%), relevance score, edit distance
> - **Performance:** Latency (p50, p95, p99 - target <200ms), error rate, fallback rate
> - **Cost:** Inference cost per suggestion, cost per user per month
> - **Health:** Drift detection, model accuracy over time
> - **User Perception:** Satisfaction score (thumbs up/down), trust indicators
>
> **Guardrail Metrics:**
> - Churn rate < 5%
> - Error rate < 1%
> - Cost per user < $5/month (to maintain margins)
> - P99 latency < 1 second
>
> **How Metrics Drive Decisions:**
> If acceptance rate drops, we'd segment by language, project type, and user cohort to diagnose. If it's a quality issue, we retrain or optimize prompts. If it's latency, we optimize inference. The key is connecting each metric to actionable improvements.
>
> Does this cover what you were looking for, or would you like me to go deeper on any specific area?"

---

## 🔍 Framework 2: Diagnosis / Investigation Questions

**Question Format:** "Metric X dropped/increased. How do you investigate?"

### **Step-by-Step Framework:**

### **Step 1: Clarify the Situation**

**Questions to Ask:**
- How much did it change? (10%? 50%?)
- Over what time period? (suddenly vs. gradual)
- Is it affecting all users or a segment?
- Are there any recent changes? (new release, marketing campaign, external events)
- What's the baseline/expected value?

**Example:**
> "Before I dive in, let me clarify: Did DAU drop 10% in one day or over a week? Is this affecting all user segments equally, or is it concentrated in specific regions, platforms, or user types? Have there been any recent product changes, outages, or external events like holidays?"

---

### **Step 2: Hypothesize Potential Causes**

**Framework: The 5 Buckets**

1. **Product/Feature Changes**
   - Did we ship a new feature or update?
   - Did we change AI model or algorithm?
   - Did we deprecate a feature?

2. **Technical Issues**
   - Are there outages or performance issues?
   - Increased latency or errors?
   - Mobile vs. web issues?

3. **External Factors**
   - Seasonality (holidays, weekends, summer)
   - Competitor launches
   - News events affecting usage

4. **User Segment Changes**
   - New user cohort with different behavior?
   - Power users churning?
   - Geographic or demographic shifts?

5. **Measurement Issues**
   - Tracking bug?
   - Definition change?
   - Data pipeline issue?

**Example (DAU dropped 10%):**

**Hypotheses:**
1. **Product:** We shipped a redesign last week that confuses users
2. **Product:** AI recommendations are lower quality (model drift)
3. **Technical:** App is crashing on Android (bug in latest release)
4. **External:** Holiday weekend (users traveling)
5. **External:** Competitor launched competing feature
6. **Segment:** Power users churning due to price increase
7. **Measurement:** Tracking pixel broken on mobile web

---

### **Step 3: Prioritize Hypotheses**

Use **Impact** and **Likelihood** to prioritize:

```
High Impact + High Likelihood → Investigate first! 🔴
High Impact + Low Likelihood → Investigate second 🟡
Low Impact → Deprioritize 🟢
```

**Example:**
```
🔴 High Priority:
  - App crashing on Android (High impact: affects 40% of users, High likelihood: we just shipped Android update)
  - AI quality drop (High impact: core feature, Medium likelihood: model hasn't been retrained in 2 months)

🟡 Medium Priority:
  - Holiday weekend (Medium impact, High likelihood: it's a holiday)
  - Tracking bug (High impact if true, Low likelihood: we haven't changed tracking)

🟢 Low Priority:
  - Competitor launch (Low immediate impact)
```

---

### **Step 4: Investigate & Gather Data**

For each hypothesis, define what data would prove/disprove it.

**Example:**

**Hypothesis: App is crashing on Android**
- **Check:** Crash rate by platform (Android vs. iOS)
- **Check:** DAU drop segmented by platform
- **Check:** Error logs for Android app
- **Expected:** If true, Android DAU down significantly, crash rate spiked

**Hypothesis: AI quality dropped (model drift)**
- **Check:** Acceptance rate over time (has it decreased?)
- **Check:** User satisfaction scores (thumbs up/down trend)
- **Check:** Model offline accuracy (current vs. baseline)
- **Expected:** If true, acceptance rate trending down, satisfaction scores lower

**Hypothesis: Holiday weekend**
- **Check:** DAU on this same holiday last year
- **Check:** DAU on other weekends vs. weekdays
- **Expected:** If true, DAU drop is temporary and consistent with historical holiday patterns

---

### **Step 5: Identify Root Cause**

Once data is gathered, triangulate to find root cause.

**Example:**
> "After investigating, I found:
> - DAU drop is **100% on Android** (iOS unaffected)
> - Android crash rate spiked from 0.1% to 15%
> - Crashes correlate with our release on Tuesday
> - Error logs show a null pointer exception in the AI suggestion module
>
> **Root Cause:** Our Android release introduced a bug in the AI suggestion feature that crashes the app for 15% of users."

---

### **Step 6: Recommend Action**

Provide clear next steps with prioritization.

**Immediate Actions (Stop the Bleeding):**
- Rollback Android release immediately
- Notify affected users
- Monitor recovery (DAU should rebound)

**Short-Term Actions (Fix the Problem):**
- Fix the null pointer bug
- Add automated test coverage for this case
- QA re-test before re-deploy
- Staged rollout (10% → 50% → 100%) to catch issues early

**Long-Term Actions (Prevent Recurrence):**
- Improve Android CI/CD pipeline (more automated tests)
- Add crash monitoring alerts (detect spikes within 1 hour)
- Implement gradual rollouts by default (never 0 → 100%)
- Post-mortem: What did we miss in QA? How can we catch this type of bug earlier?

**Communication:**
- Inform leadership: "We identified the root cause and have rolled back. DAU should recover within 24 hours."
- Inform users: "We're aware of crashes on Android and have deployed a fix."

---

### **Complete Answer Template:**

**Question:** "DAU dropped 10% last week. How do you investigate?"

**Answer:**

> "Great question. Let me start by clarifying: Did DAU drop suddenly in one day or gradually over the week? Is it affecting all users or specific segments? Have there been any recent product changes or external events?
>
> [Assuming: Dropped suddenly on Tuesday, all segments, we shipped Android update Monday]
>
> **Step 1: Hypothesize Causes**
> I'd brainstorm potential causes across 5 buckets:
> 1. **Product Changes:** Android release may have introduced a bug
> 2. **Technical Issues:** Possible outages or performance degradation
> 3. **External Factors:** Unlikely (no holiday or major event)
> 4. **User Segments:** Specific cohort churning
> 5. **Measurement:** Tracking issue (low probability)
>
> **Step 2: Prioritize**
> Given we just shipped Android update, I'd prioritize investigating technical issues on Android:
> - **Hypothesis 1:** Android app is crashing → Check crash rate, platform segmentation
> - **Hypothesis 2:** AI performance degraded → Check acceptance rate, latency
>
> **Step 3: Investigate**
> I'd pull data:
> - DAU by platform (Android vs. iOS vs. web)
> - Crash rate by platform (before vs. after release)
> - Error logs for Android
> - AI performance metrics (acceptance rate, latency)
>
> **Step 4: Findings**
> Let's say I found:
> - DAU drop is 100% Android (iOS/web unchanged)
> - Android crash rate spiked from 0.1% to 15%
> - Crashes happening in AI suggestion module
>
> **Root Cause:** Android release introduced a crash bug in AI suggestions.
>
> **Step 5: Recommend Actions**
> **Immediate:**
> - Rollback Android release now
> - Notify users we're fixing the issue
>
> **Short-term:**
> - Fix bug, add test coverage, re-deploy with staged rollout
>
> **Long-term:**
> - Improve CI/CD testing
> - Add crash rate alerts
> - Always use gradual rollouts
> - Post-mortem to prevent similar issues
>
> Does that approach make sense, or would you like me to explore a different hypothesis?"

---

## 🎯 Framework 3: Prioritization Questions

**Question Format:** "How do you prioritize features X, Y, Z?" or "You have limited resources, what do you work on?"

### **Step 1: Clarify Constraints and Goals**

**Questions to Ask:**
- What's the goal? (growth, retention, revenue, quality?)
- What resources do we have? (engineers, time, budget)
- Are there any strategic priorities or commitments?
- What's the timeline?

---

### **Step 2: Define Prioritization Criteria**

**Common Frameworks:**

#### **1. RICE Scoring**
```
RICE = (Reach × Impact × Confidence) / Effort

Reach: How many users affected? (# per quarter)
Impact: How much does it improve their experience? (0.25 = minimal, 3 = massive)
Confidence: How sure are we this will work? (0-100%)
Effort: How much work? (person-months)

Higher RICE score = Higher priority
```

**Example:**

| Feature | Reach | Impact | Confidence | Effort | RICE Score |
|---------|-------|--------|------------|--------|------------|
| AI Chat Feature | 10,000 | 3 | 80% | 6 months | (10,000 × 3 × 0.8) / 6 = **4,000** |
| Fix Latency Bug | 50,000 | 1 | 100% | 1 month | (50,000 × 1 × 1.0) / 1 = **50,000** ✅ |
| New Onboarding | 5,000 | 2 | 60% | 3 months | (5,000 × 2 × 0.6) / 3 = **2,000** |

**Decision:** Prioritize fixing latency bug - highest RICE score.

---

#### **2. Impact vs. Effort Matrix**

```
      High Impact
           │
     Q2    │    Q1  ← Do these first!
           │
─────────────────────
           │
     Q3    │    Q4
           │
      Low Impact
           │
     Low Effort → High Effort
```

**Q1 (High Impact, Low Effort):** Quick wins - do these first!
**Q2 (High Impact, High Effort):** Strategic bets - plan carefully
**Q3 (Low Impact, Low Effort):** Maybes - if there's time
**Q4 (Low Impact, High Effort):** Avoid - not worth it

---

#### **3. Value vs. Complexity (AI-Specific)**

For AI features, consider:
- **User Value:** How much does this solve user pain?
- **AI Complexity:** How hard is it to build/train/deploy AI for this?

```
   High Value
       │
   Q2  │  Q1  ← Prioritize Q1!
       │
───────┼───────
       │
   Q3  │  Q4  ← Avoid Q4
       │
   Low Value
       │
   Low Complexity → High Complexity
```

---

### **Step 3: Apply Framework and Recommend**

**Example:**

**Question:** "You have 10 feature requests and 2 engineers for next quarter. How do you prioritize?"

**Features:**
1. Add AI-powered search
2. Fix mobile app crashes
3. Improve AI response quality
4. Add dark mode
5. Build analytics dashboard
6. Integrate with Slack
7. Add user authentication SSO
8. Improve onboarding flow
9. Add export to PDF
10. Build admin panel

**Answer:**

> "Let me prioritize using RICE and Impact vs. Effort, considering our goal is to improve retention (assuming that's the priority).
>
> **Quick Analysis:**
>
> **Q1: High Impact, Low Effort (Do First):**
> - **Fix mobile app crashes** - High impact (affects 30% of users, causing churn), Low effort (1 week fix)
>   - RICE: (30,000 × 2 × 1.0) / 0.25 = 240,000 ✅
>
> - **Improve onboarding flow** - High impact (increases activation), Medium effort (2-3 weeks)
>   - RICE: (5,000 new users × 2 × 0.8) / 0.75 = 10,667
>
> **Q2: High Impact, High Effort (Strategic Bets):**
> - **Improve AI response quality** - High impact (core feature), High effort (4-6 weeks of model work)
>   - RICE: (50,000 × 3 × 0.7) / 1.5 = 70,000
>
> - **Add AI-powered search** - High impact (new capability), Very high effort (8 weeks)
>   - RICE: (50,000 × 2 × 0.6) / 2 = 30,000
>
> **Q3/Q4: Lower Priority:**
> - Add dark mode - Medium impact, Low effort (nice-to-have)
> - Slack integration - Medium impact, Medium effort
> - SSO - Low impact (only enterprise), Medium effort
> - Admin panel - Low impact (internal), High effort
>
> **My Recommendation:**
>
> **Week 1-2:**
> - **Engineer 1 & 2:** Fix mobile crashes (urgent, quick win)
>
> **Week 3-6:**
> - **Engineer 1:** Improve onboarding flow (increase activation)
> - **Engineer 2:** Start improving AI response quality (core value)
>
> **Week 7-12:**
> - **Engineer 1 & 2:** Continue AI quality improvements + testing
>
> **Deferred to Next Quarter:**
> - AI-powered search (strategic but can wait)
> - Integrations (Slack, SSO)
> - Nice-to-haves (dark mode, PDF export)
>
> **Rationale:**
> - Crashes are urgent (losing users now)
> - Onboarding improves activation (more users getting value)
> - AI quality is our core differentiator (long-term retention)
> - These three deliver most impact with 2 engineers in 3 months
>
> Does this align with strategic priorities, or is there something else I should consider?"

---

### **Step 4: Acknowledge Trade-offs**

Always acknowledge what you're NOT doing and why.

> "By prioritizing AI quality and onboarding, we're deferring AI search and integrations. The trade-off is we won't have new marquee features to market this quarter, but we'll have a more reliable, higher-quality product that retains users better. I think this is the right choice because retention is our biggest problem right now, but I'd want to validate with leadership and customers."

---

## 🚀 Framework 4: A/B Testing Questions (AI-Specific)

**Question Format:** "How would you A/B test [AI feature]?"

### **Challenges with A/B Testing AI:**
1. **Non-determinism:** AI outputs vary, hard to isolate what changed
2. **Long feedback loops:** Users may not realize AI improved for days/weeks
3. **Interaction effects:** AI learns from user feedback, creating feedback loops
4. **Cost:** Running multiple AI models in parallel is expensive

---

### **Step-by-Step Framework:**

### **Step 1: Define the Hypothesis**

**Template:**
> "We believe that [change] will result in [metric improvement] for [user segment]."

**Example:**
> "We believe that using GPT-4 instead of GPT-3.5 for article generation will increase **suggestion acceptance rate from 35% to 45%** for **content marketers** because GPT-4 produces higher-quality, more coherent long-form content."

---

### **Step 2: Choose Test Design**

**Options:**

#### **A) Simple A/B Test**
- Control (A): Current version (GPT-3.5)
- Treatment (B): New version (GPT-4)
- Split: 50/50

**When to use:** Most common, when you have one clear alternative.

#### **B) A/B/C or Multi-Variant Test**
- Control (A): GPT-3.5
- Treatment B: GPT-4
- Treatment C: GPT-4 with custom prompt engineering

**When to use:** When you have multiple variants to test.

#### **C) Staged Rollout**
- Week 1: 5% GPT-4
- Week 2: 10% GPT-4
- Week 3: 25% GPT-4
- Week 4: 50% GPT-4

**When to use:** High-risk changes, want to derisk gradually.

#### **D) Interleaved Test (AI-Specific)**
- Show user results from both models simultaneously
- Let user choose which they prefer
- Measure which gets more engagement

**When to use:** Recommendation systems, search ranking, where you can show multiple options.

---

### **Step 3: Define Metrics**

**Primary Metric:**
The one metric you're trying to move.

**Example:** Suggestion acceptance rate

**Secondary Metrics:**
Supporting metrics to understand behavior.

**Examples:**
- Edit distance (how much users modify suggestions)
- User satisfaction score
- Time saved per task
- Session length

**Guardrail Metrics:**
Metrics that should NOT get worse.

**Examples:**
- Error rate (should stay <1%)
- Latency (should stay <5s)
- Cost per user (should stay under budget)
- Churn rate (should not increase)

---

### **Step 4: Determine Sample Size and Duration**

**Sample Size Calculation:**

Need to know:
- **Baseline metric value:** e.g., 35% acceptance rate
- **Minimum detectable effect (MDE):** How much improvement matters? e.g., 5 percentage points (35% → 40%)
- **Significance level (α):** Usually 0.05 (95% confidence)
- **Power (1-β):** Usually 0.8 (80% power to detect effect)

**Use online calculator (e.g., Evan Miller's) or formula:**

For proportions (like acceptance rate):
```
n = 2 × (Z_α/2 + Z_β)² × p × (1-p) / (MDE)²

Where:
- Z_α/2 = 1.96 (for 95% confidence)
- Z_β = 0.84 (for 80% power)
- p = baseline rate (0.35)
- MDE = minimum detectable effect (0.05)
```

**Example:**
```
n = 2 × (1.96 + 0.84)² × 0.35 × 0.65 / (0.05)²
n ≈ 1,568 users per variant
Total needed: 3,136 users (1,568 control + 1,568 treatment)
```

**Duration:**
- If you have 500 users per day, you need 3,136 / 500 = **~6 days** minimum
- But: Run for at least 1 full week to account for day-of-week effects
- Ideal: **2-4 weeks** to ensure statistical validity and account for novelty effects

---

### **Step 5: Address AI-Specific Challenges**

**Challenge 1: Non-Determinism**
- **Problem:** GPT-4 gives different outputs each time, even with same input
- **Solution:**
  - Fix random seed for controlled comparison (if API allows)
  - OR run multiple trials per input and average
  - OR accept variance and increase sample size

**Challenge 2: Cost**
- **Problem:** Running GPT-4 for 50% of users doubles inference cost
- **Solution:**
  - Start with smaller test (10% GPT-4 vs. 10% GPT-3.5, 80% not in test)
  - Use cost as a guardrail metric
  - Calculate ROI: If acceptance increases by 10% and retention improves, is the cost worth it?

**Challenge 3: Model Learning/Feedback Loops**
- **Problem:** If models learn from user feedback, control and treatment diverge over time
- **Solution:**
  - Freeze models during test (no learning)
  - OR randomize at session level (not user level) to reduce feedback loop

**Challenge 4: Long-Term Effects**
- **Problem:** Users may not realize AI improved until they've used it for weeks
- **Solution:**
  - Run test for longer (4+ weeks)
  - Measure retention and long-term engagement, not just immediate metrics

---

### **Step 6: Analyze Results**

**Statistical Significance:**
- Use t-test or z-test to compare control vs. treatment
- p-value < 0.05 → statistically significant

**Practical Significance:**
- Even if statistically significant, is the improvement meaningful?
- Example: Acceptance rate increases from 35.0% to 35.5% (statistically significant) - but is 0.5% worth the cost?

**Segment Analysis:**
- Did the change work for all user segments?
- Example: GPT-4 works great for long articles (45% acceptance) but worse for short posts (30% acceptance)
- Decision: Roll out GPT-4 only for long articles

**Guardrail Check:**
- Did any guardrail metrics degrade?
- Example: Latency increased from 3s to 8s → unacceptable, don't ship

---

### **Step 7: Make Decision and Communicate**

**Decision Framework:**

```
✅ Ship if:
- Primary metric improved (statistically + practically significant)
- Guardrails not violated
- ROI positive (benefit > cost)

🟡 Iterate if:
- Mixed results (some segments improved, others not)
- Guardrails slightly violated (can we optimize?)
- Improvement too small (can we tweak and re-test?)

❌ Don't ship if:
- No improvement or negative impact
- Guardrails violated
- Cost too high for benefit
```

**Communication:**

> "We ran an A/B test of GPT-4 vs. GPT-3.5 for 2 weeks with 5,000 users. Results:
> - **Primary metric:** Acceptance rate increased from 35% to 42% (+7 pp, p<0.01) ✅
> - **Latency:** Increased from 3s to 7s ⚠️
> - **Cost:** $1.50 per user per month (vs. $0.20 previously) ⚠️
> - **Satisfaction:** Improved from 3.8 to 4.2 stars ✅
>
> **Recommendation:** Ship GPT-4, but only for Pro tier users (they're willing to pay for quality and tolerate latency). Keep GPT-3.5 for free tier to manage costs.
>
> **Next Steps:**
> - Rollout GPT-4 to Pro tier (gradual: 10% → 50% → 100%)
> - Optimize latency (target: <5s)
> - Monitor retention and churn for Pro users
> - Revisit cost optimization in Q2 (prompt caching, model distillation)"

---

### **Complete Answer Template:**

**Question:** "How would you A/B test a new recommendation algorithm for Spotify Discover Weekly?"

**Answer:**

> "Great question. Let me walk through how I'd design this experiment.
>
> **Step 1: Define Hypothesis**
> We believe that the new recommendation algorithm will increase **Discover Weekly listening time per user from 30 min to 40 min** for **active Spotify users** because it better personalizes based on recent listening patterns and mood.
>
> **Step 2: Test Design**
> I'd use a **simple A/B test**:
> - Control (A): Current recommendation algorithm
> - Treatment (B): New recommendation algorithm
> - Randomization: User-level (each user gets one algorithm for entire test)
> - Split: 50/50 (or start with 10/10/80 to derisk)
>
> **Step 3: Metrics**
> - **Primary:** Discover Weekly listening time per user (minutes per week)
> - **Secondary:**
>   - Tracks saved from Discover Weekly
>   - Completion rate (% of playlist listened to)
>   - User satisfaction (thumbs up/down on songs)
> - **Guardrails:**
>   - Overall Spotify listening time (should not decrease)
>   - Churn rate (should not increase)
>   - Latency (playlist generation should stay <10s)
>
> **Step 4: Sample Size and Duration**
> - **Baseline:** 30 min per user per week, assume std dev = 15 min
> - **MDE:** 10 min improvement (33% increase)
> - **Calculation:** Need ~1,500 users per variant (using power = 0.8, α = 0.05)
> - **Duration:** 4 weeks minimum
>   - Why 4 weeks: Discover Weekly refreshes weekly, need multiple cycles to see behavior
>   - Accounts for novelty effect (users may try new recs out of curiosity initially)
>
> **Step 5: Address AI Challenges**
> - **Non-determinism:** Freeze model weights during test, no online learning
> - **User history:** Ensure control and treatment users have similar listening histories (stratified randomization)
> - **Cold start:** Exclude brand new users (need history for recommendations)
>
> **Step 6: Analysis Plan**
> After 4 weeks:
> - **Statistical test:** t-test to compare treatment vs. control listening time
> - **Segment analysis:** Break down by user type (new vs. power users), genre preference, geography
> - **Qualitative:** Sample user feedback, analyze which types of songs worked vs. didn't
>
> **Step 7: Decision Criteria**
> - ✅ **Ship if:** Listening time increases >10%, no guardrail violations, works across segments
> - 🟡 **Iterate if:** Mixed results by segment (e.g., works for rock fans, not for pop fans)
> - ❌ **Don't ship if:** No improvement, or hurts guardrails (churn increases)
>
> **Expected Outcome:**
> If the new algorithm works, I'd plan a gradual rollout (10% → 50% → 100%) over 2-3 weeks, monitoring closely for any unexpected issues.
>
> Does this approach make sense, or would you like me to dive deeper into any specific area?"

---

## ⏱️ Time Management (45-minute interview)

**Recommended Time Allocation:**

| Phase | Time | What You're Doing |
|-------|------|-------------------|
| **Clarify** | 2-3 min | Understand the question, ask clarifications |
| **Structure** | 1-2 min | Outline your approach |
| **Analyze** | 10-15 min | Work through framework (metrics, diagnosis, etc.) |
| **Recommend** | 3-5 min | Provide clear recommendation |
| **Deep Dives / Q&A** | 20-25 min | Interviewer probes specific areas |

**Tips:**
- ⏰ Execution questions often have multiple parts - budget time accordingly
- 📊 Interviewers love to drill into details - have data ready
- 🎯 Be ready to pivot - interviewer may change the scenario mid-question

---

## 🗣️ Communication Best Practices

### 1. **Start with Clarifying Questions**
Don't assume - ask!

✅ "Before I dive in, can I clarify - is this DAU drop affecting all platforms, or is it concentrated in mobile?"

### 2. **Be Structured**
Use frameworks. State your approach upfront.

✅ "I'm going to approach this using the AARRR framework to define metrics, then prioritize based on our North Star metric."

### 3. **Use Numbers**
Execution is about data. Be specific.

❌ Bad: "Acceptance rate should be high"
✅ Good: "Target acceptance rate of 40%, up from current 30%"

### 4. **Show Trade-off Thinking**
Acknowledge pros and cons.

✅ "GPT-4 improves quality by 20% but costs 10x more. Given our premium pricing model, I think the quality is worth it."

### 5. **Connect to Business Impact**
Always tie execution to business outcomes.

✅ "Improving onboarding activation from 40% to 50% would add 500 weekly active users, increasing MRR by ~$5,000."

### 6. **Be Decisive**
Don't waffle. Make a clear recommendation.

✅ "Based on this analysis, I recommend we prioritize fixing the crash bug over adding new features."

---

## 📝 Practice Question Bank

### Metrics Questions

**Q1:** What metrics would you track for ChatGPT?
<details>
<summary>Key Considerations</summary>

**North Star:** Engaged sessions per user per week (measures value and stickiness)

**AARRR:**
- Acquisition: Sign-ups, organic vs. paid traffic
- Activation: First message sent, first valuable response received
- Retention: D1/D7/D30, weekly active users
- Revenue: Free → Plus conversion, MRR, churn
- Referral: Share rate, NPS

**AI-Specific:**
- Response quality (thumbs up/down rate)
- Latency (p50, p95, p99)
- Cost per conversation
- Conversation length (turns)
- Task completion rate

**Guardrails:**
- Error rate <1%
- Inappropriate content <0.01%
- Churn <5% monthly
</details>

**Q2:** What metrics would you track for a AI resume builder?
<details>
<summary>Key Considerations</summary>

**North Star:** Resumes created and downloaded per user

**AARRR:**
- Acquisition: Landing page → sign-up conversion
- Activation: First resume section completed
- Retention: Return to edit resume
- Revenue: Free → Premium conversion
- Referral: Shared on social, referred friends

**AI-Specific:**
- AI suggestion acceptance rate
- Resume quality score (hiring manager ratings)
- Time saved vs. manual creation
- Template usage (AI-generated vs. manual)

**Guardrails:**
- Accuracy (no hallucinated experience)
- Formatting quality (parseable by ATS)
</details>

---

### Diagnosis Questions

**Q3:** Click-through rate on AI recommendations dropped 15%. Investigate.
<details>
<summary>Approach</summary>

**Clarify:**
- Over what time period?
- All users or specific segments?
- Recent changes?

**Hypotheses:**
1. Model drift (quality degraded)
2. UI change made recs less visible
3. User preferences shifted
4. Recommendation diversity decreased (showing same items)
5. Competitor launched better product
6. Seasonal (holidays, etc.)

**Prioritize:**
- Check model performance metrics first (likely cause)
- Segment by user type, item category, platform

**Investigate:**
- Offline model accuracy - has it decreased?
- User satisfaction scores
- Recommendation diversity (are we showing same items repeatedly?)
- A/B test: old model vs. current model

**Recommend:**
- If model drift: Retrain with fresh data
- If diversity: Improve recommendation algorithm to balance relevance and diversity
- If UI: A/B test UI changes
</details>

---

**Q4:** AI feature latency increased from 2s to 10s. Diagnose.
<details>
<summary>Approach</summary>

**Clarify:**
- All users or specific requests?
- Gradual or sudden increase?
- Recent deployments?

**Hypotheses:**
1. Model size increased (recent update to larger model)
2. Traffic spike (more concurrent requests than infrastructure can handle)
3. Upstream dependency slow (API provider latency)
4. Database query slow (retrieving context for RAG)
5. Cold start issues (serverless functions timing out)

**Investigate:**
- Check: Latency by model version (before/after recent deploy)
- Check: Request volume (spike in traffic?)
- Check: Upstream API latency (e.g., OpenAI API status)
- Check: Database query time (slow queries in logs)
- Check: Infrastructure metrics (CPU, memory, GPU utilization)

**Recommend:**
- If model size: Use smaller/faster model or optimize prompts
- If traffic: Scale infrastructure, add load balancing
- If upstream: Cache frequent requests, use fallback model
- If database: Optimize queries, add indexes, cache context
</details>

---

### Prioritization Questions

**Q5:** You have bandwidth for one major feature next quarter. Options: (1) Improve AI accuracy by 10%, (2) Add multimodal (image) support, (3) Build mobile app. How do you decide?
<details>
<summary>Approach</summary>

**Clarify:**
- What's our strategic goal? (growth, retention, revenue?)
- What's current user pain? (quality issues? need mobile?)
- What's competitive landscape? (do competitors have images/mobile?)

**Framework: RICE + Strategic Fit**

**Option 1: Improve AI accuracy by 10%**
- Reach: All 50,000 users
- Impact: Medium (better quality → higher satisfaction)
- Confidence: 70% (requires significant model work)
- Effort: 3 months
- RICE: (50,000 × 1.5 × 0.7) / 3 = 17,500
- Strategic: Strengthens core value prop

**Option 2: Add multimodal (image) support**
- Reach: 20,000 users (subset who need images)
- Impact: High (new capability, differentiator)
- Confidence: 60% (new technology, uncertain adoption)
- Effort: 4 months
- RICE: (20,000 × 2.5 × 0.6) / 4 = 7,500
- Strategic: Differentiator, future-forward

**Option 3: Build mobile app**
- Reach: 30,000 potential mobile users
- Impact: High (new platform, accessibility)
- Confidence: 80% (well-understood technology)
- Effort: 4 months
- RICE: (30,000 × 2 × 0.8) / 4 = 12,000
- Strategic: Expands TAM, improves retention

**Recommendation:**
I'd choose **Option 1: Improve AI accuracy** if:
- We have retention problems (users churning due to quality)
- Competitors have similar accuracy (need to stay competitive)
- Mobile/multimodal can wait

I'd choose **Option 3: Mobile app** if:
- We're losing users who need mobile
- Current quality is "good enough"
- Growth is top priority

**Deciding factors:**
- What's our biggest problem? (retention → accuracy, growth → mobile)
- What do users ask for most?
- What's the competitive pressure?

**My choice (assuming retention is priority):**
> "I'd choose improving AI accuracy by 10% because our core value is AI quality. If users don't trust our AI, they won't stick around. Mobile and multimodal are important, but they don't matter if our core product isn't excellent. We can revisit mobile in Q2 once we've shored up quality."
</details>

---

## ✅ Final Checklist

Before your interview, ensure you can:

- [ ] Define North Star + AARRR + AI metrics for any product
- [ ] Diagnose a metric drop systematically (5 buckets of hypotheses)
- [ ] Prioritize features using RICE or Impact/Effort
- [ ] Design an A/B test for AI features (hypothesis, metrics, sample size)
- [ ] Explain trade-offs clearly (cost vs. quality, latency vs. accuracy)
- [ ] Use data and numbers (not vague statements)
- [ ] Connect execution to business impact
- [ ] Communicate structured and decisively

---

## 🎯 Sample Practice Routine

**Week Before Interview:**

**Day 1-2:** Master frameworks (AARRR, RICE, diagnosis structure)
**Day 3-4:** Practice 5-10 questions from question bank
**Day 5-6:** Mock interviews with peers
**Day 7:** Light review, rest, be confident!

---

## 🎬 Conclusion

Execution interviews test your ability to get things done. For AI PMs, this means understanding both traditional PM execution (metrics, prioritization, debugging) and AI-specific challenges (model drift, A/B testing with non-determinism, cost management).

**Keys to Success:**
1. Be structured (use frameworks)
2. Be data-driven (use numbers)
3. Be decisive (make clear recommendations)
4. Show AI fluency (address AI-specific considerations)
5. Practice (repetition builds confidence)

You've got this! Now go practice and ace those execution interviews! 🚀

---

**Next Steps:**
1. Practice defining metrics for 5 AI products
2. Work through 3 diagnosis questions
3. Practice prioritization with RICE
4. Design an A/B test for an AI feature
5. Mock interview with a peer

Good luck! 💪
