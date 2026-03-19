# Hi, I'm Chen Meng 👋

**AI Engineer** — building agentic systems that get evaluated, not just demonstrated.

Targeting internships in **agentic AI** and **climate tech** — specifically roles where AI ships to production and evals block bad merges.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your@email.com)
[![CareWatch Live](https://img.shields.io/badge/CareWatch_Live-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://carewatch-blue.vercel.app)

---

## 🛠️ What I Build

### 🤖 CareWatch — Multi-Agent AI for Elderly Care

> **Hackathon · NUS · Problem Statement 2: AI for Multimodal Remote Health & Wellness Monitoring**

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![ChromaDB](https://img.shields.io/badge/ChromaDB-6A0DAD?style=flat-square)
![Groq](https://img.shields.io/badge/Groq-00C4B4?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-FF6B6B?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

5-agent LangGraph pipeline routing anomalies to specialist agents (FallAgent · MedAgent · ChronicAgent · RoutineAgent · SummaryAgent). Hybrid RAG layer (BM25 + ChromaDB + RRF) retrieves clinical context grounded in 47 verified facts. YOLO11x pose estimation converts raw video to abstract skeletons — no pixel data stored, PDPA-compliant.

**Measured, not claimed:**

| Metric | Value |
|--------|-------|
| F1 / FNR | 1.000 / 0.000 across 20 deterministic scenarios |
| RAG MRR | 0.960 across 25 ground-truth queries |
| Agent architectures benchmarked | 3 (custom · LangGraph · LangChain) |
| Retrieval | BM25 + dense + RRF hybrid, k=60 |
| Deployment | `docker-compose up` single-command |

---

### ⚙️ WarpSense — Multi-Agent Weld Quality Assessment

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-F5A623?style=flat-square)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)

Real-time LOF/LOP defect detection on ESP32 sensor data. LangGraph coordinator routes to three domain specialists (ThermalAgent · GeometryAgent · ProcessStabilityAgent). Deterministic SummaryAgent merges results with a safety-first priority override — the final disposition never depends on the LLM alone.

**Measured, not claimed:**

| Metric | Value |
|--------|-------|
| FNR (safety-critical) | 0.000 across 24 deterministic eval scenarios |
| Agent architectures benchmarked | 3 (single · LangGraph · LangChain) |
| Prompt variants evaluated | 8 (format · context · self-check dimensions) |
| KB chunks | 63 (AWS D1.1 · ISO 5817 · IACS Rec.47) |
| RAG eval | 25 ground-truth query→chunk pairs at k=6 |
| Observability | LangSmith via zero-instrumentation env var toggle |

---

### 🏥 NeonatalGuard — Agentic Clinical Decision Support

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![Qdrant](https://img.shields.io/badge/Qdrant-DC143C?style=flat-square)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![instructor](https://img.shields.io/badge/instructor-8A2BE2?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/CI-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

End-to-end agentic system for early detection of neonatal deterioration from ECG-derived HRV signals. 6-node LangGraph agent runs Qdrant hybrid retrieval → cross-encoder reranking → instructor-enforced LLM reasoning → Pydantic protocol compliance gate → episodic memory write. FNR=0.000 for RED alerts is a hard design constraint enforced by a deterministic self-check node independent of the LLM.

**Measured, not claimed:**

| Metric | Value |
|--------|-------|
| F1 / FNR | 1.000 / 0.000 across 24 deterministic scenarios (8 RED · 8 YELLOW · 8 GREEN) |
| RAG MRR | 0.960 · hybrid dense + BM25 sparse + RRF → FlashRank cross-encoder reranker |
| Output reliability | instructor + Pydantic v2 schema enforcement, auto-retry on failure |
| Protocol compliance | Pydantic `model_validator` gates every recommended action |
| CI | GitHub Actions evals on every commit · merge blocked on F1 regression · <30s · zero API cost |
| Memory | Per-patient episodic memory (SQLite) surfaced in every agent reasoning step |
| Observability | LangSmith per-node traces · cost tracking · latency SLOs |
| Fine-tuning | 4-way comparison: base prompt · instruction tuned · LoRA · QLoRA |
| Deployment | `docker-compose up` — API + Qdrant + eval runner |

---

## 🧰 Stack

### Agents & Orchestration
![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=for-the-badge)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge)
![instructor](https://img.shields.io/badge/instructor-8A2BE2?style=for-the-badge)

### LLMs & RAG
![Groq](https://img.shields.io/badge/Groq_llama--3.3--70b-00C4B4?style=for-the-badge)
![Qdrant](https://img.shields.io/badge/Qdrant-DC143C?style=for-the-badge)
![ChromaDB](https://img.shields.io/badge/ChromaDB-6A0DAD?style=for-the-badge)
![BM25+RRF](https://img.shields.io/badge/BM25_+_RRF-FF6B6B?style=for-the-badge)
![FlashRank](https://img.shields.io/badge/FlashRank_reranker-F5A623?style=for-the-badge)

### Evaluation & Observability
![LangSmith](https://img.shields.io/badge/LangSmith-F5A623?style=for-the-badge)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions_CI-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic_v2-E92063?style=for-the-badge)

### Infra & ML
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=for-the-badge&logo=onnx&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace_PEFT_LoRA-FFD21E?style=for-the-badge)

---

## 🧠 How I Think About AI Systems

I separate **deterministic metrics** (pipeline F1, FNR) from **probabilistic metrics** (LLM alignment). In a safety system, FNR=0.000 is the design goal — a missed weld defect, a missed fall, or a missed neonatal deterioration event is worse than a false alarm. Everything else is supporting evidence.

When hybrid retrieval (BM25 + dense) came in at MRR=0.933 vs baseline 0.960 on CareWatch, I didn't ship it to production. I kept it as opt-in, documented why it regresses at 47 documents, and documented the cross-encoder upgrade path. That's the difference between building a feature and building a system.

In WarpSense, the LOF/LOP safety override is deterministic and layered three times independently — in each specialist, in SummaryAgent, and in the LangChain fallback path. The LLM can fail completely and the safety gate still holds. Eval scenarios test the threshold floor (e.g. `heat_diss_max_spike=41.0` against a threshold of 40.0), not the interior, because that's where systems actually break.

In NeonatalGuard, the same principle applies at the protocol layer: instructor enforces schema on every LLM call, the self-check node applies rule-based RED overrides independently of the LLM, and the Pydantic `model_validator` flags non-protocol actions rather than silently dropping them. Every alert is traceable back to a specific HRV z-score, a retrieved chunk, and a specific agent node.

---

## 🌱 Currently Building

- **Emissions RAG pipeline** — GHG Protocol · CSRD · SBTi · Scope 1/2/3 methodology, applying the same agentic architecture to climate tech
- **Cross-encoder reranking** in production retrieval (`ms-marco-MiniLM-L-12-v2`)
- **QLoRA domain adaptation** — parameter-efficient fine-tuning on M2 MacBook Air
- **LangSmith SLOs** — cost-per-query tracking and latency regression detection in CI

---

## 📬 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your@email.com)
