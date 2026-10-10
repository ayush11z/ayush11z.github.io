---
layout: experience-detail
title: "Machine Learning Researcher"
org: "Halıcıoğlu Data Science Institute"
org_url: "https://datascience.ucsd.edu/"
location: "San Diego, CA"
date_range: "Mar – Jun 2026"
highlight: "31% Fewer LLM Calls"
order: 2
blurb: "Designed a bandit-based selection strategy for LLM-driven algorithm discovery, achieving 31% fewer LLM calls and 24% faster convergence across 200+ optimization tasks."
stack: ["Python", "SQLite", "VizTracer", "LLM Agents"]
---

At HDSI I worked on LLM-driven algorithm discovery — using an LLM to search over a space of candidate algorithms rather than hand-designing one. The open problem was allocating limited compute across many candidate solutions efficiently.

---

#### 🔍 What I Worked On

- **Bandit-based selection**: Designed a bandit-based selection strategy with divide-and-conquer decomposition, allocating compute more efficiently toward promising candidates than existing frameworks like SkyDiscover, EoH, and FunSearch.
- **Large-scale evaluation**: Evaluated the strategy across **200+ optimization tasks**, achieving **31% fewer LLM calls** and **24% faster convergence** than baseline approaches.
- **Strategy database**: Orchestrated program generation over a SQLite strategy database, with unit tests and VizTracer instrumentation to debug and profile generated candidates.

---

#### 💡 Why It's Relevant

Most algorithm-discovery frameworks treat every candidate solution as equally worth exploring, which wastes compute on clearly weak branches. Framing selection as a bandit problem lets the search allocate effort toward the candidates most likely to pay off, which is directly useful in any setting where LLM calls are the bottleneck resource.
