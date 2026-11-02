# Hi, I'm Chen Meng

Singapore · AI systems engineer

Excited to build agentic systems.

## Start Here

- **[WarpSense](https://github.com/cmengu/warpsense)** — multi-agent weld-defect detection with a safety override that fires even if the LLM fails
- **[NeonatalGuard](https://github.com/cmengu/Neonatal)** — agentic early-sepsis decision support; every alert traces to one HRV z-score and one agent node
- **[CareWatch](https://github.com/cmengu/CareWatch)** — live eldercare check-in platform for Singapore Active Ageing Centres · [demo](https://carewatch-blue.vercel.app/dashboard.html)
- **[GroundWire](https://github.com/cmengu/GroundWire)** — reliability middleware for web agents, added in a single import

## Projects

### Active Projects
Two world-model systems on a shared backbone — a tiered evaluation that decides the verdict, with a deterministic floor beneath the LLM — pointed at very different domains, plus a live eldercare platform.

- **[WarpSense](https://github.com/cmengu/warpsense)** — Real-time multi-agent detection of lack-of-fusion and lack-of-penetration weld defects from ESP32 sensor streams, built for shipyard inspection. A LangGraph coordinator fans out to thermal, geometry, and process-stability specialists that reason over a world model of the weld process rather than a single snapshot reading. The verdict is set by a tiered evaluation whose bottom layer is a deterministic threshold override, so the safety disposition holds even on a complete LLM failure.

- **[NeonatalGuard](https://github.com/cmengu/Neonatal)** — Agentic clinical decision support for early-onset neonatal sepsis, reading ECG-derived HRV signals to model an infant's physiological trajectory as its own world model. A 6-node LangGraph pipeline runs Qdrant hybrid retrieval, cross-encoder reranking, instructor-enforced reasoning, and a Pydantic protocol gate, with a rule-based self-check that fires before any LLM output is read. The same tiered evaluation decides the verdict here, so a critical alert can't be suppressed by a bad model response — and every alert traces back to a specific HRV z-score, retrieved chunk, and agent node.

- **[CareWatch](https://github.com/cmengu/CareWatch)** — Multi-tenant community eldercare platform for Singapore's Active Ageing Centres: volunteers run daily wellness check-ins through a PWA that needs no app store and runs on any budget Android browser. A 5-agent LangGraph monitoring layer routes anomalies to domain specialists over a BM25 + ChromaDB hybrid RAG (MRR 0.96), while YOLO11x pose estimation abstracts video to skeletons at the edge so no pixel data is ever stored. Deployed live with full data isolation across 20+ centres via PostgreSQL row-level security, PDPA-compliant by architecture · [demo](https://carewatch-blue.vercel.app/dashboard.html).

### Agent Reliability & Spec Harnesses
Middleware and kernels that keep long-running agents honest.

- **[GroundWire](https://github.com/cmengu/GroundWire)** — taps the live SSE stream, scores trajectory every 5 steps, self-heals in a sandbox before retry; degrades gracefully with zero credentials
- **[Ballast](https://github.com/cmengu/Ballast)** — spec-verification kernel; locks an execution contract and scores every node boundary on tool / constraint / intent, hot-swappable mid-run
- **[spec-covenant](https://github.com/cmengu/spec-covenant)** — agents implement strictly against a conversational contract; the spec outlasts every model upgrade
- **[Harness-Scaffolding](https://github.com/cmengu/Harness-Scaffolding)** — a harness that orchestrates other harnesses (a cross-model adversarial "Council")

### Research & Automation Agents

- **[Agnes-Beta](https://github.com/cmengu/Agnes-Beta)** — multi-agent research-as-a-service with persistent memory and a debate-style critic scored across four axes
- **[Research-Swarm](https://github.com/cmengu/Research-Swarm)** — competitive-intelligence pipeline (Claude workers + critic) for biotech / pharma programs

### Models & On-Device

- **[FunctionGemma](https://github.com/cmengu/Google-functionGemma-Hackathon)** — on-device function calling on a 270M model via Cactus, Gemini fallback · Top 5, Cactus × Google DeepMind hackathon

<details>
<summary><b>Miscellaneous & early work</b></summary>

<br>

- **[thinkoo](https://github.com/cmengu/thinkoo)** — TypeScript project
- **[MengKiaKnight](https://github.com/cmengu/MengKiaKnight)** — TypeScript project
- **[Knowledge-Base](https://github.com/cmengu/Knowledge-Base)** — personal notes and references
- **[Frontend-Scaffolding](https://github.com/cmengu/Frontend-Scaffolding)** — clinical-dashboard frontend best practices
- **[Spider-Full-Stack](https://github.com/cmengu/Spider-Full-Stack)** — full-stack take-home assignment
- **[Interesting-projs](https://github.com/cmengu/Interesting-projs)** — running list of project ideas
- **[first-website](https://github.com/cmengu/first-website)** — early web project

</details>

## Activity

![Chen Meng's contribution graph](https://gitlyy.vercel.app/api/contribution?username=cmengu&hide_border=true)

## Connect

[LinkedIn](https://www.linkedin.com/in/ng-chen-meng-100abc/) · [Email](mailto:ngchenmeng1@gmail.com) · [CareWatch Live](https://carewatch-blue.vercel.app/dashboard.html)
