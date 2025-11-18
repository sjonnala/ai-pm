# Conversational & Multimodal UX Deep Dive

**Week 7 Reference**

Craft lovable AI experiences by combining conversation design, multimodal cues, and proactive safety.

---

## 🗣️ Conversation Design Blueprint

| Layer | Questions | Guidelines |
|-------|-----------|------------|
| **Persona** | Who is the AI? How formal? | Define tone sliders (playful ↔ formal) |
| **Turn Taking** | How do users start, pause, resume? | Support clarifying questions + quick replies |
| **Memory** | What context persists? For how long? | Summarize sessions >200 tokens, respect privacy |
| **Error Recovery** | How do we apologize + course correct? | Offer suggestions, show transparent limitations |

Document sample dialogs for happy path + edge cases.

---

## 🧩 Multimodal Interaction Patterns

| Pattern | Use Case | Tips |
|---------|----------|------|
| **Text + Visual Annotations** | Explain UI changes, highlight insights | Pair textual summary with screenshot markup |
| **Voice + Transcript** | On-the-go workflows | Provide visual transcript + action buttons |
| **Drag & Drop Inputs** | Document understanding, creative briefs | Auto-detect file type, show extraction preview |
| **Structured Output Cards** | Task lists, analytics recaps | Use consistent tokens (status, owner, due date) |

Map which patterns belong in mobile vs. desktop surfaces.

---

## 🛡️ UX Guardrails

- Inline disclaimers for probabilistic outputs
- Confidence pills (High/Medium/Low) near every AI response
- "Show your work" toggles that expand supporting references
- Escalation buttons: "Ask human expert" or "Report issue"
- Activity log to trace AI suggestions vs. human decisions

Include copy guidelines + component references for each guardrail.

---

## 🎨 Conversation Quality Rubric

| Dimension | 1 | 3 | 5 |
|-----------|---|---|---|
| **Understanding** | Misinterprets intents | Needs clarifications often | Anticipates needs |
| **Guidance** | Dead ends | Basic instructions | Offers proactive paths |
| **Tone** | Robotic/off-brand | Neutral | On-brand, empathetic |
| **Safety** | Missing disclaimers | Some caution | Transparent + action-able |

Use rubric when reviewing transcripts or prototypes with partners.

---

## ✅ Week 7 UX Checklist

- [ ] Conversation persona + turn framework documented
- [ ] Sample dialog library (happy path + 5 edge cases) complete
- [ ] Multimodal component decisions captured with rationale
- [ ] Guardrail UI + copy guidance shared with design/eng
- [ ] Conversation quality rubric applied to prototypes weekly
