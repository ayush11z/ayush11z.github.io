---
layout: project
title: "Customer Support Assistant: RAG Pipeline for Internal Query Answering"
description: An AI assistant that answers customer support questions using internal company documentation.
img: images/projects/hutech-rag-pipeline.jpeg
importance: 6
---

Manually searching through internal documentation to answer customer support queries is slow and inconsistent. This project builds a Retrieval-Augmented Generation (RAG) pipeline that lets a support assistant pull relevant information from internal docs automatically and generate accurate answers, instead of relying on manual search.

This project was built during my internship as an AI / Full Stack Development Intern at [Hutech Solutions](https://hutechsolutions.com/).

---

#### 🔎 Retrieval-Augmented Generation Pipeline

- **RAG pipeline**: Built a Retrieval-Augmented Generation (RAG) pipeline using **LangChain** to combine semantic document retrieval with LLM-based answer generation.
- **Embeddings**: Generated dense vector embeddings for internal documentation using **sentence-transformers** and indexed them in **MongoDB Vector Search** for semantic similarity search.
- **Chunking**: Implemented document chunking and embedding workflows to improve retrieval accuracy across large internal knowledge bases.
- **Retrieval tuning**: Tuned retrieval parameters such as chunk size and the number of retrieved documents to improve answer quality while keeping inference latency low.

---

#### 🧩 Backend API Development

- **REST APIs**: Developed REST APIs with **FastAPI** to expose document retrieval and question-answering endpoints.
- **Modular services**: Structured the backend so retrieval, embedding generation, and response generation were modular services, making the pipeline easier to maintain and extend.
- **Reliability**: Added request validation, error handling, and asynchronous processing to support multiple concurrent users.
- **Integration**: Designed the API to integrate cleanly with frontend applications and internal services.

---

#### 🗄️ Data & Storage

- **Vector storage**: Used **MongoDB Vector Search** for semantic document retrieval and storage of document embeddings alongside metadata.
- **Ingestion pipelines**: Built ingestion pipelines to preprocess documents, generate embeddings, and keep the vector index synchronized with updated documentation.
- **Metadata organization**: Organized document metadata to improve filtering and retrieval efficiency.

---

#### 📈 Evaluation & Performance

- **Answer quality**: Evaluated retrieval and answer quality across more than **1,000** internal support queries, achieving approximately **75%** answer relevance.
- **Configuration comparison**: Compared retrieval configurations and embedding strategies to identify settings that produced the most useful responses.
- **Load testing**: Measured response latency and throughput under concurrent workloads to validate production readiness.
- **Performance**: Optimized API performance to maintain **p95 response times of 1–2 seconds** while serving over **100 concurrent requests**.

---

#### 🚀 Deployment

- **Containerization**: Containerized the application with **Docker** to ensure consistent deployment across development and production environments.
- **Reproducibility**: Configured services for reproducible local development and simplified deployment workflows.
- **End-to-end validation**: Verified the complete end-to-end pipeline, from document ingestion to answer generation, under realistic workloads.

---

#### 🛠️ Tech Stack

Python, LangChain, sentence-transformers, MongoDB Vector Search, FastAPI, Docker

---

#### 💡 Why It's Relevant

Customer support is one of the clearest real-world use cases for RAG: users need fast, accurate answers pulled from a large body of internal knowledge, not generic responses. This project gave me hands-on experience with the full pipeline, from retrieval quality and chunking strategy to deployment under real concurrent load, which is directly relevant to my interest in building AI systems that hold up under real usage, not just in a demo.
