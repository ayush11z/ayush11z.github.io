---
layout: experience-detail
title: "Software Engineering Intern"
org: "Hutech Solutions"
org_url: "https://hutechsolutions.com/"
location: "Bangalore, India"
date_range: "June 2024 – Aug 2024"
highlight: "RAG Pipeline"
order: 5
blurb: "Built a RAG pipeline to replace manual internal doc search, and deployed it on AWS serving 100+ concurrent requests at p95 latency of 1-2 seconds."
highlights:
  - "Built a RAG pipeline to replace manual internal doc search, using <strong>LangChain</strong> and <strong>sentence-transformers</strong>."
  - "Built the data layer with <strong>MongoDB Vector Search</strong> for embeddings and document storage, then containerized and deployed the service on <strong>AWS (ECS/Fargate)</strong>, maintaining <strong>100+ concurrent requests</strong> at <strong>p95 latency of 1–2 seconds</strong>."
stack: ["LangChain", "FastAPI", "MongoDB", "AWS"]
---

I interned as a Software Engineering Intern at [Hutech Solutions](https://hutechsolutions.com/) in Bangalore, building a Retrieval-Augmented Generation pipeline to replace manual internal documentation search with an AI assistant.

---

#### 🔍 What I Worked On

- **RAG pipeline**: Built a Retrieval-Augmented Generation pipeline using LangChain and sentence-transformers to combine semantic document retrieval with LLM-based answer generation, replacing manual search through internal docs.
- **Data layer**: Built the data layer with MongoDB Vector Search for embeddings and document storage, indexing internal documentation for fast semantic similarity search.
- **Deployment**: Containerized and deployed the service on AWS (ECS/Fargate), maintaining 100+ concurrent requests at a p95 latency of 1–2 seconds in production.

---

#### 💡 Why It's Relevant

Internal doc search is a small-scale version of a problem every growing team eventually runs into: knowledge buried in docs nobody can find fast enough. Building this end-to-end — from retrieval and embeddings to a deployed, concurrent-load-tested service — was my first time taking a RAG system past the prototype stage into something that had to hold up under real usage.
