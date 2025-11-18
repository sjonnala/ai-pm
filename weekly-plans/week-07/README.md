# Week 7: AI-Native UX Design

## 🎯 Week Overview

**Focus Areas:**
- AI-native UX patterns and best practices
- Multimodal interfaces (text, voice, image, video)
- Conversational UI design
- Safety, transparency, and control patterns
- Redesigning existing products for AI-first experiences

**Deliverables:**
- AI-native UX pattern library
- Redesigned AI-first flow for an existing app
- Safety & guardrail design document

## 🧠 Deep Dive Resources

- [Conversational & Multimodal UX Deep Dive](./conversational-ux-deep-dive.md) — conversation personas, multimodal component patterns, guardrail UI guidance, and quality rubrics.

---

## 📚 Learning Objectives

By the end of this week, you will:

1. ✅ Master AI-native UX design patterns
2. ✅ Design multimodal experiences
3. ✅ Create conversational interfaces
4. ✅ Implement safety and control mechanisms
5. ✅ Redesign traditional products for AI-first experiences

---

## 🗓️ Daily Breakdown

### **Day 1 (Monday): AI UX Fundamentals**

**Morning Session (2 hours)**
- **Topic:** AI-Native vs. AI-Added UX
- **Learning:**
  - What makes UX "AI-native"?
  - Differences from traditional UX
  - Key design considerations:
    - Probabilistic vs. deterministic
    - Non-transparent internal logic
    - Continuous learning and change
    - Variable quality
  - Design principles for AI:
    - Set appropriate expectations
    - Show confidence levels
    - Provide explanations
    - Allow control and override
    - Design for failure
