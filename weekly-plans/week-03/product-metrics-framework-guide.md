# Product Metrics Framework Guide for AI PMs

## 🎯 Overview

Metrics are the language of product management. Great PMs use metrics to:
- Define success clearly
- Make data-driven decisions
- Communicate progress
- Identify problems early
- Prioritize ruthlessly

For AI PMs, metrics are even more critical because you need to measure both product performance AND AI model performance.

This guide covers all essential metrics frameworks every AI PM must master.

---

## 📚 Table of Contents

1. [Metrics Fundamentals](#metrics-fundamentals)
2. [AARRR (Pirate Metrics)](#aarrr-pirate-metrics)
3. [HEART Framework](#heart-framework)
4. [Input vs. Output Metrics](#input-vs-output-metrics)
5. [AI-Specific Metrics](#ai-specific-metrics)
6. [Metrics for Different Product Stages](#metrics-for-different-product-stages)
7. [Common Metrics Pitfalls](#common-metrics-pitfalls)
8. [Building Your Metrics Dashboard](#building-your-metrics-dashboard)

---

## 📊 Metrics Fundamentals

### **What Makes a Good Metric?**

**The SMART Framework:**

**S - Specific**
- ❌ Bad: "Improve user engagement"
- ✅ Good: "Increase daily active users by 20%"

**M - Measurable**
- ❌ Bad: "Users love the product"
- ✅ Good: "NPS score of 50+"

**A - Actionable**
- ❌ Bad: "Revenue" (you can't directly control this)
- ✅ Good: "Conversion rate from free to paid" (you can optimize this)

**R - Relevant**
- ❌ Bad: "Page views" (vanity metric if you're not ad-supported)
- ✅ Good: "Content pieces published" (if you're a content tool)

**T - Time-bound**
- ❌ Bad: "Increase retention"
- ✅ Good: "Increase 30-day retention from 40% to 55% by Q2"

---

### **Types of Metrics:**

**1. North Star Metric**
- The ONE metric that best captures core value delivered
- Example: Spotify = "Hours listened per user"

**2. Primary Metrics**
- 3-5 key metrics that drive the North Star
- Example: For Spotify, primary metrics might be songs added, playlist creation, recommendation click-through

**3. Secondary Metrics**
- Supporting metrics that provide context
- Example: App crashes, latency, customer support tickets

**4. Guardrail Metrics**
- Metrics that shouldn't degrade
- Example: User churn <5%, cost per user <$10

---

### **Leading vs. Lagging Indicators**

**Lagging Indicators:**
- What happened in the past
- Example: Revenue, churn, retention
- Useful for measuring outcomes
- But too late to change

**Leading Indicators:**
- Predict future outcomes
- Example: Feature adoption, engagement, user satisfaction
- Useful for making proactive decisions
- Can intervene before problems compound

**PM Strategy:** Focus on leading indicators for day-to-day decisions, use lagging indicators to validate long-term impact.

---

## 🏴‍☠️ AARRR (Pirate Metrics)

The most popular framework for consumer products and SaaS.

**AARRR = Acquisition, Activation, Retention, Revenue, Referral**

---

### **1. Acquisition**

**Definition:** How do users discover you?

**Key Metrics:**

**Traffic Metrics:**
- Unique visitors
- Traffic sources (organic, paid, direct, referral)
- Landing page visits

**Conversion:**
- Sign-up rate (visitors → sign-ups)
- Cost per acquisition (CPA)
- Quality of acquisition (do they stick around?)

**Channels to Track:**
- Organic search (SEO)
- Paid ads (Google, Facebook, LinkedIn)
- Content marketing (blog, YouTube)
- Social media
- Referrals
- Partnerships

**Example - AI Writing Assistant:**
```
Acquisition Metrics:
- Landing page visitors: 10,000/month
- Sign-up rate: 8% (800 sign-ups)
- Primary channel: SEO (40%), content marketing (30%), ads (20%)
- CPA: $25
- Goal: Reduce CPA to $15, increase sign-up rate to 12%
```

---

### **2. Activation**

**Definition:** Do users have a great first experience?

**The "Aha Moment":**
The moment when users first experience core value.

**Examples:**
- Facebook: Add 7 friends in 10 days
- Dropbox: Upload first file
- Slack: Send 2,000 messages as a team
- AI Writing Assistant: **Generate and use first AI draft**

**Key Metrics:**

**Time to Value:**
- How long from sign-up to "aha moment"?
- Target: As short as possible (minutes, not days)

**Activation Rate:**
- % of sign-ups who reach "aha moment"
- Industry benchmark: 40-60% is good

**Onboarding Completion:**
- % who complete onboarding steps
- Track drop-off at each step

**Example - AI Writing Assistant:**
```
Activation Metrics:
- Aha moment: User generates AI draft and publishes it
- Time to value: Median 15 minutes (sign-up → first draft)
- Activation rate: 45% of sign-ups generate a draft within 7 days
- Onboarding drop-off:
  - Step 1 (Enter topic): 100%
  - Step 2 (Customize settings): 70%
  - Step 3 (Generate draft): 50%
  - Step 4 (Publish): 45%
- Goal: Increase activation to 60% by simplifying onboarding
```

---

### **3. Retention**

**Definition:** Do users come back?

**Why It Matters:** Retention is the #1 predictor of product-market fit. High retention = users find value.

**Key Metrics:**

**Cohort Retention:**
Track % of users who return after X days/weeks/months

**Standard Retention Windows:**
- D1 (Day 1): % who return next day
- D7 (Day 7): % who return in first week
- D30 (Day 30): % who return in first month
- M3, M6, M12: Longer-term retention

**Retention Curves:**

**Good Retention:**
```
Day 0:  100%
Day 1:   60%
Day 7:   50%
Day 30:  45%
Day 90:  43% (flattening out)
```
Curve flattens = you've retained core users ✅

**Bad Retention:**
```
Day 0:  100%
Day 1:   30%
Day 7:   15%
Day 30:   5%
Day 90:   2% (still declining)
```
Curve keeps dropping = poor product-market fit ❌

**Other Retention Metrics:**

**WAU / MAU (Stickiness):**
- Weekly Active Users / Monthly Active Users
- Measures how often users engage
- Target: >20% is good, >50% is excellent

**Churn Rate:**
- % of users who stop using
- Monthly churn: <5% is good for SaaS
- Annual churn: <20% is good

**Example - AI Writing Assistant:**
```
Retention Metrics:
- D1: 55%
- D7: 48%
- D30: 42%
- WAU/MAU: 38% (users engage 1.5x per week)
- Monthly churn: 7%
- Goal: Increase D30 to 55%, reduce churn to 4%
```

---

### **4. Revenue**

**Definition:** Can you monetize users?

**Key Metrics:**

**Conversion Metrics:**
- Free → Paid conversion rate
- Time to conversion
- Trial → Paid conversion

**Revenue Metrics:**
- MRR (Monthly Recurring Revenue)
- ARR (Annual Recurring Revenue)
- ARPU (Average Revenue Per User)
- ARPPU (Average Revenue Per Paying User)

**Customer Value Metrics:**
- LTV (Lifetime Value): Total revenue from a customer over their lifetime
- CAC (Customer Acquisition Cost): Cost to acquire one customer
- LTV:CAC Ratio: Should be >3:1 (ideally 5:1+)

**Unit Economics:**
- Gross margin per user
- Contribution margin
- Payback period (how long to recover CAC)

**Example - AI Writing Assistant:**
```
Revenue Metrics:
- Pricing: $49/month
- Free → Paid conversion: 8% (industry: 5-10%)
- Time to conversion: 14 days median
- MRR: $39,200 (800 paying users × $49)
- ARPU: $3.92 (800 paid / 10,000 MAU)
- ARPPU: $49
- LTV: $588 (12 months avg retention × $49)
- CAC: $150 (cost per sign-up + activation costs)
- LTV:CAC = 3.9:1 ✅
- Payback period: 3 months
```

---

### **5. Referral**

**Definition:** Do users tell others?

**Why It Matters:** Organic growth is cheapest and often highest quality.

**Key Metrics:**

**Viral Coefficient (K-factor):**
```
K = (# invites per user) × (conversion rate of invites)

Example:
- Each user invites 5 friends
- 20% of invites sign up
- K = 5 × 0.2 = 1.0

If K > 1 → Viral growth (exponential)
If K < 1 → Growth requires other channels
```

**NPS (Net Promoter Score):**
```
Survey question: "How likely are you to recommend us? (0-10)"

Promoters (9-10): Enthusiastic advocates
Passives (7-8): Satisfied but not enthusiastic
Detractors (0-6): Unhappy, may spread negative word-of-mouth

NPS = % Promoters - % Detractors

Score:
- >50: Excellent
- 30-50: Good
- 0-30: Needs improvement
- <0: Crisis
```

**Referral Metrics:**
- Invites sent per user
- Invite acceptance rate
- Referred user retention (vs. non-referred)
- Shares/social mentions

**Example - AI Writing Assistant:**
```
Referral Metrics:
- NPS: 45 (good, room to improve)
- Viral coefficient: 0.6 (not viral, need other channels)
- Invites sent: 2.5 per user
- Invite acceptance: 25%
- Referred users: 15% of new sign-ups
- Referred user retention: 60% (vs. 42% overall) ✅
```

---

## ❤️ HEART Framework

Created by Google for user-centric metrics. Great for products where engagement and satisfaction matter more than revenue (early-stage, consumer products).

**HEART = Happiness, Engagement, Adoption, Retention, Task Success**

---

### **1. Happiness**

**Definition:** User satisfaction and sentiment

**Metrics:**
- NPS (Net Promoter Score)
- CSAT (Customer Satisfaction Score): "Rate your satisfaction 1-5"
- User ratings (App Store, reviews)
- Support ticket volume and sentiment
- Survey responses

**Example:**
```
Happiness Metrics for AI Writing Assistant:
- NPS: 45
- CSAT: 4.2/5
- App Store rating: 4.6/5
- Support tickets: 50/month (2% of users)
- User testimonials: Track positive vs. negative themes
```

---

### **2. Engagement**

**Definition:** Level of user involvement

**Metrics:**
- DAU (Daily Active Users)
- WAU (Weekly Active Users)
- MAU (Monthly Active Users)
- Session frequency (visits per user per week)
- Session duration
- Actions per session

**Example:**
```
Engagement Metrics:
- DAU: 2,000
- MAU: 8,000
- DAU/MAU: 25% (users engage 1.75 days/week)
- Sessions per user: 3.5/week
- Session duration: 12 minutes avg
- Drafts generated per session: 1.8
```

---

### **3. Adoption**

**Definition:** New users and feature uptake

**Metrics:**
- New user sign-ups
- Feature adoption rate (% of users who try new feature)
- Time to adopt (how quickly do users try new features)

**Example:**
```
Adoption Metrics:
- New sign-ups: 800/month
- AI draft feature adoption: 75% of users have tried it
- SEO optimizer feature: 45% adoption (room to grow)
- Time to first AI draft: Median 1 day (good!)
```

---

### **4. Retention**

**Definition:** Same as AARRR (covered above)

---

### **5. Task Success**

**Definition:** Can users complete their intended tasks?

**Metrics:**
- Task completion rate
- Time to complete task
- Error rate
- Search success rate (users find what they need)

**Example:**
```
Task Success Metrics:
- Blog post completion rate: 68% (start draft → publish)
- Time to publish: 45 min avg (down from 3 hours manually ✅)
- AI generation error rate: 2% (fails to generate)
- User satisfaction with output: 4.1/5
```

---

## 🔄 Input vs. Output Metrics

**Output Metrics:** The results you want (lagging)
- Revenue, retention, growth
- What happened

**Input Metrics:** Actions that drive outputs (leading)
- Feature usage, content creation, engagement
- What users are doing

**The Relationship:**
```
Input Metrics → Drive → Output Metrics

Example:
- Input: Blog posts published (with AI)
- Output: User retention (users who publish stay)

If output metric is down, diagnose input metrics!
```

---

### **Example: AI Writing Assistant**

**North Star (Output):** Monthly Active Users (MAU)

**Input Metrics that Drive MAU:**

**1. Content Creation**
- Drafts generated per user
- Drafts published per user
- Target: 4+ drafts/month → 80% retention

**2. Quality Experience**
- AI output rating >4/5
- Time saved vs. manual
- Target: 4.5+ rating → users keep using

**3. Feature Engagement**
- SEO optimizer usage
- Outline generator usage
- Target: 3+ features used → higher retention

**4. Habit Formation**
- Days with activity per week
- Consecutive weeks of usage
- Target: 3+ days/week → becomes habit

**PM Use:**
If MAU is declining:
1. Check input metrics
2. Identify which is broken
3. Fix the input → output recovers

---

## 🤖 AI-Specific Metrics

Beyond standard product metrics, AI products need AI-specific measurements.

### **Model Performance Metrics**

**For Classification:**
- **Accuracy:** % predictions correct
- **Precision:** Of predicted positives, % actually positive
- **Recall:** Of actual positives, % we predicted
- **F1 Score:** Harmonic mean of precision and recall

**For Ranking/Recommendation:**
- **NDCG:** Quality of ranking
- **Click-through rate:** User engagement with recommendations
- **Diversity:** Variety in recommendations

**For Generation (LLMs):**
- **BLEU/ROUGE:** Similarity to reference (rough proxy)
- **Perplexity:** Model confidence
- **Human evaluation:** User ratings (most important!)

---

### **AI Quality Metrics (User-Perceived)**

**Acceptance Rate:**
- % of AI outputs users actually use
- Example: 50% of AI drafts are published
- Target: >50% is good, >70% is excellent

**Edit Distance:**
- How much users modify AI output
- Low edit distance = high quality
- Measure: % of content changed

**User Ratings:**
- Thumbs up/down on outputs
- 1-5 star ratings
- Target: >4/5 average

**Task Completion with AI:**
- % of tasks successfully completed using AI
- Time to complete vs. manual

---

### **AI Performance Metrics**

**Latency:**
- p50, p95, p99 response times
- Example: "90% of requests complete in <5 seconds"
- User tolerance: <5s for most tasks, <2s for interactive

**Throughput:**
- Requests per second the system can handle
- Peak load capacity

**Cost Metrics:**
- Cost per inference/generation
- Cost per user per month
- API costs (if using third-party models)

**Example:**
```
AI Performance:
- p50 latency: 2.5s
- p95 latency: 8s
- p99 latency: 15s (need to optimize!)
- Throughput: 50 requests/sec
- Cost per draft: $0.35
- Cost per user/month: $5.20 (15 drafts avg)
```

---

### **AI Health Metrics**

**Error Rate:**
- % of requests that fail
- Target: <1%

**Fallback Rate:**
- % of times AI can't generate output
- Example: Topic too niche, no training data

**Hallucination Rate:**
- % of outputs containing false information
- Measured through human evaluation

**Drift Detection:**
- Model accuracy over time
- Alert if accuracy drops >5% from baseline

---

### **AI Safety & Trust Metrics**

**Content Safety:**
- % inappropriate/harmful outputs
- Target: <0.01%

**User Trust Indicators:**
- % users who review AI output before using
- % users who report inaccuracies
- Confidence in AI (survey)

**Compliance:**
- Privacy violations (should be 0)
- Copyright issues flagged
- Regulatory compliance (e.g., GDPR requests handled)

---

## 📈 Metrics for Different Product Stages

### **Early Stage (Pre-PMF)**

**Focus:** Validate product-market fit

**Key Metrics:**
- Retention (D7, D30)
- NPS
- Activation rate
- Qualitative feedback

**Why:** Retention is #1 signal of PMF. If users don't come back, nothing else matters.

**Targets:**
- D7 retention >40%
- NPS >30
- Get to these before optimizing growth

---

### **Growth Stage (Post-PMF)**

**Focus:** Acquire users efficiently

**Key Metrics:**
- Growth rate (% MoM)
- CAC (Customer Acquisition Cost)
- LTV:CAC ratio
- Viral coefficient
- Channel performance

**Targets:**
- 10-20% MoM growth (good)
- LTV:CAC >3:1
- Payback period <12 months

---

### **Scale Stage**

**Focus:** Efficiency and profitability

**Key Metrics:**
- Unit economics
- Gross margin
- Net retention (expansion revenue from existing customers)
- Operational efficiency

**Targets:**
- 70%+ gross margin
- Net retention >100% (expansion covers churn)

---

## ⚠️ Common Metrics Pitfalls

### **Pitfall 1: Vanity Metrics**

**Problem:** Metrics that look good but don't drive outcomes

**Examples:**
- ❌ Total sign-ups (growing but all churning)
- ❌ Page views (high traffic, no engagement)
- ❌ Social media followers (large audience, no conversion)

**Fix:** Focus on actionable metrics (retention, revenue, engagement)

---

### **Pitfall 2: Too Many Metrics**

**Problem:** Tracking 50 metrics → analysis paralysis

**Fix:**
- 1 North Star
- 3-5 primary metrics
- Rest are secondary (check weekly, not daily)

---

### **Pitfall 3: Gaming Metrics**

**Problem:** Optimizing metric, hurting product

**Example:**
- Optimize for DAU → Spam notifications → Users annoyed → Churn increases

**Fix:** Set guardrail metrics (churn, satisfaction) alongside growth metrics

---

### **Pitfall 4: Ignoring Segments**

**Problem:** Looking at averages, missing important patterns

**Example:**
- Overall retention: 50%
- But: Power users 90%, casual users 20%

**Fix:** Segment analysis (by user type, channel, feature usage, etc.)

---

### **Pitfall 5: Correlation vs. Causation**

**Problem:** Assuming correlation = causation

**Example:**
- "Users who use feature X have higher retention"
- Maybe: Feature X attracts engaged users (not feature itself causing retention)

**Fix:** Run experiments (A/B tests) to validate causation

---

## 📊 Building Your Metrics Dashboard

### **Dashboard Structure:**

**Level 1: Executive Dashboard (1 page)**
- North Star metric (trend over time)
- 3-5 primary metrics
- Red/yellow/green indicators

**Level 2: Product Dashboard**
- Full AARRR funnel
- Week-over-week trends
- Cohort analysis

**Level 3: AI Performance Dashboard**
- Model metrics (accuracy, latency, cost)
- AI quality metrics (acceptance rate, ratings)
- Health metrics (error rate, drift)

**Level 4: Deep-Dive Dashboards**
- Feature-specific metrics
- Segment analysis
- Experiment results

---

### **Dashboard Best Practices:**

**1. Real-Time (or Near Real-Time)**
- Update daily minimum
- Critical metrics: Update hourly

**2. Accessible to All**
- Everyone on team should see metrics
- Transparency builds alignment

**3. Actionable**
- Link metrics to actions
- "If X drops, do Y"

**4. Visual**
- Charts > tables
- Trends > single numbers
- Red/yellow/green status

**5. Contextualized**
- Show targets
- Show historical trends
- Show benchmarks

---

### **Example Dashboard Layout:**

```
┌─────────────────────────────────────────────┐
│        AI Writing Assistant Dashboard        │
├─────────────────────────────────────────────┤
│                                              │
│  North Star: MAU                             │
│  8,542 ↑ 12% MoM        [Graph: 6mo trend]  │
│                                              │
├─────────────────────────────────────────────┤
│  AARRR Metrics           This Week  vs Last │
│  ─────────────────────────────────────────  │
│  Acquisition (Sign-ups)     850     ↑ 8%    │
│  Activation (First draft)   408     ↑ 15%   │
│  Retention (D30)           52%      → 0%    │
│  Revenue (MRR)          $42,350     ↑ 11%   │
│  Referral (NPS)             48      ↑ 3pts  │
│                                              │
├─────────────────────────────────────────────┤
│  AI Performance          Current   Target   │
│  ─────────────────────────────────────────  │
│  Acceptance Rate          58%      >50% ✅   │
│  Avg Quality Rating      4.3/5     >4/5 ✅   │
│  p95 Latency             6.2s       <5s ⚠️   │
│  Cost per Draft         $0.42     <$0.50 ✅  │
│  Error Rate              1.2%       <2% ✅   │
│                                              │
└─────────────────────────────────────────────┘
```

---

## ✅ Week 3 Deliverable: Build Your Metrics Framework

**For your AI opportunity, define:**

**1. North Star Metric**
- What ONE metric captures core value?

**2. AARRR Metrics**
- Acquisition: How will you measure discovery?
- Activation: What's the "aha moment"?
- Retention: D7, D30 targets?
- Revenue: Pricing and conversion targets?
- Referral: NPS target?

**3. AI-Specific Metrics**
- Model performance: What accuracy/quality?
- User-perceived quality: Acceptance rate target?
- Performance: Latency and cost budgets?

**4. Input Metrics**
- What user actions drive your North Star?
- How will you measure them?

**5. Dashboard Design**
- Sketch your dashboard (1 page)
- What metrics would you check daily?

**Output:** 2-3 page metrics framework document

---

## 📚 Resources

**Books:**
- 📚 **"Lean Analytics"** by Alistair Croll & Benjamin Yoskovitz
- 📚 **"Measure What Matters"** by John Doerr (OKRs)

**Articles:**
- 📖 **"16 Startup Metrics"** by a16z
- 📖 **"Metrics vs. Experience"** by Julie Zhuo

**Tools:**
- **Mixpanel, Amplitude** - Product analytics
- **Looker, Tableau** - Data visualization
- **Google Analytics** - Web analytics

---

## 🎬 Conclusion

Metrics are your compass as a PM. They tell you:
- Are we building the right thing? (retention, NPS)
- Is it working? (activation, engagement)
- Is it sustainable? (unit economics, LTV:CAC)

**For AI PMs, you need TWO lenses:**
1. **Product metrics** - Is the product valuable?
2. **AI metrics** - Is the AI good enough?

Master both and you'll be able to build successful AI products! 🚀

---

**Last Updated:** 2025-01-15
