---
title: "Projects"
layout: gridlay
sitemap: false
permalink: /projects/
---

## Projects

<div class="research-grid">
{% assign sorted_projects = site.projects | sort: "importance" %}
{% for project in sorted_projects %}
<a href="{{ project.url | relative_url }}" style="text-decoration: none; color: inherit;">
<div class="research-card">
{% if project.img %}
<img src="{{ site.url }}{{ site.baseurl }}/{{ project.img }}" class="research-thumb" alt="{{ project.title }}" loading="lazy">
{% endif %}
<div class="research-body">
<h4 class="research-title">{{ project.title }}</h4>
<p class="research-desc">{{ project.description }}</p>
</div>
</div>
</a>
{% endfor %}
</div>
