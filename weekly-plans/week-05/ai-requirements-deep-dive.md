# AI Requirements Deep Dive

**Week 5 Reference**

Use this guide to capture every AI-specific consideration inside your PRDs so engineering, data, and infra teams have zero ambiguity.

---

## 🧰 Components of an AI Requirement Stack

1. **Use Case + User Interaction** – What the AI powers and how the user experiences it
2. **Data Requirements** – Sources, pipelines, freshness, ownership
3. **Model Strategy** – Model class, hosting approach, customization level
4. **Evaluation Plan** – Offline metrics + online guardrails
5. **Safety & Guardrails** – Policy, content filters, fallback paths
6. **Operational Concerns** – Latency, throughput, monitoring, cost

> Think of it as *product + data + infra* in one doc. If any pillar is missing, implementation slows down.

---

## 📦 Data Requirements Blueprint

| Dimension | Questions to Answer | Example Entry |
|-----------|--------------------|---------------|
| **Source** | Where does data originate? Internal event logs, CRM, public docs? | Product analytics warehouse (Snowflake `events_ai_feature`) |
| **Volume** | How much per day/week? | 5M events/day |
| **Freshness** | How current must it be? | <15 minutes lag |
| **Quality** | Accuracy, null rate, labeling coverage | 92% labeled; need re-labeling for Q1 data |
| **Access** | Who owns access + permissions? | Data Infra team; service role `prd_ai_writer` |
| **Privacy / Compliance** | PII? HIPAA? Regional storage? | EU data must stay in Frankfurt cluster |

**Call out gaps explicitly** (ex: "Need 2 FTE data annotators for 3 weeks").

---

## 🧠 Model Strategy Decision Tree

1. **Is deterministic logic enough?** → Use heuristics / rules.
2. **Need ML but structured outputs?** → Classification / regression.
3. **Need natural language / reasoning?** → Choose LLM or hybrid (RAG + LLM).
4. **Rare domain knowledge?** → Consider fine-tuning or domain-specific RAG.

### Model Requirement Template

| Topic | Details to Include |
|-------|--------------------|
| **Model Type** | GPT-4, Claude, proprietary LLM, Gradient Boosted Trees, etc. |
| **Access Method** | Managed API (OpenAI), hosted on Vertex, self-hosted |
| **Context Window** | Tokens required per request (prompt + completion) |
| **Customization Plan** | Zero-shot, prompt engineering, fine-tune, adapters |
| **Latency Targets** | e.g., `<2s p95 for retrieval + completion` |
| **Cost Envelope** | Token budget or GPU hours per month |
| **Fallback Model** | Lower-cost model when budgets exceeded |

> ⚖️ Always include trade-offs (quality vs. cost vs. control) to align with engineering and finance early.

---

## 🧪 Evaluation & Monitoring Plan

### Offline Evaluation

| Metric Type | Examples | Notes |
|-------------|----------|-------|
| **Quality** | BLEU/ROUGE, exact match, accuracy | Use domain-specific rubric too |
| **Safety** | Toxicity score, hallucination rate | Include threshold + sampling strategy |
| **Cost** | $ / 1k tokens, GPU hours | Evaluate vs. baseline |

### Online Evaluation

| Layer | What to Track | Tools |
|-------|---------------|-------|
| **User Behavior** | Acceptance rate, edit rate, feature retention | Product analytics |
| **Quality Signals** | Thumbs up/down, explicit ratings, error reports | Feedback widgets |
| **Operational** | Latency percentiles, error codes, model timeouts | Observability stack |

### Review Cadence
- PRD should state **who owns evaluation**, **how frequently metrics are reviewed**, and **escalation triggers**.

---

## 🛡️ Safety, Guardrails, and Governance

| Area | Checklist |
|------|-----------|
| **Content Safety** | Use moderation endpoint, block PII, define banned topics |
| **Hallucinations** | Require citations, retrieval confidence thresholds, fallback to humans |
| **Bias & Fairness** | Measure outcomes across key cohorts; document mitigations |
| **User Controls** | Offer opt-out or transparency UI; log manual overrides |
| **Auditability** | Store prompts, responses, and metadata for 90 days minimum |

> 🔒 For high-risk domains (fintech, healthcare), add regulatory references (HIPAA, FINRA, GDPR).

---

## ⚙️ Operational & Cost Considerations

| Dimension | Questions | Example |
|-----------|-----------|---------|
| **Latency Budget** | Max acceptable per user journey? | Search request budget = 2s (retrieval 700ms + LLM 1.3s) |
| **Concurrency** | Peak RPS? | 150 req/s at 10am PT weekdays |
| **Autoscaling** | How will infra scale under load? | Use Vertex auto-scaling w/ headroom 2x |
| **Token Budget** | Monthly ceiling? | $12k for prompts, $5k for completions |
| **Monitoring** | Which dashboards / alerts exist? | Datadog monitors for latency >3s |

Include a **Cost Sensitivity Table** (Base, High, Low usage) so finance partners know burn scenarios.

---

## 📝 AI Requirement Checklist

- [ ] Data sources, owners, and freshness documented
- [ ] Access + privacy requirements approved by legal/security
- [ ] Model selection rationale, fallback, and cost envelope captured
- [ ] Offline + online evaluation plan defined with owners
- [ ] Guardrails and monitoring instrumentation listed
- [ ] Operational metrics + scaling assumptions reviewed with infra

If any item is TBD, add an explicit owner + due date inside the PRD.
