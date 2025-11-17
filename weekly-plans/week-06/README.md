# Week 6: Prompt Prototyping

## 🎯 Week Overview

**Focus Areas:**
- Rapid prototyping with LLMs (ChatGPT, Claude, Gemini)
- Building interactive UX flows using prompts
- Validating concepts before engineering investment
- Prompt engineering best practices

**Deliverables:**
- Working AI prototype (prompt-based)
- 5 detailed UX user flows
- Prompt engineering playbook
- (Optional) Stakeholder demo video

---

## 📚 Learning Objectives

By the end of this week, you will:

1. ✅ Master prompt engineering techniques
2. ✅ Build functional prototypes without code
3. ✅ Design and test UX flows with AI
4. ✅ Validate product concepts with users
5. ✅ Create demo-ready prototypes for stakeholders

---

## 🗓️ Daily Breakdown

### **Day 1 (Monday): Prompt Engineering Mastery**

**Morning Session (2 hours)**
- **Topic:** Prompt Engineering Fundamentals
- **Learning:**
  - Anatomy of a good prompt (role, context, task, format, examples)
  - Zero-shot vs. few-shot prompting
  - Chain-of-thought prompting
  - System vs. user messages
  - Temperature and sampling parameters
- **Resources:**
  - 📖 [OpenAI - Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) ⭐ MUST READ
  - 📖 [Anthropic - Prompt Engineering](https://docs.anthropic.com/claude/docs/prompt-engineering) ⭐
  - 📖 [Learn Prompting - Course](https://learnprompting.org/) ⭐
  - 🎥 [Andrew Ng - ChatGPT Prompt Engineering](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)

**Evening Session (2 hours)**
- **Activity:** Prompt Engineering Practice
- **Exercises:**
  1. Write prompts for different personas
  2. Practice few-shot learning
  3. Experiment with chain-of-thought
  4. Compare outputs across models (ChatGPT, Claude, Gemini)
- **Tools:**
  - ChatGPT (chat.openai.com)
  - Claude (claude.ai)
  - Google Gemini (gemini.google.com)

**Deliverable Start:** Prompt engineering playbook

---

### **Day 2 (Tuesday): Prototype Design**

**Morning Session (2 hours)**
- **Topic:** Designing Your AI Prototype
- **Planning:**
  - Pick your AI opportunity (from Week 1)
  - Define core user journey (3-5 steps)
  - Identify what to prototype (most risky assumption)
  - Map out conversation flow
  - Decide on interaction pattern:
    - Chat-based?
    - Form-based with AI assistance?
    - Autocomplete/copilot?
    - Agentic (AI initiates)?
- **Resources:**
  - 📖 [Nielsen Norman Group - AI UX](https://www.nngroup.com/articles/ai-paradigm/)
  - 📖 [Figma - AI Design Patterns](https://www.figma.com/community/ai)

**Evening Session (2 hours)**
- **Activity:** Create Prototype Specification
- **Document:**
  - **User Goal:** What is the user trying to achieve?
  - **Input:** What does user provide?
  - **AI Processing:** What does AI do?
  - **Output:** What does user receive?
  - **Success Criteria:** How do we know it worked?
  - **Error Handling:** What if AI fails?
  - **5 Test Scenarios:** Specific cases to test

---

### **Day 3 (Wednesday): Build Prototype - Part 1**

**Morning Session (2 hours)**
- **Topic:** Build Core Experience
- **Activity:**
  - Set up your prompting environment
  - Create system prompt (defines AI behavior)
  - Build main user flow
  - Test with 3-5 variations
- **Prompt Structure:**
  ```
  SYSTEM PROMPT:
  You are [role]. Your goal is [objective].

  USER CONTEXT: [background]

  TASK: [what user wants]

  FORMAT: [how to structure output]

  CONSTRAINTS: [what to avoid]

  EXAMPLES: [few-shot examples if needed]
  ```

**Evening Session (2 hours)**
- **Activity:** Iterate on Prompts
- **Test & Refine:**
  - Run through all 5 test scenarios
  - Document what works and what doesn't
  - Refine prompts based on outputs
  - Add guardrails for common errors
  - Test edge cases
- **Track:**
  - Prompt versions (v1, v2, v3...)
  - Success rate per scenario
  - Quality of outputs

---

### **Day 4 (Thursday): Build Prototype - Part 2**

**Morning Session (2 hours)**
- **Topic:** Advanced Prompting Techniques
- **Add sophistication:**
  - **Multi-turn conversations:** Maintaining context
  - **Persona consistency:** Keeping AI in character
  - **Error recovery:** Handling misunderstandings
  - **Fallback responses:** When AI is uncertain
  - **Output formatting:** JSON, markdown, structured data
- **Techniques:**
  - Add conversation memory
  - Use prompt chaining (output of one → input to next)
  - Implement self-critique (AI reviews its own output)
  - Add citations/sources

**Evening Session (2 hours)**
- **Activity:** Build 5 UX Flows
- **Create detailed flows for:**
  1. **Happy Path:** Everything works perfectly
  2. **Ambiguous Input:** User is unclear
  3. **Edge Case:** Unusual but valid scenario
  4. **Error State:** AI fails or can't help
  5. **Power User:** Advanced user with complex need

**For each flow, document:**
- User input (exact text)
- AI response (actual output)
- User reaction (what happens next)
- Success/failure assessment
- Improvements needed

---

### **Day 5 (Friday): Testing & Refinement**

**Morning Session (2 hours)**
- **Topic:** User Testing Your Prototype
- **Activity:**
  - Recruit 3-5 test users (friends, colleagues)
  - Give them a scenario (don't tell them what to say)
  - Observe their interactions
  - Document:
    - Where they got stuck
    - What delighted them
    - What confused them
    - What they expected vs. got
- **Resources:**
  - 📖 [Nielsen Norman Group - User Testing](https://www.nngroup.com/articles/usability-testing-101/)
  - 📖 [IDEO - Prototype Testing](https://www.designkit.org/methods/user-testing)

**Evening Session (2 hours)**
- **Activity:** Iterate Based on Feedback
- **Refine:**
  - Update prompts to handle discovered issues
  - Improve error messages
  - Add missing guardrails
  - Enhance output format
  - Document learnings
- **Deliverable:** Finalize prototype + test results

---

### **Day 6-7 (Weekend): Demo & Documentation**

**Saturday (3 hours)**
- **Activity:** Create Stakeholder Demo
- **Options:**
  1. **Demo Video:** Record yourself using the prototype (5-10 min)
  2. **Demo Doc:** Screenshots + explanations
  3. **Interactive Demo:** Let stakeholders try it

**Demo Structure:**
1. **Problem Statement** (1 min)
2. **Solution Overview** (1 min)
3. **Live Demo** (5 min)
   - Show all 5 UX flows
   - Highlight key features
   - Demonstrate error handling
4. **Learnings** (2 min)
   - What worked
   - What needs engineering
   - Next steps

**Sunday (2 hours)**
- **Activity:** Complete Prompt Engineering Playbook
- **Document:**
  - Prompt patterns you discovered
  - What works vs. what doesn't
  - Best practices for your use case
  - Gotchas and edge cases
  - Recommended models and parameters
  - Cost estimates (if using API)

- **Reflection:**
  - What did you learn about your AI opportunity?
  - What assumptions were validated/invalidated?
  - What would you build differently with engineering resources?
  - What surprised you about AI capabilities/limitations?

---

## 📝 Deliverables Checklist

### Required Deliverables:

- [ ] **Working AI Prototype** (`prototype/`)
  - System prompts
  - Test scenarios
  - Example conversations
  - Success metrics

- [ ] **5 UX User Flows** (`ux-flows.md`)
  - Happy path
  - Ambiguous input
  - Edge case
  - Error state
  - Power user flow

- [ ] **Prompt Engineering Playbook** (`prompt-playbook.md`)
  - Effective patterns
  - Best practices
  - Lessons learned
  - Recommendations

### Optional Deliverables:

- [ ] **Demo Video** (5-10 min)
  - Problem → Solution → Demo → Learnings

- [ ] **User Testing Report** (`user-testing-report.md`)
  - Test methodology
  - Findings
  - Iterations made

---

## 📖 Recommended Resources

### Prompt Engineering:
- 📖 [OpenAI - Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering) ⭐ MUST READ
- 📖 [Anthropic - Prompt Library](https://docs.anthropic.com/claude/prompt-library) ⭐
- 📖 [Learn Prompting](https://learnprompting.org/) ⭐
- 🎓 [DeepLearning.AI - Prompt Engineering Course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
- 📖 [Prompt Engineering Guide](https://www.promptingguide.ai/)

### Prototyping:
- 📖 [IDEO - Prototyping](https://www.designkit.org/methods#filter)
- 📖 [Nielsen Norman - Prototyping](https://www.nngroup.com/articles/ux-prototype-hi-lo-fidelity/)

### AI UX Patterns:
- 📖 [Google - People + AI Guidebook](https://pair.withgoogle.com/) ⭐
- 📖 [Microsoft - HAX Toolkit](https://www.microsoft.com/en-us/haxtoolkit/)
- 📖 [Nielsen Norman - AI UX](https://www.nngroup.com/articles/ai-paradigm/)

### Tools:
- [ChatGPT](https://chat.openai.com/)
- [Claude](https://claude.ai/)
- [Google Gemini](https://gemini.google.com/)
- [Perplexity](https://www.perplexity.ai/)
- [LangChain](https://python.langchain.com/) (if you code)
- [Vercel AI Playground](https://sdk.vercel.ai/)

---

## 🎓 Key Concepts to Master

### Prompt Engineering:
- **Role-Task-Format:** Structure for clear prompts
- **Few-Shot Learning:** Providing examples in prompt
- **Chain-of-Thought:** Asking AI to think step-by-step
- **Temperature:** Randomness in outputs (0 = deterministic, 1 = creative)
- **System Messages:** Setting AI behavior/personality
- **Prompt Chaining:** Breaking complex tasks into steps

### Prototyping:
- **Rapid Iteration:** Test → Learn → Refine quickly
- **Assumption Testing:** Validate riskiest beliefs first
- **Lo-Fi is OK:** Crude prototype > perfect documentation
- **User-Centric:** Design for real user needs, not imagined ones
- **Fail Fast:** Discover problems early before engineering

### AI UX Patterns:
- **Transparency:** Show AI confidence, sources, reasoning
- **Control:** Let users edit, override, guide AI
- **Graceful Degradation:** Handle failures elegantly
- **Progressive Disclosure:** Don't overwhelm with AI power
- **Human-in-Loop:** Know when to escalate to humans

---

## 💡 Interview Questions You Should Be Able to Answer

1. "How do you validate product ideas quickly?"
   - **Answer:** Prompt-based prototypes! Show example from this week

2. "Walk me through your prototyping process"
   - **Framework:** Define goal → Build lo-fi → Test users → Iterate → Validate/invalidate

3. "What did you learn from prototyping [your AI feature]?"
   - **Answer:** Use specific learnings from your prototype

4. "How do you design AI experiences?"
   - **Answer:** UX patterns (transparency, control, graceful failure) + prototype examples

5. "When would you use a prompt-based prototype vs. building with engineering?"
   - **Answer:** Early validation, concept testing, assumption testing = prompts. Production scale, complex logic, integration = engineering.

6. "Your AI prototype worked great, but what are the limitations?"
   - **Answer:** Prompt-based limitations (latency, cost, reliability, customization) + what engineering would improve

---

## ⏭️ Coming Up in Week 7

**Focus:** AI-Native UX
- Design patterns for AI products
- Multimodal UX
- Conversational interfaces
- Safety and override patterns
- **Deliverable:** AI-native UX redesign + pattern library

---

## 📊 Progress Tracking

| Day | Topic | Hours Completed | Status |
|-----|-------|----------------|--------|
| Mon | Prompt Engineering Mastery | __ / 4 | ⬜ |
| Tue | Prototype Design | __ / 4 | ⬜ |
| Wed | Build Prototype - Part 1 | __ / 4 | ⬜ |
| Thu | Build Prototype - Part 2 | __ / 4 | ⬜ |
| Fri | Testing & Refinement | __ / 4 | ⬜ |
| Sat-Sun | Demo & Documentation | __ / 5 | ⬜ |

**Total Target Hours:** 25 hours

---

**Week 6 Success Criteria:**
✅ You can write effective prompts consistently
✅ You built a working AI prototype without code
✅ You tested with real users and iterated
✅ You have a demo-ready prototype
✅ You understand AI UX patterns from hands-on experience

Prototype the impossible! 🚀✨
