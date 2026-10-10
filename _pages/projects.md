---
title: "Projects"
layout: gridlay
sitemap: false
permalink: /projects/
---

<div class="section-marker" markdown="0">
<span class="eyebrow">01 &mdash; My Catalog</span>
</div>

<h2 class="section-headline">Selected Works</h2>
<p class="home-hero-sub" markdown="0" style="margin-top: calc(-1 * var(--space-4)); margin-bottom: var(--space-2);">Filter by area.</p>

{% assign sorted_projects = site.projects | sort: "importance" %}
{% assign categories = sorted_projects | map: "category" | uniq | sort %}

<div class="filter-tabs" id="projectFilters" markdown="0">
<button class="filter-tab active" data-filter="all">All</button>
{% for cat in categories %}
<button class="filter-tab" data-filter="{{ cat | slugify }}">{{ cat }}</button>
{% endfor %}
</div>

<div class="research-grid" markdown="0" id="projectGrid">
{% for project in sorted_projects %}
{% assign num = forloop.index | plus: 100 | to_string | slice: 1, 2 %}
<a href="{{ project.url | relative_url }}" class="research-card-link" data-category="{{ project.category | slugify }}">
<div class="research-card">
<span class="research-num">{{ num }}</span>
{% if project.category %}<span class="research-cat eyebrow">{{ project.category }}</span>{% endif %}
<h4 class="research-title">{{ project.title }}</h4>
<p class="research-desc">{{ project.description }}</p>
{% if project.stack %}
<div class="research-stack">
{% for item in project.stack %}<span>{{ item }}</span>{% unless forloop.last %}<span class="dot">&middot;</span>{% endunless %}{% endfor %}
</div>
{% endif %}
</div>
</a>
{% endfor %}
</div>
