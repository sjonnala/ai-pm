# AI-First App Redesign

**Created:** [Date]
**Week 7 Deliverable**
**App Being Redesigned:** [App Name]
**Redesign Type:** [Crawl / Walk / Run - or all three]

---

## Executive Summary

**App:** [Name of existing app - e.g., "Notion", "Gmail", "Trello"]

**Current Purpose:** [What the app does today in one sentence]

**Redesign Vision:** [Your AI-first vision in one sentence]

**Key AI Opportunities Identified:** [Number - e.g., "5 major AI enhancements"]

**Primary Pattern Used:** [Autocomplete, Conversational, Generative, etc.]

**Expected Impact:** [What users will gain - e.g., "50% faster task completion"]

---

## Part 1: Current State Analysis

### What the App Does Today

**Core Features:**
1. [Feature 1 - e.g., "Note-taking and organization"]
2. [Feature 2 - e.g., "Collaboration and sharing"]
3. [Feature 3 - e.g., "Task management"]
4. [Feature 4]
5. [Feature 5]

**Primary User Workflows:**

**Workflow 1:** [Name - e.g., "Creating a meeting note"]
```
1. User creates new page
2. User types title
3. User manually structures content (headers, bullets)
4. User writes notes
5. User manually tags and files
```
**Time to Complete:** [X minutes]
**Pain Points:** [List frustrations]

**Workflow 2:** [Name]
```
[Steps]
```

**Workflow 3:** [Name]
```
[Steps]
```

---

### Current User Pain Points

**Top Pain Points from User Research/Reviews:**

**Pain Point 1: [e.g., "Manual organization is time-consuming"]**
- **Frequency:** High / Medium / Low
- **Severity:** High / Medium / Low
- **User Quote:** "[Real quote from reviews or interviews]"
- **Current Workaround:** [What users do now]

**Pain Point 2: [e.g., "Hard to find old information"]**
- **Frequency:**
- **Severity:**
- **User Quote:**
- **Current Workaround:**

**Pain Point 3: [e.g., "Blank page syndrome - hard to start"]**
- **Frequency:**
- **Severity:**
- **User Quote:**
- **Current Workaround:**

---

### Competitive Landscape

**Current Competitors:**
- [Competitor 1] - Strengths: [X], Weaknesses: [Y]
- [Competitor 2] - Strengths: [X], Weaknesses: [Y]
- [Competitor 3] - Strengths: [X], Weaknesses: [Y]

**AI-Powered Alternatives Emerging:**
- [AI Alternative 1] - Approach: [How they use AI]
- [AI Alternative 2] - Approach: [How they use AI]

**Competitive Threat:**
- [ ] Low - No immediate AI threat
- [ ] Medium - Some AI features appearing
- [ ] High - AI-native competitors gaining traction

---

## Part 2: AI Opportunity Mapping

### Crawl: AI-Augmented (Months 0-6)

**Philosophy:** Add AI to existing features without changing core UX

**Opportunity 1: [Feature Name]**
- **Current State:** [How it works today]
- **AI Enhancement:** [What AI would add]
- **Pattern:** [Autocomplete, Generative, etc.]
- **User Value:** [What users gain]
- **Technical Complexity:** Low / Medium / High
- **Expected Impact:** [Metric improvement estimate]

**Example: Auto-tagging**
- **Current:** Users manually add tags
- **AI Enhancement:** AI suggests relevant tags based on content
- **Pattern:** Classification
- **User Value:** Save 30 seconds per note
- **Complexity:** Low
- **Impact:** 95% adoption, 40% time savings

**Opportunity 2: [Feature Name]**
[Repeat structure]

**Opportunity 3: [Feature Name]**
[Repeat structure]

**Quick Wins (Prioritized):**
1. [Opportunity X] - High value, low complexity
2. [Opportunity Y]
3. [Opportunity Z]

---

### Walk: AI-Native Features (Months 6-12)

**Philosophy:** New features that are only possible with AI

