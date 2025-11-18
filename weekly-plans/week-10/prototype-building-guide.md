# AI Product Prototype Building Guide

**Purpose:** Build a working, demo-able AI prototype for your portfolio project

**Time Required:** 8-12 hours (Days 3-4 of Week 10)

**Output:** Functional AI prototype you can confidently demonstrate

---

## Table of Contents

1. [Prototyping Philosophy](#prototyping-philosophy)
2. [Choosing Your Approach](#choosing-your-approach)
3. [Method 1: Custom GPT (ChatGPT Plus)](#method-1-custom-gpt-chatgpt-plus)
4. [Method 2: Claude Project](#method-2-claude-project)
5. [Method 3: API Integration with UI](#method-3-api-integration-with-ui)
6. [Method 4: No-Code Tools](#method-4-no-code-tools)
7. [Prompt Engineering Essentials](#prompt-engineering-essentials)
8. [Building Your Prototype Step-by-Step](#building-your-prototype-step-by-step)
9. [Testing & Iteration](#testing--iteration)
10. [Documentation](#documentation)
11. [Common Pitfalls](#common-pitfalls)

---

## Prototyping Philosophy

### What is a "Prototype" for Your Portfolio?

**Portfolio Prototype ≠ Production System**

**It IS:**
- ✅ Proof of concept demonstrating core AI capability
- ✅ Interactive demo showing value proposition
- ✅ Test bed for validating product assumptions
- ✅ Conversation starter for interviews

**It is NOT:**
- ❌ Fully engineered production system
- ❌ Scaled for thousands of users
- ❌ Error-free or handling all edge cases
- ❌ Optimized for performance and cost

---

### Success Criteria for Your Prototype

**Minimum Bar:**
- [ ] **Functional:** Core workflow works end-to-end
- [ ] **Demo-able:** Can show in 5 minutes
- [ ] **Impressive:** Shows AI capability clearly
- [ ] **Explainable:** You can explain how it works

**Ideal State:**
- [ ] **Polished:** Professional-looking interface
- [ ] **Tested:** Works with real users
- [ ] **Documented:** Prompts and design decisions captured
- [ ] **Shareable:** Can send link to interviewers

---

### Time Management

**You have ~8-12 hours total (Days 3-4)**

**Allocate:**
- 2 hours: Setup and initial implementation
- 3 hours: Core feature development
- 2 hours: Testing and refinement
- 2 hours: User testing
- 1-2 hours: Documentation and polish

**If running short on time:**
- Cut features, not quality
- Mock complex integrations
- Focus on demo-ability
- Simplify UI (functionality > aesthetics)

---

## Choosing Your Approach

### Decision Matrix

| Approach | Pros | Cons | Best For | Time |
|----------|------|------|----------|------|
| **Custom GPT** | No coding, fast, shareable | Limited control, ChatGPT Plus required ($20) | Conversational AI products | 4-6 hrs |
| **Claude Project** | No coding, excellent quality, free | Less shareable | Document/knowledge work | 3-5 hrs |
| **API + UI** | Full control, professional | Requires coding | Technical backgrounds | 8-12 hrs |
| **No-Code** | Visual, fast | Limited AI customization | Simple workflows | 6-8 hrs |

---

### Choose Based On:

**Your Product Type:**
- **Conversational AI** (chatbot, assistant) → Custom GPT or Claude Project
- **RAG/Knowledge Base** → Claude Project or API + LangChain
- **Complex Workflows** → API + UI or No-Code
- **Creative AI** (content generation) → Custom GPT or API

**Your Skills:**
- **Non-technical** → Custom GPT, Claude Project, or No-Code
- **Some coding** → API + Streamlit
- **Strong coding** → API + Custom UI

**Your Time:**
- **4-6 hours** → Custom GPT or Claude Project
- **8-12 hours** → API + UI or No-Code

**Your Budget:**
- **$0** → Claude Project, API free tiers, open-source
- **$20-50** → Custom GPT + API credits
- **$50-100** → Premium APIs, no-code tools

---

## Method 1: Custom GPT (ChatGPT Plus)

### Overview

**What:** Build a custom version of ChatGPT with specific instructions and knowledge

**Requirements:**
- ChatGPT Plus subscription ($20/month)
- No coding required
- ~4-6 hours to build

**Best For:**
- Conversational AI products
- Advisory/coaching assistants
- Content generation tools
- Knowledge Q&A

---

### Step-by-Step Instructions

#### Step 1: Plan Your GPT (30 minutes)

**Define:**

1. **Name:** [Your product name]
2. **Description:** [One sentence what it does]
3. **Instructions:** [How it should behave]
4. **Conversation Starters:** [4-5 prompts to guide users]
5. **Knowledge Files:** [Documents to upload, if any]
6. **Capabilities Needed:**
   - [ ] Web browsing
   - [ ] DALL-E image generation
   - [ ] Code interpreter
   - [ ] File uploads

---

#### Step 2: Create Custom GPT (1 hour)

**In ChatGPT:**

1. Click your profile → "My GPTs" → "Create"

2. **Configure Tab:**

   **Name:** [Your product name]

   **Description:**
   ```
   [Write a clear, concise description of what your GPT does and who it's for]
   ```

   **Instructions:**
   ```
   You are [role/persona]. Your goal is to [core objective].

   ## Your Capabilities
   - [Capability 1]
   - [Capability 2]
   - [Capability 3]

   ## How You Work
   1. [Step 1 of your process]
   2. [Step 2 of your process]
   3. [Step 3 of your process]

   ## Tone and Style
   - [How you communicate]
   - [What makes you unique]

   ## Safety and Guardrails
   - Do not [restriction 1]
   - Always [requirement 1]
   - If [condition], then [action]

   ## Output Format
   [How you structure responses]
   ```

   **Conversation Starters:**
   ```
   1. [Starter that shows core use case]
   2. [Starter that shows different angle]
   3. [Starter for advanced user]
   4. [Starter for beginner]
   ```

3. **Upload Knowledge (if RAG-based):**
   - Upload PDFs, text files, or documents
   - GPT will use these as context
   - Limit: 10 files, 512MB total

4. **Enable Capabilities:**
   - Check boxes for needed features
   - Most AI products need "Web Browsing" off for consistency

5. **Save and Test**

---

#### Step 3: Test and Iterate (2-3 hours)

**Testing Process:**

1. **Happy Path Test:**
   - Try the main use case
   - Does it work as intended?
   - Is output quality good?

2. **Edge Case Test:**
   - Try unusual inputs
   - Test boundaries
   - See how it handles errors

3. **User Test:**
   - Share with 3-5 people
   - Give them scenarios (don't lead them)
   - Observe and take notes

4. **Iterate:**
   - Refine instructions based on failures
   - Add examples to instructions
   - Adjust tone/style
   - Add more guardrails

**Iteration Loop:**
```
Test → Identify Issue → Update Instructions → Test Again
```

Expect 5-10 iterations to get it right.

---

#### Step 4: Polish (30 minutes)

**Make it professional:**

1. **Add a Profile Picture:**
   - Use DALL-E to generate custom icon
   - Or use branded image

2. **Refine Description:**
   - Clear value proposition
   - Who it's for
   - What makes it unique

3. **Perfect Conversation Starters:**
   - Make them enticing
   - Cover different use cases
   - Be specific, not generic

4. **Test Sharing:**
   - Get shareable link
   - Test in incognito browser
   - Ensure it works for others

---

### Custom GPT Example

**Product:** "CodeDocAI - Documentation Generator"

**Name:** CodeDocAI

**Description:**
"AI assistant that generates high-quality code documentation. Paste your code and get comprehensive docs in seconds."

**Instructions:**
```
You are CodeDocAI, an expert technical writer specializing in code documentation.

## Your Purpose
Help developers create clear, comprehensive documentation for their code.

## How You Work
1. Analyze the code provided
2. Understand its purpose and structure
3. Generate documentation including:
   - Overview/summary
   - Parameters and return values
   - Usage examples
   - Edge cases and notes

## Documentation Style
- Clear and concise
- Follow language-specific conventions (JSDoc, docstrings, etc.)
- Include practical examples
- Explain the "why" not just the "what"

## Output Format
Always use this structure:
1. **Summary:** One-line description
2. **Parameters:** List all inputs
3. **Returns:** What it outputs
4. **Example:** Code snippet showing usage
5. **Notes:** Edge cases, warnings, tips

## Safety
- Never execute the code (just document it)
- If code appears malicious, warn the user
- If you can't understand the code, ask for clarification

## Tone
Professional but friendly. You're a helpful colleague, not a robot.
```

**Conversation Starters:**
1. "Document this Python function for me"
2. "Generate docs for my React component"
3. "Create API documentation for this endpoint"
4. "Help me write docs for this class"

---

### Sharing Your Custom GPT

**Options:**

1. **Public Link:**
   - Anyone with link can use (don't need ChatGPT Plus)
   - Great for portfolio
   - Get analytics on usage

2. **Embed in Portfolio:**
   - Add link to your portfolio site
   - Include screenshots
   - Demo in video

3. **Demo in Interview:**
   - Share screen and use live
   - Prepare scenarios
   - Have backup if API is down

---

## Method 2: Claude Project

### Overview

**What:** Use Claude Projects feature to create a custom AI assistant with context

**Requirements:**
- Claude account (free)
- No coding required
- ~3-5 hours to build

**Best For:**
- Document analysis
- Knowledge work
- Long-form content
- Complex reasoning tasks

---

### Step-by-Step Instructions

#### Step 1: Create Project (15 minutes)

1. Go to claude.ai
2. Create new Project
3. Name it [Your Product Name]
4. Write project description

---

#### Step 2: Add Project Knowledge (30 minutes)

**Upload Files:**
- Documentation
- Examples
- Style guides
- Reference materials

**Limit:** 5 files per project (free tier)

**Types:** PDF, TXT, CSV, code files

---

#### Step 3: Write Custom Instructions (1 hour)

**Project Instructions:**

```markdown
# [Your Product Name]

## Role
You are [role description]

## Objective
[What you help users accomplish]

## Process
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Output Format
[How you structure responses]

## Constraints
- [Limit 1]
- [Limit 2]

## Examples
[Show 2-3 examples of ideal interactions]
```

---

#### Step 4: Test and Iterate (2-3 hours)

**Same process as Custom GPT:**
- Test workflows
- Find edge cases
- Get user feedback
- Refine instructions

---

#### Step 5: Document (30 minutes)

**Create Usage Guide:**
- How to use your Claude Project
- Sample prompts
- Expected outputs
- Limitations

**For Portfolio:**
- Screenshots of interface
- Examples of conversations
- Video walkthrough
- Explain how it demonstrates AI PM skills

---

## Method 3: API Integration with UI

### Overview

**What:** Build custom application using LLM APIs (OpenAI, Anthropic, etc.) with your own interface

**Requirements:**
- Coding skills (Python or JavaScript)
- API keys and budget ($20-50)
- ~8-12 hours to build

**Best For:**
- Complex workflows
- Custom UX
- RAG implementations
- Multi-step processes

---

### Technology Stack Options

#### Option A: Python + Streamlit (Easiest)

**Stack:**
- **Backend:** Python
- **LLM:** OpenAI API or Anthropic
- **Framework:** LangChain (optional)
- **UI:** Streamlit
- **Time:** 6-8 hours

**Pros:**
- Fastest way to build with code
- Built-in UI components
- Easy deployment (Streamlit Cloud)

**Cons:**
- Limited UI customization
- Streamlit-specific quirks

---

#### Option B: Python + FastAPI + React (Professional)

**Stack:**
- **Backend:** FastAPI
- **LLM:** OpenAI/Anthropic
- **Framework:** LangChain
- **Frontend:** React or Next.js
- **Time:** 12-16 hours

**Pros:**
- Full control
- Production-quality
- Impressive in interviews

**Cons:**
- More time
- More complexity
- Need frontend skills

---

#### Option C: Node.js + Express + Simple HTML

**Stack:**
- **Backend:** Node.js + Express
- **LLM:** OpenAI/Anthropic SDK
- **Frontend:** HTML/CSS/JavaScript
- **Time:** 8-10 hours

**Pros:**
- Good balance
- Single language (JavaScript)
- Easier than React

**Cons:**
- Less polished than React
- Node.js ecosystem can be complex

---

### Step-by-Step: Streamlit Prototype

#### Step 1: Setup (30 minutes)

```bash
# Create project directory
mkdir my-ai-prototype
cd my-ai-prototype

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install streamlit openai langchain python-dotenv

# Create project structure
touch app.py .env requirements.txt
```

**requirements.txt:**
```
streamlit==1.28.0
openai==1.3.0
langchain==0.0.340
python-dotenv==1.0.0
```

**.env:**
```
OPENAI_API_KEY=your-api-key-here
```

---

#### Step 2: Build Core Logic (2-3 hours)

**app.py:**

```python
import streamlit as st
import openai
from dotenv import load_dotenv
import os

# Load environment variables
load_dotenv()
openai.api_key = os.getenv("OPENAI_API_KEY")

# Page config
st.set_page_config(
    page_title="Your Product Name",
    page_icon="🤖",
    layout="wide"
)

# Title and description
st.title("🤖 Your Product Name")
st.write("Your value proposition in one sentence")

# Sidebar for settings (optional)
with st.sidebar:
    st.header("Settings")
    temperature = st.slider("Creativity", 0.0, 1.0, 0.7)
    max_tokens = st.slider("Response Length", 100, 2000, 500)

# Main interface
st.header("Your Main Feature")

# User input
user_input = st.text_area(
    "Enter your input:",
    height=150,
    placeholder="Paste your code, text, or question here..."
)

# Generate button
if st.button("Generate", type="primary"):
    if not user_input:
        st.error("Please provide input")
    else:
        with st.spinner("AI is working..."):
            try:
                # Call OpenAI API
                response = openai.ChatCompletion.create(
                    model="gpt-4-turbo-preview",
                    messages=[
                        {
                            "role": "system",
                            "content": "Your system prompt here"
                        },
                        {
                            "role": "user",
                            "content": user_input
                        }
                    ],
                    temperature=temperature,
                    max_tokens=max_tokens
                )

                # Display result
                result = response.choices[0].message.content
                st.success("✅ Generated!")
                st.markdown(result)

                # Option to copy
                st.code(result, language="markdown")

            except Exception as e:
                st.error(f"Error: {str(e)}")

# Examples section
with st.expander("📝 See Examples"):
    st.write("Example 1: [Description]")
    st.code("Example input", language="python")
    st.write("Example 2: [Description]")
    st.code("Example input", language="python")
```

---

#### Step 3: Add RAG (if needed) (2-3 hours)

**For knowledge-based products:**

```python
from langchain.embeddings import OpenAIEmbeddings
from langchain.vectorstores import Chroma
from langchain.text_splitter import CharacterTextSplitter
from langchain.docum import Document

# Load and process documents
def load_knowledge_base():
    # Load your documents
    with open("knowledge.txt", "r") as f:
        text = f.read()

    # Split into chunks
    text_splitter = CharacterTextSplitter(
        chunk_size=1000,
        chunk_overlap=200
    )
    chunks = text_splitter.split_text(text)

    # Create documents
    docs = [Document(page_content=chunk) for chunk in chunks]

    # Create embeddings and vector store
    embeddings = OpenAIEmbeddings()
    vectorstore = Chroma.from_documents(docs, embeddings)

    return vectorstore

# Add to your app
vectorstore = load_knowledge_base()

# When user asks question:
def generate_with_rag(question):
    # Retrieve relevant docs
    relevant_docs = vectorstore.similarity_search(question, k=3)
    context = "\n\n".join([doc.page_content for doc in relevant_docs])

    # Create prompt with context
    prompt = f"""Context:
{context}

Question: {question}

Answer based on the context provided:"""

    # Call LLM
    response = openai.ChatCompletion.create(...)
    return response
```

---

#### Step 4: Polish UI (1 hour)

**Add these elements:**

```python
# Custom CSS
st.markdown("""
<style>
    .stButton>button {
        width: 100%;
        background-color: #4CAF50;
        color: white;
    }
    .stTextArea textarea {
        font-family: monospace;
    }
</style>
""", unsafe_allow_html=True)

# Metrics display
col1, col2, col3 = st.columns(3)
with col1:
    st.metric("Generations", 42)
with col2:
    st.metric("Avg Quality", "4.2/5")
with col3:
    st.metric("Time Saved", "3.5 hrs")

# Feedback mechanism
feedback = st.radio(
    "Was this helpful?",
    ["👍 Yes", "👎 No", "🤔 Somewhat"]
)
if feedback == "👎 No":
    st.text_area("Tell us what went wrong")
```

---

#### Step 5: Deploy (1 hour)

**Streamlit Cloud (Free):**

1. Push code to GitHub
2. Go to share.streamlit.io
3. Connect GitHub repo
4. Deploy!
5. Get public URL

**Add secrets in Streamlit Cloud:**
- Settings → Secrets
- Add your API keys

---

## Method 4: No-Code Tools

### Overview

**What:** Use no-code AI builders like Voiceflow, Landbot, FlowiseAI

**Requirements:**
- No coding required
- Free tiers available
- ~6-8 hours to build

**Best For:**
- Conversational flows
- Simple workflows
- Quick prototypes

---

### Recommended Tools

| Tool | Best For | Free Tier | Ease |
|------|----------|-----------|------|
| **Voiceflow** | Chatbots, assistants | Yes | ⭐⭐⭐⭐ |
| **Landbot** | Lead gen, surveys | Limited | ⭐⭐⭐⭐⭐ |
| **FlowiseAI** | LangChain flows | Yes | ⭐⭐⭐ |
| **Bubble** | Full web apps | Yes | ⭐⭐⭐ |
| **Make/Zapier** | Automations | Yes | ⭐⭐⭐⭐⭐ |

---

### Step-by-Step: Voiceflow

#### Step 1: Create Project (15 min)

1. Go to voiceflow.com
2. Create account
3. New project → "Custom Assistant"
4. Choose template or start blank

#### Step 2: Design Conversation Flow (2 hours)

**Use Visual Builder:**

1. **Start Block:** Welcome message
2. **Capture Block:** Get user input
3. **API Block:** Call OpenAI/Anthropic
4. **Response Block:** Show result
5. **Choice Block:** Branch logic

**Example Flow:**
```
[Start] → "Hi! I'm [Product Name]"
   ↓
[Capture] → "What would you like help with?"
   ↓
[API Call] → OpenAI GPT-4
   ↓
[Response] → Show AI response
   ↓
[Choice] → "Continue?" Yes/No
```

#### Step 3: Configure AI Integration (1 hour)

**In API Block:**
- Method: POST
- URL: https://api.openai.com/v1/chat/completions
- Headers: Authorization: Bearer {API_KEY}
- Body:
```json
{
  "model": "gpt-4",
  "messages": [
    {"role": "system", "content": "Your system prompt"},
    {"role": "user", "content": "{user_input}"}
  ]
}
```
- Map response to variable

#### Step 4: Test and Iterate (2-3 hours)

- Use built-in debugger
- Test all paths
- Refine responses
- Add error handling

#### Step 5: Publish (30 min)

- Deploy to web
- Get embed code
- Add to portfolio site

---

## Prompt Engineering Essentials

### System Prompt Structure

**Template:**

```
You are [ROLE] with [EXPERTISE].

Your purpose is to [OBJECTIVE].

Follow these guidelines:
1. [Guideline 1]
2. [Guideline 2]
3. [Guideline 3]

Output format:
[Describe structure]

Constraints:
- Do NOT [restriction]
- ALWAYS [requirement]

If [edge case], then [handling].

Tone: [Description]
```

---

### Example: Documentation AI

```
You are an expert technical writer with 10+ years documenting software.

Your purpose is to generate clear, comprehensive code documentation that helps developers understand and use code effectively.

Follow these guidelines:
1. Analyze code structure before writing
2. Explain the "why" not just the "what"
3. Include practical examples
4. Highlight edge cases and gotchas
5. Use the programming language's documentation conventions

Output format:
## Summary
[One-line description]

## Parameters
- param1: [type] - [description]
- param2: [type] - [description]

## Returns
[type] - [description]

## Example
```[language]
[Code example]
```

## Notes
- [Important consideration 1]
- [Important consideration 2]

Constraints:
- Do NOT execute or run code
- ALWAYS validate code syntax before documenting
- If code is unclear, ask clarifying questions

If code appears malicious, warn the user and refuse to document.

Tone: Professional but approachable, like a helpful colleague.
```

---

### Few-Shot Prompting

**When to use:** Complex or specific output formats

**Structure:**

```
Here are examples of ideal interactions:

Example 1:
User: [Input]
Assistant: [Ideal output]

Example 2:
User: [Input]
Assistant: [Ideal output]

Example 3:
User: [Input]
Assistant: [Ideal output]

Now handle this:
User: {actual_user_input}
```

---

## Building Your Prototype Step-by-Step

### Day 3 Morning (2-3 hours)

**Goal:** Get basic working version

**Tasks:**
1. [ ] Setup development environment
2. [ ] Create initial system prompt
3. [ ] Implement main user flow
4. [ ] Test with 3-5 scenarios
5. [ ] Document what works and doesn't

**Success:** You can complete one full interaction

---

### Day 3 Evening (2-3 hours)

**Goal:** Add depth and handle edge cases

**Tasks:**
1. [ ] Refine prompts based on testing
2. [ ] Add error handling
3. [ ] Implement guardrails
4. [ ] Test 10+ edge cases from PRD
5. [ ] Add personality/tone
6. [ ] Document prompt engineering decisions

**Success:** Prototype handles most common scenarios gracefully

---

### Day 4 Morning (2-3 hours)

**Goal:** Advanced features and polish

**Tasks:**
1. [ ] Multi-turn conversations (if applicable)
2. [ ] Context management
3. [ ] Output formatting
4. [ ] Citations/sources (if applicable)
5. [ ] Polish the experience
6. [ ] Prepare demo scenarios

**Success:** Prototype feels professional and complete

---

### Day 4 Evening (2-3 hours)

**Goal:** User testing and iteration

**Tasks:**
1. [ ] Recruit 5-7 test users
2. [ ] Give them scenarios (don't lead them)
3. [ ] Observe and document:
   - What works well
   - What confuses users
   - Where AI fails
   - Unexpected uses
   - Feedback and suggestions
4. [ ] Iterate based on findings
5. [ ] Final polish

**Success:** Real users can successfully use your prototype

---

## Testing & Iteration

### Test Plan

**Test 1: Happy Path**
- Input: [Ideal use case]
- Expected: [Perfect result]
- Actual: [What happened]
- Pass/Fail: [ ]

**Test 2: Edge Case**
- Input: [Unusual input]
- Expected: [Graceful handling]
- Actual: [What happened]
- Pass/Fail: [ ]

[Create 15-20 test cases]

---

### Iteration Checklist

After each test round:

- [ ] Document failures
- [ ] Identify patterns in failures
- [ ] Adjust system prompt
- [ ] Add few-shot examples if needed
- [ ] Improve error messages
- [ ] Re-test same scenarios
- [ ] Verify fixes don't break other things

**Expect 5-10 iteration cycles.**

---

### User Testing Guide

**What to say:**

"I built an AI tool for [problem]. I'd love your feedback. I'll give you a scenario, and you try to use the tool. Think out loud as you go. There are no wrong answers - if something confuses you, that's valuable feedback!"

**Scenarios to give:**

1. [Main use case]
2. [Secondary use case]
3. [Edge case]
4. [Open-ended: "Use it however you think makes sense"]

**What to observe:**

- Where do they hesitate?
- What confuses them?
- What delights them?
- Where does AI fail?
- What unexpected uses do they try?

**What to ask:**

- "What was unclear?"
- "What would you change?"
- "Would you use this? Why or why not?"
- "What's missing?"

---

## Documentation

### What to Document

**For Your Portfolio:**

1. **README:**
   - What the prototype does
   - How to use it
   - Demo scenarios
   - Known limitations

2. **Prompt Library:**
   - System prompts used
   - User prompt templates
   - Few-shot examples
   - Why you made certain choices

3. **Test Results:**
   - Test scenarios
   - Pass/fail rates
   - User feedback summary
   - Iteration history

4. **Technical Notes:**
   - Architecture decisions
   - API choices
   - Cost estimates
   - Performance benchmarks

---

### README Template

```markdown
# [Product Name] - Prototype

## What It Does

[2-3 sentence description]

## Demo

[Link to live demo or video]

## How to Use

1. [Step 1]
2. [Step 2]
3. [Step 3]

## Example Scenarios

### Scenario 1: [Name]
**Input:** [What to enter]
**Expected Output:** [What you'll see]

### Scenario 2: [Name]
**Input:** [What to enter]
**Expected Output:** [What you'll see]

## Technical Details

- **LLM:** [Model used]
- **Framework:** [If applicable]
- **Cost:** [Estimate per interaction]
- **Latency:** [Typical response time]

## Limitations

- [Limitation 1]
- [Limitation 2]
- [Limitation 3]

## Next Steps (Post-MVP)

- [Feature to add]
- [Improvement to make]
- [Issue to fix]

## About This Prototype

Built as part of AI PM portfolio project. Demonstrates [skills shown].
```

---

## Common Pitfalls

### Pitfall 1: Over-Engineering

**Symptom:** Spending too much time on features that don't matter for demo

**Solution:**
- Focus on core workflow
- Mock complex integrations
- Prioritize demo-ability over completeness
- Cut features ruthlessly

---

### Pitfall 2: Prompt Too Vague

**Symptom:** AI outputs are inconsistent or off-target

**Solution:**
- Be very specific in system prompt
- Add examples of ideal outputs
- Use structured output formats
- Test with diverse inputs

---

### Pitfall 3: No Error Handling

**Symptom:** Prototype breaks on unexpected inputs

**Solution:**
- Anticipate common errors
- Add input validation
- Provide helpful error messages
- Always have fallback behavior

---

### Pitfall 4: Ignoring User Feedback

**Symptom:** Users struggle but you don't iterate

**Solution:**
- Actually watch people use it
- Ask for honest feedback
- Fix what confuses people
- Test again after changes

---

### Pitfall 5: Not Demo-Ready

**Symptom:** Prototype works but can't demonstrate it well

**Solution:**
- Prepare 3-5 demo scenarios
- Practice walking through
- Have backup plan if API fails
- Screenshots/video as fallback

---

## Pre-Launch Checklist

Before moving to Week 11:

- [ ] Prototype completes main workflow end-to-end
- [ ] Tested with 5+ real users
- [ ] Error handling for common issues
- [ ] Demo scenarios prepared and practiced
- [ ] All prompts documented
- [ ] README written
- [ ] Known limitations documented
- [ ] Can explain all technical decisions
- [ ] Shareable (link or deployable)
- [ ] Screenshots/video captured

---

**Your prototype is your proof. Make it work, make it demo-able, make it impressive! 🚀**
