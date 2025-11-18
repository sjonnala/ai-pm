# AI Build & Handoff Deep Dive

**Week 10 Reference**

Ensure your AI PRD, prototype, and UX flows are build-ready by covering every engineering touchpoint.

---

## 🧱 Build Readiness Scorecard

| Area | Questions | Evidence Needed |
|------|-----------|-----------------|
| **Product** | Does the PRD capture problem, scope, metrics, edge cases? | Final PRD, walkthrough recording |
| **Design/UX** | Are flows annotated with AI behavior, states, fallbacks? | Figma/diagram + notes |
| **Data** | Do we know sources, ownership, schemas? | Data contract + lineage |
| **Model** | Do prompts/models + evaluation results exist? | Prompt spec, batch test summary |
| **Infra** | Do we know hosting, latency, scalability limits? | Architecture diagram + non-functional reqs |

Score each (Green/Yellow/Red) before handoff.

---

## 🔄 PM → Eng/Design Handoff Agenda

1. **Vision refresher** – Why, impact, success metrics.
2. **Walkthrough** – UX flows, prototype demo, edge cases.
3. **AI specifics** – Prompts, data, evaluation plan, guardrails.
4. **Tech architecture** – Sequence diagrams, dependencies.
5. **Open questions** – Owner + due date per item.

Record session; share notes + artifacts same day.

---

## 🧠 Technical Architecture Deep Dive

Include:

- **Context Diagram** – External systems, user touchpoints.
- **Sequence Diagram** – Request → retrieval → model → response.
- **Data Flow** – Storage, ETL, feature store, monitoring.
- **Security Surfacing** – Secrets, auth, PII handling.

> Annotate key decisions (e.g., "Using hosted LLM to hit timeline") so reviewers understand trade-offs.

---

## 🧪 Pre-Handoff Quality Gates

| Gate | Description | Owner |
|------|-------------|-------|
| Prototype Demo | Walkthrough recorded, covers success + failure path | PM |
| Prompt Eval | ≥20 scenarios scored, success threshold hit | PM/DS |
| Edge Case Review | At least 10 documented with fallback | PM/Design |
| Risk Log | Technical + product risks logged with mitigation | PM |
| Launch Criteria | Definition of done + evaluation targets agreed | PM + Eng |

Do not schedule handoff until all gates are ✅.

---

## ✅ Week 10 Build Checklist

- [ ] Build readiness scorecard completed + shared
- [ ] Handoff session scheduled with annotated agenda + artifacts
- [ ] Architecture and data contracts documented
- [ ] Quality gates passed with evidence stored in repo
- [ ] Follow-up tasks tracked in shared board (Jira/Linear/Notion)
