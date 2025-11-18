# PM Strategy Frameworks Guide

## 🎯 Overview

Great PMs don't just execute - they think strategically. This guide covers the essential frameworks that help you:
- Frame problems effectively
- Identify user needs
- Define strategy
- Prioritize ruthlessly
- Communicate clearly

These frameworks are foundational for ALL PM work, and especially critical for AI PMs navigating ambiguity.

---

## 📚 Table of Contents

1. [North Star Framework](#north-star-framework)
2. [Jobs To Be Done (JTBD)](#jobs-to-be-done-jtbd)
3. [Problem Framing Canvas](#problem-framing-canvas)
4. [Opportunity Solution Trees](#opportunity-solution-trees)
5. [Value Proposition Canvas](#value-proposition-canvas)
6. [Product Strategy Framework](#product-strategy-framework)
7. [OKRs (Objectives & Key Results)](#okrs-objectives--key-results)

---

## ⭐ North Star Framework

### **What Is It?**
The North Star is the ONE metric that best captures the core value you deliver to customers.

### **Why It Matters:**
- Aligns entire team on what success looks like
- Guides prioritization (does this move the North Star?)
- Leading indicator of long-term success

---

### **How to Find Your North Star:**

**Step 1: Identify Core Value**
Ask: "What value do we deliver to users?"

**Examples:**
- Spotify: Listen to music
- Airbnb: Book stays
- Slack: Communicate with team
- ChatGPT: Get helpful AI assistance

**Step 2: Make It Measurable**
Convert value to a metric that:
- ✅ Reflects value delivered (not just revenue)
- ✅ Is measurable consistently
- ✅ Team can influence
- ✅ Is a leading indicator

**Examples:**

| Company | Core Value | North Star Metric |
|---------|------------|-------------------|
| Spotify | Listening to music | Time spent listening per user |
| Airbnb | Booking stays | Nights booked |
| Slack | Team communication | Messages sent per DAU |
| Netflix | Watching content | Hours watched per subscriber |
| Notion | Working in your workspace | Engaged days per user |
| GitHub Copilot | Helpful code suggestions | Suggestions accepted per developer |

---

### **North Star for AI Products:**

**Principle:** Focus on VALUE delivered, not AI usage

❌ **Bad North Stars for AI:**
- "Number of AI queries" (usage, not value)
- "API calls" (activity, not outcome)

✅ **Good North Stars for AI:**
- "Tasks completed with AI assistance" (value)
- "Time saved per user per week" (outcome)
- "Content created and published" (end result)

---

### **Example: Finding North Star for AI Writing Assistant**

**Step 1: Core Value**
Help content marketers write blog posts faster

**Step 2: Metric Options**
1. Articles generated (just output, not value)
2. Time saved (hard to measure accurately)
3. Articles published using AI (proves value - they actually used it!)

**Step 3: North Star**
> **"Articles created with AI and published per user per month"**

**Why this works:**
- ✅ Reflects value (they completed their job)
- ✅ Measurable (track which articles used AI)
- ✅ Leading indicator (if they publish AI content, they'll keep using it)

---

### **Input Metrics:**
North Star is the outcome. Input metrics are levers that move it.

**Example - Spotify:**
- **North Star:** Time spent listening
- **Input Metrics:**
  - New releases added
  - Playlist creation
  - Recommendation accuracy
  - App open frequency
  - Download vs. stream ratio

**PM Role:** Improve input metrics → move North Star

---

## 💼 Jobs To Be Done (JTBD)

### **What Is It?**
A framework for understanding WHY users "hire" your product.

**Core Idea:** Users don't buy products, they "hire" them to do a job.

**Example:**
- Users don't buy a drill, they buy a hole in the wall
- Users don't buy Spotify, they buy background music while working

---

### **The JTBD Statement:**

**Format:**
> "When I [situation], I want to [motivation], so I can [outcome]."

**Examples:**

**1. Spotify Discover Weekly:**
> "When I'm bored of my current music, I want to discover new songs I'll love, so I can enjoy fresh music without effort."

**2. ChatGPT:**
> "When I need to write an email quickly, I want AI to draft it for me, so I can save time and avoid writer's block."

**3. GitHub Copilot:**
> "When I'm writing boilerplate code, I want AI to autocomplete it, so I can focus on business logic instead of syntax."

---

### **How to Use JTBD:**

**Step 1: Identify Jobs**
Interview users. Ask:
- What were you trying to accomplish?
- What triggered you to look for a solution?
- What did you use before?
- What would you do if our product didn't exist?

**Step 2: Break Down the Job**

**Functional Job:** The practical task
- Example: "Write a blog post"

**Emotional Job:** How they want to feel
- Example: "Feel confident the post is good quality"

**Social Job:** How they want to be perceived
- Example: "Be seen as a thought leader"

**Step 3: Identify Job Stages**

**Example - Writing a Blog Post:**
1. **Ideate:** Come up with topic
2. **Research:** Gather information
3. **Outline:** Structure the post
4. **Draft:** Write first version
5. **Edit:** Refine and polish
6. **Publish:** Share with audience
7. **Promote:** Drive traffic

**PM Insight:** Your product might help with ALL stages or specialize in ONE. Both are valid!

---

### **JTBD for AI Products:**

**Principle:** AI often "helps" do jobs, not "replace" entire jobs

**Example - AI Writing Assistant:**
- ❌ Job: "Write my blog post for me" (users want control)
- ✅ Job: "Help me overcome writer's block and write faster" (augmentation)

**PM Implication:** Position AI as copilot, not autopilot (unless full automation is truly desired)

---

## 🖼️ Problem Framing Canvas

### **What Is It?**
A structured way to define problems before jumping to solutions.

**Why It Matters:** Most failed products solve the wrong problem or solve it the wrong way.

---

### **The Canvas:**

```
┌─────────────────────────────────────────────────────────┐
│                    PROBLEM FRAMING                      │
├─────────────────────────────────────────────────────────┤
│ 1. Who has the problem?                                 │
│    [User segment, personas]                             │
│                                                          │
│ 2. What is the problem?                                 │
│    [Specific pain point, struggle]                      │
│                                                          │
│ 3. Why does it matter?                                  │
│    [Impact, frequency, urgency]                         │
│                                                          │
│ 4. What's the current alternative?                      │
│    [How do they solve it today?]                        │
│                                                          │
│ 5. Why are current alternatives insufficient?           │
│    [Gaps, frustrations]                                 │
│                                                          │
│ 6. What outcome would success look like?                │
│    [Desired end state]                                  │
│                                                          │
│ 7. What's our hypothesis?                               │
│    [If we do X, then Y will happen because Z]           │
└─────────────────────────────────────────────────────────┘
```

---

### **Example: AI-Powered Customer Support Bot**

**1. Who has the problem?**
- Primary: Customer support teams at B2B SaaS companies
- Secondary: End users (customers seeking help)

**2. What is the problem?**
- Support teams are overwhelmed with repetitive questions
- Users wait hours for answers to simple questions
- Support costs scale linearly with user growth

**3. Why does it matter?**
- Frequency: 60% of tickets are repetitive (password resets, "how do I...?")
- Impact: Slow responses → customer churn, team burnout
- Urgency: Company is growing 50% YoY, support team can't keep up

**4. What's the current alternative?**
- Hiring more support agents
- FAQ pages (users don't read)
- Zendesk macros (still requires human)

**5. Why are current alternatives insufficient?**
- Hiring: Expensive, slow to train, doesn't scale
- FAQs: Static, hard to find, not conversational
- Macros: Faster but still manual, agent time required

**6. What outcome would success look like?**
- 50% of repetitive tickets answered instantly by AI
- Support team handles only complex issues
- Customer satisfaction stays high (AI answers are helpful)
- Support cost per user decreases as company grows

**7. What's our hypothesis?**
> "If we build an AI chatbot that can answer common questions using our help docs, then we'll reduce repetitive ticket volume by 50%, because users will get instant accurate answers and won't need to submit tickets."

---

### **How to Use This:**

**Step 1:** Fill out the canvas BEFORE designing solutions
**Step 2:** Validate each section with user research
**Step 3:** Use it to align stakeholders (everyone agrees on the problem)
**Step 4:** Refer back when prioritizing (does this solve THE problem?)

---

## 🌳 Opportunity Solution Trees (OST)

### **What Is It?**
A visual framework to map opportunities, solutions, and experiments.

**Created by:** Teresa Torres (Product Talk)

**Structure:**
```
Outcome (North Star / OKR)
    │
    ├── Opportunity 1
    │       ├── Solution A
    │       │       └── Experiment 1
    │       └── Solution B
    │               └── Experiment 2
    │
    ├── Opportunity 2
    │       ├── Solution C
    │       └── Solution D
    │
    └── Opportunity 3
            └── Solution E
```

---

### **How to Build an OST:**

**Step 1: Define Outcome**
What's your goal? (Usually North Star or OKR)

**Example:**
> Increase "articles published with AI per user per month" from 2 to 5

**Step 2: Identify Opportunities**
What are the problems/needs preventing users from achieving the outcome?

**How to find opportunities:**
- User interviews ("What prevents you from writing more?")
- Analytics (where do users drop off?)
- Support tickets (what do users complain about?)

**Example Opportunities:**
1. Users struggle with writer's block (can't start)
2. Users spend too much time editing AI output (quality isn't good enough)
3. Users don't trust AI-generated content (worried about accuracy)
4. Users can't integrate AI into their workflow (friction)

**Step 3: Generate Solutions**
For EACH opportunity, brainstorm solutions

**Example - Opportunity 1: Writer's Block**
- Solution A: AI topic idea generator
- Solution B: AI outline generator from keywords
- Solution C: "Writing prompts" library for inspiration

**Step 4: Design Experiments**
For each solution, design quick tests to validate

**Example - Solution B: AI Outline Generator**
- Experiment: Build simple prototype, test with 10 users, measure:
  - Do they use it?
  - Does it lead to more articles published?
  - User feedback on quality

---

### **Example OST: AI Writing Assistant**

```
Outcome: Increase articles published per user from 2 → 5 per month
    │
    ├── Opportunity 1: Writer's block
    │       ├── Solution A: Topic idea generator
    │       │       └── Experiment: Prototype + 10 user test
    │       └── Solution B: Outline generator ✅ (selected)
    │               └── Experiment: Build MVP, measure usage
    │
    ├── Opportunity 2: Low AI output quality
    │       ├── Solution C: Fine-tune model on brand voice
    │       │       └── Experiment: A/B test GPT-3.5 vs. fine-tuned
    │       └── Solution D: Iterative refinement UI
    │               └── Experiment: Prototype "refine" feature
    │
    ├── Opportunity 3: Trust / accuracy concerns
    │       ├── Solution E: Add fact-checking prompts
    │       └── Solution F: Show confidence scores
    │
    └── Opportunity 4: Workflow friction
            ├── Solution G: Notion integration
            └── Solution H: Google Docs plugin
```

**PM Use:** Visualize the problem space, prioritize which opportunities to tackle first, design experiments to learn quickly.

---

## 🎨 Value Proposition Canvas

### **What Is It?**
A framework to ensure product-market fit by mapping what you offer to what customers need.

**Structure:**
```
┌──────────────────┐        ┌──────────────────┐
│   Customer       │        │   Value          │
│   Profile        │   ←→   │   Proposition    │
└──────────────────┘        └──────────────────┘
```

---

### **Customer Profile:**

**1. Customer Jobs:**
- What are they trying to accomplish?
- What problems are they trying to solve?

**2. Pains:**
- What frustrates them?
- What obstacles do they face?
- What risks do they worry about?

**3. Gains:**
- What outcomes do they want?
- What would make their job easier?
- What would delight them?

---

### **Value Proposition:**

**1. Products & Services:**
- What you offer

**2. Pain Relievers:**
- How you eliminate or reduce pains

**3. Gain Creators:**
- How you create desired outcomes or benefits

---

### **Example: GitHub Copilot**

**Customer Profile (Software Developers):**

**Jobs:**
- Write code quickly
- Implement features
- Fix bugs

**Pains:**
- Writing boilerplate is tedious
- Forgetting syntax slows me down
- Context switching to Google disrupts flow

**Gains:**
- Ship features faster
- Focus on creative problem-solving (not syntax)
- Learn new languages/frameworks faster

---

**Value Proposition (GitHub Copilot):**

**Product:**
- AI code completion in your IDE

**Pain Relievers:**
- Auto-generates boilerplate → no more tedious typing
- Suggests syntax in real-time → no need to Google
- Works in your IDE → no context switching

**Gain Creators:**
- Code faster (10-30% productivity boost)
- Learn by seeing suggestions → educational
- Focus on logic, not syntax → more creative work

---

**Fit:**
When pain relievers address pains AND gain creators deliver gains → you have product-market fit!

---

## 📊 Product Strategy Framework

### **What Is Strategy?**
**Strategy = Choices** about:
1. **Where to play** (target market, segments)
2. **How to win** (differentiation, competitive advantage)
3. **What to build** (capabilities, features)

---

### **The Strategy Stack:**

```
Vision
  ↓
Strategy
  ↓
Roadmap
  ↓
Features
```

**Vision:** Long-term aspiration (where we want to be in 5-10 years)
**Strategy:** How we'll achieve the vision (our competitive approach)
**Roadmap:** Sequence of bets (what we'll build when)
**Features:** Specific solutions (the tactical execution)

**PM Trap:** Jumping straight to features without strategy!

---

### **How to Build Strategy:**

**Step 1: Define Vision**
Where do you want to be in 5 years?

**Example - Notion:**
> "Notion will be the operating system for work - where all knowledge, tasks, and collaboration happen."

**Step 2: Understand Context**

**Market Analysis:**
- Size, growth, trends
- Customer segments
- Competitive landscape

**Internal Analysis:**
- Our strengths, weaknesses
- Resources, capabilities
- Current position

**Step 3: Make Strategic Choices**

**A. Where to Play:**
- Which customer segments?
- Which use cases?
- Which geographies?

**Example - Notion:**
- Focus on: Tech startups, creative teams, remote-first companies
- Not (yet): Fortune 500, highly regulated industries

**B. How to Win:**
- What's our competitive advantage?
- Why will customers choose us?

**Example - Notion:**
- Flexibility (customizable blocks, databases)
- Beautiful, delightful UX
- All-in-one (docs + projects + wiki)

**Step 4: Translate to Roadmap**
What capabilities must we build to execute the strategy?

**Example - Notion:**
- Capability 1: Flexible databases (enables customization)
- Capability 2: Real-time collaboration (enables teams)
- Capability 3: AI assistance (enables productivity)

---

## 🎯 OKRs (Objectives & Key Results)

### **What Are OKRs?**
A goal-setting framework to align teams and measure progress.

**Structure:**
- **Objective:** Qualitative, aspirational goal
- **Key Results:** Quantitative, measurable outcomes

---

### **Format:**

**Objective:** [Inspirational goal]

**Key Results:**
1. [Measurable outcome 1]
2. [Measurable outcome 2]
3. [Measurable outcome 3]

**Timeframe:** Quarterly or annually

---

### **Example OKRs:**

**Example 1 - AI Writing Assistant:**

**Objective:** Become the go-to AI writing tool for content marketers

**Key Results:**
1. Increase articles published with AI from 500/month → 2,000/month
2. Achieve 60% Month 1 retention (up from 40%)
3. NPS score of 50+ (up from 35)

---

**Example 2 - GitHub Copilot:**

**Objective:** Make developers significantly more productive

**Key Results:**
1. 1M active developers using Copilot daily (up from 500K)
2. 40% suggestion acceptance rate (up from 30%)
3. Users report 25% time savings (measured via survey)

---

### **How to Write Great OKRs:**

**Objectives:**
- ✅ Inspirational, motivating
- ✅ Qualitative
- ✅ Time-bound (Q1, Q2, etc.)
- ❌ Not just "do more of X"

**Key Results:**
- ✅ Measurable (number, %, etc.)
- ✅ Outcome-focused (not activities)
- ✅ Ambitious but achievable (70% success is good)
- ❌ Not just tasks or milestones

**Bad Example:**
- Objective: Improve the product
- KR1: Ship 5 features
- KR2: Fix 100 bugs

**Why bad:** Not inspirational, KRs are activities not outcomes

**Good Example:**
- Objective: Delight users with AI-powered productivity
- KR1: Increase DAU from 10K → 25K
- KR2: Improve task completion rate from 60% → 80%
- KR3: Achieve 4.5+ App Store rating

**Why good:** Inspiring objective, outcome-based KRs

---

## 🧭 How to Use These Frameworks Together

**Step 1: Start with Problem Framing**
- Understand the problem deeply before jumping to solutions

**Step 2: Use JTBD to Understand Users**
- What job are they hiring your product for?

**Step 3: Define North Star**
- What ONE metric captures value delivered?

**Step 4: Build Opportunity Solution Tree**
- Map opportunities, solutions, experiments

**Step 5: Create Value Proposition**
- Ensure what you're building addresses pains and creates gains

**Step 6: Set Strategy**
- Where to play, how to win

**Step 7: Define OKRs**
- Quarterly goals to execute strategy

**Step 8: Build Roadmap**
- Sequence of bets to achieve OKRs

---

## ✅ Week 1 Checklist

By the end of Week 1, you should be able to:

- [ ] Define a North Star metric for any product
- [ ] Write a JTBD statement
- [ ] Fill out a Problem Framing Canvas
- [ ] Sketch an Opportunity Solution Tree
- [ ] Create a Value Proposition Canvas
- [ ] Articulate product strategy (where to play, how to win)
- [ ] Write OKRs for a product or initiative

---

## 📚 Recommended Resources

**Books:**
- 📚 **"Continuous Discovery Habits"** by Teresa Torres (OST framework)
- 📚 **"Competing Against Luck"** by Clayton Christensen (JTBD)
- 📚 **"Inspired"** by Marty Cagan (Product strategy)
- 📚 **"Measure What Matters"** by John Doerr (OKRs)

**Online:**
- 🎓 **Product Talk** (Teresa Torres' blog) - OST deep dives
- 🎓 **Lenny's Newsletter** - PM frameworks and case studies
- 🎓 **Strategyzer** - Value Proposition Canvas tools

---

## 🎬 Conclusion

These frameworks are your PM toolkit. Master them and you'll:
- Frame problems clearly
- Understand users deeply
- Prioritize confidently
- Communicate effectively
- Execute strategically

**Practice:**
1. Apply each framework to a real product (pick ChatGPT, Spotify, or your favorite app)
2. Use them for your Week 9-11 portfolio project
3. Reference them in interviews (shows structured thinking!)

You now have the strategic foundation every AI PM needs. Let's build! 🚀

---

**Last Updated:** 2025-01-15
