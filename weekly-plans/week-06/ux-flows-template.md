# AI Product UX Flows

**Created:** [Date]
**Week 6 Deliverable**
**Product:** [Your AI Product Name]
**Total Flows:** 5+ (Happy path, Ambiguous input, Edge case, Error state, Power user)

---

## Flow Overview

| Flow # | Name | Scenario Type | Status |
|--------|------|---------------|--------|
| 1 | [Happy Path] | Ideal usage | ✅ Complete |
| 2 | [Ambiguous Input] | User unclear | ✅ Complete |
| 3 | [Edge Case] | Unusual scenario | ✅ Complete |
| 4 | [Error State] | AI failure | ✅ Complete |
| 5 | [Power User] | Advanced usage | ✅ Complete |

---

## Flow #1: Happy Path (Everything Works Perfectly)

### Scenario Description
**User Goal:** [What the user is trying to achieve]

**Context:** [When/where/why the user would do this]

**User Type:** [Primary persona]

**Expected Duration:** [How long this flow should take]

---

### Flow Steps

#### Step 1: User Initiation

**User Action:**
- Interface: [Where user is - e.g., "Chat interface", "Document editor"]
- Input: [What user types/clicks]

**Exact User Input:**
```
[Copy exact text or describe exact action]

Example: "Generate a product description for eco-friendly water bottles
targeting fitness enthusiasts"
```

---

**AI Processing:**
- What happens: [e.g., "AI analyzes request, identifies intent"]
- Visible to user: [Loading indicator, typing animation, etc.]
- Duration: [Typical response time]

---

**AI Response:**

**Output:**
```
[Exact AI response or screenshot]

Example: "Introducing the EcoFlow™ Bottle: Your hydration companion for
an active, sustainable lifestyle. Made from 100% recycled materials,
this lightweight 24oz bottle keeps drinks cold for 24 hours while
helping save the planet. BPA-free, dishwasher-safe, and designed for
athletes who care about performance and the environment. Stay hydrated,
stay green."
```

**UI State:**
- How response is displayed: [e.g., "Typewriter effect", "All at once"]
- Actions available: [e.g., "Copy", "Regenerate", "Edit", "Thumbs up/down"]

---

#### Step 2: User Interaction with Result

**User Action:**
- What user does: [e.g., "Reviews output, clicks thumbs up"]
- Why: [User is satisfied/wants to iterate/etc.]

**Screenshot/Mockup:** [If available]

---

#### Step 3: [Next Action]

[Repeat structure for each step in the flow]

---

### Flow Completion

**Success Criteria:**
- [ ] User achieved their goal
- [ ] Output quality met expectations
- [ ] No errors encountered
- [ ] User would use again

**User Sentiment:** 😊 Satisfied

**Time to Completion:** [X seconds/minutes]

**User Quote (from testing):**
> "[What users said about this flow]"

---

### Learnings from This Flow

**What Worked Well:**
1. [Observation 1]
2. [Observation 2]

**Potential Improvements:**
1. [Improvement idea 1]
2. [Improvement idea 2]

---

## Flow #2: Ambiguous Input (User Request is Unclear)