- **Resources:**
  - 📖 [Google - People + AI Guidebook](https://pair.withgoogle.com/) ⭐ MUST READ
  - 📖 [Microsoft - HAX Toolkit](https://www.microsoft.com/en-us/haxtoolkit/) ⭐
  - 📖 [Apple - HIG for ML](https://developer.apple.com/design/human-interface-guidelines/machine-learning)
  - 📖 [Nielsen Norman - AI UX](https://www.nngroup.com/articles/ai-paradigm/)

**Evening Session (2 hours)**
- **Activity:** Analyze AI Product UX
- **Study 5 AI products:**
  1. **Notion AI** - Copilot pattern
  2. **ChatGPT** - Conversational pattern
  3. **Midjourney** - Generative pattern
  4. **Grammarly** - Real-time augmentation
  5. **GitHub Copilot** - Code completion

**For each, document:**
- How do they show AI confidence?
- How do users control AI behavior?
- How are errors handled?
- What makes it "AI-native"?
- What could be improved?

**Interview Prep:**
- "How do you design for AI products?"
- "What makes AI UX different?"

---

### **Day 2 (Tuesday): AI Interaction Patterns**

**Morning Session (2 hours)**
- **Topic:** Core AI Interaction Patterns
- **Learn patterns:**

  **1. Autocomplete / Copilot**
  - AI suggests, user accepts/rejects
  - Example: GitHub Copilot, Gmail Smart Compose
  - When to use: High-frequency tasks, clear right answers

  **2. Conversational**
  - Chat-based interaction
  - Example: ChatGPT, customer service bots
  - When to use: Complex tasks, open-ended queries

  **3. Generative**
  - AI creates content from prompts
  - Example: Midjourney, DALL-E
  - When to use: Creative tasks, ideation

  **4. Recommendation**
  - AI suggests options
  - Example: Netflix, Spotify
  - When to use: Choice overload, personalization

  **5. Classification / Analysis**
  - AI categorizes or analyzes input
  - Example: Email filtering, sentiment analysis
  - When to use: Large volumes, pattern recognition

  **6. Agentic**
  - AI acts autonomously
  - Example: Calendar scheduling, automated workflows
  - When to use: Delegatable tasks, clear goals

- **Resources:**
  - 📖 [a16z - LLM App Architectures](https://a16z.com/emerging-architectures-for-llm-applications/)
  - 📖 [Lenny's Newsletter - AI UX Patterns](https://www.lennysnewsletter.com/)

**Evening Session (2 hours)**
- **Activity:** Pattern Matching Exercise
- **For your AI opportunity:**
  - Which pattern(s) fit best?
  - Why?
  - What are the trade-offs?
  - Sketch 3 different pattern approaches
  - Select the best one

---

### **Day 3 (Wednesday): Multimodal UX**

**Morning Session (2 hours)**
- **Topic:** Designing for Multimodal AI
- **Learning:**
  - **Text:** Prompts, chat, documents
  - **Voice:** Speech input/output, tone, emotions
  - **Image:** Visual input, image generation
  - **Video:** Video understanding, video generation
  - **Combinations:** Text + image, voice + screen, etc.
  - Modal switching (when to use which modality)
  - Accessibility considerations
- **Resources:**
  - 📖 [OpenAI - GPT-4 Vision](https://platform.openai.com/docs/guides/vision)
  - 📖 [Google - Gemini Multimodal](https://deepmind.google/technologies/gemini/)
  - 📖 [ElevenLabs - Voice AI](https://elevenlabs.io/)

**Evening Session (2 hours)**
- **Activity:** Design Multimodal Flow
- **Exercise:**
  - Take your AI opportunity
  - Design user flow using multiple modalities
  - Example: "AI video editor"
    - Voice: "Remove all umms and pauses"
    - Visual: Shows timeline with highlights
    - Text: Fine-tune with text commands
    - Audio: Preview with AI-enhanced audio
  - Document:
    - When each modality is used
    - Why that modality
    - Transition points
    - Fallbacks if modality fails

---

### **Day 4 (Thursday): Transparency, Control & Safety**

**Morning Session (2 hours)**
- **Topic:** Transparency & Explainability
- **Design for understanding:**
  - **Show confidence:** Percentages, visual indicators
  - **Explain reasoning:** "Because you..."
  - **Cite sources:** Links, references
  - **Show alternatives:** Other options AI considered
  - **Visualize uncertainty:** Confidence intervals
- **Examples:**
  - Perplexity: Citations for every claim
  - ChatGPT: "I'm not sure" statements
  - Google Search: "Featured snippet" disclaimers

**Evening Session (2 hours)**
- **Topic:** User Control & Override
- **Design for control:**
  - **Adjustable automation levels:**
    - Manual mode (no AI)
    - Suggest mode (AI proposes)
    - Copilot mode (AI assists)
    - Auto mode (AI acts autonomously)
  - **Edit AI outputs:** Don't make AI final
  - **Provide feedback:** Thumbs up/down, corrections
  - **Undo easily:** Reversible actions
  - **Settings & preferences:** Customize AI behavior

**Activity:**
- Design control mechanisms for your AI opportunity
- Create mode-switching UI
- Document safety guardrails

---

### **Day 5 (Friday): Error States & Failure Design**

**Morning Session (2 hours)**
- **Topic:** Designing for AI Failure
- **Failure modes:**
  - **AI doesn't understand:** Clarification prompts
  - **AI is uncertain:** Show confidence, ask for confirmation
  - **AI makes mistake:** Easy correction, learning from errors
  - **AI is unavailable:** Graceful degradation, fallback UX
  - **AI is inappropriate:** Content filtering, apology, escalation

**Design patterns:**
  - Progressive disclosure (don't overwhelm)
  - Scaffolding (guide users step-by-step)
  - Fallback to human
  - Error prevention > error handling

- **Resources:**
  - 📖 [Google - Error Handling for AI](https://pair.withgoogle.com/chapter/errors-failing/)
  - 📖 [Microsoft - AI Guidelines #15-18](https://www.microsoft.com/en-us/haxtoolkit/ai-guidelines/)

**Evening Session (2 hours)**
- **Activity:** Complete Safety & Guardrail Design
- **Document for your AI opportunity:**
  1. **All potential failure modes**
  2. **Error messages for each**
  3. **Recovery paths**
  4. **When to escalate to human**
  5. **Safety guardrails (content filters, rate limits, etc.)**
  6. **User feedback mechanisms**

**Deliverable:** Safety & guardrail design document

---

### **Day 6-7 (Weekend): Redesign App + Pattern Library**

**Saturday (3-4 hours)**
- **Activity:** Redesign Existing App for AI-First
- **Pick an app you use daily:**
  - Notion
  - Trello
  - Gmail
  - Figma
  - Spotify
  - Your choice

**Redesign exercise:**
1. **Current State:** How does it work today?
2. **AI Opportunities:** Where could AI add value?
3. **Crawl (AI-added):** Augment existing features
4. **Walk (AI-native):** New AI-powered features
5. **Run (AI-first):** Reimagine from scratch for AI
6. **Detailed Flow:** Pick one feature, design complete UX
   - Wireframes or mockups (low-fi is fine!)
   - User flows
   - All states (loading, success, error)
   - Control mechanisms
   - Safety guardrails

**Tools:**
- Figma (figma.com)
- Whimsical (whimsical.com)
- Excalidraw (excalidraw.com)
- Paper and pen!

**Sunday (2 hours)**
- **Activity:** Create AI UX Pattern Library
- **Compile patterns you learned:**
  - **Interaction Patterns:** 6 core patterns (autocomplete, conversational, etc.)
  - **Transparency Patterns:** Confidence, explanations, citations
  - **Control Patterns:** Mode switching, overrides, feedback
  - **Error Patterns:** Failure handling, recovery, escalation
  - **Multimodal Patterns:** When to use which modality

**For each pattern:**
- Name and description
- When to use
- Example products
- Visual sketch
- Pros and cons

**Deliverable:** AI UX Pattern Library (can be markdown with links to screenshots)

- **Reflection:**
  - What surprised you about AI UX design?
  - How is it different from traditional UX?
  - What patterns will you use in your portfolio project?

---

## 📝 Deliverables Checklist

### Required Deliverables:

- [ ] **AI UX Pattern Library** (`ai-ux-patterns.md`)
  - 6 interaction patterns
  - Transparency patterns
  - Control patterns
  - Error handling patterns
  - Multimodal patterns
  - Examples for each

- [ ] **AI-First App Redesign** (`app-redesign/`)
  - Current state analysis
  - Crawl-Walk-Run evolution
  - Detailed flow for one feature
  - Wireframes/mockups
  - All states documented

- [ ] **Safety & Guardrail Design** (`safety-design.md`)
  - Failure modes
  - Error messages
  - Recovery paths
  - Escalation triggers
  - Safety mechanisms

---

## 📖 Recommended Resources

### AI UX Guidelines:
- 📖 [Google - People + AI Guidebook](https://pair.withgoogle.com/) ⭐ MUST READ - Interactive, comprehensive
- 📖 [Microsoft - HAX Toolkit](https://www.microsoft.com/en-us/haxtoolkit/) ⭐ MUST READ - 18 guidelines
- 📖 [Apple - HIG for ML](https://developer.apple.com/design/human-interface-guidelines/machine-learning)
- 📖 [IBM - AI Design](https://www.ibm.com/design/ai/)

### AI Product UX:
- 📖 [Nielsen Norman - AI UX Collection](https://www.nngroup.com/topic/ai-ux/)
- 📖 [Lenny's Newsletter - AI PM Guides](https://www.lennysnewsletter.com/)
- 📖 [a16z - LLM App Patterns](https://a16z.com/emerging-architectures-for-llm-applications/)

### Conversational UI:
- 📖 [Nielsen Norman - Chatbots](https://www.nngroup.com/articles/chatbot-usability/)
- 📖 [Microsoft - Conversational AI Design](https://learn.microsoft.com/en-us/azure/bot-service/bot-service-design-principles)

### Multimodal:
- 📖 [OpenAI - Vision Guide](https://platform.openai.com/docs/guides/vision)
- 📖 [Google - Multimodal Design](https://developers.google.com/learn/pathways/multimodal-design)

### Case Studies:
- 📖 [Notion - Building Notion AI](https://www.notion.so/blog/how-we-built-notion-ai)
- 📖 [GitHub Copilot - Design Decisions](https://github.blog/category/engineering/)
- 📖 [Stripe - AI in Docs](https://stripe.com/blog/ai)

---

## 🎓 Key Concepts to Master

### AI UX Principles:
- **Set Expectations:** Tell users what AI can/can't do
- **Show Confidence:** Indicate certainty levels
- **Explain Decisions:** Make AI reasoning transparent
- **Provide Control:** Users override AI anytime
- **Design for Failure:** Errors will happen, plan for them
- **Continuous Learning:** AI improves with feedback

### Interaction Patterns:
- **Autocomplete/Copilot:** Suggest-accept-reject flow
- **Conversational:** Natural language interaction
- **Generative:** Create from description
- **Recommendation:** Personalized suggestions
- **Classification:** Automated categorization
- **Agentic:** Autonomous goal pursuit

### Transparency Mechanisms:
- Confidence scores
- Source citations
- Reasoning explanations
- Alternative suggestions
- Uncertainty visualization

### Control Mechanisms:
- Automation levels (manual → suggest → copilot → auto)
- Edit and override
- Feedback (thumbs up/down)
- Undo/redo
- Preferences and settings

---

## 💡 Interview Questions You Should Be Able to Answer

1. "How do you design UX for AI products?"
   - **Framework:** Principles (transparency, control, failure) + Patterns (6 interaction types) + Examples

2. "Design an AI feature for [product]"
   - **Approach:** Identify pattern → Design for transparency → Add control → Plan for failure → Show multimodal

3. "What makes AI UX different from traditional UX?"
   - **Answer:** Probabilistic, opaque, changing, variable quality → requires confidence, explanation, control, error handling

4. "How do you handle AI errors?"
   - **Framework:** Prevent > Detect > Explain > Recover > Learn

5. "When would you use conversational UI vs. autocomplete?"
   - **Answer:** Conversational for complex/open-ended tasks; Autocomplete for high-frequency/clear-answer tasks

6. "How do you build trust in AI products?"
   - **Answer:** Transparency (show confidence, cite sources) + Control (override, adjust) + Consistency (reliable quality)

7. "Walk me through redesigning [app] with AI"
   - **Use your weekend deliverable!**

---

## ⏭️ Coming Up in Week 8

**Focus:** Evaluation Framework
- Building comprehensive AI evaluation systems
- Quantitative and qualitative evaluation
- Red-teaming and adversarial testing
- A/B testing for AI
- **Deliverable:** Complete evaluation framework + edge case catalog

---

## 📊 Progress Tracking

| Day | Topic | Hours Completed | Status |
|-----|-------|----------------|--------|
| Mon | AI UX Fundamentals | __ / 4 | ⬜ |
| Tue | AI Interaction Patterns | __ / 4 | ⬜ |
| Wed | Multimodal UX | __ / 4 | ⬜ |
| Thu | Transparency, Control & Safety | __ / 4 | ⬜ |
| Fri | Error States & Failure Design | __ / 4 | ⬜ |
| Sat-Sun | Redesign App + Pattern Library | __ / 6 | ⬜ |

**Total Target Hours:** 26 hours

---

**Week 7 Success Criteria:**
✅ You can design AI-native experiences from scratch
✅ You know all major AI UX patterns and when to use them
✅ You can design for transparency, control, and safety
✅ You have a portfolio-ready app redesign
✅ You understand what makes AI UX unique

Design the AI future! ✨🎨
