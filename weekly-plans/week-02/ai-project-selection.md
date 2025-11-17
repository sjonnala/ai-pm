# How to Choose AI Projects - 1-Pager

**Created:** [Date]
**Week 2 Deliverable**

---

## Framework Overview

A systematic approach to evaluating and selecting AI/ML projects based on **Impact**, **Feasibility**, and **Risk**.

---

## 1. Impact Assessment

### User Value Potential
**Questions to ask:**
- How many users does this affect?
- How critical is this pain point? (Scale: 1-5)
- What's the frequency of the problem? (Daily/Weekly/Monthly)
- What's the magnitude of improvement? (Time saved, quality increase, etc.)

**Scoring:**
- **High (3 pts):** Critical pain, daily frequency, affects majority of users
- **Medium (2 pts):** Important pain, weekly frequency, affects significant segment
- **Low (1 pt):** Nice-to-have, occasional, affects small segment

### Business Impact
**Metrics:**
- Revenue impact (direct or indirect)
- Cost reduction
- User acquisition/retention
- Competitive differentiation
- Strategic alignment

**Scoring:**
- **High (3 pts):** Direct revenue impact or major strategic initiative
- **Medium (2 pts):** Significant efficiency gains or competitive parity
- **Low (1 pt):** Incremental improvement

---

## 2. Feasibility Assessment

### Data Availability (Most Critical Factor)

**Questions:**
- Do we have the data? (Yes/No/Can acquire)
- Is there enough data? (Volume threshold varies by problem)
- Is the data labeled? (For supervised learning)
- Is the data quality high? (Accuracy, completeness, freshness)
- Do we have legal rights to use it?

**Data Quality Scale (1-5):**
- **5:** Large, labeled, high-quality dataset already exists
- **4:** Large dataset exists, needs labeling
- **3:** Small dataset exists, can be augmented
- **2:** No data, but feasible to collect
- **1:** No data, difficult/expensive to collect

**Rule of Thumb:**
- If data score < 3, reconsider the project
- Data availability is the #1 predictor of ML success

### Technical Complexity

**Factors:**
- Model complexity (simple regression → LLMs)
- Infrastructure requirements (can run on CPU vs. needs GPU cluster)
- Real-time vs. batch processing
- Integration complexity
- Dependency on external APIs/models

**Scoring:**
- **Low complexity (3 pts):** Established techniques, simple integration
- **Medium complexity (2 pts):** Some research needed, moderate infra
- **High complexity (1 pt):** Cutting-edge research, significant infra

### Team Capability

**Questions:**
- Do we have ML engineering talent?
- Do we have relevant domain expertise?
- Have we built similar systems before?
- Do we have infrastructure (MLOps, deployment)?

**Scoring:**
- **High (3 pts):** Strong team, proven track record
- **Medium (2 pts):** Some gaps, need to hire/upskill
- **Low (1 pt):** Significant gaps, steep learning curve

### Time to Value

**Questions:**
- How long to MVP? (Weeks/Months/Quarters)
- How long to see business impact?
- What's the iteration cycle time?

**Scoring:**
- **Fast (3 pts):** < 2 months to MVP
- **Medium (2 pts):** 2-6 months to MVP
- **Slow (1 pt):** > 6 months to MVP

---

## 3. Risk Assessment

### Technical Risk

**Questions:**
- Is the ML approach proven or experimental?
- What's the performance threshold for success?
- How critical is the use case? (errors = disaster?)
- Can we fall back to non-ML solution?

**Risk Level:**
- **Low:** Proven techniques, graceful degradation possible
- **Medium:** Some unknowns, acceptable error rate
- **High:** Unproven approach, high accuracy required

### Ethical & Safety Risk

**Questions:**
- Could this cause user harm?
- Are there bias/fairness concerns?
- Privacy implications?
- Transparency requirements?
- Regulatory constraints?

**For each "Yes" answer, document:**
- The specific risk
- Mitigation strategy
- Acceptance criteria

### Business Risk

**Questions:**
- What if it doesn't work?
- What's the opportunity cost?
- Does this create dependencies?
- Could this cannibalize existing value?

---

## 4. Decision Matrix

### Impact-Feasibility Grid

```
High Impact  |  Strategic Bets  |  Quick Wins
             |  (do carefully)  |  (do first!)
             |                  |
-------------|------------------|-------------
Low Impact   |  Don't Do        |  Fill-Ins
             |  (deprioritize)  |  (if capacity)
             |                  |
             Low Feasibility    High Feasibility
```

**Quick Wins:** High impact + High feasibility
- **Action:** Prioritize immediately
- **Example:** Improve existing model with more data

**Strategic Bets:** High impact + Low feasibility
- **Action:** Break down into phases, validate incrementally
- **Example:** New LLM-powered feature (high value, complex)

**Fill-Ins:** Low impact + High feasibility
- **Action:** Do if you have extra capacity
- **Example:** Small optimization to existing feature

**Don't Do:** Low impact + Low feasibility
- **Action:** Deprioritize
- **Example:** Novel research project with unclear value

---

## 5. RICE Scoring for AI Projects

Modified RICE framework for AI/ML:

