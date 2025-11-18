# AI Guardrails & Human-in-the-Loop Guide

**Week 5 Reference**

Use this guide to design mitigation plans for probabilistic AI behavior before you ship.

---

## 🧭 Guardrail Strategy Overview

| Layer | Purpose | Tactics |
|-------|---------|---------|
| **Prevention** | Stop bad inputs | Input validation, policy filters, prompt hardening |
| **Detection** | Catch bad outputs | Classifiers, factuality checks, automated tests |
| **Reaction** | Recover gracefully | Human review, fallback experience, alerting |
| **Learning** | Improve over time | Feedback loops, retraining queues, RCA rituals |

> 🎯 Goal: Keep high-impact risks at **<1% occurrence** while maintaining a fast user experience.

---

## 🛑 Input Guardrails

### Checklist
- [ ] Validate required fields (leng, format, attachments)
- [ ] Run content moderation (toxicity, PII, policy categories)
- [ ] Rate-limit abusive actors (tokens/minute and req/minute)
- [ ] Sanitize instructions (remove prompt injections, SQL statements)
- [ ] Tag input with metadata (user ID, cohort, access level)

**Prompt Hardening Tips**
- Define system prompt rules explicitly ("Never mention internal tooling")
- Use instruction-following guardrails ("If unsure, ask the user for clarification")
- Inject context windows with sanitized text only

---

## 🚨 Output Guardrails

| Risk | Detection Method | Fallback |
|------|------------------|----------|
| **Hallucinations** | Retrieval confidence score < threshold; fact-checker LLM | Return "Need more info" + ask follow-up |
| **Toxic / Disallowed Content** | Moderation endpoint on completion | Block response, show apology, alert trust & safety |
| **Personally Identifiable Info** | Regex / entity detection | Mask fields before displaying |
| **Low Confidence** | Model self-reported confidence or scoring rubric | Route to human review |

**Automation Tip:** Chain-of-thought or critique prompts often raise quality but increase tokens; call that out in PRD cost section.

---

## 🧑‍⚖️ Human-in-the-Loop (HITL) Patterns

| Pattern | When to Use | Example |
|---------|-------------|---------|
| **Review Before Publish** | High stakes, regulated content | Loan approval explanations |
| **Second Opinion** | AI aids humans but humans decide | Medical summarization |
| **Sampling Audits** | Medium risk, high volume | Review 5% of support replies daily |
| **Escalation Path** | On-demand human help | "Escalate to human" button in chat |

### Designing a HITL Workflow
1. **Trigger** – confidence threshold, keyword, user flag, or random sampling
2. **Queue** – route tasks to the right team with SLA (ex: <2 hours)
3. **Tooling** – surface AI output, context, and edit surface
4. **Loop Closure** – log edits as training data + annotate reason codes

Document each step in the PRD to avoid operational gaps.

---

## 🧪 Evaluation & Incident Playbooks

### Pre-Launch
- Dry run with synthetic edge cases (prompt attacks, ambiguous queries)
- Chaos testing: remove retrieval context, degrade latency, simulate outages
- Scenario review with Legal / T&S for high-risk categories

### Post-Launch
- Define **Severity Levels** (Sev0 = exposure of PII, etc.)
- Incident response doc: on-call owner, comms template, rollback plan
- Weekly review of guardrail metrics + open incidents

---

## 📊 Guardrail Metrics Dashboard

| Metric | Target | Owner |
|--------|--------|-------|
| Moderation Block Rate | <2% (unless high-risk) | Trust & Safety |
| Hallucination Rate | <5% on sampled eval set | Applied AI |
| Human Escalation Rate | 10-20% for v1, trending down | Operations |
| Time to Human Response | <2 hours | Support |
| Incident Count (Sev1+) | 0 per release | PM |

Include these metrics in your PRD "Success Metrics" or "Monitoring" section to keep them top-of-mind.

---

## ✅ Guardrail & HITL Checklist

- [ ] Input validation + policy filters defined
- [ ] Output checks (toxicity, factuality, PII) wired into design
- [ ] Confidence thresholds documented with numbers
- [ ] HITL workflow mapped (trigger → queue → SLA → tooling)
- [ ] Incident response expectations in place
- [ ] Monitoring dashboard + owners listed

If any guardrail depends on a future capability, capture interim mitigations (e.g., smaller rollout, manual QA) and timeline.
