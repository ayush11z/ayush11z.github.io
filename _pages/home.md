---
title: "Home"
layout: homelay
sitemap: false
permalink: /
---

<h2 class="home-hero">{{ site.name }}</h2>
<p class="home-hero-sub">{{ site.title }}, {{ site.institution }}</p>

<div class="chip-container" markdown="0">
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Agentic AI Systems</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Applied Machine Learning</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Health-Focused NLP</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">LLM Alignment</a>
</div>

### About me

I'm an incoming Master's student in Computer Science at UC San Diego, starting Fall 2026. My work sits at the intersection of agentic AI systems, applied machine learning, and health-focused NLP.

Right now, I'm working on agentic AI systems, exploring algorithm-discovery strategies for bio-simulation pipelines, and using preference optimization techniques like DPO and LoRA to study emotion regulation in language models. I've also worked on speech-based disease detection using audio transformers, built a classification pipeline with real GPU training infrastructure, and developed agentic systems that automate research and outreach workflows end-to-end.

<div style="display: flex; flex-wrap: wrap; gap: var(--space-1); margin-top: var(--space-8); padding-top: var(--space-6); border-top: 1px solid var(--border-color);" markdown="0">
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.url }}{{ site.baseurl }}/{{ site.links.cv }}" class="icon-link" title="CV"><i class="ai ai-cv"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" class="icon-link" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" class="icon-link" title="ResearchGate"><i class="ai ai-researchgate"></i></a>{% endif %}
{% if site.links.orcid and site.links.orcid != "" %}<a href="{{ site.links.orcid }}" class="icon-link" title="ORCID"><i class="ai ai-orcid"></i></a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<a href="{{ site.links.twitter }}" class="icon-link" title="Twitter"><i class="fa-brands fa-x-twitter"></i></a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<a href="{{ site.links.linkedin }}" class="icon-link" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
</div>
