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
<a href="{{ project.url | relative_url }}" class="research-card-link" data-category="{{ project.category | slugify }}" data-modal="project-{{ project.slug }}">
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

<div class="modal-overlay" id="projectModalOverlay" markdown="0">
<div class="modal-panel">
<button class="modal-close" id="projectModalClose" aria-label="Close">&times;</button>
<div class="modal-scroll" id="projectModalScroll">
<div class="modal-body" id="projectModalBody"></div>
</div>
</div>
</div>

{% for project in sorted_projects %}
{% assign num = forloop.index | plus: 100 | to_string | slice: 1, 2 %}
<template id="project-{{ project.slug }}" markdown="0">
<div class="modal-project">
<div class="modal-project-sidebar">
<span class="modal-project-num">{{ num }}</span>
{% if project.category %}
<div class="modal-project-field">
<span class="eyebrow">Domain</span>
<span class="modal-project-field-value">{{ project.category }}</span>
</div>
{% endif %}
{% if project.stack %}
<div class="modal-project-field">
<span class="eyebrow">Stack</span>
<ul class="modal-project-stacklist">
{% for item in project.stack %}<li>{{ item }}</li>{% endfor %}
</ul>
</div>
{% endif %}
</div>
<div class="modal-project-main">
<h2 class="modal-project-title">{{ project.title }}</h2>
{% if project.description %}<p class="modal-project-subtitle">{{ project.description }}</p>{% endif %}
<hr class="modal-project-divider">
<p class="modal-project-summary">{{ project.summary }}</p>
</div>
</div>
</template>
{% endfor %}
