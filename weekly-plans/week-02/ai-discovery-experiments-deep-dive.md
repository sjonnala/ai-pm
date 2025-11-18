# AI Discovery Experiments Deep Dive

**Week 2 Reference**

Design a repeatable system for validating AI opportunities before you commit precious engineering time.

---

## 🔁 Continuous Discovery Loop

| Stage | Goal | Activities | Decision Artifact |
|-------|------|------------|-------------------|
| **Discover** | Surface unmet needs | Opportunity Solution Trees, JTBD interviews, log mining | Opportunity backlog w/ unmet outcomes |
| **Define** | Narrow on riskiest assumptions | Assumption mapping (desirability, viability, feasibility) | Ranked assumption list |
| **Experiment** | Test cheaply | Fake-door tests, concierge workflows, Wizard-of-Oz AI prototypes | Evidence report |
| **Decide** | Prioritize or pivot | Score vs. opportunity criteria | Updated roadmap / kill list |

Run the loop every 2 weeks. Always capture learnings in the shared OST doc.

---

## 🔨 Experiment Toolkit

| Experiment | What It Tests | Time to Spin Up | How to Measure |
|------------|---------------|-----------------|----------------|
| **Prompt Concierge** | Quality of AI output + user trust | 1 day | CSAT, completion time |
| **Form or Fake Door** | Demand / intent | 1-2 days | CTR, signups, waitlist |
| **Wizard-of-Oz** | Workflow fit + value | 2-3 days | Feedback, drop-offs, ops load |
| **Data Backfill Analysis** | Data sufficiency | 1 day | Coverage %, label quality |
| **Benchmark Replay** | Feasibility vs. existing models | 2 days | Accuracy vs. baseline |

Pick the experiment that invalidates the biggest unknown for cheapest.

---

## 🧪 Assumption Mapping Board

1. Brainstorm assumptions across **desirability, viability, feasibility, usability**.
2. Plot each on a 2x2 (impact vs. uncertainty).
3. Convert highest priority assumptions into experiments.

| Assumption | Category | Impact (H/M/L) | Uncertainty (H/M/L) | Experiment | Owner | ETA |
|------------|----------|----------------|---------------------|------------|-------|-----|
| Users trust AI-generated onboarding emails | Desirability | High | High | Prompt concierge script for top cohort | PM | Fri |

---

## 🎙️ Discovery Interview Script Enhancements

- Start with **context** (role, goals) before problems.
- Use **contrast questions**: "What happens if you do nothing?" to reveal stakes.
- End with **artifacts**: ask for screenshots, docs, or allow shadowing.
- Log quotes verbatim; tag them to OST nodes to keep evidence linked.

---

## ✅ Week 2 Discovery Checklist

- [ ] Every OST node has at least one supporting interview or data point
- [ ] Top 3 assumptions mapped with aligned experiments
- [ ] At least 1 fake-door or concierge test scheduled this week
- [ ] Evidence repo updated (Notion/Doc) with raw notes and synthesized insights
- [ ] Prioritization of AI projects updated using latest experiment data
