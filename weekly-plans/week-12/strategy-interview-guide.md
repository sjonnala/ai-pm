# Strategy Interview Guide for AI PMs

## 🎯 Overview

Strategy interviews test your ability to think big picture: market dynamics, competitive positioning, business models, and long-term vision. Unlike execution (tactical) or product sense (user-focused), strategy questions assess CEO-level thinking.

For AI PM roles, strategy questions have unique dimensions: AI market dynamics, platform decisions, build vs. buy, competitive moats in AI, and navigating rapid technological change.

This guide covers frameworks, question types, and practice to master strategy interviews.

---

## 📋 What Interviewers Are Evaluating

### Core Competencies:
1. **Strategic Thinking** - Can you think beyond features to markets and ecosystems?
2. **Business Acumen** - Do you understand business models, revenue, and profitability?
3. **Market Analysis** - Can you analyze competitive landscapes and trends?
4. **Vision** - Can you articulate a compelling long-term direction?
5. **Trade-off Evaluation** - Can you weigh strategic options against constraints?
6. **Risk Assessment** - Do you identify and mitigate strategic risks?
7. **AI Market Fluency** - Do you understand AI-specific dynamics? ⭐
8. **Platform Thinking** - Can you think in ecosystems, not just features? ⭐
9. **Technology Evolution** - Can you anticipate where AI is heading? ⭐
10. **Decision-Making** - Can you make bold, defensible strategic bets?

---

## 🎨 Common Question Types

### Type 1: Market Entry / Expansion
**Examples:**
- "Should Google build an AI-first search competitor?"
- "Should we enter the AI coding assistant market?"
- "How would you expand into the enterprise segment?"

**What they're testing:** Market analysis, competitive positioning, entry strategy

---

### Type 2: Competitive Strategy
**Examples:**
- "How should Notion compete with Microsoft Copilot?"
- "What should OpenAI do about open-source LLMs?"
- "How do you defend against [competitor]?"

**What they're testing:** Competitive moats, differentiation, defensibility

---

### Type 3: Pricing & Monetization
**Examples:**
- "How would you price ChatGPT?"
- "Should we charge per seat or per usage for our AI product?"
- "What's the right business model for an AI recommendation engine?"

**What they're testing:** Business model design, unit economics, willingness to pay

---

### Type 4: Build vs. Buy / Partnership
**Examples:**
- "Should we build our own LLM or use OpenAI's API?"
- "Should Spotify partner with OpenAI or build in-house?"
- "Would you acquire [startup] or build the feature ourselves?"

**What they're testing:** Make vs. buy analysis, partnership strategy, resource allocation

---

### Type 5: Portfolio & Prioritization
**Examples:**
- "What AI products should Amazon prioritize?"
- "How do you decide between improving existing products vs. launching new ones?"
- "Should we focus on consumer or enterprise?"

**What they're testing:** Portfolio management, resource allocation, strategic focus

---

### Type 6: Long-Term Vision
**Examples:**
- "Where will AI search be in 5 years?"
- "What's your vision for the future of AI productivity tools?"
- "How will AI change [industry]?"

**What they're testing:** Vision, trend anticipation, thought leadership

---

### Type 7: Platform Strategy
**Examples:**
- "Should we build a platform or a product?"
- "How would you create a developer ecosystem around your AI product?"
- "Should we open-source our AI model?"

**What they're testing:** Platform thinking, ecosystem strategy, network effects

---

## 🧭 Framework 1: Market Entry Strategy

**Question Format:** "Should [company] enter [market/launch product]?"

### **Step 1: Clarify the Context**

**Questions to Ask:**
- Why are we considering this? (strategic imperative, opportunity, competitive threat?)
- What are our goals? (revenue, market share, learning, defense?)
- What resources do we have? (capital, talent, technology, distribution?)
- What constraints exist? (time, regulatory, technical?)
- What's the time horizon? (short-term experiment vs. long-term bet?)

---

### **Step 2: Analyze the Market**

**Market Opportunity Framework:**

#### **A. Market Size & Growth**
```
TAM (Total Addressable Market): How big is the entire market?
SAM (Serviceable Addressable Market): How much can we realistically target?
SOM (Serviceable Obtainable Market): How much can we capture in Year 1-3?

Growth: Is the market growing, stable, or declining?
```