**R = Reach** (# users impacted per quarter)
**I = Impact** (massive=3, high=2, medium=1, low=0.5)
**C = Confidence** (high=100%, medium=80%, low=50%)
**E = Effort** (person-months, including ML engineer + PM + data scientist time)

**Formula:** (R × I × C) / E

**AI-Specific Additions:**

**Data Score (D):** 1-5 scale from above
**Risk Multiplier (RM):**
- Low risk: 1.0
- Medium risk: 0.8
- High risk: 0.6

**Modified Formula:** (R × I × C × D × RM) / E

---

## 6. Applied Examples

### Example 1: Email Auto-Categorization

**Impact:**
- User value: High (saves time daily)
- Business: Medium (improves engagement)
- **Score: 5/6**

**Feasibility:**
- Data: 5 (have millions of labeled emails)
- Complexity: 3 (established NLP techniques)
- Team: 3 (done similar projects)
- Time: 3 (2-3 weeks to MVP)
- **Score: 14/15**

**Risk:**
- Technical: Low (proven approach)
- Ethical: Low (no sensitive decisions)
- Business: Low (can fall back to manual)
- **Risk Multiplier: 1.0**

**RICE:**
- Reach: 100,000 users/quarter
- Impact: 2 (high)
- Confidence: 100%
- Effort: 1 person-month
- Data: 5
- **Score: (100,000 × 2 × 1.0 × 5 × 1.0) / 1 = 1,000,000**

**Decision: QUICK WIN** ✅ - Prioritize immediately

---

### Example 2: AI-Powered Video Editing Assistant

**Impact:**
- User value: High (saves hours per video)
- Business: High (key differentiator)
- **Score: 6/6**

**Feasibility:**
- Data: 3 (need to collect user video data)
- Complexity: 1 (cutting-edge multimodal ML)
- Team: 2 (need to upskill)
- Time: 1 (6+ months to MVP)
- **Score: 7/15**

**Risk:**
- Technical: High (new models, quality threshold critical)
- Ethical: Medium (user content, copyright)
- Business: Medium (expensive to build)
- **Risk Multiplier: 0.6**

**RICE:**
- Reach: 10,000 users/quarter
- Impact: 3 (massive)
- Confidence: 50%
- Effort: 6 person-months
- Data: 3
- **Score: (10,000 × 3 × 0.5 × 3 × 0.6) / 6 = 4,500**

**Decision: STRATEGIC BET** ⚠️ - Break into phases, validate incrementally

**Phase 1 (Quick Win):** Simple cuts (remove silence) - 2 weeks
**Phase 2 (Test):** Scene detection with existing models - 1 month
**Phase 3 (Bet):** Custom ML for creative editing - 3+ months

---

### Example 3: [Your Project]

**Impact:**
- User value: [High/Medium/Low] - [Why?]
- Business: [High/Medium/Low] - [Why?]
- **Score: ___/6**

**Feasibility:**
- Data: ___/5 - [Describe data situation]
- Complexity: ___/3 - [Describe technical approach]
- Team: ___/3 - [Describe team capability]
- Time: ___/3 - [Time to MVP]
- **Score: ___/15**

**Risk:**
- Technical: [Low/Medium/High] - [Why?]
- Ethical: [Low/Medium/High] - [Why?]
- Business: [Low/Medium/High] - [Why?]
- **Risk Multiplier: ___**

**RICE:**
- Reach: ___ users/quarter
- Impact: ___ (massive=3, high=2, medium=1, low=0.5)
- Confidence: ___% (high=100%, medium=80%, low=50%)
- Effort: ___ person-months
- Data: ___
- **Score: ___**

**Decision: [QUICK WIN / STRATEGIC BET / FILL-IN / DON'T DO]**

**Action Plan:**

---

## 7. Decision Checklist

Before committing to an AI project, validate:

### Must-Haves:
- [ ] Clear user problem identified (not just "let's use AI")
- [ ] Data exists or is feasible to collect (score ≥ 3)
- [ ] Success metrics defined
- [ ] Failure mode acceptable or mitigated
- [ ] Team has necessary skills or can acquire them

### Strong Yes Indicators:
- [ ] Users actively seeking solutions
- [ ] Large labeled dataset available
- [ ] Proven ML techniques apply
- [ ] Can ship MVP in < 3 months
- [ ] Clear business value

### Red Flags:
- [ ] No data (score < 3)
- [ ] "We should use AI because AI is cool"
- [ ] No clear success metric
- [ ] Unacceptable failure modes (safety-critical, no fallback)
- [ ] Needs perfection (99%+ accuracy) without path to get there

---

## 8. Key Principles

1. **Data First:** If data doesn't exist, the project is 10x harder
2. **Start Simple:** Prove value with simple ML before going complex
3. **Iterate Fast:** Prefer projects with short feedback loops
4. **Think Hybrid:** Combine ML + rules + human-in-loop
5. **Failure Modes:** Always have a fallback
6. **Measure Everything:** Track model performance + business metrics
7. **User Value:** AI is a means, not the end

---

## Interview Application

**Question:** "How do you decide which AI projects to build?"

**Your Answer (using this framework):**

"I use a three-part framework: Impact, Feasibility, and Risk.

**Impact:** I assess user value and business impact. For AI specifically, I focus on whether we're solving a real user struggle, not just adding AI for AI's sake.

**Feasibility:** The #1 factor is data availability. I've learned that most AI projects fail due to data issues, so I score data quality on a 1-5 scale and only proceed if we're at a 3 or above. I also consider technical complexity and team capability.

**Risk:** I evaluate technical, ethical, and business risk. For high-risk projects, I look for phased approaches or ways to validate incrementally.

I plot projects on an impact-feasibility matrix to identify 'Quick Wins' vs. 'Strategic Bets.' Quick Wins get prioritized for immediate execution, while Strategic Bets are broken into phases.

For example, [use one of your examples above]."

---

**Practice explaining this framework in 3 minutes or less!**
