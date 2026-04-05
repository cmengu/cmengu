# Hi, I'm Chen Meng 👋

AI systems engineer. Building agentic pipelines where deterministic safety sits above the LLM, not inside it. Targeting internships in **agentic AI** and **climate tech**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
[![CareWatch Live](https://img.shields.io/badge/CareWatch_Live-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://carewatch-blue.vercel.app/dashboard.html)

---

## Projects

### [WarpSense](https://github.com/cmengu/warpsense) — Multi-Agent Weld Quality Assessment

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-F5A623?style=flat-square)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)

Real-time LOF/LOP defect detection on ESP32 sensor data for shipyard inspection. A LangGraph coordinator fans out to three domain specialists (ThermalAgent, GeometryAgent, ProcessStabilityAgent) and a deterministic SummaryAgent merges results with a safety-first priority override. A threshold-based fallback fires independently of the LLM, so the safety disposition holds even on a complete model failure. The system was benchmarked across three architectures (linear, LangGraph fan-out, tool-calling) against 24 deterministic scenarios before the design was finalised.

---

### [NeonatalGuard](https://github.com/cmengu/neonatalguard) — Agentic Clinical Decision Support for Early-Onset Sepsis

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![Qdrant](https://img.shields.io/badge/Qdrant-DC143C?style=flat-square)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![instructor](https://img.shields.io/badge/instructor-8A2BE2?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/CI-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

End-to-end agentic system for early detection of neonatal deterioration from ECG-derived HRV signals. A 6-node LangGraph pipeline runs Qdrant hybrid retrieval, cross-encoder reranking, instructor-enforced LLM reasoning, and a Pydantic protocol compliance gate before writing to episodic memory. A rule-based self-check node fires before any LLM output is read, ensuring critical alerts cannot be suppressed by a bad model response. Every alert is traceable back to a specific HRV z-score, a retrieved chunk, and a specific agent node.

---

### [CareWatch](https://github.com/cmengu/carewatch) — Eldercare Volunteer Check-in Platform

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=pwa&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

Multi-tenant community eldercare platform built for Active Ageing Centres in Singapore. Volunteers conduct daily wellness check-ins on assigned seniors through a PWA; no app store, no installation, runs on any budget Android browser. AAC staff monitor coverage, review flags, and manage escalations in real time, with full data isolation across 20+ AACs enforced at the database level through PostgreSQL Row Level Security.

### [CareWatch Backend](https://github.com/cmengu/carewatch-backend) — Multi-Agent AI Monitoring Layer

![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![ChromaDB](https://img.shields.io/badge/ChromaDB-6A0DAD?style=flat-square)
![Groq](https://img.shields.io/badge/Groq-00C4B4?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-FF6B6B?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

Production-deployed ([live](https://carewatch-blue.vercel.app/dashboard.html)) agentic monitoring layer for the CareWatch platform. A 5-agent LangGraph pipeline routes anomalies to domain specialists (FallAgent, MedAgent, ChronicAgent, RoutineAgent, SummaryAgent). The hybrid RAG layer combines BM25 and ChromaDB with reciprocal rank fusion, firing separate retrievals per anomaly type so exact clinical term matches are not lost to semantic drift, achieving MRR of 0.960 across 25 ground-truth queries. YOLO11x pose estimation converts raw video to abstract skeletons at the edge; no pixel data is stored, and PII is stripped before Telegram alerts while keeping the internal audit log fully queryable. PDPA-compliant by architecture.

---

### [GroundWire](https://github.com/cmengu/groundwire) — Reliability Middleware for Web Agents

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenAI](https://img.shields.io/badge/GPT--4o-412991?style=flat-square&logo=openai&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic_v2-E92063?style=flat-square)

Reliability middleware for web agents (TinyFish is one example) that adds one import and requires no new infrastructure. It taps the live SSE event stream and handles the failure modes that kill production agents silently: trajectory is scored every 5 steps on a 4-axis rubric with a dual-model gate that takes the more conservative score before any replan fires; self-healing generates a hypothesis, validates it in a sandbox, and commits a confirmed fix before the agent retries; post-stream bot-block detection classifies Cloudflare, DataDome, and CAPTCHA challenges and auto-retries on a stealth profile. Cross-agent memory means confirmed site quirks are shared across runs — cold-start navigation dropped from 11 steps to 6 on warm runs in benchmarks. Every feature degrades gracefully; the run completes even with no credentials.

---

### [Agnes-Beta](https://github.com/cmengu/Agnes-Beta) - Research-as-a-Service for Deep Research
 
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![OpenAI Compatible](https://img.shields.io/badge/OpenAI--compatible-412991?style=flat-square&logo=openai&logoColor=white)
 
A multi-agent research and writing pipeline with a persistent memory layer: user run history, distilled skill summaries, and a cross-goal source cache that prevents redundant fetches across sessions. Goals are validated against a written constitution before any compute is spent; research sub-tasks run in parallel with prompt-injection sanitisation and a Playwright fallback for JS-heavy pages. A debate-style critic scores output across four axes and routes targeted rechecks back into the same thread pool; every delivery is prefixed with a quality badge showing confidence, critic score, revision count, and source coverage.

---

### [Ballast](https://github.com/cmengu/ballast) — Spec-Driven Execution Harness for Multi-Agent Systems

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![pydantic-ai](https://img.shields.io/badge/pydantic--ai-E92063?style=flat-square)

A spec-verification kernel for long-running agentic systems. Write an execution contract through a short conversation (intent, success criteria, constraints, allowed tools) and the system locks it before any agent runs. A trajectory checker scores every node boundary against the locked spec across three dimensions: tool compliance, constraint adherence, and intent alignment. When drift is detected, a critic agent diagnoses the failure before a replan fires. Live spec updates can be injected between nodes without stopping the run; the version hash in the audit log changes at exactly the node where the update landed. 

---

### [spec-covenant](https://github.com/cmengu/spec-covenant) — Spec-Driven System Implementation
 
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![pydantic-ai](https://img.shields.io/badge/pydantic--ai-E92063?style=flat-square)
 
Write a contract through a short conversation and agents implement strictly against it. A verification agent scores every node boundary against the locked spec; a critic agent diagnoses failures before any replan fires. The spec outlasts every model upgrade — the contract is the stable artefact, not the model.

---

### [FunctionGemma](https://github.com/cmengu/functiongemma) — On-Device Function Calling · Top 5, Cactus x Google DeepMind Hackathon

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini_2.5_Flash-4285F4?style=flat-square&logo=google&logoColor=white)

On-device function-calling system using a 270M parameter model via the Cactus runtime, with Gemini 2.5 Flash as cloud fallback. Ranked top 5 on the evaluation leaderboard at AI Tinkerers and AI Nexus Singapore. Accuracy gains came from rule-based prompt hinting (time values, proper nouns, and 24-hour alarm conversions pre-injected before inference), clause splitting for compound requests so the small model handles one tool call at a time, and argument post-processing to correct the model's systematic errors on time format conversion. No bigger model required.

---

## Stack

### Agents and Orchestration
![LangGraph](https://img.shields.io/badge/LangGraph-FF6B35?style=for-the-badge)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge)
![instructor](https://img.shields.io/badge/instructor-8A2BE2?style=for-the-badge)

### LLMs and RAG
![Groq](https://img.shields.io/badge/Groq_llama--3.3--70b-00C4B4?style=for-the-badge)
![Qdrant](https://img.shields.io/badge/Qdrant-DC143C?style=for-the-badge)
![ChromaDB](https://img.shields.io/badge/ChromaDB-6A0DAD?style=for-the-badge)
![BM25+RRF](https://img.shields.io/badge/BM25_+_RRF-FF6B6B?style=for-the-badge)
![FlashRank](https://img.shields.io/badge/FlashRank_reranker-F5A623?style=for-the-badge)

### Evaluation and Observability
![LangSmith](https://img.shields.io/badge/LangSmith-F5A623?style=for-the-badge)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions_CI-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic_v2-E92063?style=for-the-badge)

### Infra and ML
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=for-the-badge&logo=onnx&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace_PEFT_LoRA-FFD21E?style=for-the-badge)

---

## Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