**Opportunity 4: [Feature Name]**
- **Problem Solved:** [User pain point addressed]
- **AI Capability:** [What AI enables]
- **Pattern:** [Primary interaction pattern]
- **User Flow:** [How users would interact]
- **Dependencies:** [What's needed technically]
- **Differentiation:** [How this sets app apart]

**Example: AI Meeting Summarizer**
- **Problem:** Users struggle to take good notes during meetings
- **AI Capability:** Listens to meeting, generates structured summary
- **Pattern:** Generative
- **User Flow:**
  1. User starts meeting with "Record and summarize" enabled
  2. AI transcribes in real-time
  3. During meeting, AI extracts action items and key points
  4. After meeting, AI generates structured summary with sections
  5. User reviews, edits, and shares
- **Dependencies:** Audio transcription API, GPT-4 for summarization
- **Differentiation:** Only tool with AI-generated meeting structures

**Opportunity 5: [Feature Name]**
[Repeat structure]

**Opportunity 6: [Feature Name]**
[Repeat structure]

**Game-Changing Features (Prioritized):**
1. [Opportunity X] - High differentiation
2. [Opportunity Y]
3. [Opportunity Z]

---

### Run: AI-First Reimagination (12-24 months)

**Philosophy:** Redesign the entire experience assuming AI from day one

**Radical Rethink: [Vision Statement]**

**Example for Notion:**
"What if your workspace was an AI that understands your goals and proactively helps you achieve them?"

**Key Changes from Current Product:**

**Change 1: From Manual Pages to AI-Organized Knowledge Graph**
- **Current:** Users create pages and organize manually
- **AI-First:** AI automatically connects related information, surfaces relevant context
- **Why:** Users want answers, not file management

**Change 2: From Blank Pages to AI-Initiated Workflows**
- **Current:** Users start with blank page
- **AI-First:** AI suggests templates, drafts, and structures based on user intent
- **Why:** Blank page syndrome is the biggest friction

**Change 3: From Search to Proactive Intelligence**
- **Current:** Users must search for information
- **AI-First:** AI surfaces relevant information before user asks
- **Why:** Best UX is invisible - anticipate needs

**Entirely New Capabilities:**
1. [Capability 1]
2. [Capability 2]
3. [Capability 3]

**What We'd Remove:**
- [Feature X] - No longer needed because AI handles it
- [Feature Y] - Replaced by AI alternative
- [Feature Z] - Complexity no longer justified

---

## Part 3: Detailed Design (Pick One Feature)

### Selected Feature for Deep Dive

**Feature:** [Name - e.g., "AI Writing Assistant"]

**Rationale for Selection:**
- High user value
- Feasible in near term
- Demonstrates AI-native thinking
- Addresses major pain point

---

### User Flow Design

**Primary User Flow:**

```
┌─────────────────────────────────────────────────────────┐
│ Step 1: User Initiation                                  │
├─────────────────────────────────────────────────────────┤
│ User Action: [What user does]                            │
│ UI State: [What's visible on screen]                     │
│ Example: User types "/ai write" or clicks "AI Assistant" │
│                                                           │
│ [Wireframe or mockup sketch]                             │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Step 2: AI Interaction                                   │
├─────────────────────────────────────────────────────────┤
│ AI Action: [What AI does]                                │
│ User Sees: [Visible feedback]                            │
│ Example: AI shows prompt input with suggestions          │
│                                                           │
│ [Wireframe or mockup sketch]                             │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Step 3: AI Generation                                    │
├─────────────────────────────────────────────────────────┤
│ AI Action: [Processing]                                  │
│ User Sees: [Loading state, progress indicator]           │
│ Duration: [Expected time]                                │
│ Example: "Generating content..." with animated dots      │
│                                                           │
│ [Wireframe or mockup sketch]                             │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Step 4: Output Display                                   │
├─────────────────────────────────────────────────────────┤
│ AI Shows: [Generated output]                             │
│ Controls Available: [Accept, Edit, Regenerate, etc.]     │
│ Transparency: [Confidence, sources, reasoning shown]     │
│ Example: AI-generated draft with inline editing          │
│                                                           │
│ [Wireframe or mockup sketch]                             │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Step 5: User Action                                      │
├─────────────────────────────────────────────────────────┤
│ User Chooses: [Accept / Edit / Regenerate / Discard]     │
│ What Happens Next: [Flow branches based on choice]       │
│ Example: User clicks "Accept" → content inserted         │
│                                                           │
│ [Wireframe or mockup sketch]                             │
└─────────────────────────────────────────────────────────┘
```

---

### UI States Documentation

**State 1: Default / Empty State**

**Visual:**
```
┌─────────────────────────────────────┐
│ 📄 New Page                          │
│                                      │
│ Type '/' for commands                │
│ Or just start writing...             │
│                                      │
│ ✨ Try AI Assistant                  │
│ [Generate outline] [Write draft]    │
│ [Summarize notes]                    │
└─────────────────────────────────────┘
```

**Interaction:**
- User can type normally or invoke AI
- Clear AI capabilities shown upfront
- Low barrier to trying AI features

---

**State 2: AI Prompt Input**

**Visual:**
```
┌─────────────────────────────────────┐
│ ✨ AI Assistant                      │
│ ┌─────────────────────────────────┐ │
│ │ What would you like to write?   │ │
│ │ [Cursor here]                   │ │
│ └─────────────────────────────────┘ │
│                                      │
│ Suggestions:                         │
│ • "Write a blog post about..."      │
│ • "Summarize my meeting notes"      │
│ • "Create an outline for..."        │
│                                      │
│ [Cancel]                   [Generate]│
└─────────────────────────────────────┘
```

**Interaction:**
- Clear input for user intent
- Suggestions help users get started
- Cancel option always available

---

**State 3: Loading / Processing**

**Visual:**
```
┌─────────────────────────────────────┐
│ ✨ AI is writing...                  │
│                                      │
│ ▓▓▓▓▓▓▓▓▓▓░░░░░░░░░░  50%          │
│                                      │
│ [Stop Generation]                    │
│                                      │
│ "This usually takes 10-15 seconds"  │
└─────────────────────────────────────┘
```

**Interaction:**
- Progress indicator shows it's working
- Time estimate sets expectations
- User can stop if taking too long

---

**State 4: Output Display (Success)**

**Visual:**
```
┌─────────────────────────────────────┐
│ ✨ AI Generated Draft                │
│ ┌─────────────────────────────────┐ │
│ │ [Editable AI-generated content] │ │
│ │ User can click anywhere to edit │ │
│ │                                 │ │
│ │ # Introduction                  │ │
│ │ [AI-written paragraph...]       │ │
│ │                                 │ │
│ │ # Main Points                   │ │
│ │ [AI-written content...]         │ │
│ └─────────────────────────────────┘ │
│                                      │
│ Quality: ████████░░ 82% confident   │
│                                      │
│ [✓ Insert] [🔄 Regenerate] [✗ Discard] │
└─────────────────────────────────────┘
```

**Interaction:**
- Content immediately editable
- Confidence shown transparently
- Three clear action options

---

**State 5: Error / Failure**

**Visual:**
```
┌─────────────────────────────────────┐
│ ⚠️ AI generation failed               │
│                                      │
│ Reason: Request too complex          │
│                                      │
│ Suggestions:                         │
│ • Try breaking into smaller parts   │
│ • Be more specific in your prompt   │
│ • [See examples of good prompts]    │
│                                      │
│ [Try Again] [Start Over] [Get Help] │
└─────────────────────────────────────┘
```

**Interaction:**
- Clear error explanation
- Actionable suggestions
- Multiple recovery paths

---

**State 6: Refinement / Iteration**

**Visual:**
```
┌─────────────────────────────────────┐
│ ✨ Refine AI Output                  │
│                                      │
│ Current output: [Preview snippet]   │
│                                      │
│ Make it:                             │
│ • [More concise]                     │
│ • [More detailed]                    │
│ • [Change tone to professional]     │
│ • [Add examples]                     │
│                                      │
│ Or describe changes:                 │
│ ┌─────────────────────────────────┐ │
│ │ [Custom refinement request]     │ │
│ └─────────────────────────────────┘ │
│                                      │
│ [Apply Changes]                      │
└─────────────────────────────────────┘
```

**Interaction:**
- Quick refinement options
- Custom refinement allowed
- Iterative improvement supported

---

### Interaction Pattern Applied

**Primary Pattern:** [e.g., "Generative"]

**Why This Pattern:**
- [Reason 1 - e.g., "Task is creative content creation"]
- [Reason 2 - e.g., "Users expect to iterate and refine"]
- [Reason 3 - e.g., "Output quality varies, need user review"]

**Pattern Elements Used:**
- ✅ Prompt input
- ✅ Generation with progress
- ✅ Editable output
- ✅ Regenerate option
- ✅ Refinement capability

---

### Transparency Implementation

**How We Show Confidence:**
- Percentage score (0-100%)
- Visual bar indicator
- Text label ("High confidence", "Uncertain")

**How We Explain Decisions:**
- "Based on your previous notes about [topic]"
- "I structured this as [format] because [reason]"
- Optional "Show reasoning" expandable section

**How We Cite Sources:**
- [If applicable] Inline citations
- References to user's own notes
- External sources with links

**Example:**
```
┌─────────────────────────────────────┐
│ AI Generated Summary                 │
│ Confidence: 87%                      │
│                                      │
│ [Content here]                       │
│                                      │
│ 📊 How I created this:               │
│ • Analyzed 3 of your recent notes   │
│ • Identified common themes          │
│ • Structured as outline per your style│
│                                      │
│ [Show full reasoning]                │
└─────────────────────────────────────┘
```

---

### Control Mechanisms

**User Control Elements:**

**1. Automation Level:**
- Manual: No AI assistance
- Suggest: AI offers ideas (user decides)
- Copilot: AI drafts (user edits)
- Auto: AI writes (user reviews)

**2. Override and Edit:**
- All AI outputs are fully editable
- Inline editing with standard text editor
- Undo/redo support

**3. Feedback:**
- Thumbs up/down on every AI output
- Detailed feedback form (optional)
- "Report issue" for harmful content

**4. Preferences:**
```
┌─────────────────────────────────────┐
│ AI Writing Preferences               │
│                                      │
│ Tone:       ● Professional  ○ Casual│
│ Length:     ○ Concise  ● Balanced   │
│ Creativity: Low ▓▓▓▓▓░░░░░ High    │
│                                      │
│ Auto-suggestions:                    │
│ ● Enabled   ○ Disabled              │
│                                      │
│ Language: [English ▼]               │
│                                      │
│ [Save Preferences]                   │
└─────────────────────────────────────┘
```

---

### Error Handling Design

**Error Scenario 1: AI Doesn't Understand Request**

**Trigger:** Vague or unclear prompt

**Response:**
```
I'm not quite sure what you'd like me to write.

Could you provide more details?
• What topic should I write about?
• Who is the audience?
• What format? (blog post, email, outline, etc.)
• Any specific points to include?

[Examples of good prompts]
```

**Recovery:** User provides more detail, AI retries

---

**Error Scenario 2: AI Output Quality Is Poor**

**Trigger:** User clicks thumbs down or regenerates multiple times

**Response:**
```
I notice you've regenerated 3 times.

Let me try a different approach:
• Would you like to provide an example of what you want?
• Should I try a different format/structure?
• Would you prefer to start with an outline first?

[Help me improve] [Try manual mode]
```

**Recovery:** Collaborative problem-solving

---

**Error Scenario 3: Service Unavailable**

**Trigger:** API timeout or service down

**Response:**
```
⚠️ AI service temporarily unavailable

While we're fixing this, you can:
• [Use standard editor] (no AI assistance)
• [Try again in 2-3 minutes]
• [Save your request] (we'll generate when back online)
• [Browse templates] (manual alternatives)

We're usually back within 5 minutes.
```

**Recovery:** Graceful degradation to manual mode

---

**Error Scenario 4: Inappropriate Content Request**

**Trigger:** Request violates content policy

**Response:**
```
I can't help with that request because it violates our content policy.

Specifically: [Harmful content, Personal info, Copyrighted material, etc.]

What I can help with:
• [Alternative suggestion 1]
• [Alternative suggestion 2]
• [Link to content policy]

[Try different request]
```

**Recovery:** Clear explanation, alternative paths

---

### Safety & Guardrails

**Input Guardrails:**
- Content filter for harmful requests
- PII detection (warn if user includes personal info)
- Length limits (max prompt length)
- Rate limiting (max requests per hour)

**Output Guardrails:**
- Content safety filter
- Fact-checking (flag unverified claims)
- Plagiarism detection
- Bias detection and mitigation

**Human-in-Loop Triggers:**
- Low confidence (<50%)
- Safety flags triggered
- User reports issue
- Repeated failures

---

## Part 4: Technical Considerations

### AI/ML Requirements

**Model Selection:**
- **Primary Model:** [e.g., "GPT-4 for generation"]
- **Backup Model:** [e.g., "GPT-3.5 for simpler tasks"]
- **Specialized Models:** [e.g., "Classification model for tagging"]

**Why These Models:**
- [Reasoning for primary choice]
- [Cost considerations]
- [Performance requirements]

**Parameters:**
- Temperature: [0.7] (balance creativity and consistency)
- Max Tokens: [1000] (appropriate length)
- Top-p: [0.9] (nucleus sampling)

---

### Data Requirements

**Training Data Needed:**
- User-generated content (with permission)
- High-quality examples
- Diverse use cases
- Volume: [Estimated amount]

**Inference Data:**
- User context (recent notes, preferences)
- Document metadata
- User feedback history

**Privacy Considerations:**
- User data stays encrypted
- Opt-in for AI features
- Clear data usage policy
- Ability to delete AI training data

---

### Infrastructure

**Architecture:**
```
User Interface (Frontend)
    ↓
API Gateway
    ↓
AI Service Layer
    ├─ Model API (OpenAI, Anthropic, etc.)
    ├─ Prompt Management
    ├─ Context Retrieval
    └─ Safety Filters
    ↓
Data Storage
```

**Latency Requirements:**
- p50: <2 seconds
- p95: <5 seconds
- p99: <10 seconds

**Scalability:**
- Expected QPS: [Queries per second]
- Peak load handling
- Caching strategy

**Cost Estimates:**
- Per-user monthly cost: [$X]
- Per-query cost: [$Y]
- Infrastructure cost: [$Z/month]

---

## Part 5: Success Metrics

### Product Metrics

**North Star Metric:**
[e.g., "AI-assisted content created per user per week"]

**Supporting Metrics:**

**Adoption:**
- % of users who try AI feature (target: >60%)
- % of daily active users using AI (target: >40%)
- Feature activation rate (target: >50%)

**Engagement:**
- AI interactions per user per session (target: 3+)
- Acceptance rate of AI outputs (target: >60%)
- Edit rate (target: <40% - shows quality)

**Satisfaction:**
- User satisfaction score (target: >8/10)
- Net Promoter Score (target: >40)
- Feature satisfaction (target: >80% positive feedback)

**Retention:**
- D7 retention lift (target: +10% vs. non-AI users)
- D30 retention lift (target: +15%)
- Feature retention (target: >50% use weekly)

---

### AI Quality Metrics

**Output Quality:**
- Acceptance rate (target: >60%)
- Edit rate (target: 20-40%)
- Regeneration rate (target: <30%)
- User satisfaction with output (target: >7/10)

**Performance:**
- Latency p95 (target: <5s)
- Error rate (target: <2%)
- Uptime (target: >99.9%)

**Safety:**
- Content safety violations (target: <0.1%)
- User reports (target: <1%)
- False positive rate (target: <5%)

---

### Business Metrics

**Revenue Impact:**
- Conversion to paid (if freemium) (target: +20%)
- ARPU increase (target: +15%)
- Churn reduction (target: -25%)

**Efficiency:**
- Time saved per user (target: 30 min/week)
- Tasks completed per session (target: +50%)
- Content created per user (target: +40%)

**Competitive:**
- Feature parity with competitors
- Unique AI capabilities vs. alternatives
- User preference vs. competitors (win rate >60%)

---

## Part 6: Rollout Plan

### Phase 1: Internal Alpha (Week 1-2)

**Participants:** Internal team (10-20 people)

**Goals:**
- Test basic functionality
- Find obvious bugs
- Refine UX based on team feedback

**Success Criteria:**
- No critical bugs
- Team satisfaction >7/10
- Core flow works end-to-end

---

### Phase 2: Closed Beta (Week 3-6)

**Participants:** 100-500 power users

**Goals:**
- Validate with real users
- Test at moderate scale
- Collect detailed feedback

**Success Criteria:**
- Acceptance rate >50%
- No major bugs
- User satisfaction >6/10
- Can handle load

---

### Phase 3: Open Beta (Week 7-10)

**Participants:** All users (opt-in)

**Goals:**
- Broad user feedback
- Scale testing
- Marketing validation

**Success Criteria:**
- Adoption >30% of invited users
- Acceptance rate >55%
- User satisfaction >7/10
- Infrastructure stable

---

### Phase 4: General Availability (Week 11+)

**Launch:**
- Feature available to all users
- Default-on (with easy opt-out)
- Full marketing push

**Post-Launch:**
- Monitor metrics daily
- Iterate based on data
- Expand to related features

---

## Part 7: Future Iterations

### V2 Enhancements (3-6 months)

**Feature 1: [Name]**
- What: [Description]
- Why: [User value]
- Complexity: Low/Medium/High

**Feature 2: [Name]**
**Feature 3: [Name]**

---

### V3 Enhancements (6-12 months)

**Feature 1: [Name]**
- What: [Description]
- Why: [User value]
- Complexity: Low/Medium/High

**Feature 2: [Name]**
**Feature 3: [Name]**

---

### Long-Term Vision (12-24 months)

[Describe how this feature evolves into the "Run" (AI-first) vision]

---

## Part 8: Wireframes and Mockups

### Key Screens

**Screen 1: Main Interface with AI Entry Points**
```
[Sketch or embed image here]

Key elements:
- AI button placement
- Contextual triggers
- User education
```

**Screen 2: AI Interaction Modal/Panel**
```
[Sketch or embed image here]

Key elements:
- Prompt input
- Suggestions
- Settings access
```

**Screen 3: Output Display**
```
[Sketch or embed image here]

Key elements:
- Generated content
- Confidence indicator
- Action buttons
```

**Screen 4: Error State**
```
[Sketch or embed image here]

Key elements:
- Error message
- Recovery options
- Help resources
```

**Screen 5: Settings/Preferences**
```
[Sketch or embed image here]

Key elements:
- Customization options
- Privacy controls
- Examples
```

---

## Part 9: Key Learnings

### Design Decisions

**Decision 1: [e.g., "Use modal vs. inline for AI interaction"]**
- **Choice:** [What you chose]
- **Rationale:** [Why]
- **Trade-offs:** [What you gave up]

**Decision 2: [e.g., "Show confidence percentage vs. qualitative"]**
- **Choice:**
- **Rationale:**
- **Trade-offs:**

**Decision 3: [e.g., "Default automation level"]**
- **Choice:**
- **Rationale:**
- **Trade-offs:**

---

### What I Learned About AI UX

**Insight 1:**
[What you learned - e.g., "Transparency is more important than perfect accuracy"]

**Insight 2:**
[What you learned - e.g., "Users need more control than I initially thought"]

**Insight 3:**
[What you learned - e.g., "Error handling is 50% of the UX work"]

---

### How This Differs from Traditional UX

**Difference 1:**
[e.g., "Traditional UX is deterministic; AI UX must embrace uncertainty"]

**Difference 2:**
[e.g., "Traditional UX hides complexity; AI UX must show reasoning"]

**Difference 3:**
[e.g., "Traditional UX optimizes for efficiency; AI UX balances efficiency with trust"]

---

## Part 10: Interview Application

### Talking Points for Interviews

**30-Second Pitch:**
"I redesigned [App] to be AI-first. Currently, users spend [X minutes] on [task]. I added [AI feature] using a [pattern] pattern, which could reduce that to [Y minutes]. Key insights: [1-2 learnings]."

**2-Minute Deep Dive:**
"Let me walk you through my redesign of [App].

**Current State:** [Brief description of pain points]

**AI Opportunities:** I identified [X] opportunities across Crawl-Walk-Run phases. For the deep dive, I focused on [specific feature].

**Design:** I used a [pattern] pattern because [reason]. Key UX decisions included [decision 1], [decision 2], and [decision 3].

**Transparency and Control:** I designed for transparency by [how], and gave users control through [how].

**Impact:** If implemented, this could [metric improvement] and differentiate [App] from [competitors].

**Learnings:** The biggest insight was [key learning]."

---

### Questions This Prepares You For

✅ "Design an AI feature for [product]"
✅ "How would you use AI to improve [app]?"
✅ "What makes AI UX different?"
✅ "Walk me through a product you redesigned"
✅ "How do you design for trust in AI products?"
✅ "What AI interaction pattern would you use for [use case]?"

---

## Appendix: Resources Used

**Design Tools:**
- [Tool 1 - e.g., Figma]
- [Tool 2 - e.g., Whimsical]
- [Tool 3 - e.g., Excalidraw]

**Research Sources:**
- [Source 1 - e.g., App Store reviews]
- [Source 2 - e.g., User interviews]
- [Source 3 - e.g., Competitor analysis]

**AI UX Guidelines Referenced:**
- Google People + AI Guidebook
- Microsoft HAX Toolkit
- [Others]

---

**This redesign demonstrates:**
- ✅ Understanding of AI-native UX
- ✅ Ability to identify AI opportunities
- ✅ Thoughtful application of interaction patterns
- ✅ Design for transparency and control
- ✅ Comprehensive error handling
- ✅ Portfolio-ready case study

**Next Steps:**
- Create high-fidelity mockups (optional)
- User test with 5+ people
- Refine based on feedback
- Add to portfolio

---

**Remember:** This is a portfolio piece, not a production spec. Focus on demonstrating AI PM thinking, not pixel-perfect design!
