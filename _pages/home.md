---
title: "Home"
layout: homelay
sitemap: false
permalink: /
---

<div class="masthead" markdown="0">
<h1 class="masthead-name">{{ site.name }}</h1>
<p class="masthead-sub">{{ site.title }}, {{ site.institution }}</p>
</div>

<div class="double-rule" markdown="0"></div>

<div class="section-marker" markdown="0">
<span class="eyebrow">01 &mdash; Introduction</span>
</div>

<h2 class="section-headline">Who am I?</h2>

<div class="home-content" markdown="0">
<p class="drop-cap">I'm an incoming Master's student in Computer Science at UC San Diego, starting Fall 2026. My work sits at the intersection of agentic AI systems, applied machine learning, and health-focused NLP.</p>

<p>Right now, I'm working on agentic AI systems, exploring algorithm-discovery strategies for bio-simulation pipelines, and using preference optimization techniques like DPO and LoRA to study emotion regulation in language models. I've also worked on speech-based disease detection using audio transformers, built a classification pipeline with real GPU training infrastructure, and developed agentic systems that automate research and outreach workflows end-to-end.</p>
</div>

<div class="chip-container" markdown="0">
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Agentic AI Systems</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Applied Machine Learning</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">Health-Focused NLP</a>
<a href="{{ site.url }}{{ site.baseurl }}/projects" class="chip">LLM Alignment</a>
</div>

{% if site.data.news and site.data.news.size > 0 %}
<div class="section-marker" markdown="0">
<span class="eyebrow">02 &mdash; Lately</span>
</div>

<h2 class="section-headline">What's New</h2>

<div class="news-timeline" markdown="0">
{% for article in site.data.news limit:5 %}
<div class="news-item">
<div class="news-date">{{ article.date }}</div>
<div class="news-headline">{{ article.headline }}</div>
</div>
{% endfor %}
</div>
{% endif %}
