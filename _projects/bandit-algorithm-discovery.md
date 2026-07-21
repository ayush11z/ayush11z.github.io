---
layout: page
title: "LLM-Driven Algorithm Discovery"
description: Using LLMs to automatically discover and improve algorithms for optimization problems.
img: assets/img/bandit-algorithm-discovery.jpeg
importance: 3
category: work
---

An AI system that automatically discovers algorithms is only as good as the search strategy behind it. This project builds a new **bandit-based** approach to LLM-driven algorithm discovery, benchmarked against existing frameworks like [**SkyDiscover**](https://github.com/skydiscover-ai/skydiscover) on classic optimization problems.

This project was research under [Professor Yusu Wang](https://yusu.belkin-wang.org/) at the [Halıcıoğlu Data Science Institute (HDSI)](https://datascience.ucsd.edu/), UC San Diego.

---

#### 🔍 What I Worked On

- **Bandit-based search**: Built a novel algorithm-discovery system using a **UCB (Upper Confidence Bound)** bandit strategy to guide LLM-driven search toward the most promising candidate solutions, analyzing existing frameworks like **SkyDiscover** and [**ShinkaEvolve**](https://github.com/SakanaAI/shinkaevolve) to understand their search strategies as baseline references.
- **Research mapping**: Used **Obsidian** to build a mental map of how these existing systems approached search, decomposition, and candidate selection, helping structure the design of the new bandit-based approach.
- **Problem decomposition**: Designed a divide-and-conquer decomposition strategy that broke complex optimization tasks into smaller subproblems, allowing the LLM to reason over and solve each piece independently before recombining into a full solution.
- **LLM orchestration**: Orchestrated LLM program generation using local, open-source models, tracking fitness-scored candidates over a **SQLite** strategy database.
- **Benchmarking**: Benchmarked performance against **SkyDiscover** on classic optimization tasks — on circle packing, the system reached a score of **1.56** versus SkyDiscover's best of **1.53**; on the traveling salesman problem (TSP), it outperformed SkyDiscover by roughly **0.1** points.
- **Testing & profiling**: Wrote unit tests specifically targeting the bandit selection logic — verifying that UCB scores were computed correctly across exploration/exploitation tradeoffs, that the divide-and-conquer decomposition produced valid, recombinable subproblems, and that candidate fitness scores were tracked consistently in the database — alongside using **VizTracer** for real-time execution profiling to catch performance regressions during search runs.

---

#### 🛠️ Tech Stack

Python, UCB Bandit Algorithms, SQLite, VizTracer, Obsidian, Local LLMs (Ollama), SkyDiscover, ShinkaEvolve

---

#### 💡 Why It's Relevant

Most algorithm-discovery frameworks treat search strategy as an afterthought bolted onto whichever LLM is available. This project treats it as the core research question — how do you allocate limited compute and LLM calls toward the most promising candidates, using classic bandit theory instead of naive search? That's directly relevant to my broader interest in making agentic systems more efficient and reliable, not just capable.
