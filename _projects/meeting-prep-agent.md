---
layout: project
title: "Professor Outreach Agent"
description: An agentic tool that finds professors in a research area, drafts personalized cold emails with a team of CrewAI agents, sends them via Gmail, and tracks replies against your calendar.
importance: 10
category: Software
stack: ["CrewAI", "Flask", "Gmail API", "Supabase"]
github: https://github.com/ayush11z/Meeting-prep-agent
summary: >-
  Reaching out to professors about research positions means repeating the same multi-step process
  dozens of times — find relevant researchers, read their papers, personalize a pitch, track
  replies, check calendar availability — so I built an agent to run the whole pipeline. It
  searches Semantic Scholar, arXiv, and the web to surface active researchers at top institutions,
  then three CrewAI agents collaborate on each email: a Research Agent reads the professor's
  papers, a Writer Agent drafts against my resume, and a Critic Agent reviews it before I send
  anything myself through the Gmail API. Every sent email is tracked in Supabase by its Gmail
  thread ID, with an LLM pass that reads replies for proposed meeting times and checks them
  against Google Calendar — and if a professor doesn't respond, the agent finds PhD students in
  their lab to reach out to instead.
---

Finding and reaching out to professors for research opportunities is a genuinely repetitive multi-step process — the kind of work that's tedious precisely because it demands care at every step. This project builds an agentic pipeline that handles discovery, personalized drafting, sending, and reply tracking end to end, while keeping a human in the loop before anything actually gets sent.

---

#### 🔍 Discovery

- **Multi-source search**: Searched **Semantic Scholar** (300+ papers across query variations), **arXiv**, and the web via an **Exa → SerpApi → DuckDuckGo** fallback chain to find active researchers in a given area.
- **Candidate filtering**: Filtered for top institutions, sorted by most recent publication, and actively searched for a lab or personal page for top candidates missing one.

---

#### ✍️ Drafting with CrewAI

- **Multi-agent drafting**: Used **CrewAI** to coordinate three collaborating agents — a Research Agent that reads the professor's papers, a Writer Agent that drafts a personalized email against my resume, and a Critic Agent that reviews and refines the result.
- **Human-in-the-loop send**: Nothing is ever sent automatically — every draft is reviewed before being sent via the **Gmail API** with a resume attached.

---

#### 📬 Tracking & Follow-Up

- **Reply tracking**: Stored every sent email in **Supabase**, keyed by its Gmail thread ID, and polled threads for replies.
- **Calendar matching**: Used an LLM pass to extract proposed meeting times from replies, then checked them against **Google Calendar** availability via OAuth.
- **Lab outreach fallback**: If a professor doesn't reply, the agent finds PhD students in their lab and drafts peer-to-peer emails to them instead.

---

#### 🛠️ Tech Stack

Python, Flask, CrewAI, LangGraph, Mistral / Groq / Anthropic / Ollama, Gmail API, Google Calendar API, Supabase, Exa, SerpApi, pdfplumber

---

#### 💡 Why It's Relevant

The hard part of outreach at scale isn't sending emails, it's staying genuinely personalized across dozens of them without losing a week to manual research. Building this forced me to coordinate multiple specialized agents around a shared goal, integrate real external APIs (Gmail, Calendar, Supabase) rather than mocked data, and design the system so a human stays firmly in control of what actually goes out.
