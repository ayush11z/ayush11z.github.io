---
layout: page
title: "Agentic AI for Computational Biology"
description: An AI pipeline that turns biology research papers into working simulations.
img: assets/img/agentic-computational-biology.jpeg
importance: 4
category: work
---

Turning a biology research paper into a working computational simulation usually takes a researcher days of manual work — reading the paper, extracting the right parameters, and hand coding the model. This project builds a multi-agent AI pipeline that automates that translation, converting biology papers directly into parameterized simulations.

This project was a research collaboration with [Professor Dhananjay Bhaskar](https://engineering.wisc.edu/directory/profile/dhananjay-bhaskar/) and PhD student [Levi Svaren](https://biophysics.wisc.edu/staff/svaren-levi/) at the University of Wisconsin, Madison. Code is available on [GitHub](https://github.com/UW-Madison-CBML/paper_agenticAI).

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