**Example (AI Coding Assistant Market):**
```
TAM: 27M developers globally × $10-20/month = $3-6B annually
SAM: 5M professional developers (enterprises + serious indie devs) = $600M-1B
SOM: Capture 5% in Year 3 = $30-50M

Growth: 20-30% annually (driven by AI adoption + developer growth)
```

#### **B. Market Dynamics**
- **Maturity:** Emerging, growing, mature, declining?
- **Fragmentation:** Many small players or dominated by few big players?
- **Customer Pain:** How acute is the problem? Willingness to pay?
- **Switching Costs:** Hard or easy for customers to switch?

**Example (AI Search):**
```
Maturity: Emerging (Perplexity, You.com, but Google dominates traditional search)
Fragmentation: Google has 90%+ share, but AI search is wide open
Customer Pain: Information overload, desire for direct answers (high)
Switching Costs: Low (behavior change is the barrier, not technology)
```

---

### **Step 3: Competitive Analysis**

**5 Forces Framework (Porter):**

#### **1. Competitive Rivalry**
- Who are the current players?
- What are their strengths/weaknesses?
- How intense is competition?

#### **2. Threat of New Entrants**
- How easy is it for others to enter?
- What are the barriers (capital, data, brand, distribution)?

#### **3. Bargaining Power of Buyers**
- How much power do customers have?
- Can they negotiate price?
- Are there many alternatives?

#### **4. Bargaining Power of Suppliers**
- Who are suppliers? (e.g., compute providers, LLM APIs)
- Can they dictate terms?

#### **5. Threat of Substitutes**
- What alternatives exist?
- How easy is it for customers to use something else?

**Example (AI Coding Assistant):**
```
Rivalry: GitHub Copilot dominates, but Cursor, Replit, Tabnine compete
New Entrants: Low barrier (fine-tune LLM), but quality & integration are hard
Buyer Power: High (developers can switch easily, many options)
Supplier Power: High (OpenAI, Anthropic control best models)
Substitutes: Traditional autocomplete, Stack Overflow, doing it manually
```

---

### **Step 4: Our Competitive Advantages**

**Framework: VRIO (Valuable, Rare, Inimitable, Organized)**

Ask: What unique advantages do we have?

