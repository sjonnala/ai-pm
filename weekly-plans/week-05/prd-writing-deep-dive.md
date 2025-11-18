# PRD Writing Deep Dive

**Week 5 Reference**

A comprehensive guide for taking a raw idea and turning it into an execution-ready Product Requirements Document.

---

## 🧱 Core Structure (The "Golden 8")

| Section | Why It Matters | Tips |
|---------|----------------|------|
| **Background / Problem** | Creates shared context and urgency | Tell the story in <150 words; include customer anecdotes |
| **Goals & Success Metrics** | Keeps teams aligned on outcomes | Mix 1-2 product metrics + 1 business metric + guardrail metric |
| **User Stories / Use Cases** | Ensures user-centric design | Follow "As a ___, I want ___, so that ___"; include trigger + success criteria |
| **Functional Requirements** | Defines observable behavior | Write numbered requirements (FR-1, FR-2...); separate core vs. stretch |
| **Non-Functional Requirements** | Prevents costly rework later | Capture performance, security, privacy, localization, accessibility |
| **Edge Cases & Failure Modes** | Reduces surprises later | Force yourself to list "what if ___" scenarios; predefine fallbacks |
| **Out of Scope** | Protects timeline | Explicitly list "not in v1" to stop scope creep |
| **Open Questions & Dependencies** | Drives follow-ups | Include owner + due dates; update weekly |

> 🔁 **Iteration tip:** Draft PRD → share w/ design + eng for comments → revise → secure sign-off. The first draft rarely survives contact with the team.

---

## 🧭 Building a Sharp Problem Statement

Use the **"Situation → Complication → Opportunity" (SCO)** framing:

1. **Situation:** Current state with data (ex: "Daily active creators dropped 12% QoQ")
2. **Complication:** Why the status quo fails (ex: "Creators cite poor analytics on exit interviews")
3. **Opportunity:** Desired outcome (ex: "Give creators proactive insights so they can course-correct")

**Checklist:**
- Includes at least one quantitative data point
- Names the user persona explicitly
- Explains why now (trigger, market shift, competitive pressure)
- Ends with the proposed product direction in one sentence

---

## 🎯 Defining Success Metrics

**Metric stack:**
1. **North Star** – business outcome (ARR, retention, NPS)
2. **Product Metric** – user-level behavior (adoption, completion rate)
3. **Guardrail** – ensures we do no harm (latency, accuracy, quality)

### Example Metrics Table

| Metric | Baseline | Target | Measurement |
|--------|----------|--------|-------------|
| Weekly Active Creators | 18% | 25% (+7pp) | Product analytics |
| Feature Adoption | 0% | 60% of creators | Feature flag events |
| CSAT for Insights | 3.4 / 5 | ≥4.2 | In-product survey |
| Guardrail - Latency | 1.8s | ≤1s p95 | Synthetic monitoring |

> ✋🏻 Do not add more than 4 metrics. Anything beyond is noise for execution teams.

---

## 🧑‍💻 Writing Requirements Engineers Love

### Functional Requirements Format

```
FR-1: When a creator opens the dashboard, show a prioritized list of AI-generated insights ranked by impact score.
FR-2: Each insight must display: title, metric trend, contributing factor, recommended action.
FR-3: Users can dismiss or snooze insights; dismissed insights should not resurface for 30 days.
```

**Guidelines:**
- Start with the trigger / user action
- Describe expected behavior and system response
- Include validation rules (limits, thresholds)
- Add acceptance criteria for complex flows (Given / When / Then)

### Non-Functional Requirements Examples

| Type | Requirement |
|------|-------------|
| Performance | p95 latency < 1.5s for insight generation |
| Security | Follow SOC2 logging requirements; redact PII in logs |
| Privacy | Data residency in region of user access |
| Accessibility | Meet WCAG 2.1 AA for insight cards |

---

## 🧪 Edge Cases, Risks, and Open Questions

### Edge Case Brainstorm Prompts
- What happens if data is delayed or missing?
- How does the system behave when the user has no historical activity?
- What if an upstream dependency fails?
- How do we prevent duplicate notifications?
- How do we revert if the experiment underperforms?

List each edge case with:
1. **Scenario**
2. **Expected behavior / fallback**
3. **Owner**

### Risk Register Example

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Data warehouse latency spikes | Medium | High | Precompute key metrics hourly |
| Ambiguous prioritization logic | High | Medium | Hold workshop with data science |

---

## 📣 Communication & Stakeholder Alignment

| Audience | What They Need | Artifact |
|----------|----------------|----------|
| Execs | Outcome, cost, timeline | 1-page summary + key metrics |
| Engineering | Requirements, constraints, dependencies | Full PRD |
| Design | Scenarios, user journeys, edge cases | PRD + annotated flows |
| GTM | Launch messaging, training needs | PRD summary + FAQ |

**Cadence:** Kickoff review → milestone check-ins → readiness review before build.

---

## ✅ PRD Quality Checklist

- [ ] Problem is data-backed and time-bound
- [ ] Metrics include success + guardrails
- [ ] Requirements map to user stories
- [ ] Edge cases + failure modes documented
- [ ] Dependencies and owners listed
- [ ] Hand-off plan to Eng/Design is explicit
- [ ] Document version history + approvals

**If you cannot check all boxes, iterate before calling the PRD "done."**
