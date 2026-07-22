# Hi, I'm Chen Meng 👋

📍 **Singapore** &nbsp;|&nbsp; 🤖 **AI systems engineer** &nbsp;|&nbsp; 🎯 **Agentic AI · Climate tech**

Building agentic pipelines where a **deterministic safety floor sits *above* the LLM, not inside it** — so the safe disposition holds even on a total model failure.

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![LangGraph](https://img.shields.io/badge/-LangGraph-FF6B35?style=flat-square)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Qdrant](https://img.shields.io/badge/-Qdrant_·_ChromaDB-DC143C?style=flat-square)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![PyTorch](https://img.shields.io/badge/-PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/-ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=next.js&logoColor=white)

## Start Here

- 🛡️ **[WarpSense](https://github.com/cmengu/warpsense)** — multi-agent weld-defect detection with a safety override that fires even if the LLM fails
- 🫀 **[NeonatalGuard](https://github.com/cmengu/Neonatal)** — agentic early-sepsis decision support; every alert traces to one HRV z-score and one agent node
- 🧓 **[CareWatch](https://github.com/cmengu/CareWatch)** — live eldercare check-in platform for Singapore Active Ageing Centres · [demo](https://carewatch-blue.vercel.app/dashboard.html)
- 🔌 **[GroundWire](https://github.com/cmengu/GroundWire)** — reliability middleware for web agents, added in a single import

## Projects

### 🩺 Safety-Critical Agent Systems
*Multi-agent pipelines where a deterministic floor overrides the model on anything safety-relevant.*

- 🛡️ **[WarpSense](https://github.com/cmengu/warpsense)** — LangGraph coordinator fans out to thermal / geometry / process specialists; a threshold fallback holds the safety call on total model failure
- 🫀 **[NeonatalGuard](https://github.com/cmengu/Neonatal)** — 6-node pipeline (Qdrant hybrid retrieval → cross-encoder rerank → instructor-enforced reasoning → Pydantic protocol gate); a rule-based self-check fires before any LLM output is read
- 🧓 **[CareWatch](https://github.com/cmengu/CareWatch)** — multi-tenant PWA for 20+ Active Ageing Centres, full data isolation via PostgreSQL row-level security
- 👁️ **[CareWatch Backend](https://github.com/cmengu/CareWatch-backend)** — 5-agent monitoring layer, BM25 + ChromaDB hybrid RAG (MRR 0.96), YOLO11x edge pose skeletons, PDPA-compliant by architecture

### ⚙️ Agent Reliability & Spec Harnesses
*Middleware and kernels that keep long-running agents honest.*

- 🔌 **[GroundWire](https://github.com/cmengu/GroundWire)** — taps the live SSE stream, scores trajectory every 5 steps, self-heals in a sandbox before retry; degrades gracefully with zero credentials
- ⚓ **[Ballast](https://github.com/cmengu/Ballast)** — spec-verification kernel; locks an execution contract and scores every node boundary on tool / constraint / intent, hot-swappable mid-run
- 📜 **[spec-covenant](https://github.com/cmengu/spec-covenant)** — agents implement strictly against a conversational contract; the spec outlasts every model upgrade
- 🧩 **[Harness-Scaffolding](https://github.com/cmengu/Harness-Scaffolding)** — a harness that orchestrates other harnesses (a cross-model adversarial "Council")

### 🔬 Research & Automation Agents

- 🧠 **[Agnes-Beta](https://github.com/cmengu/Agnes-Beta)** — multi-agent research-as-a-service with persistent memory and a debate-style critic scored across four axes
- 🐝 **[Research-Swarm](https://github.com/cmengu/Research-Swarm)** — competitive-intelligence pipeline (Claude workers + critic) for biotech / pharma programs

### 📱 Models & On-Device

- 🤖 **[FunctionGemma](https://github.com/cmengu/Google-functionGemma-Hackathon)** — on-device function calling on a 270M model via Cactus, Gemini fallback · **Top 5, Cactus × Google DeepMind hackathon**

## Connect

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ng-chen-meng-100abc/)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:ngchenmeng1@gmail.com)
[![CareWatch Live](https://img.shields.io/badge/-CareWatch_Live-000000?style=flat-square&logo=vercel&logoColor=white)](https://carewatch-blue.vercel.app/dashboard.html)
