# Prit Dhanani

I build LLM systems that have to survive outside a notebook: preference alignment on hardware you actually own, retrieval pipelines that get measured, and agents that take real actions and log why.

M.Sc. AI & Robotics, Hochschule Hof (Bavaria) · GenAI Engineer at INFINITE Mind GmbH, Munich

[Dhananipreet101@gmail.com](mailto:Dhananipreet101@gmail.com) · [LinkedIn](https://www.linkedin.com/in/prit-dhanani/) · [Hugging Face](https://huggingface.co/Prit84697)

---

### What I'm working on

**At INFINITE Mind** - production RAG for enterprise clients (hybrid retrieval, reranking, live monitoring) and alignment pipelines that run fully on-premise, with no external API calls.

**Master's thesis** - agentic AI. Looking for a thesis position from October 2026 at the intersection of LLMs, MLOps and applied AI.

**Currently curious about** - evaluation that predicts production behaviour instead of flattering the model, multi-agent orchestration, and how much useful reasoning you can get under hard memory and privacy constraints.

---

### Selected work

#### [Deck Engine](https://github.com/preetdhanani/Trelis--dacke-engine)

Turns a plain-language brief into a brand-consistent, editable `.pptx`, unattended.

The problem is not generating slide copy, it's stopping a language model from quietly destroying a locked template. So the model never touches design: it emits text and data only, while a deterministic engine clones hand-built seed slides and fills their named shapes. Per-slot limits come from a template manifest and are enforced three times over, injected into the prompt, encoded as a JSON schema, and re-validated after generation. A slot that can't be filled honestly is left empty rather than invented. One bounded retry feeds the exact validation errors back; after three failures the slide is flagged `needs_review` and escalated to a human. Native editable charts and process-flow diagrams are built from the data shape, not from model guesses.

`Python 3.13` `python-pptx` `Pydantic` `Anthropic / Gemini / local Ollama` · three dependencies total · v1.0.0 · system design doc in `DOCS/`

#### [Local LLM Training & Optimization Suite](https://github.com/preetdhanani/Local-llm-training-optimization)

SFT and DPO alignment for 7B/8B models on a single consumer GPU, entirely on customer-managed hardware.

DPO optimizes policy weights straight from preference pairs, which skips reward-model training and the PPO loop altogether. Fitting that into 16GB meant NF4 (4-bit) QLoRA, activation checkpointing and paged optimizers. The part I'd defend hardest is process isolation: every training run is forked into a spawned subprocess, so when a job ends the OS reclaims 100% of CUDA VRAM instead of leaving a context locked behind a live Python process. Ingestion enforces a strict `prompt` / `chosen` / `rejected` schema with filters for duplicates and degenerate pairs.

`PyTorch` `TRL` `QLoRA / NF4` `FastAPI` `React + Vite` `SQLite` `CUDA` · MIT

#### [ScoutFox](https://github.com/preetdhanani/ScoutFox_browser_agent)

An open-source browser agent: Chrome Manifest V3 extension plus a standalone Playwright runner, driving the same agent loop.

One provider abstraction covers local Ollama (`qwen2.5:14b`, `llama3.1:8b`) and cloud APIs (Gemini, Groq, OpenAI, Claude), so the identical task can be run fully offline or against a frontier model and compared. Agent failures are usually invisible, so the telemetry console exposes each step's DOM snapshot, the raw LLM output, the parser result and network latency. A generated plan checklist ticks off sub-goals as it navigates, and runs are saved as restorable sessions.

`JavaScript` `Chrome MV3` `Python` `Playwright` `Ollama` · MIT · Contributor Covenant v2.1

---

### Also in here

- **[LlamaIndex Quest](https://github.com/preetdhanani/Llamaindex-Quest-Semantic-Crawl-to-Answer-Engine-main)** - crawl-to-answer RAG. Scrapy/Selenium crawl, semantic chunking, FAISS, query expansion, hybrid BM25 + dense retrieval.
- **[MLOps Pipeline](https://github.com/preetdhanani/MLOps)** - config-driven ingestion → validation → transformation → training → evaluation, with a schema gate, MLflow tracking mirrored to DagsHub, Docker and GitHub Actions.
- **[SmartDiet AI](https://github.com/preetdhanani/SmartDiet-AI-Personalized-Diet-Recommendation-System-Full-stack-project)** - every model scored a perfect 1.00, which is the interesting part. We traced it to a near-deterministic disease-to-diet mapping in the public dataset, documented the leakage, and noted that real clinical data lands closer to 70-85%.
- **[AskToYaana](https://github.com/preetdhanani/AskToYaana-Fullstack-personal-project)** - fine-tuned LLaMA 3.3 plus an LSTM intent classifier behind a Django backend. Deployed and publicly reachable.

---

### Stack I reach for

```
Core          Python, PyTorch, FastAPI, Docker, Git
LLM / GenAI   Hugging Face Transformers, TRL (SFT, DPO), QLoRA / NF4,
              LangChain, LlamaIndex, Ollama, schema-constrained generation
Retrieval     FAISS, BM25, hybrid retrieval, rerankers, sentence-transformers
MLOps         MLflow, DagsHub, DVC, GitHub Actions
Data / ML     scikit-learn, XGBoost, pandas, NumPy, SQL, PostgreSQL, SQLite
Also used     React + Vite, Django, Flask, Streamlit, Playwright, Scrapy,
              Azure ML, Azure OpenAI
```

---

### How I work

When I get stuck I go back to the question underneath the task: why are we building this at all? Then I look for people who hit the same wall before me, and use AI tools as a second pair of hands rather than an oracle.

A result I can't explain isn't a result yet. A perfect score makes me suspicious before it makes me happy, which is how the SmartDiet label leakage got caught.

---

### Background

One year as an AI Engineer at Woxxin Solution Pvt. Ltd (India), owning client-facing AI products end to end on Azure.
B.E. Information Technology, SCET Surat → M.Sc. AI & Robotics, Hochschule Hof, Germany.
AWS Certified AI Practitioner · 2nd place, ML Hackathon 2.0.

### Open to

Master's thesis positions in Germany from October 2026, in LLM alignment, applied AI or ML infrastructure. Flexible for a Sommersemester 2027 start.

German B2, English fluent.