### Scenario Description
**User Goal:** [What user wants but hasn't articulated clearly]

**Context:** [Why request is ambiguous]

**Challenge:** [What's unclear - multiple interpretations, missing info, etc.]

---

### Flow Steps

#### Step 1: User Provides Ambiguous Input

**User Action:**
- Interface: [Where]
- Input: [What]

**Exact User Input:**
```
[Vague or unclear request]

Example: "Write something about our product"
```

**Why This Is Ambiguous:**
- Missing: [What information is missing - e.g., "Which product?", "What type of content?", "For whom?"]

---

**AI Processing:**
- What happens: [AI detects ambiguity]
- Decision: [How AI responds to unclear input]

---

**AI Response (Clarification):**

**Output:**
```
I'd be happy to help you write about your product! To create something
useful, I need a bit more information:

1. Which product are you referring to?
2. What type of content do you need? (e.g., description, email, social post)
3. Who is your target audience?
4. Any specific points you want to emphasize?

Please provide these details and I'll create something great for you!
```

**UI State:**
- Clarifying questions displayed clearly
- Input field ready for user response

---

#### Step 2: User Provides Clarification

**User Action:**
- Provides additional details

**User Input:**
```
"It's for our eco-friendly water bottle. Need a product description for
our website. Targeting environmentally conscious millennials. Emphasize
the recycled materials and 24-hour cold retention."
```

---

**AI Processing:**
- What happens: [AI now has enough context]

---

**AI Response:**

**Output:**
```
[Now provides the requested content with all the specified details]
```

---

#### Step 3: User Confirms Satisfaction

**User Action:**
- Reviews output
- Accepts result

---

### Flow Completion

**Success Criteria:**
- [ ] AI successfully identified ambiguity
- [ ] Clarifying questions were helpful
- [ ] User provided needed info
- [ ] Final output met expectations

**User Sentiment:** 😊 Satisfied (after clarification)

**Time to Completion:** [X seconds/minutes] (longer due to clarification)

---

### Learnings from This Flow

**How AI Handled Ambiguity:**
- Strategy: [Ask clarifying questions vs. make assumptions vs. provide multiple options]
- Effectiveness: [Did it work?]

**UX Improvements:**
- [Idea 1: e.g., "Could provide smart defaults"]
- [Idea 2: e.g., "Could show examples of good requests"]

**Prompt Engineering Insight:**
- [What you learned about handling ambiguity]

---

## Flow #3: Edge Case (Unusual but Valid Scenario)

### Scenario Description
**User Goal:** [Uncommon but legitimate use case]

**Context:** [Why this is an edge case]

**Frequency:** [How often you expect this - e.g., "<5% of use cases"]

---

### Flow Steps

#### Step 1: User Provides Edge Case Input

**User Action:**

**Exact User Input:**
```
[Unusual request that's still valid]

Example: "Generate a product description but make it sound like it's
written by a pirate and include the technical specs in a table"
```

**Why This Is an Edge Case:**
- Unusual requirement: [What's unusual]
- Challenge for AI: [Why this might be difficult]

---

**AI Processing:**
- What happens: [AI attempts to handle unusual request]

---

**AI Response:**

**Output:**
```
[AI's attempt to handle the edge case]

Example:
Ahoy, matey! Feast yer eyes on the finest vessel fer keepin' yer grog
ice-cold on the high seas! The EcoFlow™ Bottle be crafted from the
treasures of recycled materials, keepin' yer beverages colder than a
mermaid's heart fer a full 24 hours. Perfect fer swashbucklin' athletes
who give a barnacle about Mother Earth!

| Specification | Value |
|---------------|-------|
| Capacity | 24 oz (710 ml) |
| Material | 100% Recycled Stainless Steel |
| Insulation | Double-wall vacuum |
| Temperature | Cold 24hrs, Hot 12hrs |
| Dimensions | 10.5" x 2.8" |
```

**Quality Assessment:**
- Did it work? [Yes/Partial/No]
- Issues: [Any problems]

---

#### Step 2: User Response

**User Action:**
- [How user reacted to the output]
- [Whether they accepted, edited, or regenerated]

---

### Flow Completion

**Success Criteria:**
- [ ] AI attempted to handle unusual request
- [ ] Output was creative/appropriate
- [ ] Technical requirements met
- [ ] User satisfied with result

**User Sentiment:** [Emoji + description]

---

### Learnings from This Flow

**AI Capabilities:**
- Strengths: [What AI handled well]
- Limitations: [What it struggled with]

**Design Implications:**
- [Should you support this use case?]
- [How to make it better?]

---

## Flow #4: Error State (AI Fails or Can't Help)

### Scenario Description
**User Goal:** [What user wants]

**Why It Fails:** [Root cause - e.g., "Outside AI's knowledge", "Violates safety policy", "Technical error"]

**Error Type:**
[ ] AI doesn't understand request
[ ] AI lacks required information
[ ] Request violates guidelines
[ ] Technical failure (API down, timeout)
[ ] Other: [Specify]

---

### Flow Steps

#### Step 1: User Makes Problematic Request

**User Action:**

**Exact User Input:**
```
[Request that will cause an error]

Example: "Generate medical advice for treating my symptoms"
```

**Why This Fails:**
- [Specific reason - e.g., "Medical advice outside scope and safety policy"]

---

**AI Processing:**
- What happens: [AI detects problem]
- Safety check: [How safety system responds]

---

**AI Response (Error Handling):**

**Output:**
```
I understand you're looking for medical advice, but I'm not able to
provide medical diagnoses or treatment recommendations. For health
concerns, please consult with a qualified healthcare professional.

What I can help with instead:
- General health and wellness information
- Finding medical resources in your area
- Understanding medical terminology
- Preparing questions for your doctor visit

Would any of these alternatives be helpful?
```

**UI State:**
- Error indicated clearly (not just blank/generic "error")
- Alternative paths offered
- Maintains helpful tone (not cold/robotic)

---

#### Step 2: User Response to Error

**User Action:**
- [How user reacted]

**Options Provided:**
1. [Alternative action 1]
2. [Alternative action 2]
3. [Contact support / escalate]

---

### Flow Completion

**Success Criteria:**
- [ ] Error explained clearly
- [ ] User understands why request failed
- [ ] Alternatives offered
- [ ] User can proceed with alternative or understands limitations

**User Sentiment:** 😐 Disappointed but understands

---

### Learnings from This Flow

**Error Handling Strategy:**
- Approach: [How you designed error messages]
- User Response: [How users reacted]

**Improvements Needed:**
1. [Improvement 1]
2. [Improvement 2]

**Fallback Design:**
- [What happens when AI can't help]
- [How to gracefully degrade]

---

## Flow #5: Power User (Advanced Features/Complex Needs)

### Scenario Description
**User Goal:** [Complex or advanced use case]

**User Type:** Power user who knows how to use the tool well

**Complexity:** [What makes this advanced]

---

### Flow Steps

#### Step 1: User Leverages Advanced Features

**User Action:**
- Shows mastery of tool
- Uses advanced prompt techniques
- Multi-step workflow

**Exact User Input:**
```
[Sophisticated request showing user understands AI capabilities]

Example: "Generate 3 versions of a product description for our eco water
bottle: Version A for Instagram (casual, emoji-friendly, <50 words),
Version B for our website (professional, SEO-optimized, 150 words,
include keywords: sustainable, BPA-free, athlete), Version C for email
campaign (conversational, focus on environmental impact, include CTA).
Format as markdown with clear labels."
```

---

**AI Processing:**
- What happens: [AI processes complex multi-part request]

---

**AI Response:**

**Output:**
```
# Product Descriptions - EcoFlow™ Bottle

## Version A: Instagram
🌊 Meet your new hydration hero! 100% recycled, keeps drinks cold for
24hrs 🧊 Perfect for athletes who love the planet 🌍 Sustainable +
Stylish = ✨ #EcoFlow #SustainableHydration

## Version B: Website (SEO-Optimized)
Stay hydrated sustainably with the EcoFlow™ Bottle - your eco-friendly
hydration solution for active lifestyles. [Full 150-word description
with keywords naturally integrated...]

## Version C: Email Campaign
Hey there!

Ready to upgrade your hydration game while making a positive impact?

[Conversational copy focusing on environmental impact... ending with clear CTA]

Ready to make the switch? Shop EcoFlow™ Bottles today →
```

---

#### Step 2: Power User Iterates

**User Action:**
- Refines request with specific feedback
- Knows exactly what to ask for

**User Input:**
```
"Great! For Version B, can you increase the focus on the 24-hour cold
retention and add a comparison to regular bottles? Also mention the
lifetime warranty."
```

---

**AI Response:**
- Handles iteration smoothly
- Makes requested changes precisely

---

### Flow Completion

**Success Criteria:**
- [ ] AI handled complex, multi-part request
- [ ] Output quality high across all variations
- [ ] Iterations were smooth
- [ ] Power user's efficiency increased

**User Sentiment:** 🤩 Impressed

**Time to Completion:** [Efficient for amount of work done]

---

### Learnings from This Flow

**Power User Behaviors:**
- [Pattern 1 they exhibited]
- [Pattern 2 they exhibited]

**Advanced Features Needed:**
- [Feature idea 1 for power users]
- [Feature idea 2 for power users]

**Prompt Engineering Insight:**
- [What makes a power user prompt effective]

---

## Bonus Flow #6: [Additional Scenario]

[Optional: Add more flows like "Multi-turn conversation", "First-time user onboarding", "Mobile vs Desktop", etc.]

---

## Cross-Flow Analysis

### Common Patterns Across All Flows

**Success Factors:**
1. [Pattern that led to success across flows]
2. [Pattern that led to success across flows]
3. [Pattern that led to success across flows]

**Failure Patterns:**
1. [Common failure mode]
2. [Common failure mode]

---

### UX Principles Applied

**Transparency:**
- How we showed AI confidence: [Method]
- How we explained reasoning: [Method]

**Control:**
- How users could adjust AI: [Method]
- How users could override: [Method]

**Feedback:**
- How users provided feedback: [Method]
- How we used feedback: [Method]

---

### Metrics Summary

| Flow | Task Completion | User Satisfaction | Avg Time | Acceptance Rate |
|------|----------------|-------------------|----------|-----------------|
| Happy Path | [%] | [X/5] | [Xs] | [%] |
| Ambiguous Input | [%] | [X/5] | [Xs] | [%] |
| Edge Case | [%] | [X/5] | [Xs] | [%] |
| Error State | [%] | [X/5] | [Xs] | [%] |
| Power User | [%] | [X/5] | [Xs] | [%] |
| **Overall** | **[%]** | **[X/5]** | **[Xs]** | **[%]** |

---

## Key Learnings

### What Users Loved ❤️
1. [Specific thing users consistently praised]
2. [Specific thing users consistently praised]
3. [Specific thing users consistently praised]

### What Users Struggled With 😕
1. [Common pain point]
2. [Common pain point]
3. [Common pain point]

### Surprising Discoveries 💡
1. [Unexpected finding from testing]
2. [Unexpected finding from testing]
3. [Unexpected finding from testing]

---

## Design Improvements Based on Flows

### Immediate Wins (Can do with prompts)
1. [Improvement 1]
   - **Why:** [Rationale]
   - **Expected Impact:** [Outcome]

2. [Improvement 2]
   - **Why:**
   - **Expected Impact:**

---

### Requires Engineering
1. [Improvement 1]
   - **Why:** [Why prompts aren't enough]
   - **Expected Impact:** [Outcome]

2. [Improvement 2]
   - **Why:**
   - **Expected Impact:**

---

## Interview Application

**When asked: "Walk me through your UX research process"**

**Your Answer:**

"For my AI prototype, I tested 5 core user flows to cover the full experience:

**Flows Tested:**
1. Happy path - ideal usage
2. Ambiguous input - unclear requests
3. Edge cases - unusual scenarios
4. Error states - AI failures
5. Power users - advanced needs

**Method:** I gave [X] users real scenarios and observed their interactions. I tracked task completion, satisfaction, and time to complete.

**Key Findings:**
- [Specific insight 1 with metric]
- [Specific insight 2 with metric]
- [Specific insight 3 with metric]

**Impact:** Based on these flows, I [specific action taken, specific improvement made]. This improved [metric] by [%].

**Learnings:** The biggest surprise was [unexpected finding]. This taught me [broader lesson about AI UX]."

**Practice explaining your UX flows in 3-5 minutes with specific examples!**