| Resource/Capability | Valuable? | Rare? | Inimitable? | Organized? | Competitive Advantage? |
|---------------------|-----------|-------|-------------|------------|------------------------|
| Proprietary data | ✅ | ✅ | ✅ | ✅ | Sustained advantage |
| Brand (e.g., Google) | ✅ | ✅ | ✅ | ✅ | Sustained advantage |
| Distribution (e.g., Microsoft's Office) | ✅ | ✅ | ✅ | ✅ | Sustained advantage |
| Capital | ✅ | ❌ | ❌ | ✅ | Temporary advantage |
| AI talent | ✅ | ✅ | ❌ | ✅ | Temporary advantage |

**Example (Should Spotify Build AI Music Discovery?):**
```
Spotify's Advantages:
✅ 100B+ hours of listening data (rare, valuable, hard to replicate)
✅ 500M users (distribution)
✅ Music industry relationships (rare)
✅ Brand trust in music recommendations

Weaknesses:
❌ No in-house LLM (dependent on third parties)
❌ Limited AI research team (vs. Google, OpenAI)
```

**Conclusion:** Spotify should build on AI music discovery because they have unmatched data and distribution. They can use third-party LLMs (OpenAI) but differentiate with proprietary data.

---

### **Step 5: Strategic Options & Evaluation**

**Brainstorm Strategic Options:**

1. **Enter aggressively** (full investment, make it a priority)
2. **Enter cautiously** (MVP, test, iterate)
3. **Partner** (integrate with existing player)
4. **Acquire** (buy a startup in the space)
5. **Don't enter** (focus resources elsewhere)

**Evaluation Criteria:**

| Criterion | Weight | Option 1 | Option 2 | Option 3 |
|-----------|--------|----------|----------|----------|
| Market opportunity | 30% | 8 | 6 | 4 |
| Strategic fit | 25% | 9 | 7 | 5 |
| Competitive advantage | 20% | 7 | 8 | 6 |
| Execution risk | 15% | 5 | 8 | 9 |
| ROI potential | 10% | 8 | 6 | 5 |
| **Total Score** | | **7.45** | **7.00** | **5.65** |

**Example Decision:**
> "Based on this analysis, I recommend we **enter cautiously** with an MVP approach:
> - Market opportunity is large (7/10)
> - We have competitive advantages (data, distribution)
> - But execution risk is high (new technology, uncertain adoption)
> - MVP lets us learn quickly with limited downside"

---

### **Step 6: Entry Strategy & Success Metrics**

**Define:**
- **Go-to-market:** How will we enter? (Beta, full launch, partnerships?)
- **Timeline:** Phased approach (MVP in 3 months → Scale in 6 months)
- **Resources:** What do we need? (engineers, budget, partnerships)
- **Success metrics:** How will we know it's working?
  - Year 1: 10,000 users, 30% retention, learn product-market fit
  - Year 2: 100,000 users, $1M ARR, positive unit economics
  - Year 3: 500,000 users, $10M ARR, clear path to profitability

---

### **Step 7: Risks & Mitigations**

**Identify Key Risks:**

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Competitor launches better product | High | High | Move fast, differentiate on unique data |
| Technology doesn't work (AI quality) | Medium | High | Extensive testing, phased rollout |
| Users don't adopt | Medium | High | User research, clear value prop, onboarding |
| Regulatory issues | Low | High | Legal review, privacy-first design |
| Cost too high (AI inference) | Medium | Medium | Optimize models, tiered pricing |

---

### **Complete Answer Template:**

**Question:** "Should Google build an AI-first search competitor?"

**Answer:**

> "Great question. Let me clarify first: Are we talking about replacing Google Search entirely, or launching a separate AI search product alongside it? [Assume: separate product to test]
>
> **Market Analysis:**
> The AI search market is emerging and high-growth. Users increasingly want direct answers, not links. Perplexity, You.com, and ChatGPT are gaining traction, showing demand. TAM is massive - search is a $150B+ market. If AI search captures even 10%, that's $15B.
>
> **Competitive Landscape:**
> Google dominates traditional search (90% share), but AI search is wide open. Competitors:
> - Perplexity: First-mover in AI search, strong UX, but small scale
> - OpenAI: ChatGPT has search capabilities, massive distribution
> - Microsoft: Bing + GPT partnership, improving share
>
> **Google's Advantages:**
> - Unmatched data (web index, user behavior, Knowledge Graph)
> - Best AI research (DeepMind, Google Brain)
> - Distribution (default search on Chrome, Android)
> - Brand trust
>
> **Strategic Options:**
> 1. Build AI-first search as separate product (Google AI Search)
> 2. Integrate AI into existing Google Search
> 3. Acquire Perplexity or similar
> 4. Do nothing (defend traditional search)
>
> **Recommendation: Build AI-first search as SEPARATE product**
> Why separate, not integrated?
> - Traditional search has different UX (links) vs. AI search (direct answers)
> - Ad model is different (uncertain how to monetize AI search without disrupting core business)
> - Let AI search iterate fast without breaking Google Search
> - Hedge against disruption (cannibalize ourselves before others do)
>
> **Entry Strategy:**
> - Phase 1 (3 months): Limited beta with power users, focus on quality and trust
> - Phase 2 (6 months): Public launch, free tier, gather usage data
> - Phase 3 (12 months): Iterate on monetization (subscription, enterprise, ads?)
>
> **Success Metrics:**
> - Year 1: 10M users, 40% weekly retention, NPS >50
> - Year 2: 50M users, find sustainable monetization model
> - Year 3: 100M users, clear path to $1B+ revenue
>
> **Key Risks:**
> 1. **Cannibalization:** AI search could cannibalize Google Search revenue
>    - Mitigation: Keep separate, experiment with new business models
> 2. **Accuracy:** AI hallucinations damage Google's trust
>    - Mitigation: Rigorous evaluation, citations, human review
> 3. **Competitive response:** Microsoft, OpenAI move faster
>    - Mitigation: Leverage Google's data and AI advantages, move quickly
>
> **Why This Makes Sense:**
> AI search is the future. If Google doesn't build it, someone else will - and could disrupt Google's core business. Building a separate AI search product lets Google innovate without risking $150B in search revenue. It's a classic innovator's dilemma situation - the right move is to disrupt yourself.
>
> Does this align with what you were looking for, or should I dive deeper into any specific area?"

---

## 💰 Framework 2: Pricing & Business Model Strategy

**Question Format:** "How would you price [AI product]?" or "What business model should we use?"

### **Step 1: Understand Cost Structure**

**For AI Products, Key Costs:**

#### **1. Infrastructure Costs**
- **Compute:** GPU/TPU for inference
- **Storage:** Data storage, model weights
- **Bandwidth:** API calls, data transfer

#### **2. Model Costs** (if using third-party)
- **OpenAI API:** $0.01-0.06 per 1K tokens (varies by model)
- **Anthropic Claude:** Similar pricing
- **Self-hosted:** Higher upfront, lower marginal

#### **3. Operational Costs**
- **Engineering:** Development, maintenance, improvements
- **Support:** Customer support, documentation
- **Sales & Marketing:** Customer acquisition

**Example (AI Writing Assistant):**
```
Cost per user per month:
- LLM API (GPT-4): $3 (assuming 50 requests/month, 2K tokens each)
- Infrastructure: $0.50 (hosting, storage)
- Support & ops: $1 (customer support, tools)
- S&M: $2 (acquisition cost amortized)
---
Total: $6.50 per user per month
```

**Margin Target:** Aim for 70-80% gross margin → Price at $20-30/month

---

### **Step 2: Understand Willingness to Pay**

**Questions to Answer:**
- What value does the product deliver to users?
- What are they currently paying for alternatives?
- How much time/money does the product save?
- What's the ROI for the customer?

**Value-Based Pricing Framework:**
```
User Value = Time Saved × Hourly Rate + Quality Improvement Value

Example (AI Writing Assistant for Content Marketer):
- Time saved: 10 hours/month (article writing)
- Hourly rate: $50/hour
- Value: 10 × $50 = $500/month

User would pay up to $500/month for this value.
Price at 10-20% of value = $50-100/month
```

**Competitive Pricing:**
- What do competitors charge?
- Where do we fit (premium, mid-tier, budget)?

**Example:**
```
Jasper AI: $49/month (established player)
Copy.ai: $36/month (mid-tier)
ChatGPT Plus: $20/month (general-purpose, lower than specialized)

Our price: $39/month (competitive with specialized tools, premium over ChatGPT)
```

---

### **Step 3: Choose Business Model**

**Common AI Product Business Models:**

#### **1. Subscription (Flat Fee)**
- **How it works:** $X/month or $Y/year, unlimited usage
- **Pros:** Predictable revenue, simple for users
- **Cons:** Power users get subsidized, light users overpay
- **Example:** ChatGPT Plus ($20/month)

#### **2. Usage-Based Pricing**
- **How it works:** Pay per API call, per generation, per token
- **Pros:** Fair (pay for what you use), scales with value
- **Cons:** Unpredictable costs for users, can discourage usage
- **Example:** OpenAI API ($0.01-0.06 per 1K tokens)

#### **3. Freemium**
- **How it works:** Free tier (limited) + Paid tier (unlimited/premium features)
- **Pros:** Wide adoption, land-and-expand, try before buy
- **Cons:** Free users are costly, conversion can be low
- **Example:** ChatGPT (Free: GPT-3.5, Paid: GPT-4)

#### **4. Tiered Pricing**
- **How it works:** Multiple tiers (Basic, Pro, Enterprise) with different features/limits
- **Pros:** Captures different willingness to pay, upsell opportunities
- **Cons:** Complex to manage, users may feel nickel-and-dimed
- **Example:** Jasper AI (Creator $49, Teams $125, Business custom)

#### **5. Seat-Based (B2B)**
- **How it works:** $X per user per month
- **Pros:** Predictable, scales with team size
- **Cons:** Doesn't reflect actual usage, can discourage adding users
- **Example:** GitHub Copilot Business ($19/user/month)

#### **6. Hybrid (Seats + Usage)**
- **How it works:** Base fee per user + overages for heavy usage
- **Pros:** Predictable baseline + scales with value
- **Cons:** More complex to understand
- **Example:** Many enterprise AI tools

---

### **Step 4: Recommend Pricing Strategy**

**Decision Framework:**

| Factor | Subscription | Usage-Based | Freemium | Tiered |
|--------|--------------|-------------|----------|--------|
| Predictable costs for user | ✅ | ❌ | ✅ | ✅ |
| Fair (pay for value) | ❌ | ✅ | ✅ | ✅ |
| Encourages heavy usage | ✅ | ❌ | ✅ | ✅ |
| Drives adoption | ❌ | ❌ | ✅ | ✅ |
| Simple to understand | ✅ | ✅ | ❌ | ❌ |
| Good for B2C | ✅ | ❌ | ✅ | ✅ |
| Good for B2B | ✅ | ✅ | ❌ | ✅ |

---

### **Complete Answer Template:**

**Question:** "How would you price ChatGPT?"

**Answer:**

> "Great question. Let me think through cost structure, willingness to pay, and business model options.
>
> **Cost Structure:**
> Per user per month:
> - LLM inference (GPT-4): ~$5-10 (depending on usage)
> - Infrastructure: $1
> - Support & ops: $1
> Total: ~$7-12 per user
>
> Target 70-80% gross margin → price at $30-50/month
>
> **Willingness to Pay:**
> ChatGPT delivers massive value:
> - Professionals: Saves 5-10 hours/month on writing, research, analysis
> - At $50/hour, that's $250-500/month of value
> - Users would pay up to 10-20% of value = $25-100/month
>
> Competitors:
> - Gemini Advanced: $20/month
> - Claude Pro: $20/month
> - Specialized tools (Jasper): $49/month
>
> ChatGPT is generalist, so should be priced lower than specialized tools but premium for quality.
>
> **Business Model Options:**
>
> **Option 1: Freemium (Current Model)**
> - Free: GPT-3.5 (lower quality, slower)
> - Plus: $20/month for GPT-4, faster, priority
> Pros: Wide adoption (100M+ free users), land-and-expand
> Cons: Free users are costly to serve
>
> **Option 2: Tiered Pricing**
> - Basic: $10/month (GPT-3.5, limited)
> - Pro: $30/month (GPT-4, unlimited)
> - Team: $50/user/month (collaboration, admin)
> - Enterprise: Custom (security, SLA)
> Pros: Captures more willingness to pay, upsell path
> Cons: More complex
>
> **Option 3: Usage-Based**
> - Pay per message or per token
> Pros: Fair, scales with value
> Cons: Unpredictable costs discourage usage
>
> **My Recommendation: Tiered Freemium**
> - Free: GPT-3.5, 10 messages/day (drive adoption)
> - Plus: $20/month, GPT-4, 50 messages/3 hours (current offering)
> - Pro: $50/month, GPT-4, unlimited, faster, priority features (capture power users)
> - Teams: $40/user/month, collaboration, shared knowledge, admin controls
> - Enterprise: Custom, security, compliance, dedicated support
>
> **Rationale:**
> - Free tier drives adoption and viral growth (already working - 100M users)
> - Plus tier ($20) is proven and competitive with Gemini/Claude
> - Pro tier ($50) captures power users who get more value (writers, researchers, developers)
> - Teams/Enterprise captures B2B market (huge opportunity, higher margins)
>
> **Success Metrics:**
> - Free → Plus conversion: >5% (industry standard)
> - Plus → Pro upgrade: >10% (power users willing to pay more)
> - ARPU: $15 (blended across free and paid)
> - LTV: $500+ (assuming 2-3 year retention)
> - CAC: <$50 (viral growth keeps acquisition costs low)
>
> **Risks & Mitigations:**
> - Risk: Competitors price lower → Mitigation: Differentiate on quality (GPT-4 superiority)
> - Risk: Free tier too costly → Mitigation: Throttle usage (messages/day limit)
> - Risk: Power users churn → Mitigation: Build stickiness (memory, integrations, personalization)
>
> Does this approach make sense, or should I explore a different direction?"

---

## 🏆 Framework 3: Competitive Strategy

**Question Format:** "How should [company] compete with [competitor]?"

### **Step 1: Understand the Competitive Threat**

**Questions:**
- Who is the competitor?
- What's their advantage? (product, distribution, brand, cost, data, etc.)
- What are they doing well?
- Where are they weak?
- How urgent is the threat?

---

### **Step 2: Analyze Our Position**

**Our Strengths vs. Weaknesses:**

Use **SWOT Analysis:**

| **Strengths** | **Weaknesses** |
|---------------|----------------|
| What do we do better? | Where are we behind? |
| What unique advantages? | What vulnerabilities? |

| **Opportunities** | **Threats** |
|-------------------|-------------|
| What market trends favor us? | What could disrupt us? |
| Where can we grow? | What are we at risk of losing? |

---

### **Step 3: Choose Competitive Strategy**

**Porter's Generic Strategies:**

#### **1. Cost Leadership**
- Be the lowest-cost provider
- Compete on price
- Example: ChatGPT free tier (subsidize with premium users)

#### **2. Differentiation**
- Be unique in ways customers value
- Compete on quality, features, brand
- Example: GitHub Copilot (native IDE integration, developer trust)

#### **3. Focus (Niche)**
- Dominate a specific segment
- Compete by being the best for a specific audience
- Example: Harvey AI (legal-specific AI, deep domain expertise)

**For AI Products, Common Differentiation Dimensions:**
- **Quality:** Better model, fewer hallucinations
- **Speed:** Lower latency
- **Cost:** Cheaper pricing
- **Data:** Proprietary data advantage
- **Integration:** Seamless workflow integration
- **Trust:** Safety, privacy, compliance
- **Customization:** Fine-tuned for specific use cases

---

### **Step 4: Develop Competitive Moves**

**Offensive Strategies:**
1. **Out-innovate:** Build better product faster
2. **Out-distribute:** Win on distribution/partnerships
3. **Out-spend:** Aggressive marketing, acquire users faster
4. **Undercut:** Price lower to gain share

**Defensive Strategies:**
1. **Build moats:** Create switching costs, lock-in, network effects
2. **Partnerships:** Exclusive deals, strategic alliances
3. **Vertical integration:** Own more of the stack (data, model, distribution)
4. **Brand:** Build strong brand loyalty

---

### **Complete Answer Template:**

**Question:** "How should Notion compete with Microsoft Copilot?"

**Answer:**

> "This is a classic David vs. Goliath scenario. Let me analyze the competitive dynamics.
>
> **Understand the Threat:**
> Microsoft Copilot is integrated across Office 365 (Word, Excel, PowerPoint, Teams). They have:
> - **Distribution:** 345M paid Office 365 users
> - **Integration:** Native in workflows users already use
> - **Brand:** Microsoft trust, enterprise relationships
> - **Resources:** Unlimited capital, top AI talent, OpenAI partnership
>
> This is a significant threat. Microsoft could make Notion obsolete if they build flexible workspace capabilities into Copilot.
>
> **Notion's Position (SWOT):**
>
> **Strengths:**
> - **Product:** Flexible, loved by users (Net Promoter Score very high)
> - **Community:** Passionate user base, viral growth
> - **Workflow:** People have entire workflows/knowledge bases in Notion (high switching cost)
> - **Agility:** Can move faster than Microsoft (smaller, more focused)
>
> **Weaknesses:**
> - **Distribution:** 30M users vs. Microsoft's 345M (10x smaller)
> - **Enterprise:** Less penetration in large enterprises (Microsoft's stronghold)
> - **Resources:** Can't outspend Microsoft
>
> **Opportunities:**
> - **Collaboration:** Remote work trends favor flexible tools like Notion
> - **Customization:** Power users want more than Office offers
> - **AI-native redesign:** Notion can reimagine workspace from scratch for AI era
>
> **Threats:**
> - **Microsoft builds Notion-like flexibility into Office** (biggest risk)
> - **Enterprises stick with Microsoft** (procurement relationships, compliance)
>
> **Competitive Strategy: Differentiation + Focus**
>
> Notion CANNOT compete on distribution or price. Must differentiate.
>
> **My Recommendation: "AI-Native Workspace" Strategy**
>
> **1. Double Down on Flexibility (Core Strength)**
> - Make Notion THE platform for building custom AI workflows
> - Let users create custom AI agents, automations, databases
> - Microsoft Copilot is one-size-fits-all; Notion is endlessly customizable
>
> **2. Build AI-Native Features Microsoft Can't**
> - **Proactive AI:** Notion AI suggests tasks, organizes info automatically
> - **Memory:** AI learns from your entire workspace, suggests connections
> - **Custom AI Agents:** Users build domain-specific AI assistants
> - Example: Marketing team builds "Brand Voice AI" trained on past campaigns
>
> **3. Win Specific Segments (Focus Strategy)**
> - Target: **Startups, tech companies, creative teams** (Notion's stronghold)
> - These users value flexibility > legacy Office integration
> - Build community, templates, ecosystem for these segments
>
> **4. Deepen Switching Costs**
> - Make Notion indispensable by:
>   - AI that learns from YOUR workspace (can't replicate in Office)
>   - Community templates and integrations (network effects)
>   - Workflows deeply embedded (high exit cost)
>
> **5. Strategic Partnerships**
> - Integrate with Slack, Figma, Linear (workflow tools startups use)
> - Build "best of breed" stack vs. Microsoft's all-in-one
> - Position as "AI layer" that connects everything
>
> **What NOT to Do:**
> ❌ Don't compete on distribution (Microsoft wins)
> ❌ Don't try to win enterprise Fortune 500 (Microsoft's home turf)
> ❌ Don't race to add every Copilot feature (you'll always be behind)
>
> **Success Metrics:**
> - Retain existing users (churn <5% annually)
> - Deepen engagement (DAU/MAU ratio, pages per user)
> - Win specific segments (50%+ market share in tech startups, agencies)
> - AI feature adoption (>70% of users use Notion AI weekly)
>
> **Long-Term Vision:**
> Notion becomes the "operating system for work" for modern teams. While Microsoft owns traditional enterprises, Notion owns the future of work - flexible, AI-native, customizable. Think: Microsoft Office is to Boomers/Gen X as Notion is to Millennials/Gen Z.
>
> **Key Insight:**
> This isn't about beating Microsoft head-on. It's about being so different and so valuable to your core audience that Microsoft's advantages don't matter. Notion should be the AI workspace that Microsoft Copilot *can't* be because of Microsoft's legacy constraints.
>
> Does this strategy make sense, or should I explore a different approach?"

---

## 🔮 Framework 4: Long-Term Vision & Trends

**Question Format:** "Where will [AI category] be in 5 years?" or "What's your vision for [AI in industry]?"

### **Approach:**

1. **Acknowledge current state** (where are we today?)
2. **Identify key trends** (what's changing?)
3. **Extrapolate forward** (where does this lead?)
4. **Paint a vision** (what becomes possible?)
5. **Identify implications** (what does this mean for products/companies?)

---

### **Key AI Trends to Know:**

#### **1. Model Capabilities**
- **Now:** GPT-4 level, multimodal (text + image)
- **5 years:** Ultra-long context (millions of tokens), true reasoning, video understanding, agentic behavior

#### **2. Cost & Accessibility**
- **Now:** GPT-4 quality costs $0.01-0.06 per 1K tokens
- **5 years:** 10-100x cheaper, local models on devices (Apple Intelligence style)

#### **3. Personalization**
- **Now:** Generic models, some fine-tuning
- **5 years:** Deeply personalized (learns your style, preferences, context)

#### **4. Integration**
- **Now:** Standalone apps, some API integrations
- **5 years:** AI embedded in everything (OS-level, every app)

#### **5. Autonomy**
- **Now:** Reactive (you ask, AI responds)
- **5 years:** Proactive agents (AI takes actions on your behalf)

#### **6. Regulation**
- **Now:** Light regulation, mostly self-regulation
- **5 years:** Stricter rules (safety, copyright, privacy, misinformation)

---

### **Complete Answer Template:**

**Question:** "Where will AI search be in 5 years?"

**Answer:**

> "Let me paint a picture of where I think AI search is heading.
>
> **Today (2025):**
> - AI search is emerging: Perplexity, You.com, ChatGPT search
> - UX: Type question → get answer with citations
> - Limitations: Sometimes wrong, no personalization, limited follow-up
> - Google Search still dominant (90% share)
>
> **Key Trends:**
> 1. **Model quality improving rapidly:** GPT-5+ will have better reasoning, fewer hallucinations
> 2. **Cost dropping:** AI search will be economically viable at scale
> 3. **User behavior shifting:** Younger users prefer ChatGPT over Google for many queries
> 4. **Multimodal:** Search will handle text, images, video, voice seamlessly
>
> **My Vision for 2030:**
>
> **1. AI Search Becomes Conversational Research Assistant**
> - Not just answering questions, but helping you *explore* topics
> - Example: 'I'm planning a trip to Japan'
>   - AI suggests itinerary, books flights, adapts based on preferences
>   - Multi-turn conversation that refines over time
>   - Saves research in your 'knowledge graph' for future reference
>
> **2. Deeply Personalized**
> - AI knows your interests, reading level, preferred sources
> - Same query, different answers for different people
> - Example: 'Explain quantum computing'
>   - For physicist: Deep technical explanation
>   - For student: ELI5 version with analogies
>   - For me (based on past searches): Assumes I know basic physics, skips intro
>
> **3. Proactive, Not Reactive**
> - AI anticipates information needs
> - Example: Monday morning → 'Here's your weekly briefing on topics you follow'
> - Sees you booking a flight → 'Want me to find hotels and create an itinerary?'
>
> **4. Multimodal & Spatial**
> - Search with images, video, voice, AR
> - Example: Point phone at plant → AI identifies it, suggests care instructions
> - Voice-first for many use cases (especially mobile, driving, cooking)
>
> **5. Integrated Everywhere**
> - Not a separate app, but embedded in OS, apps, devices
> - Every text box has AI search behind it
> - Example: Writing email → AI pulls relevant info without you asking
>
> **6. Trust & Verification**
> - Citations become standard (like Wikipedia)
> - AI shows confidence levels ('I'm 95% sure' vs. 'I'm guessing')
> - Fact-checking and source credibility built-in
> - Regulation requires transparency on AI-generated content
>
> **Market Implications:**
>
> **Winners:**
> - AI-first search engines (Perplexity, OpenAI) if they execute well
> - Companies with proprietary data (Reddit, Stack Overflow) - AI needs grounding
> - Vertical AI search (legal, medical, finance) - domain expertise matters
>
> **Losers:**
> - Traditional SEO companies (less relevant when AI synthesizes answers)
> - Low-quality content farms (AI prefers authoritative sources)
> - Google *if* they don't adapt (but I think they will)
>
> **Business Model Shifts:**
> - Search may not be ad-driven (hard to insert ads in conversational AI)
> - Likely: Subscription (like ChatGPT Plus) or B2B (enterprise search)
> - Publishers will need new models (less click-through traffic)
>
> **What This Means for AI PMs:**
> - Build for conversation, not keyword search
> - Invest in personalization and memory
> - Prioritize trust, citations, accuracy (table stakes)
> - Think multi-turn, not single-query
> - Anticipate regulation around transparency and misinformation
>
> **Bottom Line:**
> In 5 years, AI search won't be 'Google with AI' - it'll be a fundamentally different paradigm. Instead of searching for information, you'll have an AI research assistant that knows you, anticipates your needs, and helps you explore ideas. The companies that win will be those that reimagine search from first principles, not bolt AI onto existing models.
>
> Does this vision resonate, or would you like me to dive into any specific area?"

---

## ⏱️ Time Management (45-minute interview)

**Recommended Time Allocation:**

| Phase | Time | What You're Doing |
|-------|------|-------------------|
| **Clarify** | 2-3 min | Ask questions, understand context |
| **Framework** | 1-2 min | State your approach (market analysis, SWOT, etc.) |
| **Analysis** | 12-15 min | Work through framework systematically |
| **Recommendation** | 3-5 min | Clear, decisive recommendation |
| **Deep Dives / Q&A** | 20-25 min | Interviewer probes specific areas |

---

## ✅ Final Checklist

Before your interview, ensure you can:

- [ ] Analyze market opportunities (TAM/SAM/SOM, growth, dynamics)
- [ ] Conduct competitive analysis (5 Forces, SWOT, positioning)
- [ ] Recommend pricing strategies (cost structure, willingness to pay, business models)
- [ ] Develop competitive strategies (differentiation, focus, moats)
- [ ] Articulate long-term vision (trends, implications, market shifts)
- [ ] Evaluate build vs. buy decisions
- [ ] Make strategic recommendations decisively
- [ ] Identify and mitigate strategic risks
- [ ] Connect strategy to business outcomes (revenue, profitability, market share)
- [ ] Discuss AI-specific strategic considerations (data moats, model economics, etc.)

---

## 🎬 Conclusion

Strategy interviews test CEO-level thinking: markets, competition, business models, and long-term vision. For AI PMs, you must layer on AI-specific dynamics: data advantages, model economics, platform strategies, and rapid technological change.

**Keys to Success:**
1. **Think big picture:** Connect tactics to strategy to vision
2. **Be structured:** Use frameworks (5 Forces, SWOT, etc.)
3. **Be decisive:** Make clear recommendations, not "it depends"
4. **Show trade-off thinking:** Acknowledge what you're NOT doing
5. **Know the AI landscape:** Understand market trends, competitors, technology evolution
6. **Connect to business impact:** Revenue, profitability, market share

Practice these frameworks with real AI companies and you'll be ready to impress in strategy interviews!

You've got this! 🚀

---

**Next Steps:**
1. Practice analyzing 3-5 AI markets (coding, search, creative tools, etc.)
2. Study real company strategies (OpenAI, Anthropic, Google, Microsoft in AI)
3. Read AI strategy articles (a16z, Benedict Evans, Stratechery)
4. Mock interview with peers on strategy questions
5. Build your strategic point of view on AI trends

Good luck! 💪
