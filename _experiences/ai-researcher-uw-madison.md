---
layout: experience-detail
title: "AI Researcher"
org: "University of Wisconsin–Madison"
org_url: "https://engineering.wisc.edu/directory/profile/dhananjay-bhaskar/"
location: "Remote"
date_range: "June 2026 – now"
highlight: "Biophysics Simulations"
order: 1
blurb: "Architected a 7-agent LangChain pipeline for automated simulation generation, cutting manual debugging time 38% and accelerating experimentation cycles 30%."
highlights:
  - "Architected a 7-agent LangChain pipeline decoupling literature parsing from execution, cutting debugging time <strong>38%</strong> and speeding up experimentation <strong>30%</strong>."
  - "Added AST-based validation and CI/CD regression testing over a scoped MCP server, catching <strong>63%+ of breaking changes</strong> before execution."
stack: ["LangChain", "MCP", "Agentic AI", "CI/CD"]
---

Turning a biology research paper into a working computational simulation usually takes a researcher days of manual work — reading the paper, extracting the right parameters, and hand coding the model. This work builds a multi-agent AI pipeline that automates that translation, converting biology papers directly into parameterized simulations.

This is a research collaboration with [Professor Dhananjay Bhaskar](https://engineering.wisc.edu/directory/profile/dhananjay-bhaskar/) and PhD student [Levi Svaren](https://biophysics.wisc.edu/staff/svaren-levi/) at the University of Wisconsin, Madison. Code is available on [GitHub](https://github.com/UW-Madison-CBML/paper_agenticAI).

---

#### 🔍 What I Worked On

- **Multi-agent pipeline**: Contributed to a multi-agent pipeline built with **LangChain** that reads biology papers and translates them into parameterized **PhysiCell**/**Morpheus** simulations using the **Hybrid Automata Library (HAL)**.
- **Self-correction loop**: Designed a cyclical self-correction feedback loop that feeds the pipeline's final output back through itself for validation, catching errors before a simulation is finalized.
- **Parameter retrieval**: Built a **LangChain**-based web search agent to automatically pull missing simulation parameters from external sources like **NCBI**, when a paper didn't specify every value needed.
- **Tracing & debugging**: Used **LangSmith** to trace and debug agent runs across the pipeline, making it easier to pinpoint where a translation failed across the multi-step Librarian-to-Runner flow.

---

#### 🛠️ Tech Stack

Python, LangChain, LangSmith, PhysiCell, Morpheus, Hybrid Automata Library (HAL), NCBI API

---

#### 💡 Why It's Relevant

Computational biology research is often bottlenecked by the manual work of translating literature into runnable models — this project treats that translation step itself as an AI problem, with self-correction and automated parameter retrieval reducing the amount of manual babysitting needed. It's directly relevant to my interest in building agentic systems that can reason reliably over multi-step, knowledge-intensive tasks.
