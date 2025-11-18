# AI UX Pattern Library

**Created:** [Date]
**Week 7 Deliverable**
**Version:** [e.g., 1.0]
**Author:** [Your Name]

---

## Pattern Library Overview

**Purpose:** A comprehensive reference guide for AI-native UX patterns to guide product design decisions

**Scope:** Covers 6 core interaction patterns + transparency + control + error handling + multimodal design

**How to Use This:**
- Reference when designing new AI features
- Choose patterns based on use case
- Combine patterns for complex experiences
- Adapt examples to your specific context

---

## Table of Contents

1. [Core Interaction Patterns](#core-interaction-patterns) (6 patterns)
2. [Transparency Patterns](#transparency-patterns)
3. [Control Patterns](#control-patterns)
4. [Error Handling Patterns](#error-handling-patterns)
5. [Multimodal Patterns](#multimodal-patterns)
6. [Pattern Selection Guide](#pattern-selection-guide)

---

## Core Interaction Patterns

### Pattern 1: Autocomplete / Copilot

**Description:**
AI suggests completions or next actions while the user works. User can accept, reject, or ignore suggestions.

**When to Use:**
- ✅ High-frequency, repetitive tasks
- ✅ Clear "right" answers exist
- ✅ User wants to maintain control
- ✅ Speed is important
- ✅ User expertise varies (novices get help, experts can ignore)

**When NOT to Use:**
- ❌ Creative tasks requiring unique outputs
- ❌ High-stakes decisions (medical, legal)
- ❌ Tasks where AI accuracy is <80%
- ❌ When interruptions would be annoying

**User Flow:**
```
1. User begins task (typing, drawing, coding)
2. AI detects intent and generates suggestion
3. AI shows suggestion (inline, grayed out, or in sidebar)
4. User accepts (Tab/Enter), rejects (Esc), or ignores (keeps working)
5. AI learns from user's choice
```

**Example Products:**
- **GitHub Copilot** - Code completion
- **Gmail Smart Compose** - Email writing
- **Grammarly** - Writing suggestions
- **Notion AI** - Content suggestions
- **Figma AI** - Design assistance

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ User is typing...                    │
│ The quick brown fox jumps over      │
│ [the lazy dog] ← AI suggestion (gray)│
│                                      │
│ Press Tab to accept                  │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Visual Distinction:** Suggestions appear grayed out or with different styling
- **Keyboard Shortcuts:** Tab to accept, Esc to reject
- **Non-Intrusive:** Doesn't interrupt user flow
- **Contextual:** Appears only when relevant
- **Confidence:** Only shows high-confidence suggestions

**Pros:**
- ✅ Doesn't disrupt workflow
- ✅ User maintains full control
- ✅ Speeds up experienced users
- ✅ Educates novice users
- ✅ Low cognitive load

**Cons:**
- ❌ Can be ignored if not helpful
- ❌ Requires good contextual understanding
- ❌ May slow down if suggestions are poor
- ❌ Limited to sequential tasks

**Implementation Notes:**
- Show suggestions with <500ms latency
- Only show when confidence >70%
- Allow users to disable
- Track acceptance rate to measure quality

**Metrics to Track:**
- Acceptance rate (target: >30%)
- Time saved per accepted suggestion
- User satisfaction with suggestions
- Frequency of use

---

### Pattern 2: Conversational

**Description:**
User interacts with AI through natural language dialogue. AI responds, asks clarifying questions, and maintains context across turns.

**When to Use:**
- ✅ Complex, multi-step tasks
- ✅ Open-ended queries
- ✅ User needs exploration and discovery
- ✅ Multiple valid solutions exist
- ✅ Task requires clarification or iteration

**When NOT to Use:**
- ❌ Simple, single-action tasks (use buttons instead)
- ❌ When speed is critical (chat is slower)
- ❌ Visual tasks better shown than described
- ❌ When users prefer structured forms

**User Flow:**
```
1. User enters initial query/request
2. AI processes and responds (or asks clarifying questions)
3. User provides more context or refines request
4. AI generates improved response
5. Conversation continues until task complete
6. User can start new conversation or continue thread
```

**Example Products:**
- **ChatGPT** - General assistant
- **Perplexity** - Research assistant
- **Claude** - Advanced reasoning
- **Customer Support Chatbots** - Help and support
- **Intercom** - Sales and support

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ 💬 Chat with AI Assistant            │
├─────────────────────────────────────┤
│                                      │
│ 👤 User: How do I export my data?   │
│                                      │
│ 🤖 AI: I can help! Data can be      │
│     exported in CSV or JSON.         │
│     Which format do you prefer?      │
│                                      │
│ 👤 User: CSV please                 │
│                                      │
│ 🤖 AI: Great! Click Settings > Export│
│     > Select CSV. It will download   │
│     as data_export.csv               │
│     [Export CSV] button              │
│                                      │
│ ┌─────────────────────────────────┐ │
│ │ Type your message...            │ │
│ └─────────────────────────────────┘ │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Message History:** Visible conversation log
- **Typing Indicators:** Show AI is "thinking"
- **Message Bubbles:** Distinguish user vs. AI
- **Quick Replies:** Suggested follow-up questions
- **Context Awareness:** AI remembers previous messages
- **Reset Option:** Clear conversation and start fresh

**Pros:**
- ✅ Natural, familiar interface
- ✅ Handles complex, nuanced requests
- ✅ Allows iterative refinement
- ✅ Good for exploration
- ✅ Low learning curve

**Cons:**
- ❌ Slower than direct manipulation
- ❌ Requires typing (accessibility issue)
- ❌ Can be verbose
- ❌ Context window limits
- ❌ Hard to discover capabilities

**Implementation Notes:**
- Maintain conversation context (at least 10 turns)
- Add "Examples" or "Suggestions" to help users start
- Show typing indicator after 500ms
- Implement "Stop generating" button
- Allow editing previous messages

**Metrics to Track:**
- Task completion rate
- Average turns to completion
- User satisfaction (CSAT)
- Abandonment rate
- Follow-up question rate

---

### Pattern 3: Generative

**Description:**
User provides a prompt/description, and AI generates original content (text, images, code, etc.). User can regenerate or refine.

**When to Use:**
- ✅ Creative content creation
- ✅ Ideation and brainstorming
- ✅ Multiple iterations expected
- ✅ Subjective quality assessment
- ✅ User wants variety and options

**When NOT to Use:**
- ❌ When accuracy is critical (use retrieval instead)
- ❌ Tasks requiring deterministic outputs
- ❌ When users want to build from scratch
- ❌ Copyright-sensitive content

**User Flow:**
```
1. User enters prompt/description
2. User sets parameters (style, length, format)
3. AI generates content
4. User reviews output
5. User accepts, regenerates, or refines with additional prompts
6. User can iterate multiple times
7. User saves or exports final output
```

**Example Products:**
- **Midjourney** - Image generation
- **DALL-E** - Image generation
- **ChatGPT** - Text generation
- **Runway** - Video generation
- **Jasper** - Marketing copy
- **GitHub Copilot** - Code generation

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ 🎨 Generate Image                    │
├─────────────────────────────────────┤
│ Prompt:                              │
│ ┌─────────────────────────────────┐ │
│ │ A serene mountain lake at sunset│ │
│ │ with reflections, photorealistic │ │
│ └─────────────────────────────────┘ │
│                                      │
│ Style: [Photorealistic ▼]           │
│ Size: [1024x1024 ▼]                 │
│ Variations: [4]                      │
│                                      │
│        [Generate]                    │
│                                      │
│ ┌─────────┬─────────┬─────────┐    │
│ │  IMG 1  │  IMG 2  │  IMG 3  │    │
│ │ [Save]  │ [Save]  │ [Save]  │    │
│ └─────────┴─────────┴─────────┘    │
│                                      │
│ [Regenerate] [Refine Prompt]        │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Prompt Input:** Clear, prominent text area
- **Parameter Controls:** Style, format, length sliders/dropdowns
- **Multiple Variations:** Show 2-4 options
- **Regenerate:** Easy one-click regeneration
- **Refine:** Iterate on specific output
- **Save/Export:** Clear action to keep results
- **History:** Access previous generations

**Pros:**
- ✅ Enables creativity and ideation
- ✅ Fast iteration
- ✅ Produces unique outputs
- ✅ Lowersbarrier to content creation
- ✅ Inspires users

**Cons:**
- ❌ Output quality can be inconsistent
- ❌ "Prompt engineering" learning curve
- ❌ Can be expensive (compute costs)
- ❌ Copyright/ownership concerns
- ❌ Hard to get exactly what you want

**Implementation Notes:**
- Provide example prompts to guide users
- Show parameter effects with examples
- Implement seed values for reproducibility
- Add "Enhance prompt" feature (AI improves user's prompt)
- Allow saving prompts for reuse

**Metrics to Track:**
- Generation acceptance rate
- Average regenerations per task
- Prompt length and complexity
- User retention (do they come back?)
- Cost per generation

---

### Pattern 4: Recommendation

**Description:**
AI suggests personalized options based on user preferences, history, or context. User browses and selects from recommendations.

**When to Use:**
- ✅ Choice overload (too many options)
- ✅ Personalization is valuable
- ✅ Historical data exists
- ✅ Discovery is important
- ✅ Preferences can be learned

**When NOT to Use:**
- ❌ Limited options (just show all)
- ❌ No personalization data available
- ❌ Users want full control over selection
- ❌ Cold start problem can't be solved

**User Flow:**
```
1. User opens app/feature
2. AI analyzes user context, history, preferences
3. AI generates personalized recommendations
4. User browses recommendations
5. User selects item or requests more/different recommendations
6. AI learns from user's selection
7. Future recommendations improve
```

**Example Products:**
- **Netflix** - Movie/show recommendations
- **Spotify** - Music discovery
- **Amazon** - Product recommendations
- **LinkedIn** - Job recommendations
- **YouTube** - Video suggestions
- **Pinterest** - Visual discovery

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ 🎬 Recommended for You               │
├─────────────────────────────────────┤
│ Because you watched "Inception"      │
│                                      │
│ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐   │
│ │ MOV1│ │ MOV2│ │ MOV3│ │ MOV4│   │
│ │ 95% │ │ 89% │ │ 87% │ │ 85% │   │
│ │Match│ │Match│ │Match│ │Match│   │
│ └─────┘ └─────┘ └─────┘ └─────┘   │
│                                      │
│ 🎵 Discover Weekly                   │
│ Updated every Monday                 │
│                                      │
│ ┌────────────────────────────────┐  │
│ │ 🎵 Song 1 - Artist A            │ │
│ │ 🎵 Song 2 - Artist B            │ │
│ │ 🎵 Song 3 - Artist C            │ │
│ └────────────────────────────────┘  │
│                                      │
│ [Show More] [Not Interested]        │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Relevance Score:** Show match percentage or confidence
- **Explanation:** "Because you liked X"
- **Diversity:** Mix of safe bets and discovery
- **Feedback Buttons:** Thumbs up/down, "Not interested"
- **Refresh:** Get new recommendations
- **Filters:** Refine by category, genre, etc.
- **Fallback:** When no good recommendations, show popular/trending

**Pros:**
- ✅ Reduces decision fatigue
- ✅ Helps discovery
- ✅ Personalized experience
- ✅ Increases engagement
- ✅ Learns and improves over time

**Cons:**
- ❌ Filter bubble risk
- ❌ Cold start problem (new users)
- ❌ Privacy concerns
- ❌ Requires significant data
- ❌ Can feel creepy if too accurate

**Implementation Notes:**
- Hybrid approach: collaborative + content-based filtering
- Explain why items are recommended
- Add diversity to prevent echo chamber
- Allow users to edit preferences
- Provide "Not interested" feedback

**Metrics to Track:**
- Click-through rate (CTR)
- Conversion rate
- Recommendation diversity
- User engagement (time spent)
- Feedback rate (thumbs up/down)

---

### Pattern 5: Classification / Analysis

**Description:**
AI categorizes, labels, or analyzes user input automatically. User can review and correct if needed.

**When to Use:**
- ✅ Large volumes of content
- ✅ Repetitive categorization tasks
- ✅ Pattern recognition is valuable
- ✅ Speed is important
- ✅ Categories are well-defined

**When NOT to Use:**
- ❌ Subjective or nuanced categorization
- ❌ High-stakes classification (medical diagnosis)
- ❌ Categories frequently change
- ❌ Small volumes (manual is faster)

**User Flow:**
```
1. User submits content (email, document, image, etc.)
2. AI analyzes and classifies automatically
3. AI applies label/category
4. User is notified of classification (optional)
5. User can review and correct if wrong
6. AI learns from corrections
```

**Example Products:**
- **Gmail** - Email categorization (Spam, Social, Promotions)
- **Google Photos** - Image recognition and tagging
- **Notion** - Auto-tagging notes
- **Superhuman** - Email triage
- **Slack** - Message categorization
- **Grammarly** - Tone detection

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ 📧 Inbox                             │
├─────────────────────────────────────┤
│ ┌─────────────────────────────────┐ │
│ │ 🏷️ [Work] Meeting Notes          │ │
│ │ Auto-tagged as "Work Project A"  │ │
│ │ Confidence: 92%                   │ │
│ │ [Change Tag ▼]                   │ │
│ └─────────────────────────────────┘ │
│                                      │
│ ┌─────────────────────────────────┐ │
│ │ 📸 [Vacation] Beach Sunset       │ │
│ │ Detected: Beach, Sunset, People  │ │
│ │ Location: Miami, FL              │ │
│ │ [Edit Tags]                      │ │
│ └─────────────────────────────────┘ │
│                                      │
│ ┌─────────────────────────────────┐ │
│ │ ⚠️ [Spam] "You've won $1M!"      │ │
│ │ [Not Spam] [Delete]              │ │
│ └─────────────────────────────────┘ │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Auto-Applied Labels:** Classification happens automatically
- **Confidence Indicator:** Show certainty level
- **Easy Override:** One-click to change classification
- **Bulk Actions:** Reclassify multiple items
- **Feedback Loop:** Learn from corrections
- **Transparency:** Explain why classified this way

**Pros:**
- ✅ Saves time on manual categorization
- ✅ Consistent classification
- ✅ Scales to large volumes
- ✅ Improves with feedback
- ✅ Low user effort

**Cons:**
- ❌ Errors can be frustrating
- ❌ Lacks nuance for edge cases
- ❌ May reinforce biases
- ❌ Requires training data
- ❌ Users may not trust classifications

**Implementation Notes:**
- Show confidence scores
- Make corrections easy (one click)
- Retrain model with user corrections
- Provide manual override option
- Alert users to low-confidence classifications

**Metrics to Track:**
- Classification accuracy
- User correction rate
- Time saved vs. manual classification
- False positive/negative rates
- User trust (do they verify?)

---

### Pattern 6: Agentic / Autonomous

**Description:**
AI acts autonomously to achieve user-defined goals. User sets objective, AI plans and executes steps, reports back on progress.

**When to Use:**
- ✅ Multi-step workflows
- ✅ Delegatable tasks with clear goals
- ✅ User trusts AI to take actions
- ✅ Human oversight available
- ✅ Tasks are reversible or low-risk

**When NOT to Use:**
- ❌ High-stakes decisions
- ❌ Irreversible actions
- ❌ Tasks requiring human judgment
- ❌ Unpredictable environments
- ❌ When users want hands-on control

**User Flow:**
```
1. User defines goal or objective
2. User sets constraints and preferences
3. AI creates execution plan
4. User reviews and approves plan (optional)
5. AI executes steps autonomously
6. AI reports progress and results
7. AI asks for human input when uncertain
8. User reviews final outcome
```

**Example Products:**
- **x.ai** - Meeting scheduling
- **Zapier AI** - Workflow automation
- **Auto-GPT** - Autonomous GPT tasks
- **Adept** - Browser automation
- **Devin** - Autonomous coding
- **Personal AI assistants** - Email, calendar, booking

**Visual Pattern:**

```
┌─────────────────────────────────────┐
│ 🤖 AI Agent: Meeting Scheduler       │
├─────────────────────────────────────┤
│ Goal: Schedule meeting with John     │
│       for next week, 1 hour          │
│                                      │
│ ✅ Step 1: Check your calendar       │
│    Found: 3 available slots          │
│                                      │
│ ✅ Step 2: Check John's availability │
│    Sent email, awaiting response     │
│                                      │
│ 🔄 Step 3: Propose time slots        │
│    In progress...                    │
│                                      │
│ ⏸️ Waiting for confirmation          │
│                                      │
│ [Pause Agent] [Cancel] [Override]   │
└─────────────────────────────────────┘
```

**Key UX Elements:**
- **Goal Input:** Clear objective definition
- **Plan Preview:** Show what AI will do before starting
- **Progress Tracking:** Real-time status updates
- **Step-by-Step Breakdown:** Transparency in actions
- **Pause/Cancel:** User can stop at any time
- **Human-in-Loop:** AI asks when uncertain
- **Audit Log:** Review all actions taken

**Pros:**
- ✅ Automates complex workflows
- ✅ Saves significant time
- ✅ Handles multi-step planning
- ✅ Operates asynchronously
- ✅ Scales user capabilities

**Cons:**
- ❌ Requires high trust
- ❌ Can make mistakes at scale
- ❌ Black box execution (transparency needed)
- ❌ Hard to debug failures
- ❌ Ethical concerns with autonomy

**Implementation Notes:**
- Always show plan before execution
- Implement pause/cancel controls
- Log all actions for review
- Ask for confirmation on irreversible actions
- Fail gracefully and explain failures
- Set clear boundaries (what AI won't do)

**Metrics to Track:**
- Task completion rate
- Average time saved
- Error rate
- User intervention rate
- Trust score (surveys)
- Actions per goal

---

## Transparency Patterns

### Pattern 1: Confidence Indicators

**What It Is:**
Show AI's confidence level in its output or recommendation.

**Examples:**
- Percentage match (Netflix: "95% match")
- Star ratings (quality prediction)
- Color coding (green = high, yellow = medium, red = low)
- Text labels ("I'm confident", "I'm not sure")
- Numerical scores (0-100)

**When to Use:**
- Recommendations
- Predictions
- Classifications
- Search results

**Implementation:**
```
┌─────────────────────────────────┐
│ Recommendation: Product A        │
│ Confidence: ████████░░ 82%      │
│                                  │
│ Why this score:                  │
│ • Matches 4/5 of your criteria  │
│ • Similar to your past purchases│
│ • Popular with similar users    │
└─────────────────────────────────┘
```

---

### Pattern 2: Source Citations

**What It Is:**
Show where AI got its information from.

**Examples:**
- Perplexity: Inline citations with links
- Bing Chat: Footnote numbers
- ChatGPT: "According to [source]"
- NotebookLM: Direct quotes with sources

**When to Use:**
- Factual information retrieval
- Research assistants
- Question answering
- Content generation based on sources

**Implementation:**
```
┌─────────────────────────────────┐
│ The capital of France is Paris   │
│ [1][2]                           │
│                                  │
│ Sources:                         │
│ [1] Wikipedia - France           │
│ [2] CIA World Factbook           │
└─────────────────────────────────┘
```

---

### Pattern 3: Reasoning Explanation

**What It Is:**
Explain why AI made a particular decision or recommendation.

**Examples:**
- "Because you watched X"
- "Based on your search history"
- "You frequently visit this type of site"
- "Chain of thought" explanations

**When to Use:**
- Recommendations
- Content moderation decisions
- Automated decisions affecting users
- Complex reasoning tasks

**Implementation:**
```
┌─────────────────────────────────┐
│ We removed your post             │
│                                  │
│ Reason: Violates community       │
│ guidelines (spam policy)         │
│                                  │
│ Details:                         │
│ • Contains 5+ promotional links │
│ • Similar to known spam patterns│
│ • Posted within 1 min of signup │
│                                  │
│ [Appeal Decision]                │
└─────────────────────────────────┘
```

---

### Pattern 4: Alternative Options

**What It Is:**
Show other options AI considered but didn't choose.

**Examples:**
- Google: "People also ask"
- GPT: "Here are 3 approaches..."
- Search: Related searches
- Recommendations: "You might also like"

**When to Use:**
- When multiple valid solutions exist
- To show AI explored thoroughly
- To help users discover alternatives
- To build trust through transparency

**Implementation:**
```
┌─────────────────────────────────┐
│ Top Recommendation: ⭐ Plan A    │
│ Best for: Your use case          │
│                                  │
│ Other options considered:        │
│ • Plan B - Cheaper but slower   │
│ • Plan C - Faster but expensive │
│ • Plan D - Didn't match criteria│
│                                  │
│ [See All Options]                │
└─────────────────────────────────┘
```

---

### Pattern 5: Uncertainty Visualization

**What It Is:**
Visually show where AI is uncertain.

**Examples:**
- Confidence intervals (ranges)
- Highlighted uncertain text
- "I'm not sure" statements
- Error bars on predictions

**When to Use:**
- Predictions with ranges
- Transcriptions (voice to text)
- Translations
- OCR and document extraction

**Implementation:**
```
┌─────────────────────────────────┐
│ Transcription:                   │
│                                  │
│ "The meeting is on [Monday?]    │
│ at 3pm to discuss the           │
│ [quarterly?] report."           │
│                                  │
│ [?] = Low confidence - click to │
│      review and correct         │
└─────────────────────────────────┘
```

---

## Control Patterns

### Pattern 1: Automation Levels

**What It Is:**
Let users choose how much AI assists vs. automates.

**Levels:**
1. **Manual Mode:** No AI, full user control
2. **Suggest Mode:** AI proposes, user decides
3. **Copilot Mode:** AI assists, user guides
4. **Auto Mode:** AI acts autonomously (user can review)

**When to Use:**
- Complex workflows
- When trust varies by user
- When tasks have varying risk levels

**Implementation:**
```
┌─────────────────────────────────┐
│ Automation Level:                │
│                                  │
│ ○ Manual   (No AI assistance)   │
│ ● Suggest  (AI proposes)         │
│ ○ Copilot  (AI assists)          │
│ ○ Auto     (AI acts alone)       │
│                                  │
│ Learn more about each mode →    │
└─────────────────────────────────┘
```

---

### Pattern 2: Edit and Override

**What It Is:**
All AI outputs are editable; user has final say.

**Key Principle:**
AI should never produce "final" outputs that users can't change.

**Examples:**
- Inline editing of AI text
- Override AI classification
- Modify AI-generated images
- Adjust AI recommendations

**Implementation:**
```
┌─────────────────────────────────┐
│ AI-Generated Summary:            │
│ ┌─────────────────────────────┐ │
│ │ [Editable text here...]     │ │
│ │ User can click and modify   │ │
│ │ any part of this output     │ │
│ └─────────────────────────────┘ │
│                                  │
│ [Regenerate] [Accept] [Discard] │
└─────────────────────────────────┘
```

---

### Pattern 3: Feedback Mechanisms

**What It Is:**
Let users rate and improve AI outputs.

**Types:**
- Binary (thumbs up/down)
- Scale (1-5 stars)
- Detailed (specific issues)
- Corrective (show correct answer)

**When to Use:**
- All AI features
- Especially during early stages
- When quality varies

**Implementation:**
```
┌─────────────────────────────────┐
│ AI Response:                     │
│ [AI output here]                 │
│                                  │
│ Was this helpful?                │
│ 👍 Yes  👎 No                    │
│                                  │
│ [Clicked 👎]                     │
│ ├─ ○ Inaccurate                 │
│ ├─ ○ Incomplete                 │
│ ├─ ○ Not helpful                │
│ └─ ○ Other: [text input]        │
│                                  │
│ [Submit Feedback]                │
└─────────────────────────────────┘
```

---

### Pattern 4: Undo and Rollback

**What It Is:**
Easy way to reverse AI actions.

**Key Principle:**
All AI actions should be reversible (where possible).

**Examples:**
- Undo button (Ctrl+Z)
- "Revert to original"
- Version history
- Restore previous state

**Implementation:**
```
┌─────────────────────────────────┐
│ ✅ AI applied 12 changes          │
│                                  │
│ [⟲ Undo All] [⚙️ Review Changes]│
│                                  │
│ Version History:                 │
│ • Now: AI edited (5 min ago)    │
│ • Previous: Manual (1 hr ago)   │
│ • Original: Draft (3 hrs ago)   │
│                                  │
│ Click to restore any version    │
└─────────────────────────────────┘
```

---

### Pattern 5: Preferences and Settings

**What It Is:**
User customizes AI behavior, tone, style, etc.

**What to Allow:**
- Tone (formal, casual, friendly)
- Verbosity (concise, detailed)
- Creativity (conservative, creative)
- Safety level (strict, moderate, permissive)

**Implementation:**
```
┌─────────────────────────────────┐
│ AI Settings                      │
│                                  │
│ Response Style:                  │
│ ○ Concise    ● Balanced    ○ Detailed │
│                                  │
│ Tone:                            │
│ ○ Formal     ● Professional ○ Casual  │
│                                  │
│ Creativity:                      │
│ Conservative ▓▓▓▓▓░░░░ Creative │
│                                  │
│ Safety:                          │
│ ● Strict filtering               │
│ ○ Moderate filtering             │
│ ○ Minimal filtering              │
│                                  │
│ [Reset to Defaults] [Save]      │
└─────────────────────────────────┘
```

---

## Error Handling Patterns

### Pattern 1: Clarification Prompts

**When AI Doesn't Understand:**
Ask specific questions to narrow down intent.

**Example:**
```
User: "Book a flight"

AI: "I'd be happy to help! To book a flight, I need:
    • Departure city
    • Destination city
    • Date(s) of travel
    • Number of passengers

    Which of these would you like to provide first?"
```

---

### Pattern 2: Graceful Degradation

**When AI Fails:**
Provide useful fallback instead of blank error.

**Example:**
```
┌─────────────────────────────────┐
│ ⚠️ AI Generation Unavailable     │
│                                  │
│ Our AI service is temporarily    │
│ down, but you can:               │
│                                  │
│ • [Use basic editor] (manual)   │
│ • [Browse templates]             │
│ • [Try again] in a few minutes  │
│ • [Contact support] for help    │
└─────────────────────────────────┘
```

---

### Pattern 3: Confidence-Based UI

**When AI Is Uncertain:**
Show uncertainty and ask for human input.

**Example:**
```
┌─────────────────────────────────┐
│ I'm not certain about this.      │
│ Confidence: 45%                  │
│                                  │
│ My best guess: [Answer A]       │
│                                  │
│ Did I get this right?            │
│ • Yes, that's correct            │
│ • No, it's actually [input]     │
│ • I'm not sure either            │
└─────────────────────────────────┘
```

---

### Pattern 4: Escalation to Human

**When AI Can't Help:**
Clear path to human assistance.

**Example:**
```
┌─────────────────────────────────┐
│ This requires human expertise    │
│                                  │
│ I've tried to help but this is   │
│ beyond my capabilities. I've     │
│ notified a specialist.           │
│                                  │
│ Expected response: 2-4 hours     │
│                                  │
│ [Talk to human now] (chat)      │
│ [Continue with AI] (different approach) │
└─────────────────────────────────┘
```

---

### Pattern 5: Contextual Help

**When Users Struggle:**
Detect struggles and offer guidance.

**Example:**
```
┌─────────────────────────────────┐
│ 💡 It looks like you're stuck    │
│                                  │
│ You've regenerated 5 times.      │
│ Would you like:                  │
│                                  │
│ • [Tips for better prompts]     │
│ • [See examples]                 │
│ • [Start over with template]    │
│ • [Contact support]              │
│                                  │
│ [No thanks, keep trying]        │
└─────────────────────────────────┘
```

---

## Multimodal Patterns

### Pattern 1: Text + Image Input

**Use Case:** Visual question answering, image analysis

**Example Flow:**
```
User: [Uploads photo of plant] + "What plant is this?"
AI: Analyzes image → "This is a Monstera Deliciosa"
```

**When to Use:**
- Product identification
- Visual search
- Accessibility (describe images)
- Document analysis

---

### Pattern 2: Voice + Screen

**Use Case:** Hands-free interaction while viewing content

**Example Flow:**
```
User: [Looking at dashboard] "Show me last quarter's revenue"
AI: [Highlights chart on screen] + Speaks: "Last quarter revenue was $2.5M"
```

**When to Use:**
- Driving/cooking scenarios
- Accessibility
- Presentations
- Ambient computing

---

### Pattern 3: Text to Image/Video

**Use Case:** Creative content generation

**Example Flow:**
```
User: [Types description]
AI: Generates image/video matching description
User: [Refines with text] "Make it darker"
AI: Regenerates with adjustments
```

**When to Use:**
- Design and creative work
- Marketing content
- Prototyping
- Visualization

---

### Pattern 4: Multimodal Output

**Use Case:** Presenting information in best format for each piece

**Example Flow:**
```
User: "Explain quantum computing"
AI:
  - Text explanation
  - Diagram (image)
  - Video demonstration
  - Interactive simulation
User chooses preferred format
```

**When to Use:**
- Educational content
- Complex explanations
- Different learning styles
- Accessibility

---

## Pattern Selection Guide

### Decision Tree

```
Start: What is the user's goal?

├─ Get suggestions while working
│  └─ → AUTOCOMPLETE/COPILOT
│
├─ Have a conversation or ask questions
│  └─ → CONVERSATIONAL
│
├─ Create original content from description
│  └─ → GENERATIVE
│
├─ Discover personalized options
│  └─ → RECOMMENDATION
│
├─ Categorize or analyze content
│  └─ → CLASSIFICATION
│
└─ Automate multi-step workflow
   └─ → AGENTIC
```

---

### Pattern Comparison Matrix

| Pattern | Speed | Control | Complexity | Learning Curve | Trust Required |
|---------|-------|---------|------------|----------------|----------------|
| Autocomplete | ⚡⚡⚡ | High | Low | Low | Low |
| Conversational | ⚡ | Medium | Medium | Low | Medium |
| Generative | ⚡⚡ | Medium | Medium | Medium | Medium |
| Recommendation | ⚡⚡⚡ | Medium | Low | Low | Medium |
| Classification | ⚡⚡⚡ | Low | Low | Low | Medium |
| Agentic | ⚡ | Low | High | High | High |

---

## Interview Application

### Question: "Design an AI feature for [product]"

**Use This Framework:**

**1. Understand the Use Case**
- What problem are we solving?
- Who is the user?
- What's the context of use?

**2. Select Pattern(s)**
- Which interaction pattern fits best?
- Why this pattern over others?
- Will we combine multiple patterns?

**3. Design for Transparency**
- How will we show AI confidence?
- How will we explain AI decisions?
- What sources/reasoning will we show?

**4. Add Control**
- How can users override AI?
- What automation level is appropriate?
- How can users provide feedback?

**5. Plan for Failure**
- What are the failure modes?
- How will we handle errors gracefully?
- When do we escalate to human?

**6. Consider Multimodal**
- Could other modalities improve the experience?
- When would we use voice, image, video?

---

## Key Takeaways

### What Makes AI UX Different:
1. **Probabilistic, not deterministic** - Won't always work the same
2. **Opaque reasoning** - Hard to explain why
3. **Continuously changing** - Models update and improve
4. **Variable quality** - Some outputs great, others poor

### Core Principles:
1. **Set expectations** - Tell users what AI can/can't do
2. **Show confidence** - Indicate certainty levels
3. **Explain decisions** - Make reasoning transparent
4. **Provide control** - Users can always override
5. **Design for failure** - Errors will happen

### Pattern Selection:
- **Autocomplete:** High-frequency tasks, clear answers
- **Conversational:** Complex, open-ended tasks
- **Generative:** Creative content creation
- **Recommendation:** Discovery and personalization
- **Classification:** Large volumes, pattern recognition
- **Agentic:** Multi-step, delegatable workflows

---

**Use this pattern library when:**
- ✅ Designing new AI features
- ✅ Evaluating existing AI UX
- ✅ Answering interview questions
- ✅ Creating portfolio projects
- ✅ Communicating with engineers and designers

**Next Steps:**
- Apply these patterns to your portfolio project
- Create mockups using appropriate patterns
- Document your pattern choices and rationale
- Test with users and iterate

---

**This pattern library is a living document. Update as you learn new patterns and best practices!**
