# AI Product UX Flows Template

**Purpose:** Document all major user experience flows for your AI product

**Time Required:** 3-4 hours (Day 5 morning of Week 10)

**Output:** 5-7 detailed UX flows covering all key scenarios

---

## Table of Contents

1. [UX Flow Fundamentals](#ux-flow-fundamentals)
2. [AI-Specific UX Considerations](#ai-specific-ux-considerations)
3. [Flow Templates](#flow-templates)
4. [How to Create Flows](#how-to-create-flows)
5. [Tools and Formats](#tools-and-formats)
6. [Quality Checklist](#quality-checklist)

---

## UX Flow Fundamentals

### What is a UX Flow?

**A step-by-step visualization of how a user accomplishes a goal within your product.**

**Elements:**
- User actions (what they do)
- System responses (what the app does)
- AI processing (what the AI does)
- UI states (what they see)
- Decision points (branching logic)
- Success/error outcomes

---

### Why Document Flows?

**For Your Portfolio:**
- ✅ Shows you think through complete user experiences
- ✅ Demonstrates understanding of AI UX patterns
- ✅ Proves attention to edge cases and error states
- ✅ Gives interviewers concrete discussion points

**For Development:**
- ✅ Engineers know what to build
- ✅ Designers know what to design
- ✅ QA knows what to test
- ✅ Stakeholders understand the experience

---

### Required Flows (Minimum 5)

**1. Happy Path Flow**
- Everything works perfectly
- User gets ideal result
- No errors or issues
- Showcases core value

**2. Ambiguous Input Flow**
- User provides unclear request
- AI asks clarifying questions
- User refines input
- Shows AI can handle uncertainty

**3. Multi-Turn Conversation Flow**
- Complex task requiring back-and-forth
- AI maintains context
- Progressive refinement
- Shows conversational capability

**4. Error/Failure Flow**
- AI can't complete request
- System handles gracefully
- User gets alternatives
- Shows robustness

**5. Edge Case Flow**
- Unusual but valid scenario
- System handles appropriately
- Shows comprehensiveness

**Bonus Flows:**

**6. First-Time User Flow**
- Onboarding experience
- Guidance and tooltips
- Sample prompts
- Shows user-friendliness

**7. Power User Flow**
- Advanced features
- Shortcuts and customization
- Shows depth

---

## AI-Specific UX Considerations

### 1. Loading States

**AI takes time to process. Users need to know:**

- [ ] Processing started
- [ ] Estimated time (if possible)
- [ ] Progress (if multi-step)
- [ ] Ability to cancel

**Examples:**
```
🤖 "Analyzing your code..."
⏱️ "This may take 10-30 seconds"
▓▓▓▓░░░░░░ 40% complete
[Cancel] button
```

---

### 2. Confidence Indicators

**Show users how confident the AI is:**

- High confidence: ✅ "High confidence" or no indicator
- Medium confidence: ⚠️ "Medium confidence - please review"
- Low confidence: ❗ "Low confidence - verify carefully"

**Example:**
```
Generated Documentation ✅ High Confidence

[Documentation content]

This was generated with high confidence based on clear code structure.
```

---

### 3. Explainability

**Help users understand AI decisions:**

- Show reasoning
- Cite sources (if RAG)
- Explain confidence
- Make process transparent

**Example:**
```
Why this recommendation?
• Your code follows pattern X
• Similar to Y examples in knowledge base
• Matches style guide Z
```

---

### 4. User Control

**Users should always feel in control:**

- [ ] Preview before applying
- [ ] Edit AI outputs easily
- [ ] Reject suggestions
- [ ] Undo actions
- [ ] Adjust AI behavior (settings)

---

### 5. Error Recovery

**When AI fails, provide paths forward:**

- Clear error explanation
- Suggested fixes
- Alternative approaches
- Manual fallback
- Help/contact support

---

### 6. Feedback Loops

**Let users improve AI quality:**

- Thumbs up/down
- Edit tracking
- Explicit feedback forms
- Report issues

---

## Flow Templates

### Template 1: Happy Path Flow

**Flow Name:** [e.g., "Generate Documentation - Perfect Scenario"]

**User Goal:** [What the user wants to accomplish]

**Preconditions:** [Starting state - e.g., "User is logged in, has code to document"]

**Success Criteria:** [How we know it worked - e.g., "User receives accurate documentation and accepts it"]

---

#### Step-by-Step Flow

| Step | Actor | Action | UI State | Notes |
|------|-------|--------|----------|-------|
| 1 | User | Clicks "Generate Documentation" | Main screen | Entry point |
| 2 | System | Shows input form | Input screen with code editor | Clear, focused |
| 3 | User | Pastes code into editor | Code visible in editor | Syntax highlighting |
| 4 | User | Selects language (Python) | Dropdown selected | Auto-detection possible |
| 5 | User | Clicks "Generate" | Button highlighted | Primary CTA |
| 6 | System | Validates input | Loading state starts | Check for errors |
| 7 | AI | Processes code | "Analyzing code..." with spinner | 5-10 seconds |
| 8 | AI | Generates documentation | Processing indicator | LLM API call |
| 9 | System | Displays result | Documentation preview | Well-formatted |
| 10 | User | Reviews output | Can scroll, read | Quality check |
| 11 | User | Clicks "Accept" | Button available | Happy with result |
| 12 | System | Saves documentation | Success message + confetti | Celebration! |

---

#### Visual Representation

```
[Main Screen]
     ↓ (Click "Generate Documentation")
[Input Form]
 - Code editor
 - Language selector
 - [Generate] button
     ↓ (Click Generate)
[Validation]
     ↓ (If valid)
[AI Processing] 🤖
 "Analyzing your code..."
 ⏱️ 10-30 seconds
     ↓
[Preview Documentation]
 ┌─────────────────┐
 │ ## Function     │
 │ Description...  │
 │ Parameters...   │
 └─────────────────┘
 [✏️ Edit] [✅ Accept] [❌ Reject]
     ↓ (Click Accept)
[Success] 🎉
 "Documentation saved!"
```

---

#### Screenshots/Mockups

[Insert screenshots or wireframes for each key screen]

**Screen 1: Input Form**
![Input Form]

**Screen 2: Processing**
![Loading State]

**Screen 3: Preview**
![Result Preview]

**Screen 4: Success**
![Success Message]

---

### Template 2: Ambiguous Input Flow

**Flow Name:** [e.g., "Handle Unclear Code"]

**User Goal:** [Document code, but code is unclear/incomplete]

**Preconditions:** [User is on input screen]

**Success Criteria:** [AI asks clarifying questions, user provides context, documentation generated]

---

#### Step-by-Step Flow

| Step | Actor | Action | UI State | Notes |
|------|-------|--------|----------|-------|
| 1 | User | Pastes unclear code snippet | Code in editor | Missing context |
| 2 | User | Clicks "Generate" | Loading starts | |
| 3 | AI | Analyzes code | Processing | |
| 4 | AI | Detects ambiguity | | Low confidence |
| 5 | System | Shows clarifying questions | Question modal | ⚠️ "Need more info" |
| 6 | System | "What does this function do?" | Text input | Helpful UI |
| 7 | User | Provides context | Typing answer | Clear explanation |
| 8 | User | Clicks "Continue" | Submit button | |
| 9 | AI | Re-processes with context | Loading state | Now has full picture |
| 10 | System | Shows documentation | Preview with ⚠️ "Medium confidence" | Indicates uncertainty |
| 11 | User | Reviews and edits | Editing mode | Fixes AI gaps |
| 12 | User | Accepts | | Happy enough |

---

#### Visual Representation

```
[User Pastes Unclear Code]
     ↓
[AI Processes] 🤖
     ↓ (Low confidence detected)
[Clarifying Questions] ⚠️
 ┌────────────────────────┐
 │ To generate better     │
 │ documentation, we need:│
 │                        │
 │ 1. What does this do?  │
 │ [Text input________]   │
 │                        │
 │ 2. What's the context? │
 │ [Text input________]   │
 │                        │
 │ [Skip] [Continue]      │
 └────────────────────────┘
     ↓ (User provides context)
[AI Re-processes with Context]
     ↓
[Shows Result] ⚠️ Medium Confidence
 "Please review carefully"
     ↓
[User Edits and Accepts]
```

---

### Template 3: Multi-Turn Conversation Flow

**Flow Name:** [e.g., "Iterative Documentation Refinement"]

**User Goal:** [Perfect the documentation through conversation]

**Preconditions:** [Initial documentation generated]

**Success Criteria:** [User gets exactly what they want after 2-3 exchanges]

---

#### Conversation Example

**Turn 1:**
```
User: "Generate documentation for this function"

AI: [Generates initial docs]

"Here's the documentation. Would you like me to:
• Make it more detailed?
• Add more examples?
• Change the style?"
```

**Turn 2:**
```
User: "Add more examples, especially edge cases"

AI: [Regenerates with 3 examples including edge cases]

"I've added examples for:
1. Normal use
2. Edge case: empty input
3. Edge case: very large input

Anything else to adjust?"
```

**Turn 3:**
```
User: "Perfect! Save it."

AI: ✅ "Saved! Your documentation is ready."
```

---

#### Visual Representation

```
[Chat Interface]

┌──────────────────────────┐
│ User: Generate docs      │
└──────────────────────────┘
     ↓
┌──────────────────────────┐
│ AI: Here's the docs...   │
│ [Documentation shown]    │
│                          │
│ Would you like me to:    │
│ • Make it more detailed? │
│ • Add more examples?     │
│ • Change the style?      │
└──────────────────────────┘
     ↓
┌──────────────────────────┐
│ User: Add more examples  │
└──────────────────────────┘
     ↓
┌──────────────────────────┐
│ AI: Updated with 3       │
│ examples. [Shows updated]│
│                          │
│ Anything else?           │
└──────────────────────────┘
     ↓
┌──────────────────────────┐
│ User: Perfect! Save it.  │
└──────────────────────────┘
     ↓
┌──────────────────────────┐
│ AI: ✅ Saved!            │
└──────────────────────────┘
```

---

### Template 4: Error/Failure Flow

**Flow Name:** [e.g., "AI Can't Process Code"]

**User Goal:** [Document code]

**Actual Outcome:** [AI fails to process]

**Success Criteria:** [User understands why it failed and has alternative path]

---

#### Step-by-Step Flow

| Step | Actor | Action | UI State | Notes |
|------|-------|--------|----------|-------|
| 1 | User | Pastes very complex code | Code in editor | 50,000 characters |
| 2 | User | Clicks "Generate" | Loading starts | |
| 3 | System | Validates input | | Checks length |
| 4 | System | Detects input too long | | 50K > 10K limit |
| 5 | System | Shows error message | Error modal | Clear, helpful |
| 6 | System | "Code too large (50K chars)" | Red text | Specific issue |
| 7 | System | "Max: 10,000 characters" | | Clear limit |
| 8 | System | Suggests solutions | Bullet list | Helpful guidance |
| 9 | System | "Try: • Split into functions" | | Actionable |
| 10 | System | "• Document one function at a time" | | Alternative path |
| 11 | User | Selects one function | Editing code | Follows guidance |
| 12 | User | Re-tries with smaller input | | Second attempt |
| 13 | AI | Successfully processes | | Now works! |

---

#### Visual Representation

```
[User Submits Huge Code]
     ↓
[System Validates]
     ↓ (Too large!)
[Error Screen] ❌
 ┌────────────────────────┐
 │ ⚠️ Input Too Large     │
 │                        │
 │ Your code: 50,000 chars│
 │ Maximum:   10,000 chars│
 │                        │
 │ Suggestions:           │
 │ • Split into smaller   │
 │   functions            │
 │ • Document one piece   │
 │   at a time            │
 │ • Use our CLI for bulk │
 │                        │
 │ [Try Again] [Learn More]│
 └────────────────────────┘
     ↓ (User splits code)
[Retry with Smaller Input]
     ↓
[Success!] ✅
```

---

### Template 5: Edge Case Flow

**Flow Name:** [e.g., "Document Non-English Code Comments"]

**User Goal:** [Document code with Chinese comments]

**Success Criteria:** [AI handles gracefully, preserves original language]

---

#### Step-by-Step Flow

| Step | Actor | Action | UI State | Notes |
|------|-------|--------|----------|-------|
| 1 | User | Pastes code with Chinese comments | Code visible | Edge case |
| 2 | User | Clicks "Generate" | | |
| 3 | AI | Processes code | | Detects non-English |
| 4 | AI | Generates English docs | | Main docs in English |
| 5 | AI | Preserves Chinese comments | | Keeps original |
| 6 | System | Shows result with note | Info banner | Transparency |
| 7 | System | "ℹ️ Code contains Chinese comments" | | User awareness |
| 8 | System | "Preserved in original language" | | Shows approach |
| 9 | User | Reviews bilingual output | | Satisfied |
| 10 | User | Accepts | | Works well |

---

### Template 6: First-Time User Flow (Bonus)

**Flow Name:** [e.g., "Onboarding New User"]

**User Goal:** [Learn how to use the product]

**Success Criteria:** [User successfully generates first documentation]

---

#### Step-by-Step Flow

| Step | Actor | Action | UI State | Notes |
|------|-------|--------|----------|-------|
| 1 | User | Arrives at product | Landing page | First visit |
| 2 | System | Detects first-time user | | Cookie/auth check |
| 3 | System | Shows welcome modal | Onboarding overlay | Friendly |
| 4 | System | "Welcome! Let's get started" | | Encouraging |
| 5 | System | Shows quick tutorial (3 steps) | Step 1 of 3 | Simple |
| 6 | User | Clicks "Next" | Progress indicator | |
| 7 | System | Highlights code editor | Tooltip | Visual guidance |
| 8 | System | "Paste your code here" | | Clear instruction |
| 9 | System | Provides sample code | "Try this example" button | Easy start |
| 10 | User | Clicks "Try this example" | Sample auto-fills | Low friction |
| 11 | User | Clicks "Generate" | Guided action | Following tutorial |
| 12 | AI | Processes sample code | Fast! | Good first experience |
| 13 | System | Shows result with celebration | 🎉 "You did it!" | Positive reinforcement |
| 14 | System | "Now try with your own code" | Encouragement | Next step |

---

## How to Create Flows

### Step 1: Identify the Scenario (10 minutes)

**Ask:**
- What is the user trying to do?
- What's the starting point?
- What does success look like?
- What could go wrong?

**Prioritize:**
1. Most common workflows first
2. Critical paths (happy path)
3. Error cases
4. Edge cases

---

### Step 2: Map Out Steps (30 minutes per flow)

**Use this format:**

**Actor → Action → System Response**

**Example:**
1. User clicks "Generate"
2. System validates input
3. AI processes request
4. System displays result
5. User reviews output
6. User accepts or edits

**Be specific:**
- ❌ "User provides input"
- ✅ "User pastes code into editor (up to 10,000 chars)"

---

### Step 3: Add UI Details (20 minutes per flow)

**For each step, describe:**

- What the screen looks like
- What elements are visible
- What's enabled/disabled
- Loading states
- Error messages
- Success confirmations

**Example:**
```
Step 7: AI Processing
Screen: Shows loading spinner with message
Message: "🤖 Analyzing your code..."
Duration: ~10-30 seconds
Elements:
- Animated spinner
- Progress text
- [Cancel] button (enabled)
- Previous screen dimmed in background
```

---

### Step 4: Create Visuals (30-60 minutes per flow)

**Options:**

**A. Flowchart Diagram**
- Use shapes and arrows
- Show decision points
- Include all paths

**B. Wireframes**
- Sketch key screens
- Show UI elements
- Annotate interactions

**C. Annotated Screenshots**
- If prototype exists
- Add arrows and labels
- Explain each element

**D. Text-Based (Markdown)**
- ASCII art
- Clear descriptions
- Code block formatting

---

## Tools and Formats

### Recommended Tools

| Tool | Best For | Cost | Learning Curve |
|------|----------|------|----------------|
| **Figma** | Professional wireframes | Free | ⭐⭐⭐ |
| **Whimsical** | Quick flowcharts | Free tier | ⭐⭐⭐⭐⭐ |
| **Miro** | Collaborative boards | Free tier | ⭐⭐⭐⭐ |
| **Lucidchart** | Detailed flowcharts | Free trial | ⭐⭐⭐ |
| **Excalidraw** | Hand-drawn style | Free | ⭐⭐⭐⭐⭐ |
| **Markdown** | Text-based, fast | Free | ⭐⭐⭐⭐⭐ |

---

### Format Examples

#### Flowchart Notation

```
┌─────────┐
│  Start  │
└────┬────┘
     │
     ↓
┌────────────┐
│ User Action│
└─────┬──────┘
      │
      ↓
  ┌───┴───┐
 ╱Decision? ╲
 ╲─────────╱
  │     │
 Yes   No
  │     │
  ↓     ↓
[A]   [B]
```

#### Swimlane Diagram

```
User    │ System  │ AI
────────┼─────────┼────────
Click   │         │
  ↓     │         │
        │ Validate│
        │    ↓    │
        │         │Process
        │         │   ↓
        │ Display │
   ↓    │         │
Review  │         │
  ↓     │         │
Accept  │         │
        │  Save   │
```

#### Storyboard Format

```
Frame 1: [User at main screen]
"User sees empty code editor with 'Paste code here' placeholder"

Frame 2: [User pastes code]
"Code appears in editor with syntax highlighting"

Frame 3: [User clicks Generate]
"Button changes to loading state, spinner appears"

Frame 4: [AI processing]
"Message shows: 'Analyzing your code...' with animated dots"

Frame 5: [Result displayed]
"Documentation appears below code with 'Accept' and 'Edit' buttons"
```

---

## Quality Checklist

### Before Calling Flows "Complete"

**Coverage:**
- [ ] 5+ flows documented
- [ ] Happy path covered
- [ ] At least 2 error cases covered
- [ ] At least 1 edge case covered
- [ ] Onboarding flow (if applicable)

**Detail Level:**
- [ ] Every step is specific and clear
- [ ] UI states are described
- [ ] Timing/latency noted where relevant
- [ ] Error messages written out
- [ ] Success confirmations included

**AI-Specific Elements:**
- [ ] Loading states shown
- [ ] Confidence indicators included
- [ ] User control options present
- [ ] Error recovery paths defined
- [ ] Feedback mechanisms included

**Visuals:**
- [ ] Flowcharts or wireframes for each flow
- [ ] Key screens visualized
- [ ] Annotations clear and readable
- [ ] Professional appearance

**Usability:**
- [ ] Flows make sense to others
- [ ] No missing steps
- [ ] Branching logic clear
- [ ] Edge cases handled

**Portfolio Ready:**
- [ ] Presentable in interviews
- [ ] Demonstrates UX thinking
- [ ] Shows attention to detail
- [ ] PDF/image exports ready

---

## Flow Documentation Template

Use this structure for each flow:

```markdown
# Flow [Number]: [Flow Name]

## Overview
- **User Goal:** [What they're trying to accomplish]
- **Preconditions:** [Starting state]
- **Success Criteria:** [How we know it worked]
- **Frequency:** [How often this happens - common/occasional/rare]

## Flow Diagram
[Insert visual flowchart or swimlane diagram]

## Step-by-Step

| Step | Actor | Action | UI State | Duration | Notes |
|------|-------|--------|----------|----------|-------|
| 1 | | | | | |
| 2 | | | | | |
[... continue ...]

## Key Screens

### Screen 1: [Name]
[Wireframe or screenshot]

**Elements:**
- [UI element 1]
- [UI element 2]

**User Actions Available:**
- [Action 1]
- [Action 2]

### Screen 2: [Name]
[Wireframe or screenshot]

## Alternative Paths

**Alt Path 1:** If [condition]
- [What happens differently]

**Alt Path 2:** If [condition]
- [What happens differently]

## Error Handling

**Error 1:** [Error type]
- **Cause:** [What triggers it]
- **Message:** "[Exact error message]"
- **Recovery:** [How user recovers]

## Success Metrics
- [ ] Task completion rate: [Target]
- [ ] Time to complete: [Target]
- [ ] User satisfaction: [Target]
- [ ] Error rate: [Target]

## Notes
- [Any special considerations]
- [Technical constraints]
- [Future improvements]
```

---

## Quick Start: Your First Flow

**Don't overthink it! Start simple:**

1. **Pick your main use case** (5 min)
2. **Write out steps** like a recipe (15 min)
3. **Draw simple boxes and arrows** (15 min)
4. **Add UI details** to each step (15 min)
5. **Review for gaps** (10 min)

**Total time: 1 hour for first flow**

**Then repeat** for other flows (faster each time)

---

## Example: Complete Flow for Reference

See below for a fully worked example you can use as reference:

---

### Example Flow: Generate Code Documentation (Happy Path)

## Overview
- **User Goal:** Generate documentation for a Python function
- **Preconditions:** User is logged in, has Python code ready
- **Success Criteria:** User receives accurate documentation and accepts it
- **Frequency:** Very common (primary use case)

## Flow Diagram

```
   START
     ↓
┌──────────────┐
│ Main Screen  │
└──────┬───────┘
       ↓ (Click "Generate Docs")
┌──────────────┐
│ Input Screen │
│ - Code editor│
│ - Language   │
│ - [Generate] │
└──────┬───────┘
       ↓ (Click Generate)
┌──────────────┐
│  Validation  │
└──────┬───────┘
       ↓ (Valid)
┌──────────────┐
│ AI Processing│
│  "Analyzing" │
│   🤖 ⏱️      │
└──────┬───────┘
       ↓ (10-30 sec)
┌──────────────┐
│Preview Result│
│ Documentation│
│ [Edit][Accept]│
└──────┬───────┘
       ↓ (Click Accept)
┌──────────────┐
│   Success!   │
│      🎉      │
└──────────────┘
     ↓
    END
```

## Step-by-Step

| Step | Actor | Action | UI State | Duration | Notes |
|------|-------|--------|----------|----------|-------|
| 1 | User | Navigates to product | Dashboard visible | - | Entry point |
| 2 | User | Clicks "Generate Documentation" | Button highlighted on hover | - | Primary CTA |
| 3 | System | Navigates to input screen | Code editor loads | 1s | Smooth transition |
| 4 | User | Pastes Python function (200 lines) | Code visible with syntax highlighting | - | Copy/paste |
| 5 | System | Auto-detects language as Python | Dropdown shows "Python" | Instant | Smart detection |
| 6 | User | Reviews settings (default is fine) | Settings panel visible | 5s | Optional step |
| 7 | User | Clicks "Generate" button | Button→ loading state | - | Initiates process |
| 8 | System | Validates input (checks length, syntax) | Backend validation | <1s | Error prevention |
| 9 | System | Shows loading screen | Spinner + "Analyzing code..." | - | User feedback |
| 10 | AI | Processes code via GPT-4 | Background LLM call | 10-30s | Main AI work |
| 11 | AI | Generates documentation | JSON response | <1s | Fast parsing |
| 12 | System | Displays result in preview pane | Split view: code │ docs | <1s | Clean presentation |
| 13 | System | Shows confidence: ✅ "High" | Badge at top of docs | - | Transparency |
| 14 | User | Reads generated documentation | Scrollable preview | 30-60s | Quality review |
| 15 | User | Satisfied with quality | No edits needed | - | Happy path |
| 16 | User | Clicks "Accept" button | Button enabled | - | Final action |
| 17 | System | Saves documentation to database | Loading briefly | 2s | Persistence |
| 18 | System | Shows success message + confetti | Modal overlay | 3s | Celebration |
| 19 | System | Returns to dashboard with saved doc | Dashboard + new item | - | Complete |

## Key Screens

### Screen 1: Input Screen
```
┌──────────────────────────────────────────┐
│ CodeDocAI                         [User] │
├──────────────────────────────────────────┤
│                                          │
│  Generate Documentation                  │
│  ──────────────────────                  │
│                                          │
│  Paste your code:                        │
│  ┌────────────────────────────────────┐ │
│  │ def calculate_total(items,         │ │
│  │                    tax_rate=0.08): │ │
│  │     """TODO: Add documentation"""  │ │
│  │     ...                            │ │
│  │                                    │ │
│  └────────────────────────────────────┘ │
│                                          │
│  Language: [Python ▼]                   │
│                                          │
│  Style: [Auto-detect ▼]                 │
│                                          │
│  [Generate Documentation]                │
│                                          │
└──────────────────────────────────────────┘
```

### Screen 2: Processing Screen
```
┌──────────────────────────────────────────┐
│ CodeDocAI                         [User] │
├──────────────────────────────────────────┤
│                                          │
│            🤖                            │
│                                          │
│     Analyzing your code...               │
│                                          │
│     This may take 10-30 seconds          │
│                                          │
│     ▓▓▓▓▓▓▓░░░░░░░░ 45%                 │
│                                          │
│                                          │
│            [Cancel]                      │
│                                          │
└──────────────────────────────────────────┘
```

### Screen 3: Preview Screen
```
┌──────────────────────────────────────────┐
│ CodeDocAI                         [User] │
├──────────────────────────────────────────┤
│                                          │
│  ✅ High Confidence                      │
│  ────────────────────────────────────    │
│                                          │
│  ## calculate_total                      │
│                                          │
│  Calculates the total cost including tax│
│                                          │
│  **Parameters:**                         │
│  - items (list): List of item prices    │
│  - tax_rate (float): Tax rate (default  │
│    0.08)                                 │
│                                          │
│  **Returns:**                            │
│  - float: Total cost with tax           │
│                                          │
│  **Example:**                            │
│  ```python                               │
│  total = calculate_total([10, 20], 0.1) │
│  # Returns: 33.0                         │
│  ```                                     │
│                                          │
│  [✏️ Edit]  [❌ Reject]  [✅ Accept]    │
│                                          │
└──────────────────────────────────────────┘
```

---

**Now create your flows! Start with the happy path, then build from there. 🎨**
