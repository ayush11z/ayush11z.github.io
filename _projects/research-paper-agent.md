---
layout: project
title: "Research Paper Agent"
description: An AI research assistant that searches arXiv, OpenAlex, and Semantic Scholar from five angles at once, expands results via citation graphs, and flags gaps and contradictions in the literature.
importance: 11
category: Research
stack: ["LangChain", "Ollama", "Gemini", "Express.js"]
github: https://github.com/ayush11z/research-paper-agent
summary: >-
  Literature reviews are tedious partly because a single search query only surfaces one slice of
  the relevant work, so this agent searches from five angles at once — direct, synonym,
  methodology, domain, and opposing — using a local Llama 3 model via LangChain and Ollama to
  generate each variant, then pulls results from arXiv, OpenAlex, and Semantic Scholar in
  parallel. It expands the candidate set further by walking each paper's Semantic Scholar citation
  graph, then runs a separate LLM pass to surface specific gaps in the literature and pairs of
  papers that directly contradict each other. For arXiv papers, Gemini 1.5 Flash vision reads
  every figure and table in the PDF to judge how well it actually supports the thesis. An Express
  server streams every stage of the pipeline to a live dashboard over Server-Sent Events.
---

Literature review is one of the most repetitive parts of research — rephrasing the same search a dozen ways, chasing citation trails by hand, and reading entire papers just to check whether two sources actually agree. This project automates that process end to end, from query generation to contradiction detection.

---

#### 🔍 Multi-Angle Search

- **Query diversification**: Used a local **Llama 3** model (via **LangChain** and **Ollama**) to rewrite a thesis into five distinct search angles — direct, synonym, methodology, domain, and opposing — so the search surfaces work a single query would miss.
- **Multi-source retrieval**: Queried **arXiv**, **OpenAlex**, and **Semantic Scholar** in parallel across all five angles, de-duplicating and merging results into a single ranked candidate set.

---

#### 🕸️ Citation Graph & Literature Analysis

- **Citation graph expansion**: Walked each paper's reference list via the **Semantic Scholar** API to pull in closely related work that direct search missed.
- **Gap detection**: Ran a dedicated LLM pass over the candidate papers to identify specific arguments, methodologies, or perspectives missing from the literature relative to the thesis.
- **Contradiction detection**: Identified pairs of papers that make conflicting claims, with an explanation of what they disagree on.

---

#### 👁️ Vision-Based Figure Analysis

- **PDF vision ranking**: Used **Gemini 1.5 Flash** vision to read every figure and table in each arXiv paper's PDF directly, scoring how well the visual evidence actually supports the thesis rather than relying on the abstract alone.

---

#### 🖥️ Live Dashboard

- **Streaming backend**: Built an **Express.js** server that spawns the Python pipeline as a subprocess and streams every stage — queries, papers found, gaps, contradictions — to the frontend in real time over Server-Sent Events.

---

#### 🛠️ Tech Stack

Python, LangChain, Ollama (Llama 3), Google Gemini 1.5 Flash, Express.js, Node.js, arXiv API, OpenAlex API, Semantic Scholar API

---

#### 💡 Why It's Relevant

A good literature review isn't just a keyword search — it requires reading between the lines of what the field hasn't said yet and noticing where researchers disagree. Building an agent that does both, grounded in actual figures and tables rather than just text, pushed me past basic retrieval and into the kind of multi-step reasoning agentic research tools need.
