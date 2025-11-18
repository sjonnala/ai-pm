# Roadmap Prioritization Framework Guide

## 🎯 Overview

Product managers face the hardest question daily: "What should we build next?" With limited resources and unlimited ideas, prioritization is the most critical PM skill. This guide provides comprehensive frameworks to systematically prioritize features, especially for AI products.

**Goal:** Master prioritization frameworks to build compelling, data-driven roadmaps that align with strategy and maximize impact.

---

## 📚 Table of Contents

1. [Why Prioritization Matters](#why-prioritization-matters)
2. [Core Prioritization Frameworks](#core-prioritization-frameworks)
3. [AI-Specific Prioritization Considerations](#ai-specific-prioritization-considerations)
4. [When to Use Which Framework](#when-to-use-which-framework)
5. [Building a Prioritization Process](#building-a-prioritization-process)
6. [Common Prioritization Mistakes](#common-prioritization-mistakes)
7. [Templates & Checklists](#templates--checklists)

---

## 🎯 Why Prioritization Matters

### **The Prioritization Challenge**

Every PM faces these constraints:

**Limited Resources:**
- Engineering team has finite capacity
- Design bandwidth is precious
- Your time is limited

**Unlimited Demands:**
- Sales wants enterprise features
- Marketing wants viral features
- Support wants bug fixes
- Users want everything
- Leadership wants innovation

**High Opportunity Cost:**
- Every "yes" means saying "no" to something else
- Wrong choices compound over quarters
- Reversing course is expensive

---

### **What Good Prioritization Delivers**

**1. Clarity**
- Everyone knows what's next and why
- No constant priority shifts
- Teams can plan confidently

**2. Alignment**
- Roadmap connects to strategy
- Stakeholders understand trade-offs
- Org moves in one direction

**3. Impact**
- Resources focus on highest-value work
- Metrics improve faster
- Product reaches goals

**4. Trust**
- Transparent decision-making
- Stakeholders feel heard
- Data drives choices, not politics

---

## 📊 Core Prioritization Frameworks

### **Framework 1: RICE Scoring**

**Developed by Intercom, RICE is the most popular quantitative framework.**

**RICE = (Reach × Impact × Confidence) / Effort**

---

#### **R = Reach**

**Definition:** How many users will this affect in a given time period?

**How to Measure:**
- Number of users per month/quarter
- Transactions per period
- Events per period

**Examples:**
- Feature for all users: Reach = 10,000 users/month
- Feature for premium users only: Reach = 1,000 users/month
- Onboarding improvement: Reach = 500 new users/month

**AI Product Example:**
- AI writing assistant for all users: Reach = 50,000 users/month
- AI code completion for enterprise: Reach = 2,000 users/month
- AI personalized recommendations: Reach = 100,000 sessions/month

---

#### **I = Impact**

**Definition:** How much will this feature impact each user?

**Scale:**
- **3 = Massive impact** (transforms experience)
- **2 = High impact** (significant improvement)
- **1 = Medium impact** (nice improvement)
- **0.5 = Low impact** (small improvement)
- **0.25 = Minimal impact** (barely noticeable)

**How to Estimate:**
- User research feedback
- A/B test results from similar features
- Benchmark data from industry
- Expert judgment

**Examples:**
- Massive (3): GitHub Copilot autocomplete (transforms coding workflow)
- High (2): ChatGPT web browsing (major capability expansion)
- Medium (1): Notion AI summarize (useful but not game-changing)
- Low (0.5): UI polish, minor improvements
- Minimal (0.25): Button color changes

**Framework for Estimating Impact:**
Ask these questions:
1. Does this solve a critical pain point? (Massive)
2. Does this significantly improve a core workflow? (High)
3. Does this make something noticeably better? (Medium)
4. Is this a nice-to-have? (Low)
5. Will users barely notice? (Minimal)

---

#### **C = Confidence**

**Definition:** How confident are you in your Reach and Impact estimates?

**Scale:**
- **100% = High confidence** (strong data, proven patterns)
- **80% = Medium confidence** (some data, reasonable assumptions)
- **50% = Low confidence** (mostly assumptions, little data)

**Examples:**
- **High (100%):** You have A/B test data showing impact
- **High (100%):** Similar feature exists at competitors with known metrics
- **Medium (80%):** User research shows strong interest, no hard data
- **Medium (80%):** Analytics show potential, but unvalidated
- **Low (50%):** Hypothesis with little validation
- **Low (50%):** Moonshot idea, no precedent

**AI Examples:**
- **100%:** Adding ChatGPT-like feature (proven model, known demand)
- **80%:** AI search improvement (promising research, unclear adoption)
- **50%:** Novel AI agent workflow (unproven territory)

---

#### **E = Effort**

**Definition:** How much work is this, measured in "person-months"?

**How to Estimate:**
- Work with engineering to size
- Count person-months (1 engineer for 1 month = 1 PM)
- Include all disciplines (eng, design, PM, QA)

**Examples:**
- Small button change: 0.1 PM (few days)
- Simple API integration: 0.5 PM (2 weeks)
- New feature with backend: 3 PM (3 months for 1 eng)
- Complex AI model integration: 12 PM (3 eng for 4 months)

**T-Shirt Sizing:**
If person-months too detailed, use:
- **XS:** <0.5 PM (< 2 weeks)
- **S:** 0.5-1 PM (2-4 weeks)
- **M:** 1-3 PM (1-3 months)
- **L:** 3-6 PM (3-6 months)
- **XL:** >6 PM (> 6 months)

---

#### **Calculating RICE Score**

**Formula:**
```
RICE Score = (Reach × Impact × Confidence%) / Effort
```

**Example 1: AI Writing Assistant**
- Reach: 10,000 users/month
- Impact: 2 (high)
- Confidence: 80%
- Effort: 4 PM

RICE = (10,000 × 2 × 0.8) / 4 = **4,000**

**Example 2: AI Code Autocomplete**
- Reach: 50,000 users/month
- Impact: 3 (massive)
- Confidence: 100%
- Effort: 8 PM

RICE = (50,000 × 3 × 1.0) / 8 = **18,750**

**Example 3: UI Polish**
- Reach: 100,000 users/month
- Impact: 0.5 (low)
- Confidence: 100%
- Effort: 1 PM

RICE = (100,000 × 0.5 × 1.0) / 1 = **50,000**

**Ranking:** UI Polish (50K) > Code Autocomplete (18.75K) > Writing Assistant (4K)

**Surprising?** Yes! This shows why data matters. High reach with low effort can beat high impact with high effort.

---

#### **RICE Best Practices**

**Do's:**
- ✅ Be consistent in how you measure Reach
- ✅ Use same time period for all features (monthly recommended)
- ✅ Involve engineering in Effort estimates
- ✅ Document assumptions
- ✅ Re-score when new data arrives
- ✅ Use as input, not absolute truth

**Don'ts:**
- ❌ Don't compare features with different Reach time periods
- ❌ Don't let one person score everything
- ❌ Don't ignore strategic alignment (RICE is just one input!)
- ❌ Don't use RICE for everything (maintenance, tech debt, etc.)

---

### **Framework 2: Value vs. Effort Matrix**

**Also called Impact/Effort, this is the most visual framework.**

**The Matrix:**
```
High Value │ Big Bets        │ Quick Wins
           │ (Do Strategic)  │ (DO FIRST!)
           │                 │
           │ 3               │ 1
───────────┼─────────────────┼──────────────
Low Value  │ Money Pit       │ Fill-ins
           │ (DON'T DO!)     │ (Do if capacity)
           │                 │
           │ 4               │ 2
           Low Effort         High Effort
```

**Priority Order:**
1. **Quick Wins** (High Value, Low Effort) - DO THESE FIRST
2. **Fill-ins** (Low Value, Low Effort) - Do if you have capacity
3. **Big Bets** (High Value, High Effort) - Strategic initiatives
4. **Money Pit** (Low Value, High Effort) - AVOID

---

#### **How to Use Value vs. Effort**

**Step 1: Define "Value"**

Value can mean different things:
- User impact
- Revenue potential
- Strategic importance
- Learning value
- Competitive necessity

**For AI Products, Consider:**
- User pain solved
- Engagement increase
- Conversion lift
- Retention improvement
- Competitive differentiation
- Data/learning value

**Step 2: Plot Features**

Example for AI Writing Tool:

**Quick Wins:**
- Grammar check (high value, easy)
- Tone adjustment (high value, easy)
- Template library (high value, easy)

**Big Bets:**
- Full AI co-writer (high value, hard)
- Multi-language support (high value, hard)
- SEO optimization AI (high value, hard)

**Fill-ins:**
- Export to PDF (low value, easy)
- Dark mode (low value, easy)

**Money Pit:**
- Voice dictation (low value, hard)
- Handwriting recognition (low value, hard)

**Step 3: Balance Portfolio**

A healthy roadmap has:
- 40-50% Quick Wins (fast momentum)
- 30-40% Big Bets (strategic future)
- 10-20% Fill-ins (polish, delight)
- 0% Money Pit (say no!)

---

### **Framework 3: MoSCoW Method**

**MoSCoW categorizes features into 4 buckets.**

**Must Have:**
- Critical for launch/success
- Product fails without it
- Legal/compliance requirements

**Should Have:**
- Important but not critical
- Significant value
- Can launch without, but soon after

**Could Have:**
- Nice to have
- Minimal impact if excluded
- Include if capacity allows

**Won't Have (this time):**
- Out of scope for this release
- Low priority
- Maybe later

---

#### **MoSCoW for AI Products**

**Example: Launching AI Customer Support Bot**

**Must Have:**
- Natural language understanding
- Integration with help docs
- Human handoff when stuck
- Basic analytics dashboard
- GDPR compliance

**Should Have:**
- Multi-language support
- Sentiment analysis
- Personalized responses based on user history
- A/B testing framework

**Could Have:**
- Voice interface
- Proactive outreach
- Custom branding per customer
- Advanced analytics

**Won't Have (this time):**
- Video chat
- AR troubleshooting
- Blockchain integration (why would you?!)

---

#### **When to Use MoSCoW**

**Best For:**
- Release planning ("What's in v1?")
- MVP scoping
- Stakeholder alignment on scope
- Agile sprint planning

**Not Great For:**
- Long-term roadmaps
- Continuous prioritization
- Quantitative comparison

---

### **Framework 4: Kano Model**

**The Kano Model categorizes features by user satisfaction.**

**Three Categories:**

**1. Basic Needs (Must-Haves)**
- Expected by users
- Absence causes dissatisfaction
- Presence doesn't increase satisfaction much

**Examples:**
- App loads quickly
- Search works
- No bugs/crashes

**AI Examples:**
- AI doesn't hallucinate nonsense
- AI responses are relevant
- AI feature doesn't slow down app

**2. Performance Needs (More is Better)**
- Linear satisfaction increase
- More/better = more happy
- Less/worse = less happy

**Examples:**
- Faster load time
- More integrations
- Better accuracy

**AI Examples:**
- AI response accuracy (70% → 90% → 95%)
- AI response speed (5s → 2s → 1s)
- Coverage (works for 50% → 80% → 95% of cases)

**3. Delighters (Excitement)**
- Unexpected features
- Absence doesn't cause dissatisfaction
- Presence creates delight

**Examples:**
- GitHub Copilot suggestions (2021)
- ChatGPT conversational ability (2022)
- Midjourney image quality (2023)

**AI Examples:**
- AI that suggests things you didn't know you needed
- AI that feels like magic
- AI that has personality

---

#### **Using Kano for Roadmap**

**Healthy roadmap mix:**
- **50-60% Basic Needs** - Don't ship broken product
- **30-40% Performance** - Competitive necessity
- **10-20% Delighters** - Differentiation, wow factor

**For AI Products:**
- **Basics:** Reliability, accuracy, speed, safety
- **Performance:** Better accuracy, faster inference, more use cases
- **Delighters:** Novel capabilities, magical experiences

**Example: AI Email Assistant Roadmap**

**Q1 (Basics):**
- Email summarization works accurately
- No hallucinations
- Privacy/security compliance

**Q2 (Performance):**
- Summarize 90% faster
- Support 10 more languages
- Handle complex email threads

**Q3 (Delighters):**
- AI suggests perfect reply before you think of it
- AI auto-schedules meetings by understanding context
- AI detects urgency and prioritizes inbox

---

### **Framework 5: ICE Scoring**

**Simpler version of RICE, popularized by Growth hackers.**

**ICE = Impact × Confidence × Ease**

**Each scored 1-10:**
- **Impact:** How much will this move the metric?
- **Confidence:** How sure are we?
- **Ease:** How easy to implement? (10 = very easy)

**ICE Score = (Impact + Confidence + Ease) / 3** or multiply them

**Example:**
- **Feature A:** Impact=9, Confidence=8, Ease=7 → ICE = 8
- **Feature B:** Impact=10, Confidence=5, Ease=3 → ICE = 6

**When to Use:**
- Growth experiments
- Quick prioritization
- Early-stage products
- Small teams

**Pros:**
- Very fast
- Easy to understand
- Good for experiments

**Cons:**
- Less precise than RICE
- 1-10 scales are subjective
- Doesn't account for reach

---

### **Framework 6: Weighted Scoring**

**Assign weights to different criteria based on strategy.**

**Example Criteria & Weights:**

| Criterion | Weight | Feature A | Feature B |
|-----------|--------|-----------|-----------|
| User Impact | 30% | 8 | 6 |
| Revenue Potential | 25% | 5 | 9 |
| Strategic Alignment | 20% | 9 | 7 |
| Technical Feasibility | 15% | 7 | 4 |
| Competitive Need | 10% | 6 | 8 |
| **Total** | **100%** | **7.25** | **6.85** |

**Calculation for Feature A:**
```
Score = (8×0.3) + (5×0.25) + (9×0.2) + (7×0.15) + (6×0.1)
      = 2.4 + 1.25 + 1.8 + 1.05 + 0.6
      = 7.25
```

---

#### **Weighted Scoring for AI Products**

**AI-Specific Criteria:**

| Criterion | Weight | Rationale |
|-----------|--------|-----------|
| User Pain Solved | 25% | AI should solve real problems |
| AI Suitability | 20% | Is AI the right solution? |
| Data Availability | 15% | Can't build without data |
| Differentiation | 15% | Competitive moat |
| Technical Feasibility | 15% | Can we actually build this? |
| ROI / Unit Economics | 10% | Sustainable business |

**Example: Scoring 3 AI Features**

**Feature 1: AI Code Autocomplete**
- User Pain: 10 (developers hate boilerplate)
- AI Suitability: 10 (perfect for LLMs)
- Data: 9 (GitHub has tons of code)
- Differentiation: 7 (Copilot exists)
- Feasibility: 8 (proven tech)
- ROI: 9 (high willingness to pay)
- **Score: 8.85**

**Feature 2: AI Design Generator**
- User Pain: 8 (designers want faster iteration)
- AI Suitability: 7 (image gen is good, not perfect)
- Data: 6 (design data harder to get)
- Differentiation: 9 (few competitors)
- Feasibility: 6 (challenging)
- ROI: 7 (unclear pricing)
- **Score: 7.25**

**Feature 3: AI Video Editing**
- User Pain: 9 (video editing very slow)
- AI Suitability: 6 (video AI still early)
- Data: 5 (video data expensive)
- Differentiation: 10 (blue ocean)
- Feasibility: 4 (very hard)
- ROI: 8 (high value if it works)
- **Score: 6.95**

**Ranking:** Code Autocomplete > Design Generator > Video Editing

---

### **Framework 7: WSJF (Weighted Shortest Job First)**

**From SAFe Agile, prioritizes by Cost of Delay / Job Duration.**

**WSJF = (User-Business Value + Time Criticality + Risk Reduction) / Job Size**

**When to Use:**
- Multiple teams
- Enterprise/large orgs
- Portfolio management

**Pros:**
- Accounts for urgency
- Considers risk
- Good for dependencies

**Cons:**
- Complex
- Overkill for small teams

---

## 🤖 AI-Specific Prioritization Considerations

### **Unique Factors for AI Products**

**1. Data Availability**

AI features need data. Prioritize based on:
- **Data exists:** High priority
- **Can collect quickly:** Medium priority
- **Expensive/slow to collect:** Lower priority
- **Can't get data:** Don't build

**Example:**
- ✅ AI email summarization (emails readily available)
- ⚠️ AI medical diagnosis (need labeled medical data)
- ❌ AI personality analysis (no good dataset exists)

---

**2. Model Maturity**

State-of-the-art matters:
- **Proven tech (LLMs for text):** High confidence
- **Emerging tech (multimodal):** Medium confidence
- **Research stage (AGI):** Low confidence

**Example:**
- ✅ AI writing assistance (GPT-4 proven)
- ⚠️ AI video generation (improving but inconsistent)
- ❌ AI general reasoning (not there yet)

---

**3. Human-in-the-Loop Requirements**

Some AI needs more human oversight:
- **Fully autonomous:** Faster to ship, higher risk
- **Human-in-loop:** Slower, safer, more trusted

**Prioritization Impact:**
- Low-risk use cases → autonomous → faster ship
- High-risk use cases → human-in-loop → slower ship

**Examples:**
- Low risk: AI grammar suggestions (autonomous OK)
- Medium risk: AI code suggestions (review needed)
- High risk: AI medical advice (doctor required)

---

**4. AI Cost Structure**

AI features have ongoing costs:
- **Inference cost:** Every API call costs $
- **Compute cost:** GPUs aren't cheap
- **Data storage:** Vector DBs, training data

**Prioritization:**
- High-value, affordable features → Priority
- High-value, expensive features → Validate first
- Low-value, expensive → Avoid

**Example:**
- ✅ AI autocomplete (low cost per user)
- ⚠️ AI video gen (expensive, need high willingness to pay)

---

**5. Explainability Needs**

Some domains require AI explainability:
- **Black box OK:** Content creation, recommendations
- **Explainability needed:** Healthcare, finance, legal

**Prioritization:**
- Explainability not needed → Easier, higher priority
- Explainability critical → Harder, slower ship

---

**6. Competitive Dynamics**

AI moves fast. Consider:
- **Commodity:** ChatGPT-like chat (everyone has it)
- **Differentiated:** Unique application of AI
- **Proprietary:** Special data/model

**Prioritization:**
- Commoditized features → Lower priority (unless table stakes)
- Differentiated features → High priority
- Proprietary moat → Highest priority

---

### **AI Feature Prioritization Scorecard**

Use this for AI-specific features:

| Criterion | Weight | Score 1-10 |
|-----------|--------|------------|
| User Pain Intensity | 20% | |
| AI Suitability | 15% | |
| Data Availability | 15% | |
| Model Maturity | 15% | |
| Differentiation | 10% | |
| Unit Economics | 10% | |
| Technical Feasibility | 10% | |
| Explainability Risk | 5% | |

---

## 🔄 When to Use Which Framework

### **Framework Selection Guide**

**Use RICE when:**
- ✅ You have data on reach/impact
- ✅ You want quantitative scoring
- ✅ You're comparing features objectively
- ✅ You need to defend decisions with data

**Use Value/Effort when:**
- ✅ You want visual prioritization
- ✅ You need stakeholder alignment
- ✅ You're balancing quick wins vs. big bets
- ✅ You want portfolio balance

**Use MoSCoW when:**
- ✅ You're scoping a release
- ✅ You need to cut features
- ✅ You're doing sprint planning
- ✅ You need binary in/out decisions

**Use Kano when:**
- ✅ You're planning differentiation
- ✅ You want to understand satisfaction drivers
- ✅ You're balancing basics vs. delighters
- ✅ You're in competitive market

**Use ICE when:**
- ✅ You're running growth experiments
- ✅ You need quick prioritization
- ✅ You have limited data
- ✅ You're early stage

**Use Weighted Scoring when:**
- ✅ Multiple criteria matter
- ✅ Strategy drives specific weights
- ✅ You need customized framework
- ✅ Stakeholders agree on weights

---

### **Combining Frameworks**

**The Best Approach: Use Multiple!**

**Example Process:**

**Step 1: MoSCoW** to get long list down to realistic scope

**Step 2: RICE** to quantitatively score what's left

**Step 3: Value/Effort** to visualize and balance portfolio

**Step 4: Kano** to ensure you have delighters

**Result:** Data-driven, balanced roadmap with quick wins, strategic bets, and wow factors.

---

## 🏗️ Building a Prioritization Process

### **The Complete Prioritization Workflow**

**Phase 1: Gather Inputs (Week 1)**

**Collect ideas from:**
- User research & feedback
- Support tickets
- Sales requests
- Analytics insights
- Competitive analysis
- Team brainstorms
- Leadership strategy

**Tools:**
- ProductBoard
- Canny
- Internal idea board
- Spreadsheet

**Output:** Long list of 50-100+ ideas

---

**Phase 2: Initial Filtering (Week 2)**

**Filter out:**
- Not aligned with strategy
- Technically impossible
- Too expensive
- Out of scope

**Apply:**
- Strategic fit test
- Technical feasibility check
- Basic effort estimate

**Output:** Shortlist of 20-30 features

---

**Phase 3: Deep Scoring (Week 3)**

**For each feature:**
- Score with RICE
- Estimate effort with eng
- Map to Value/Effort matrix
- Categorize with Kano

**Involve:**
- Engineering (effort)
- Design (feasibility)
- Data (impact estimates)
- Customers (validation)

**Output:** Scored, ranked features

---

**Phase 4: Portfolio Balancing (Week 4)**

**Check balance:**
- 40% Quick Wins
- 40% Strategic Bets
- 20% Fill-ins
- Mix of themes
- Mix of user segments

**Adjust if needed**

**Output:** Balanced roadmap

---

**Phase 5: Stakeholder Review (Week 5)**

**Present:**
- Scoring methodology
- Top priorities with rationale
- What's NOT on roadmap and why
- Trade-offs made

**Gather:**
- Feedback
- Concerns
- Additional data

**Output:** Aligned roadmap

---

**Phase 6: Execution & Iteration (Ongoing)**

**As you ship:**
- Measure actual impact
- Update confidence scores
- Re-prioritize based on data
- Add new features to backlog

**Cadence:**
- Weekly: Review progress
- Monthly: Re-score top 10
- Quarterly: Refresh roadmap

---

### **Prioritization Meeting Structure**

**Monthly Prioritization Meeting (2 hours)**

**Attendees:**
- PM (owner)
- Engineering lead
- Design lead
- Data/Analytics
- Key stakeholders

**Agenda:**

**0:00-0:15 - Review last month**
- What shipped?
- What was actual impact?
- What did we learn?

**0:15-0:30 - New inputs**
- New user feedback
- Competitive moves
- Strategic shifts
- New data

**0:30-1:00 - Scoring session**
- Score new features
- Re-score existing based on new data
- Debate assumptions

**1:00-1:30 - Roadmap update**
- Adjust roadmap
- Balance portfolio
- Identify dependencies

**1:30-2:00 - Alignment**
- What's in/out
- Rationale
- Communication plan

---

## ⚠️ Common Prioritization Mistakes

### **Mistake 1: HiPPO (Highest Paid Person's Opinion)**

**What it is:**
CEO/VP says "we need X" → roadmap changes

**Why it's bad:**
- Ignores data
- Demoralizes team
- Often wrong

**How to fix:**
- Use frameworks to show trade-offs
- Ask HiPPO to weight criteria
- Run small experiment first
- Measure results, iterate

---

### **Mistake 2: Squeaky Wheel Gets the Grease**

**What it is:**
Loudest customer/stakeholder gets priority

**Why it's bad:**
- Vocal minority ≠ majority
- Reactive, not strategic
- Roadmap whiplash

**How to fix:**
- Quantify reach (1 customer or 10,000?)
- Score impact systematically
- Communicate prioritization process
- Set expectations

---

### **Mistake 3: Analysis Paralysis**

**What it is:**
Endlessly scoring, never shipping

**Why it's bad:**
- Opportunity cost
- Data comes from shipping
- Perfect is enemy of good

**How to fix:**
- Time-box scoring (1 week max)
- Accept imperfect data
- Ship, measure, iterate
- Frameworks are guides, not gospel

---

### **Mistake 4: Short-Term Thinking**

**What it is:**
Only quick wins, no strategic bets

**Why it's bad:**
- No competitive moat
- Rivals catch up
- No transformation

**How to fix:**
- Balance quick wins (40%) with big bets (40%)
- Reserve capacity for strategic work
- Protect innovation time

---

### **Mistake 5: Ignoring Effort**

**What it is:**
Prioritizing only by value, ignoring feasibility

**Why it's bad:**
- Roadmap slips
- Team burnout
- Miss quick wins

**How to fix:**
- Always include effort in scoring
- Prefer 80% solution in 20% time
- Ship iteratively

---

### **Mistake 6: No Re-Prioritization**

**What it is:**
Set roadmap once, never change

**Why it's bad:**
- Markets shift
- Data changes understanding
- New opportunities emerge

**How to fix:**
- Monthly re-scoring
- Quarterly roadmap refresh
- Be flexible, not rigid

---

## 📋 Templates & Checklists

### **RICE Scoring Template**

```markdown
| Feature | Reach (/mo) | Impact (0-3) | Confidence (%) | Effort (PM) | RICE Score |
|---------|-------------|--------------|----------------|-------------|------------|
| Feature A | 10,000 | 2 | 80 | 4 | 4,000 |
| Feature B | 50,000 | 1 | 100 | 5 | 10,000 |
| Feature C | 5,000 | 3 | 50 | 2 | 3,750 |
```

**Ranking:** Feature B > Feature A > Feature C

---

### **Value vs. Effort Mapping Template**

```markdown
## Quick Wins (High Value, Low Effort)
- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3

## Big Bets (High Value, High Effort)
- [ ] Feature 4
- [ ] Feature 5

## Fill-ins (Low Value, Low Effort)
- [ ] Feature 6
- [ ] Feature 7

## Money Pit (Low Value, High Effort)
- ❌ Feature 8 (Don't do!)
```

---

### **Prioritization Decision Template**

```markdown
## Feature: [Name]

**Problem:** [What user problem does this solve?]

**Solution:** [How does this feature solve it?]

**Scoring:**
- RICE Score: [X]
- Value/Effort: [Quick Win / Big Bet / etc.]
- Kano Category: [Basic / Performance / Delighter]

**Decision:** [Ship / Don't Ship / Experiment First]

**Rationale:** [Why this decision?]

**Success Metrics:**
- [Metric 1]: [Target]
- [Metric 2]: [Target]

**Next Steps:**
- [ ] [Action 1]
- [ ] [Action 2]
```

---

### **Prioritization Checklist**

**Before finalizing roadmap:**

- [ ] All features scored with consistent framework
- [ ] Engineering has reviewed effort estimates
- [ ] Strategic alignment verified
- [ ] Portfolio balance checked (quick wins + big bets)
- [ ] Success metrics defined for each initiative
- [ ] Stakeholders consulted
- [ ] Trade-offs documented
- [ ] What's NOT on roadmap communicated
- [ ] Re-prioritization cadence established
- [ ] Room for experimentation/learning preserved

---

## 🎯 Interview Preparation

### **Common Interview Questions**

**Q: "How do you prioritize features?"**

**Great Answer:**

"I use a structured approach combining multiple frameworks:

**First, I gather inputs** from users, data, sales, and strategy.

**Then I apply RICE scoring** to quantitatively rank features based on reach, impact, confidence, and effort. For example, in my last role, we had 50 feature ideas. RICE helped us identify that improving onboarding (RICE: 15K) would have 3x more impact than adding a requested enterprise feature (RICE: 5K).

**Next, I visualize with Value/Effort matrix** to ensure we balance quick wins with strategic bets. A healthy roadmap is 40% quick wins for momentum, 40% big bets for the future.

**Finally, I validate alignment** with stakeholders, clearly communicating what's in, what's out, and why.

The result is a data-driven roadmap that maximizes impact while building stakeholder trust."

---

**Q: "You have 10 feature requests from customers, sales, and leadership. How do you choose?"**

**Great Answer:**

"I'd follow this process:

**1. Understand the 'why':** For each request, dig into the underlying need. Sometimes 10 requests = 3 actual problems.

**2. Quantify impact:** How many users? How much pain? What's the value?

**3. Score systematically:** Use RICE to compare apples-to-apples.

**4. Check strategic fit:** Does this align with our vision? Is this the right solution?

**5. Balance portfolio:** Can't do all 10. Pick mix of quick wins and strategic bets.

**6. Communicate decisions:** Show my scoring, explain trade-offs, set expectations on what's not happening and why.

For example, [share specific story from your experience]."

---

**Q: "How do you handle pressure from executives to build their pet feature?"**

**Great Answer:**

"I respect that executives have valuable context and instincts. My approach:

**1. Understand their reasoning:** Why do they think this is important? What outcome do they expect?

**2. Score it objectively:** Run it through the same RICE framework as everything else.

**3. Show trade-offs:** 'If we do this, we won't do X and Y. Here's the impact comparison.'

**4. Propose experiment:** 'Let's validate with a small test first, then scale if it works.'

**5. Align on metrics:** 'What success would look like? Let's measure and iterate.'

Usually, this structured approach either validates their instinct OR reveals better alternatives. Either way, we make better decisions together."

---

## 🎓 Week 4 Deliverable: Prioritized Roadmap

**Your Assignment:**

Using the frameworks in this guide:

1. **Score your AI opportunities** from Week 1 using RICE
2. **Map to Value/Effort matrix** to visualize
3. **Select top 6 initiatives** for 6-month roadmap
4. **Balance portfolio:** Quick wins + strategic bets + delighters
5. **Document rationale:** Why these? Why not others?

**Template:** Use the 6-month roadmap template in this folder

---

## 📚 Resources

**Prioritization Frameworks:**
- [Intercom - RICE Framework](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/) ⭐
- [ProductPlan - Prioritization Guide](https://www.productplan.com/learn/prioritization-frameworks/)
- [Amplitude - Feature Prioritization](https://amplitude.com/blog/product-feature-prioritization)

**Books:**
- *Inspired* - Marty Cagan (Prioritization chapter)
- *Escaping the Build Trap* - Melissa Perri

**Tools:**
- ProductBoard (prioritization + roadmaps)
- Aha! (roadmap planning)
- Airfocus (priority scoring)

---

## 🎬 Conclusion

Prioritization is the PM superpower. Master these frameworks, but remember:

**Frameworks are tools, not rules.**

The best PMs combine:
- 📊 Data (frameworks, scoring)
- 🧠 Judgment (strategy, intuition)
- 🤝 Collaboration (stakeholder input)
- 🔄 Iteration (measure, learn, adjust)

**Practice prioritization weekly.** It's a muscle that strengthens with use.

Now go build your roadmap! 🚀

---

**Last Updated:** 2025-01-15
