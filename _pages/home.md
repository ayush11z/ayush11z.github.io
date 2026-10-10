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

<div class="home-grid" markdown="0">
<div class="home-main">

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

<div class="icon-link-row" markdown="0">
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.url }}{{ site.baseurl }}/{{ site.links.cv }}" class="icon-link" title="Resume"><i class="ai ai-cv"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" class="icon-link" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" class="icon-link" title="ResearchGate"><i class="ai ai-researchgate"></i></a>{% endif %}
{% if site.links.orcid and site.links.orcid != "" %}<a href="{{ site.links.orcid }}" class="icon-link" title="ORCID"><i class="ai ai-orcid"></i></a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<a href="{{ site.links.twitter }}" class="icon-link" title="Twitter"><i class="fa-brands fa-x-twitter"></i></a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<a href="{{ site.links.linkedin }}" class="icon-link" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
</div>

</div>

<div class="home-side">

<div class="profile-card" markdown="0">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="profile-photo" alt="{{ site.name }}" loading="lazy">
<h4 class="profile-name">{{ site.name }}</h4>
<p class="profile-institution">{{ site.institution }}</p>
{% if site.data.pi[0].educationshort %}
<ul style="text-align: left; margin-top: var(--space-4); list-style: none; padding-left: 0;">
{% for education in site.data.pi[0].educationshort %}
<li style="font-size: 0.875rem; color: var(--text-secondary); padding: var(--space-1) 0;">{{ education | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
{% endif %}
</div>

{% if site.data.news and site.data.news.size > 0 %}
<div class="section-card" style="margin-top: var(--space-6);">
<h4>What's New</h4>
<div class="news-timeline">
{% for article in site.data.news limit:5 %}
<div class="news-item">
<div class="news-date">{{ article.date }}</div>
<div class="news-headline">{{ article.headline }}</div>
</div>
{% endfor %}
</div>
<p style="margin-top: var(--space-4); margin-bottom: 0;"><a href="{{ site.url }}{{ site.baseurl }}/allnews.html">See all news &rarr;</a></p>
</div>
{% endif %}

</div>

</div>
