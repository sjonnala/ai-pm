# Prompt Prototyping Lab Guide

**Week 6 Reference**

Build production-ready prompt experiments quickly so you can validate UX, feasibility, and quality before engineering commits.

---

## 🧪 Experiment Loop

| Step | Goal | Tooling | Output |
|------|------|---------|--------|
| **Collect** | Gather representative inputs + gold outputs | Google Sheet, Notion | 20-50 canonical scenarios |
| **Design** | Draft prompt variants + guardrails | Prompt IDE (Dust, Latent, GPT Builder) | Prompt matrix |
| **Run** | Execute batch tests | LangSmith, Marvin CLI | CSV / JSON results |
| **Review** | Score outputs (rubric + human ratings) | Airtable, Calibrated rubric | Pass/fail + notes |
| **Decide** | Promote best prompt, log learnings | Retro doc | Versioned prompt spec |

Repeat daily; version prompts like code.

---

## 🧱 Prompt Specification Template

| Section | What to Capture |
|---------|-----------------|
| **Intent** | What job does the prompt perform? |
| **Inputs** | List all variables + format (JSON, Markdown) |
| **Context Packing** | Retrieval strategy, ordering, truncation rules |
| **System / Developer Prompts** | Exact wording + rationale |
| **Output Schema** | Example + validation (JSON schema, RegEx) |
| **Safety Rules** | Disallowed content, disclaimers, fallback |
| **Evaluation Plan** | Metrics, sample size, acceptance thresholds |

Store this spec beside prototype so hand-off is frictionless.

---

## 🧠 Prompt Patterns Cheat Sheet

| Pattern | When to Use | Example |
|---------|-------------|---------|
| **Chain-of-Thought** | Complex reasoning, math, planning | "Let's think through steps before answering." |
| **Critique + Refine** | Higher quality outputs | Prompt model to critique first response, then fix |
| **XML/JSON Schemas** | Structured outputs for integrations | Wrap instructions inside `<schema>` tags |
| **Self-Ask** | Retrieval-augmented flows | Let model ask clarifying Qs before responding |
| **Role Play** | Tone control | "You are a compliance analyst..." |

Document which patterns improved quality + cost trade-offs.

---

## 📊 Batch Testing Rubric

| Dimension | Score 1 | Score 3 | Score 5 |
|-----------|---------|---------|---------|
| **Accuracy** | Wrong/missing key facts | Minor omissions | Exact answer + context |
| **Actionability** | No clear next step | Some guidance | Clear, structured actions |
| **Tone** | Off-brand, robotic | Acceptable | Perfectly on-brand |
| **Safety** | Violates policy | Mild risk | Fully compliant |

Add comments + blockers for every failing case so you can fine-tune prompts or UX.

---

## ✅ Week 6 Prompt Checklist

- [ ] Prompt spec documented with versioning (v0.1, v0.2...)
- [ ] Dataset of 20+ real scenarios tagged with outcomes
- [ ] Batch test results logged with rubric scores + insights
- [ ] Guardrails + fallbacks explored using critique/self-check prompts
- [ ] Handoff summary ready for engineers (prompt, eval data, risks)
