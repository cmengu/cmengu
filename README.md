# Hi, I'm Chen Meng 👋
AI Engineer — building agentic systems that actually get evaluated, not just demonstrated.

Currently targeting roles in agentic AI and climate tech. Open to internships at companies where AI ships to production.

---

## What I Build

### 🤖 CareWatch — Multi-Agent AI for Elderly Care
`LangGraph · ChromaDB · Groq · BM25 · Docker`

Multi-agent pipeline: LangGraph orchestrator routes anomalies to specialist agents (FallAgent / MedAgent / RoutineAgent), retrieves clinical context via hybrid RAG, and fires Telegram alerts.

**Measured, not claimed:**
- F1 = 1.000 / FNR = 0.000 across 20 deterministic eval scenarios
- 3 agent architectures benchmarked (custom · LangGraph · LangChain)
- RAG MRR = 0.960 across 25 ground-truth queries
- Query decomposition + BM25 + RRF hybrid retrieval (Phase 4)
- `docker-compose up` single-command deployment

---

### ⚙️ WarpSense — Multi-Agent Weld Quality Assessment
`LangGraph · ChromaDB · BM25 · Groq · FastAPI · PostgreSQL`

Multi-agent pipeline for real-time LOF/LOP defect detection on ESP32 sensor data. LangGraph coordinator routes to three domain specialists (ThermalAgent / GeometryAgent / ProcessStabilityAgent). Deterministic SummaryAgent merges results with a safety-first priority override — the final disposition never depends on the LLM alone.

**Measured, not claimed:**
- FNR = 0.000 across 24 deterministic eval scenarios (4 categories, boundary-value test cases)
- 3 agent architectures benchmarked: single agent · LangGraph · LangChain
- 8 prompt variants evaluated (A/B/C dimensions: format · context · self-check)
- BM25 + dense hybrid retrieval with RRF merge over 63 domain-specific KB chunks (AWS D1.1 · ISO 5817 · IACS Rec.47)
- RAG eval: 25 ground-truth query→chunk pairs at k=6 operating point
- LangSmith observability via zero-instrumentation env var toggle
- Full-stack integration: FastAPI routes · PostgreSQL · Next.js frontend

---

## Stack
```
Agents       LangGraph · LangChain · custom pipelines
LLMs         Groq (llama-3.3-70b) · prompt variant A/B testing
RAG          ChromaDB · BM25 · Reciprocal Rank Fusion · sentence-transformers
Eval         deterministic F1/FNR · MRR · Precision@k · latency p50/p95
Infra        Docker · FastAPI · PostgreSQL · SQLite · Python 3.12
```

---

## How I Think About AI Systems

I separate deterministic metrics (pipeline F1, FNR) from probabilistic metrics (LLM alignment). In a safety system, FNR=0.000 is the design goal — a missed weld defect or a missed fall is worse than a false alarm. Everything else is supporting evidence.

When hybrid retrieval (BM25 + dense) came in at MRR=0.933 vs baseline 0.960 on CareWatch, I didn't ship it to production. I kept it as opt-in, documented why it regresses at 47 documents, and documented the cross-encoder upgrade path. That's the difference between building a feature and building a system.

In WarpSense, the LOF/LOP safety override is deterministic and layered three times independently — in each specialist, in SummaryAgent, and in the LangChain fallback path. The LLM can fail completely and the safety gate still holds. Eval scenarios test the threshold floor (e.g. `heat_diss_max_spike=41.0` against a threshold of 40.0), not the interior, because that's where systems actually break.

---

## Currently Learning
- Cross-encoder reranking (`sentence-transformers/ms-marco-MiniLM-L-6-v2`)
- LangSmith observability for production LangGraph traces
- LoRA / instruction tuning (exploring for domain adaptation)

---

## Contact
LinkedIn · Email## Hi there 👋

<!--
**cmengu/cmengu** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
