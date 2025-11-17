# Week 5: PRDs + AI-Specific Requirements

## 🎯 Week Overview

**Focus Areas:**
- Writing execution-ready Product Requirements Documents (PRDs)
- AI-specific requirements (data, models, evaluation, guardrails)
- Edge cases and failure modes for AI products
- Human-in-the-loop patterns

**Deliverables:**
- Standard PRD for a traditional feature
- AI PRD with RAG/LLM requirements
- PRD template for future use

---

## 📚 Learning Objectives

By the end of this week, you will:

1. ✅ Write clear, comprehensive PRDs that engineers can execute from
2. ✅ Add AI-specific requirements (data sources, model selection, evaluation criteria)
3. ✅ Document edge cases and failure modes systematically
4. ✅ Design human-in-the-loop workflows
5. ✅ Create PRDs at FAANG quality level

---

## 🗓️ Daily Breakdown

### **Day 1 (Monday): PRD Fundamentals**

**Morning Session (2 hours)**
- **Topic:** Anatomy of a Great PRD
- **Learning:**
  - Problem statement (why are we building this?)
  - Success metrics (how do we measure success?)
  - User stories & use cases
  - Requirements (functional & non-functional)
  - Out of scope (what we're NOT building)
  - Open questions & assumptions
- **Resources:**
  - 📚 [Lenny's Newsletter - How to Write a PRD](https://www.lennysnewsletter.com/p/how-to-write-a-product-requirements) ⭐
  - 📖 [Atlassian - PRD Template](https://www.atlassian.com/agile/product-management/requirements)
  - 📖 [ProductPlan - PRD Guide](https://www.productplan.com/learn/write-product-requirements-document/)

**Evening Session (2 hours)**
- **Activity:** Analyze Real PRDs
- **Study examples:**
  - Find public PRDs or templates from top companies
  - Analyze structure and depth
  - Note what makes them clear and actionable
- **Exercise:**
  - Pick a simple feature (e.g., "Add dark mode")
  - Write outline for PRD
  - Focus on completeness

**Interview Prep:**
- "How do you write requirements?"
- "What makes a good PRD?"

---

### **Day 2 (Tuesday): Write a Standard PRD**

**Morning Session (2 hours)**
- **Topic:** User Stories & Acceptance Criteria
- **Learning:**
  - User story format: "As a [user], I want [goal], so that [benefit]"
  - Acceptance criteria (definition of done)
  - Edge cases and error states
  - Non-functional requirements (performance, security, etc.)
- **Resources:**
  - 📖 [Mountain Goat Software - User Stories](https://www.mountaingoatsoftware.com/agile/user-stories)
  - 📖 [Atlassian - Acceptance Criteria](https://www.atlassian.com/agile/project-management/user-stories)

**Evening Session (2 hours)**
- **Activity:** Write Complete Standard PRD
- **Feature:** Pick a non-AI feature from your Week 1 opportunities
- **Include all sections:**
  - Problem & Background
  - Goals & Success Metrics
  - User Stories (at least 5)
  - Functional Requirements
  - Non-Functional Requirements
  - Edge Cases
  - Out of Scope
  - Open Questions
- **Deliverable:** Standard PRD completed

---

### **Day 3 (Wednesday): AI-Specific Requirements - Part 1**

**Morning Session (2 hours)**
- **Topic:** Data Requirements for AI Products
- **Learning:**
  - **Data Sources:** Where does training data come from?
  - **Data Volume:** How much is needed?
  - **Data Quality:** Labeling, accuracy, freshness
  - **Data Privacy:** PII, consent, compliance
  - **Data Pipeline:** Collection → Cleaning → Storage → Access
- **Resources:**
  - 📚 [Chip Huyen - Designing ML Systems](https://huyenchip.com/machine-learning-systems-design/) (Data chapters) ⭐
  - 📖 [Google - Data Requirements](https://developers.google.com/machine-learning/data-prep)
  - 📖 [AWS - Data Labeling](https://aws.amazon.com/sagemaker/data-labeling/)

**Evening Session (2 hours)**
- **Topic:** Model Selection & Configuration
- **Learning:**
  - Model type selection (classification, regression, LLM, etc.)
  - Pre-trained vs. fine-tuned vs. trained from scratch
  - Model hosting (API vs. self-hosted)
  - Context window considerations (for LLMs)
  - Cost modeling (tokens, compute)
- **Resources:**
  - 📖 [OpenAI - Model Selection Guide](https://platform.openai.com/docs/models)
  - 📖 [Hugging Face - Model Hub](https://huggingface.co/models)
  - 📖 [Google - Vertex AI Models](https://cloud.google.com/vertex-ai/docs/start/explore-models)

**Activity:**
- For your AI opportunity, document:
  - Required data sources
  - Data volume estimates
  - Model type recommendation
  - Cost estimate

---

### **Day 4 (Thursday): AI-Specific Requirements - Part 2**

**Morning Session (2 hours)**
- **Topic:** Evaluation & Quality Criteria
- **Learning:**
  - **Offline Evaluation:** Test sets, benchmark metrics
  - **Online Evaluation:** A/B testing, user feedback
  - **Quality Thresholds:** Minimum acceptable performance
  - **Acceptance Criteria:** When is model "ready to ship"?
  - **Regression Testing:** Ensuring new versions don't degrade
- **Resources:**
  - 📖 [Google - Testing ML Systems](https://developers.google.com/machine-learning/testing-debugging)
  - 📖 [Netflix - A/B Testing](https://netflixtechblog.com/its-all-a-bout-testing-the-netflix-experimentation-platform-4e1ca458c15)

**Evening Session (2 hours)**
- **Topic:** Guardrails & Safety Requirements
- **Learning:**
  - **Content Filters:** Toxicity, PII, harmful content
  - **Rate Limiting:** Preventing abuse
  - **Fallback Mechanisms:** What happens when AI fails?
  - **Human-in-the-Loop:** When to escalate to humans
  - **Monitoring & Alerts:** Drift detection, performance degradation
- **Resources:**
  - 📖 [OpenAI - Safety Best Practices](https://platform.openai.com/docs/guides/safety-best-practices)
  - 📖 [Google - Responsible AI Practices](https://ai.google/responsibility/responsible-ai-practices/)
  - 📖 [Microsoft - HAX Toolkit](https://www.microsoft.com/en-us/haxtoolkit/)

**Activity:**
- Define evaluation criteria for your AI feature
- Document guardrails and safety requirements

---

### **Day 5 (Friday): Write AI PRD**

**Morning Session (2 hours)**
- **Topic:** Edge Cases & Failure Modes for AI
- **Learning:**
  - Common AI failure modes:
    - Hallucinations (making up information)
    - Bias and fairness issues
    - Adversarial inputs
    - Distribution shift
    - Cold start problems
  - Documenting "what could go wrong"
  - Mitigation strategies
- **Resources:**
  - 📖 [Google - Responsible AI](https://ai.google/responsibility/responsible-ai-practices/)
  - 📖 [Partnership on AI - Guidelines](https://partnershiponai.org/)

**Evening Session (2 hours)**
- **Activity:** Write Complete AI PRD
- **Feature:** Pick your top AI opportunity from Week 1
- **AI PRD Sections:**
  1. Problem & Background
  2. Goals & Success Metrics (product + ML)
  3. User Stories
  4. **Data Requirements** ⭐
     - Sources
     - Volume
     - Labeling
     - Privacy
  5. **Model Requirements** ⭐
     - Type/Architecture
     - Input/Output specs
     - Performance thresholds
  6. **Evaluation Criteria** ⭐
     - Offline metrics
     - Online metrics
     - A/B test plan
  7. **Guardrails & Safety** ⭐
     - Content filtering
     - Rate limits
     - Fallback behavior
  8. **Human-in-the-Loop** ⭐
     - When to involve humans
     - Escalation paths
  9. Edge Cases & Failure Modes
  10. Technical Architecture (high-level)
  11. Cost Estimate
  12. Out of Scope
  13. Open Questions

- **Deliverable:** Complete AI PRD

---

### **Day 6-7 (Weekend): RAG-Specific PRD + Polish**

**Saturday (3 hours)**
- **Topic:** RAG (Retrieval-Augmented Generation) Requirements
- **Learning:**
  - What is RAG? (Combining retrieval + generation)
  - When to use RAG vs. fine-tuning
  - RAG architecture components:
    - Document ingestion & chunking
    - Vector database
    - Retrieval mechanism
    - Prompt construction
    - LLM generation
  - RAG-specific requirements:
    - Document sources & refresh rates
    - Chunk size and overlap
    - Embedding model selection
    - Retrieval strategy (semantic, keyword, hybrid)
    - Context window management
    - Citation requirements
- **Resources:**
  - 📖 [LangChain - RAG Tutorial](https://python.langchain.com/docs/use_cases/question_answering/) ⭐
  - 📖 [Pinecone - RAG Guide](https://www.pinecone.io/learn/retrieval-augmented-generation/)
  - 📖 [OpenAI - RAG Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)

**Activity:**
- Add RAG section to your AI PRD (if applicable)
- OR create a separate RAG chatbot PRD

**Sunday (2 hours)**
- **Activity:** Polish & Review
  - Review both PRDs (standard + AI)
  - Add diagrams (user flows, system architecture)
  - Create PRD template for future use
  - Self-review checklist:
    - [ ] Clear problem statement?
    - [ ] Measurable success metrics?
    - [ ] Complete user stories?
    - [ ] Edge cases documented?
    - [ ] AI requirements comprehensive?
    - [ ] Engineer could build from this?

- **Reflection:**
  - What was hardest about writing AI requirements?
  - What questions came up that you couldn't answer?
  - How would you improve your PRD?

---

## 📝 Deliverables Checklist

### Required Deliverables:

- [ ] **Standard PRD** (`standard-prd.md`)
  - Problem & Goals
  - Success Metrics
  - User Stories (5+)
  - Requirements
  - Edge Cases
  - Out of Scope

- [ ] **AI PRD** (`ai-prd.md`)
  - All standard PRD sections PLUS:
  - Data requirements
  - Model requirements
  - Evaluation criteria
  - Guardrails & safety
  - Human-in-the-loop
  - Edge cases & failure modes
  - Cost estimates

- [ ] **PRD Template** (`prd-template.md`)
  - Reusable template for future PRDs
  - AI-specific sections clearly marked

---

## 📖 Recommended Resources

### PRD Writing:
- 📚 [Lenny's Newsletter - PRD Guide](https://www.lennysnewsletter.com/p/how-to-write-a-product-requirements) ⭐
- 📖 [Atlassian - PRD Template](https://www.atlassian.com/agile/product-management/requirements)
- 📖 [ProductPlan - PRD Examples](https://www.productplan.com/learn/product-requirements-document-examples/)

### AI Requirements:
- 📚 [Chip Huyen - ML Systems Design](https://huyenchip.com/machine-learning-systems-design/) ⭐
- 📖 [Google - ML Guide](https://developers.google.com/machine-learning/guides)
- 📖 [AWS - ML Best Practices](https://aws.amazon.com/machine-learning/ml-use-cases/)

### RAG & LLMs:
- 📖 [LangChain Documentation](https://python.langchain.com/docs/) ⭐
- 📖 [OpenAI - Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- 📖 [Pinecone - Vector DB Guide](https://www.pinecone.io/learn/)

### Safety & Ethics:
- 📖 [Google - Responsible AI](https://ai.google/responsibility/responsible-ai-practices/)
- 📖 [Microsoft - HAX Toolkit](https://www.microsoft.com/en-us/haxtoolkit/)
- 📖 [Partnership on AI](https://partnershiponai.org/)

---

## 🎓 Key Concepts to Master

### PRD Fundamentals:
- **Problem Statement:** Why are we building this?
- **Success Metrics:** How do we measure success?
- **User Stories:** Who does what and why?
- **Acceptance Criteria:** Definition of done
- **Edge Cases:** What could go wrong?

### AI-Specific Requirements:
- **Data Requirements:** Source, volume, quality, privacy
- **Model Requirements:** Type, performance, cost
- **Evaluation:** Offline + online metrics
- **Guardrails:** Safety, fallbacks, monitoring
- **Human-in-the-Loop:** When to involve humans

### RAG Components:
- **Retrieval:** Finding relevant context
- **Augmentation:** Adding context to prompt
- **Generation:** LLM produces answer
- **Chunking:** Breaking documents into pieces
- **Embeddings:** Vector representations
- **Vector DB:** Storage for embeddings

---

## 💡 Interview Questions You Should Be Able to Answer

1. "Walk me through how you write a PRD"
   - **Framework:** Problem → Goals → Users → Requirements → Metrics → Edge Cases

2. "What AI-specific requirements do you include in PRDs?"
   - **Answer:** Data, model, evaluation, guardrails, human-in-loop, failure modes, cost

3. "How do you handle AI failure modes?"
   - **Answer:** Document them, design fallbacks, monitor, have escalation paths

4. "What's the difference between a PRD for a traditional feature vs. an AI feature?"
   - **Answer:** AI adds: data requirements, model specs, probabilistic behavior, evaluation complexity, safety considerations

5. "How do you decide between RAG and fine-tuning?"
   - **Answer:** RAG for: dynamic data, citations needed, lower cost. Fine-tuning for: specific style/format, better performance, proprietary knowledge

6. "Your AI feature is hallucinating. How did you prevent this in your PRD?"
   - **Answer:** Evaluation criteria, guardrails (fact-checking, citations), human review for high-stakes, monitoring

---

## ⏭️ Coming Up in Week 6

**Focus:** Prompt Prototyping
- Rapid prototyping with prompts
- Building UX flows with ChatGPT/Claude
- Validating concepts before engineering
- **Deliverable:** Working prototype + 5 UX flows

---

## 📊 Progress Tracking

| Day | Topic | Hours Completed | Status |
|-----|-------|----------------|--------|
| Mon | PRD Fundamentals | __ / 4 | ⬜ |
| Tue | Write Standard PRD | __ / 4 | ⬜ |
| Wed | AI Requirements - Part 1 | __ / 4 | ⬜ |
| Thu | AI Requirements - Part 2 | __ / 4 | ⬜ |
| Fri | Write AI PRD | __ / 4 | ⬜ |
| Sat-Sun | RAG PRD + Polish | __ / 5 | ⬜ |

**Total Target Hours:** 25 hours

---

**Week 5 Success Criteria:**
✅ You can write execution-ready PRDs
✅ You know all AI-specific requirements to include
✅ You can document edge cases and failure modes
✅ You have 2 portfolio-quality PRDs
✅ Engineers could build from your PRD

Document the future! 📝🚀
