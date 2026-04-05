# Hi, I'm Chen Meng 👋

AI systems engineer. Building agentic pipelines where deterministic safety sits above the LLM, not inside it. Targeting internships in **agentic AI** and **climate tech** 

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
[![CareWatch Live](https://img.shields.io/badge/CareWatch_Live-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://carewatch-blue.vercel.app/dashboard.html)

---

## Projects

### [WarpSense](https://github.com/cmengu/warpsense) — Multi-Agent Weld Quality Assessment
`LangGraph` `PostgreSQL` `FastAPI` `LangSmith` `Next.js`

Real-time LOF/LOP defect detection on ESP32 sensor data for shipyard inspection. A LangGraph coordinator fans out to three domain specialists (ThermalAgent, GeometryAgent, ProcessStabilityAgent) and a deterministic SummaryAgent merges results with a safety-first priority override. A threshold-based fallback fires independently of the LLM, so the safety disposition holds even on a complete model failure. The system was benchmarked across three architectures (linear, LangGraph fan-out, tool-calling) against 24 deterministic scenarios before the design was finalised.

---

### [NeonatalGuard](https://github.com/cmengu/neonatalguard) — Agentic Clinical Decision Support for Early-Onset Sepsis
`LangGraph` `Qdrant` `ONNX` `instructor` `GitHub Actions` `Docker`

End-to-end agentic system for early detection of neonatal deterioration from ECG-derived HRV signals. A 6-node LangGraph pipeline runs Qdrant hybrid retrieval, cross-encoder reranking, instructor-enforced LLM reasoning, and a Pydantic protocol compliance gate before writing to episodic memory. A rule-based self-check node fires before any LLM output is read, ensuring critical alerts cannot be suppressed by a bad model response. Every alert is traceable back to a specific HRV z-score, a retrieved chunk, and a specific agent node.

---

### [CareWatch](https://github.com/cmengu/carewatch) — Eldercare Volunteer Check-in Platform
`React` `Vite` `PWA` `Supabase` `PostgreSQL`

Multi-tenant community eldercare platform built for Active Ageing Centres in Singapore. Volunteers conduct daily wellness check-ins on assigned seniors through a PWA; no app store, no installation, runs on any budget Android browser. AAC staff monitor coverage, review flags, and manage escalations in real time, with full data isolation across 20+ AACs enforced at the database level through PostgreSQL Row Level Security.

### [CareWatch Backend](https://github.com/cmengu/carewatch-backend) — Multi-Agent AI Monitoring Layer
`LangGraph` `ChromaDB` `Groq` `BM25` `Docker` `FastAPI`

Production-deployed ([live](https://carewatch-blue.vercel.app/dashboard.html)) agentic monitoring layer for the CareWatch platform. A 5-agent LangGraph pipeline routes anomalies to domain specialists (FallAgent, MedAgent, ChronicAgent, RoutineAgent, SummaryAgent). The hybrid RAG layer combines BM25 and ChromaDB with reciprocal rank fusion, firing separate retrievals per anomaly type so exact clinical term matches are not lost to semantic drift, achieving MRR of 0.960 across 25 ground-truth queries. YOLO11x pose estimation converts raw video to abstract skeletons at the edge; no pixel data is stored, and PII is stripped before Telegram alerts while keeping the internal audit log fully queryable. PDPA-compliant by architecture.

---

### [GroundWire](https://github.com/cmengu/groundwire) — Reliability Middleware for Web Agents
`Python` `GPT-4o` `Supabase` `Pydantic v2`

Reliability middleware for web agents (TinyFish is one example) that adds one import and requires no new infrastructure. It taps the live SSE event stream and handles the failure modes that kill production agents silently: trajectory is scored every 5 steps on a 4-axis rubric with a dual-model gate that takes the more conservative score before any replan fires; self-healing generates a hypothesis, validates it in a sandbox, and commits a confirmed fix before the agent retries; post-stream bot-block detection classifies Cloudflare, DataDome, and CAPTCHA challenges and auto-retries on a stealth profile. Cross-agent memory means confirmed site quirks are shared across runs — cold-start navigation dropped from 11 steps to 6 on warm runs in benchmarks. Every feature degrades gracefully; the run completes even with no credentials.

---

### [Ballast](https://github.com/cmengu/ballast) — Spec-Driven Execution Harness for Multi-Agent Systems
`Python` `FastAPI` `pydantic-ai`

A spec-verification kernel for long-running agentic systems. Write an execution contract through a short conversation (intent, success criteria, constraints, allowed tools) and the system locks it before any agent runs. A trajectory checker scores every node boundary against the locked spec across three dimensions: tool compliance, constraint adherence, and intent alignment. When drift is detected, a critic agent diagnoses the failure before a replan fires. Live spec updates can be injected between nodes without stopping the run; the version hash in the audit log changes at exactly the node where the update landed. The spec outlasts every model upgrade — the contract is the stable artefact, not the model.

---

### [FunctionGemma](https://github.com/cmengu/functiongemma) — On-Device Function Calling · Top 5, Cactus x Google DeepMind Hackathon
`Python` `Gemini 2.5 Flash`

On-device function-calling system using a 270M parameter model via the Cactus runtime, with Gemini 2.5 Flash as cloud fallback. Ranked top 5 on the evaluation leaderboard at AI Tinkerers and AI Nexus Singapore. Accuracy gains came from rule-based prompt hinting (time values, proper nouns, and 24-hour alarm conversions pre-injected before inference), clause splitting for compound requests so the small model handles one tool call at a time, and argument post-processing to correct the model's systematic errors on time format conversion. No bigger model required.

---

## Stack

**Agents and Orchestration** — LangGraph · LangChain · instructor  
**LLMs and RAG** — Groq llama-3.3-70b · Qdrant · ChromaDB · BM25+RRF · FlashRank reranker  
**Evals and Observability** — LangSmith · GitHub Actions CI · Pydantic v2  
**Infra and ML** — Docker · FastAPI · ONNX · PyTorch · HuggingFace PEFT/LoRA
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

I separate **deterministic metrics** (pipeline F1, FNR) from **probabilistic metrics** (LLM alignment). In a safety system, FNR=0.000 is the design goal — a missed weld defect, a missed fall, or a missed neonatal deterioration event is worse than a false alarm.

In WarpSense, the LOF/LOP safety override is deterministic and layered three times independently — in each specialist, in SummaryAgent, and in the LangChain fallback path. The LLM can fail completely and the safety gate still holds. Eval scenarios test the threshold floor (e.g. `heat_diss_max_spike=41.0` against a threshold of 40.0), not the interior, because that's where systems actually break.

In NeonatalGuard, the same principle applies at the protocol layer: instructor enforces schema on every LLM call, the self-check node applies rule-based RED overrides independently of the LLM, and the Pydantic `model_validator` flags non-protocol actions rather than silently dropping them. Every alert is traceable back to a specific HRV z-score, a retrieved chunk, and a specific agent node.

---

## 🌱 Currently Building

- **Cross-encoder reranking** in production retrieval (`ms-marco-MiniLM-L-12-v2`)
- **QLoRA domain adaptation** — parameter-efficient fine-tuning on M2 MacBook Air
- **LangSmith SLOs** — cost-per-query tracking and latency regression detection in CI

---

## 📬 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
