---
title: "Experience"
layout: gridlay
sitemap: false
permalink: /experience/
---

<div class="section-marker" markdown="0">
<span class="eyebrow">01 &mdash; My Work</span>
</div>

<h2 class="section-headline">A Working Résumé</h2>
<p class="home-hero-sub" markdown="0" style="margin-top: calc(-1 * var(--space-4)); margin-bottom: var(--space-8);">Research, internships, and everything in between.</p>

<div class="exp-list" markdown="0">
{% assign roles = site.experiences | sort: "order" %}
{% for role in roles %}
<div class="exp-entry exp-entry-split">
<div class="exp-main">
<div class="exp-meta">
<span class="exp-date">{{ role.date_range }}</span>
{% if role.highlight %}<span class="exp-highlight">{{ role.highlight }}</span>{% endif %}
</div>
<a href="{{ role.url | relative_url }}" class="exp-title-link">
<div class="exp-title">{{ role.title }}</div>
<div class="exp-org-line">{{ role.org }}{% if role.location %} &mdash; {{ role.location }}{% endif %}</div>
</a>

{% if role.stack %}
<div class="exp-stack">
{% for item in role.stack %}
<span class="stack-chip">{{ item }}</span>
{% endfor %}
</div>
{% endif %}

<a href="{{ role.url | relative_url }}" class="btn-story">Read the story <span class="arrow">&rarr;</span></a>
</div>

{% if role.highlights %}
<div class="exp-highlights">
<span class="eyebrow">Highlights</span>
<ul>
{% for h in role.highlights %}
<li>{{ h }}</li>
{% endfor %}
</ul>
</div>
{% endif %}
</div>
{% endfor %}
</div>
