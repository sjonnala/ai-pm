# Evaluation Ops Deep Dive

**Week 8 Reference**

Operationalize AI evaluation so quality, safety, and drift monitoring run like clockwork.

---

## 🪜 Evaluation Ownership Model

| Layer | Primary Owner | Cadence | Output |
|-------|---------------|---------|--------|
| **Model Benchmarks** | Applied AI/DS | Weekly | Benchmark report (accuracy, F1, hallucination) |
| **Product QA** | PM + Design | Twice weekly | Rubric scores, UX blockers |
| **Red Teaming** | T&S / Security | Monthly | Incident log, mitigation plan |
| **Monitoring / Drift** | Data Platform | Daily | Alerts, dashboards |

Create RACI so every evaluation artifact has a home.

---

## 🧬 Test Suite Architecture

```
Golden Dataset (labeled) ──┬─ Offline regression tests
                            ├─ Prompt gallery tests
                            └─ Safety & policy tests
Synthetic / adversarial ────┼─ Red team suite
Live traffic samples ───────┴─ Shadow eval & drift monitors
```

Document data sources, storage, refresh cadence, and access controls.

---

## 📊 Eval Board Template

| Metric | Target | Current | Trend | Notes/Action |
|--------|--------|---------|-------|--------------|
| Hallucination Rate | <5% | 4.3% | ↘︎ | OK |
| Toxicity Incidents | 0 | 1 | ↗︎ | Investigating prompt injection |
| Acceptance Rate | >55% | 48% | ↘︎ | Launch follow-up test |
| Drift Score (KS) | <0.2 | 0.35 | ↗︎ | Recalculate embeddings |

Review weekly; convert action items into Jira/Trello tasks.

---

## 🛡️ Red-Teaming Playbook

1. Define threat scenarios (prompt injection, PII exfiltration, jailbreaks).
2. Create attack vectors (scripts, automation tools).
3. Run tests in staging; capture prompts/responses.
4. Score severity, log incidents, prioritize fixes.
5. Share highlights + mitigations in eval review.

Maintain a repository of past attacks + resolved patterns.

---

## 🌡️ Drift & Regression Monitoring

| Signal | Tooling | Alert Threshold | Response |
|--------|---------|-----------------|----------|
| Data Drift | Evidently, WhyLabs | KS > 0.3 | Investigate data pipeline |
| Prediction Drift | Custom dashboards | 10% delta vs. rolling avg | Trigger retraining |
| Feature Drift | Feature store stats | Missing value >5% | Backfill/recompute |

Link alerts to Slack/PagerDuty with clear runbooks.

---

## ✅ Week 8 Evaluation Checklist

- [ ] Evaluation ownership matrix agreed with stakeholders
- [ ] Test suites (golden, synthetic, safety) cataloged + versioned
- [ ] Eval board live with automated data pulls
- [ ] Red-teaming scenarios + scripts documented with owners
- [ ] Drift/monitoring alerts configured with runbooks
