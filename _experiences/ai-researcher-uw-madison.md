---
layout: experience-detail
title: "AI Researcher"
org: "University of Wisconsin–Madison"
org_url: "https://engineering.wisc.edu/directory/profile/dhananjay-bhaskar/"
location: "Remote"
date_range: "June 2026 – now"
highlight: "7-Agent Pipeline"
order: 1
blurb: "Architected a 7-agent LangChain pipeline for automated simulation generation, cutting manual debugging time 38% and accelerating experimentation cycles 30%."
stack: ["LangChain", "MCP", "AST Validation", "CI/CD"]
---

I work with [Professor Dhananjay Bhaskar](https://engineering.wisc.edu/directory/profile/dhananjay-bhaskar/)'s lab at UW–Madison on turning biology research papers into runnable simulations automatically, without a researcher manually translating the paper by hand.

---

#### 🔍 What I Worked On

- **7-agent pipeline**: Architected a multi-agent LangChain pipeline that decouples literature parsing from simulation execution, cutting manual debugging time **38%** and accelerating experimentation cycles **30%**.
- **Scoped tool access**: Standardized how agents access external tools through a scoped MCP server, so each agent only sees the tools relevant to its step.
- **Validation & CI/CD**: Added AST-based validation and CI/CD regression testing on top of the pipeline, cutting integration overhead **41%**, reducing failed runs **35%**, and catching **63%+ of breaking changes** before execution.

---

#### 💡 Why It's Relevant

Research pipelines that chain multiple AI agents together tend to fail silently — a bad intermediate output quietly corrupts everything downstream. This work is about making that failure mode visible early, through validation and regression testing, rather than discovering it after a simulation has already run for hours.
