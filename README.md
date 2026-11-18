# Hi, I'm Nikhil Kaveti 👋

**Generative AI Engineer** specializing in production **Retrieval-Augmented Generation (RAG)**, **Multimodal Vision Pipelines**, and **Agentic AI Workflows** with Python.

📍 Hyderabad, India | 🔗 [LinkedIn](https://linkedin.com/in/nikhil540/) | 🌐 [Portfolio](https://chrome-540.github.io/port/) | 📧 nikhilff540@gmail.com

---

## 🛠️ Tech Stack

* **Generative AI & Agents:** LangChain, LangGraph, CrewAI, Google GenAI SDK (`gemini-2.5-flash`, `gemini-embedding-001`), Agentic Workflows, Prompt Engineering
* **RAG, Retrieval & Evaluation:** Hybrid Search (Vector + BM25 + Reciprocal Rank Fusion), ChromaDB, Pinecone, Cross-Encoder Reranking, RAGAS, OpenCV Visual Diffing
* **Backend & UI Frameworks:** Python, FastAPI, Streamlit, Pydantic, `asyncio`, PyMuPDF
* **Cloud & Inference:** AWS Bedrock AgentCore, AWS SageMaker, GCP, RunPod, Groq

---

## 💼 Experience

### Generative AI Engineer — Orcalex Technologies LLP
*Sept 2024 – July 2026 | Hyderabad*

* Architected **SmartLearners.ai**, an AI-powered student performance analytics chatbot built on **Google Gemini 2.5 Flash**, analyzing homework, exam, and self-practice records to generate personalized insights and remedial study plans across grades 6–12.
* Designed a **6-stage NLP & RAG pipeline** (`intent detection → routing → data loading → filtering → prompt construction → LLM execution`) to convert natural-language queries into structured, hallucination-free responses grounded in student data.
* Built a weighted prioritization engine combining NCERT curriculum weightage with student-specific weakness frequency across multi-source submissions to recommend chapter-level study allocations.
* Engineered modular Python data-aggregation services and standardized status objects across all pipeline stages for graceful degradation on malformed or incomplete datasets.

---

## 🚀 Featured Projects

### 1. Multimodal Version-Aware Blueprint RAG & Visual Diff Engine
* **Problem:** Standard text chunkers shred spatial layouts on 300+ page architectural/construction blueprints, regex fails on vectorized CAD fonts, and pure dense retrieval misses exact sheet/panel callouts (`A152`, `E801`, `S102`).
* **Architecture:**
  * **Offline Multimodal Enrichment:** Rendered 306 sheets (`v1`: 154 pages, `v2`: 152 pages) via PyMuPDF and ran async `gemini-2.5-flash` vision extraction with Pydantic schema validation to verify canonical sheet IDs, disciplines, entities, and spatial summaries.
  * **Automated Visual Revision Diffing:** Built an OpenCV red/green pixel-diffing + VLM filtering stage to isolate genuine architectural/MEP geometry edits while filtering out false-positive title-block stamp shifts.
  * **Hybrid Multi-Version Retrieval:** Fused `gemini-embedding-001` (ChromaDB) with BM25 lexical search via Reciprocal Rank Fusion (RRF), routing version-comparison queries (`diff_mode`) with both `v2` blueprint PNGs and red/green diff overlays attached to the VLM.
* **Benchmark:** Achieved **100% Top-1 Retrieval Precision (18/18)** on sheet-specific engineering & revision queries and **90% Recall@3** across a 20-query golden evaluation set.

### 2. Production RAG-Based Document QA System
* Built a multimodal PDF ingestion pipeline using Gemini Vision to extract and describe diagrams, tables, and charts alongside structured text.
* Implemented hybrid retrieval combining **Pinecone** (3072-dim Gemini embeddings) and **BM25** merged via Reciprocal Rank Fusion with optional cross-encoder reranking and dual chunking (header-aware + parent-child).
* Automated evaluation using **RAGAS** (`faithfulness`, `answer_relevancy`, `context_precision`, `context_recall`) and a custom page-accuracy metric with per-phase latency tracing, exposed via **FastAPI** and a **Streamlit** dashboard.

### 3. AI Interview Analyzer
* Built a modular audio-to-report evaluation pipeline separating audio preprocessing, chunked 5-minute transcription (`faster-whisper` with `int8` quantization for CPU efficiency), LLM evaluation signal extraction, and structured candidate report generation.

---

## 🎓 Education

* **Bachelor of Computer Science** — Jawaharlal Nehru Technological University (JNTU) *(2020 – 2024)*
