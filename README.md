# Hi, I'm Chen Meng 👋

**AI Crazed** — building agentic systems for the love of the game

Targeting internships in **agentic AI** and **climate tech** — specifically roles where AI ships to production and evals block bad merges.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
[![CareWatch Live](https://img.shields.io/badge/CareWatch_Live-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://carewatch-blue.vercel.app/dashboard.html)

---

## 🛠️ CURRENT PROJECTS

### 🤖 CareWatch — Multi-Agent AI for Elderly Care Monitoring

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![ChromaDB](https://img.shields.io/badge/ChromaDB-6A0DAD?style=flat-square)
![Groq](https://img.shields.io/badge/Groq-00C4B4?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-FF6B6B?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

5-agent LangGraph pipeline routing anomalies to specialist agents (FallAgent · MedAgent · ChronicAgent · RoutineAgent · SummaryAgent). Hybrid RAG layer (BM25 + ChromaDB + RRF) retrieves clinical context grounded in 47 verified facts. YOLO11x pose estimation converts raw video to abstract skeletons — no pixel data stored, PDPA-compliant.

| Feature | What it does |
|---------|-------------|
| 5-agent LangGraph routing | Anomalies classified by a weight-based detector and routed to the right specialist — fall, medication, chronic, or routine. SummaryAgent merges with priority override; no alert depends on a single model call. |
| Hybrid RAG (BM25 + ChromaDB + RRF) | Per-anomaly query decomposition fires separate retrievals for each deviation type. BM25 catches exact clinical term matches that semantic embeddings miss; RRF merges both lists. MRR=0.960 across 25 ground-truth queries. |
| PDPA privacy layer | YOLO11x converts raw video to abstract skeletons — no pixel data stored. PII is stripped at the Telegram alert boundary, not at storage, keeping the internal audit log queryable while ensuring real names never leave the system. |

---

### ⚙️ WarpSense — Multi-Agent Weld Quality Assessment for Shipyards

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-F5A623?style=flat-square)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)

Real-time LOF/LOP defect detection on ESP32 sensor data. LangGraph coordinator routes to three domain specialists (ThermalAgent · GeometryAgent · ProcessStabilityAgent). Deterministic SummaryAgent merges results with a safety-first priority override — the final disposition never depends on the LLM alone.

| Feature | What it does |
|---------|-------------|
| Deterministic safety override | If the LLM returns a parse failure or empty response, a threshold-based fallback fires: REWORK_REQUIRED if any feature is in the RISK band, CONDITIONAL if MARGINAL. The LLM can fail completely and FNR=0.000 holds. |
| Domain-decomposed RAG queries | Each specialist injects violation-specific numeric values into expanded queries (`heat_diss_max_spike 65.2 C/s corrective action threshold`) before BM25 and dense retrieval. Exact token matches the LLM needs for corrective actions — not just semantically related chunks. |
| Three-way architecture benchmark | WarpSenseAgent (linear), WarpSenseGraph (LangGraph fan-out), WarpSenseLangChainAgent (tool-calling) all share the same eval harness. Every architectural decision is measured against 24 deterministic scenarios, not assumed. |

---

### 🏥 NeonatalGuard — Agentic Clinical Decision Support for Early Onset Sepsis in Pre-mature Babies

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![Qdrant](https://img.shields.io/badge/Qdrant-DC143C?style=flat-square)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![instructor](https://img.shields.io/badge/instructor-8A2BE2?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/CI-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

End-to-end agentic system for early detection of neonatal deterioration from ECG-derived HRV signals. 6-node LangGraph agent runs Qdrant hybrid retrieval → cross-encoder reranking → instructor-enforced LLM reasoning → Pydantic protocol compliance gate → episodic memory write. FNR=0.000 for RED alerts is a hard design constraint enforced by a deterministic self-check node independent of the LLM.

| Feature | What it does |
|---------|-------------|
| Deterministic RED override | `self_check_node` hardcodes: `risk_score > 0.8 AND max_z > 3.0 → RED, regardless of LLM output`. Fires before any LLM self-check. The LLM cannot hallucinate a YELLOW on a critical patient — FNR(RED)=0.000 is a design constraint, not an eval result. |
| 4-specialist multi-agent routing | Signal · Brady · Clinical · Protocol agents each receive only their domain-relevant KB chunks via category-filtered retrieval. Separates HRV pattern classification from bradycardia assessment, clinical reasoning, and protocol compliance — the exact failure mode Phase 4 identified as YELLOW↔GREEN confusion. |
| CI evals blocking merge | GitHub Actions runs the full 30-scenario no-LLM eval on every commit. Merge is blocked on F1 regression. Zero API cost, <30s. Every architectural change is gated — not self-reported. |

---

### 🔌 GroundWire — Reliability Middleware for Web Agents

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenAI](https://img.shields.io/badge/GPT--4o-412991?style=flat-square&logo=openai&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic_v2-E92063?style=flat-square)

> *"TinyFish gives you the agent. GroundWire gives you the SLA."*

Reliability middleware that wraps the TinyFish web agent API — one import, seven features, zero new infrastructure. Taps the live SSE event stream and handles the failure modes that kill production agents silently.

| Feature | What it does |
|---------|-------------|
| Trajectory Validation | Scores every 5 steps on a 4-axis rubric (goal alignment · efficiency · risk · progress rate). Dual GPT-4o gate — conservative score wins. Triggers replan before drift compounds. |
| Self-Healing | Hypothesis → TinyFish sandbox → confirmed fix. Proves the fix before replanning. Never guesses. |
| Adversarial Hardening | Post-stream block detection (Cloudflare · DataDome · CAPTCHA). GPT-4o mini classifies, auto-retries on stealth profile with US proxy. |

Every feature degrades gracefully — no Supabase credentials, no OpenAI key, no TinyFish key: the system never crashes, the run always completes.

Built at the **TinyFish × OpenAI Hackathon**.

---

### 🏆 FunctionGemma — On-Device Function Calling (Cactus × Google DeepMind Hackathon)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini_2.5_Flash-4285F4?style=flat-square&logo=google&logoColor=white)

**Ranked Top 5 on the Evaluation Leaderboard** at the Cactus × Google DeepMind Hackathon (AI Tinkerers & AI Nexus, Singapore).

Competition goal: build the most accurate and fastest on-device function-calling system using a 270M parameter model (`functiongemma-270m-it`) running locally via the Cactus runtime — with Google Gemini 2.5 Flash as cloud fallback.

Given a natural language message and a tool schema, the system identifies which tool(s) to call and extracts the correct arguments as structured JSON. Evaluated on F1 (60%), on-device ratio (25%), and latency (15%) across easy / medium / hard compound requests.

| Feature | What it does |
|---------|-------------|
| Hinted prompts | Rule-based regex pre-populates time values, 24h alarm conversions, and proper nouns into the prompt before the model sees it. Reduces ambiguity and gives the 270M model maximum context in minimal tokens — the biggest single accuracy lever at this parameter count. |
| Clause splitting | Compound requests ("set an alarm and check the weather") are split into individual clauses; the model is called once per tool. Small models handle one function call at a time far more reliably than multi-tool generation in a single shot. |
| Argument post-processing | After inference: time strings normalised to HH:MM AM/PM, alarm hours recomputed from the original message (the model frequently errors on 24h conversion), reminder titles stripped of time expressions, proper-noun casing restored. Accuracy gains that don't require a bigger model. |

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
