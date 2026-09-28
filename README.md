# Hi, I'm Aish Soni 👋
<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=F75C7E&center=true&vCenter=true&width=520&lines=Full-Stack+%26+Applied+AI+Engineer;Building+AI+products;Designing+distributed+systems;Developer+tools+%26+communities" alt="Typing SVG" />
</div>
<p align="center">
  I build web products, AI systems, real-time collaboration tools, and developer tools.
</p>
<p align="center">
  <a href="https://www.linkedin.com/in/Aishh-soni15/">LinkedIn</a> ·
  <a href="https://github.com/AishSoni">GitHub</a> ·
  <a href="mailto:Aishhsoni15@gmail.com">Email</a>
</p>
---
## About me
- 🎓 B.Tech in Electronics & Communication Engineering from **IIIT Bhopal**, CGPA **8.41/10**
- 🧩 I recently completed an **SDE internship at Plum Benefits**, where I worked on insurance checkout, payments, observability, and frontend architecture
- 🤖 My interests include **AI agents, RAG systems, LLM evaluation, and reliable product engineering**
- ⚡ I work across design, implementation, and deployment
- 📍 India · Asia/Kolkata
## Experience
### Plum Benefits | SDE Intern | Jan 2026 - Jul 2026
I worked on the Retail Health Insurance product, mainly around the checkout journey, payment handling, observability, and frontend architecture.
### Resustainability | Software Engineering Intern | May 2025 - Aug 2025
I worked on internal AI tooling and Dockerized AWS deployments for ESG compliance workflows.
## Projects
### [Fabriik | Multiplayer Canvas Editor](https://github.com/AishSoni/Fabriik-MP-Creator)
A local-first website editor built for experimenting with layouts, code, and AI-assisted changes. A single schema-validated document powers the canvas, JSON code panel, viewport previews, compare view, import/export, and AI review flow.
- Solo documents persist in IndexedDB and work without an account or network connection. Sharing creates a room and synchronizes the local document without a migration step.
- Multiplayer uses a Yjs CRDT in the browser and one Cloudflare Durable Object per room. Clients send validated `EditCommand` JSON upward; the server applies accepted commands and broadcasts Yjs binary updates.
- The Durable Object is also the trust boundary for validation, history, deduplication, rate limiting, connection limits, and idle-room cleanup. AI providers only return proposals, which must be reviewed before they can change the document.
- Reached 15-20 ms sync latency for rooms with up to 16 concurrent players and shipped seven starter templates with self-contained HTML export.
**Stack:** React, TypeScript, Zustand, Zod, Yjs, Cloudflare Workers, Durable Objects  
**Live demo:** [aish-s-fabriik-mp.vercel.app](https://aish-s-fabriik-mp.vercel.app)
### [Sabha AI | Multi-Agent Workspace](https://github.com/AishSoni/Sabha-AI)
A workspace for user-directed meetings with multiple AI personas. Each participant has a role, system prompt, provider configuration, and optional private Knowledge Stack. The user controls who speaks next, while a lightweight auto-facilitate mode can run a short sequence of turns.
- The orchestration loop hydrates the meeting from Supabase, assembles the agenda and compressed history, calls the selected model with tools, runs tool calls such as knowledge search or consensus logging, streams the response over SSE, and persists the result.
- RAG is scoped in two ways: shared meeting documents are available to the room, while private Knowledge Stacks are visible only to assigned personas. Qdrant stores the document embeddings.
- Disagreements and consensus are first-class records with severity or strength scores. The live scoreboard updates as agents call the logging tools, instead of treating those decisions as ordinary chat text.
- Supports Gemini, OpenRouter, and Ollama with per-agent model and temperature overrides. The meeting flow uses a five-state FSM, achieved sub-100 ms TTFT in testing, and reached 88% average retrieval relevance on a curated test set.
**Stack:** Python, FastAPI, Next.js, TypeScript, Supabase, Qdrant, SSE
### [Narada AI | Deep Research Agent](https://github.com/AishSoni/Narada-AI)
A locally runnable deep-research assistant for questions that need more than one search result. It decomposes a question into focused sub-questions, searches multiple sources, checks whether the returned pages actually answer them, and produces a cited synthesis.
- The search workflow combines LangGraph orchestration with Tavily and Firecrawl, then retries unanswered sub-questions with alternative queries.
- Every source is shown with the answer, and validation rejects sources that do not contain evidence for the claim. The workflow also reports progress as individual searches complete.
- Local mode uses Ollama for generation and embeddings and Qdrant for document knowledge bases. The settings page supports OpenAI, Ollama, OpenRouter, Firecrawl, Tavily, SERP, and DuckDuckGo configurations.
- MCP server support provides an extension point for filesystem access, database queries, external APIs, and other tools. Docker Compose packages the application with Qdrant for local deployment.
**Stack:** Next.js, React, LangGraph, Qdrant, Docker, Firecrawl, Tavily, Ollama, MCP
### [Mini ERM | Employer Relationship Manager](https://github.com/AishSoni/Mini_ERM)
A multi-user Employer Relationship Manager for keeping job applications and outreach in one place. Each application, contact, resume, event, and notification is scoped to a user, while one central identifier connects the records across the system.
- The Telegram flow starts with a job link, generates LinkedIn and Apollo search URLs, accepts recruiter contacts, creates the application, attaches a resume, and triggers an n8n cold-email workflow.
- Tracked resume links record views and classify likely recruiter activity versus automated scanners using timing, IP ranges, user-agent patterns, dwell time, and scroll depth. Genuine activity can trigger an immediate Telegram notification.
- The application lifecycle handles deduplication by company and role, reactivation, expiry, status changes, follow-up cadence, response-based cancellation, and idempotency keys.
- A Next.js portfolio serves tracked resume pages and the analytics dashboard. The backend is designed as a user-scoped multi-tenant service with Supabase storage and PostgreSQL data.
**Stack:** TypeScript, Node.js, Express, Zod, Supabase/PostgreSQL, Next.js, n8n, Telegram
### [IIIT Bhopal Connect](https://github.com/AishSoni/iiitBhopal-Connect)
A campus platform built for IIIT Bhopal to bring student communication and resources into one place.
- Includes campus posts, event management, lost and found, timetables, study materials, profiles, feeds, and notifications.
- Uses Firebase authentication, Firestore data, cloud storage, security rules, and real-time synchronization for dynamic content.
- Adds career-focused tools including peer resume review, AI-assisted cover-letter generation, and a chat assistant for opportunity-related questions.
**Stack:** Next.js, React, Firebase, Firestore, cloud storage
### [Double Perovskite Band Gap Prediction | Research](https://github.com/AishSoni/Silica-Perovskite-Energy-Band-Gap-Prediction)
A research pipeline for predicting Materials Project DFT band gaps and direct or indirect gap labels for double perovskites in the `ABC2D6` and `A2BB'X6` families.
- Uses a single experiment configuration to define query ranges, dataset scope, validation rules, output paths, and modeling defaults.
- Organizes the workflow into data collection, validation, featurization, feature selection, model training, and evaluation, with dataset manifests and validation summaries for reproducibility.
- The repository was cleaned up after an audit found that earlier generated artifacts came from an invalid data-collection workflow; current results are regenerated from the corrected pipeline.
**Stack:** Python, machine learning, Materials Project data
### [Selective Amnesia (SA) for CVAEs](https://github.com/AishSoni/CVAE-Un-learning-Framework)
A machine-unlearning project that applies Selective Amnesia to conditional variational autoencoders trained on MNIST.
- Trains a CVAE on all classes, computes a Fisher information matrix for the checkpoint, and runs forgetting training for a chosen target label.
- Generates samples for the forgotten class and evaluates them with a separately trained classifier using average class probability and entropy.
- Includes scripts for baseline CVAE training, Fisher calculation, selective forgetting, sample generation, classifier training, and evaluation.
**Stack:** Python, conditional VAEs, Fisher information, machine unlearning
### [Cloth Simulation - OpenGL Backend](https://github.com/AishSoni/Cloth-Simulation)
A real-time cloth simulator built around a hand-written OpenGL rendering pipeline.
- Simulates cloth particles with Verlet integration and solves constraints using Jacobson's method for fast, stable behavior during interaction.
- Includes a 3D scene, custom shaders, mouse interaction, and an ImGui overlay for changing simulation parameters while the program is running.
- The project focuses on C++ object-oriented design, matrix and coordinate-space math, low-level rendering, and performance work.
**Stack:** C++, OpenGL, SDL2, GLEW, ImGui
### [Imagyn MCP Server](https://github.com/AishSoni/Imagyn)
An MCP server that adds image generation and editing to tool-capable chat clients.
- Exposes tools for generating images, editing previous generations, and listing available LoRA models for ComfyUI workflows.
- Supports local ComfyUI execution as well as Replicate and Fal.ai cloud providers through a common configuration layer.
- Provides a standard-input MCP server for desktop clients, with an optional FastAPI server and versioned image outputs for iterative edits.
**Stack:** Python, MCP, ComfyUI, Replicate, Fal.ai
### [Mental Health Chatbot](https://github.com/AishSoni/Mental_Health_Chatbot)
A hackathon-built mental health chatbot with both text and voice interaction.
- Supports speech-to-text and text-to-speech so users can interact without relying only on typed input.
- Combines OpenAI responses with a resource database covering psychiatric hospitals, doctors, and suicide helpline information.
- Designed as a multilingual, multimodal support interface rather than a replacement for professional care.
**Stack:** Python, OpenAI API, speech recognition, text-to-speech
### [Synapse Extension](https://github.com/AishSoni/Synapse-App)
The browser extension component of Synapse, a cross-platform workspace that connects browser capture, the core web application, and a desktop client.
- The monorepo contains the web app and backend, desktop client, browser extension source, and a Chrome package.
- Synapse is designed to capture information in the browser, manage workflows on the desktop, and keep the connected surfaces in sync.
- Supporting documentation covers setup, packaging, distribution, extension testing, and the shared system architecture.
**Stack:** Browser extensions, web applications, desktop applications
## Tech stack
### Languages
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white)
### Frameworks, AI & data
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-D50000?style=for-the-badge&logo=qdrant&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
**Also:** LangGraph · RAG · MCP · DeepEval · Zustand · Zod · Yjs · PostgreSQL · Firebase · AWS EC2 · Google Cloud · Cloudflare Durable Objects · CI/CD · Linux
