# RAG PRD Blueprint

**Week 5 Reference**

This blueprint helps you capture every Retrieval-Augmented Generation (RAG) requirement inside your PRD so engineers know what to build and evaluate.

---

## 🧱 End-to-End Architecture

```
User Request → Orchestrator → Retrieval Layer → Context Builder → LLM → Post-Processing → Response + Logging
```

| Layer | Key Decisions | PRD Questions |
|-------|---------------|---------------|
| **Retrieval Source** | Docs, knowledge base, DB tables, APIs | What repositories? Who owns access? |
| **Indexing Pipeline** | Chunking, embedding, sync cadence | What jobs keep the index fresh? |
| **Vector Store** | Pinecone, PGVector, Weaviate, Vespa | Where is it hosted? SLA? |
| **Orchestration** | LangChain, custom service, AWS Bedrock | How do components connect? |
| **LLM** | Model choice, context window | Does context fit? Need compression? |
| **Post-Processing** | Citation formatting, output schema | How do we enforce structure + tone? |

> 📌 Include a diagram or sequence chart in your PRD if the system is new to stakeholders.

---

## 📚 Retrieval Design

### Document Preparation Checklist
- [ ] Identify document types + formats (PDF, HTML, tickets)
- [ ] Normalize text (strip HTML, remove boilerplate, preserve tables)
- [ ] Define chunking rules (token size, overlap, hierarchical chunks)
- [ ] Tag metadata (source, author, updated_at, permissions)
- [ ] Establish refresh cadence (real-time, hourly, daily)

### Retrieval Configuration Table

| Setting | Default | Notes |
|---------|---------|-------|
| Chunk Size | 500 tokens | Overlap 50 tokens for continuity |
| Embedding Model | `text-embedding-3-large` | Evaluate vs. smaller model for cost |
| Top-K Matches | 5 | Use MMR for diversity |
| Filters | Permission scope = user org | Avoid cross-tenant leakage |
| Cache Strategy | 5 min TTL | Warm cache for top documents |

---

## 🧠 Prompt & Context Strategy

| Component | Description | PRD Guidance |
|-----------|-------------|--------------|
| **System Prompt** | Governs tone + behavior | Include example snippet + style rules |
| **Context Template** | How retrieved docs are inserted | Example: `<doc_title>\n<doc_excerpt>` |
| **Instruction Layering** | Order of system → developer → user prompts | Document priority rules |
| **Output Schema** | JSON, markdown, natural language | Provide explicit schema + validation |

> ✂️ Use **context compression** (summary models, keyword extraction) if RAG context regularly exceeds 4k tokens. Capture this decision in the PRD.

---

## 📏 Evaluation Plan for RAG

| Area | Offline Eval | Online Metrics |
|------|--------------|----------------|
| **Retrieval Quality** | Recall@K, MRR on labeled dataset | % of responses citing relevant doc |
| **Generation Quality** | Human rubric (accuracy, completeness), LLM-as-judge | Acceptance rate, edit rate |
| **Groundedness** | % sentences backed by docs | Hallucination rate <5% |
| **Latency** | Retrieval + LLM latency budgets | p95 end-to-end <3s |
| **Cost** | Tokens per response, embedding cost | $ per answer |

**Human Eval Rubric Sample**
- Correct answer? (Y/N)
- Citations valid? (Y/N)
- Completeness score (1-5)
- Tone/style on-brand? (1-5)

---

## 🔐 Security & Permissions

| Concern | Questions | Mitigation |
|---------|-----------|------------|
| **Multi-tenant data** | Can users see other tenants' docs? | Filter vector store by tenant/org ID |
| **Access Revocation** | What happens when a doc access is removed? | Rebuild or reindex nightly + real-time delete hooks |
| **PII / Secrets** | Are sensitive docs chunked + stored? | Obfuscate before embedding; encrypt at rest |
| **Audit Logs** | Do we log retrieval + response metadata? | Store prompt, doc IDs, and response ID |

---

## 🧯 Failure Modes & Fallbacks

| Scenario | Detection | Fallback |
|----------|-----------|----------|
| Retrieval returns zero docs | `top_k_results == 0` | Ask clarification OR use default knowledge |
| Embedding service down | Error from embedding API | Switch to cached embeddings / backup model |
| Vector store latency spikes | p95 > SLA threshold | Serve last-known-good answer; degrade gracefully |
| Citation mismatch | Validator detects mismatch | Insert disclaimer + highlight low confidence |

Document each fallback path and user messaging inside the PRD so design + eng can align early.

---

## ✅ RAG PRD Checklist

- [ ] Data ingestion + chunking plan documented with owners
- [ ] Vector store + embedding choices justified
- [ ] Retrieval parameters (chunk size, top-k, filters) captured
- [ ] Prompt template, context strategy, and output schema included
- [ ] Evaluation plan covers retrieval + generation + groundedness
- [ ] Fallbacks defined for zero results, low confidence, outages
- [ ] Security + permissions requirements approved

Use this blueprint alongside your AI PRD template to make RAG initiatives buildable.
