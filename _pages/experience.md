---
title: "Experience"
layout: gridlay
sitemap: false
permalink: /experience/
---

## Experience

<div class="exp-list" markdown="0">
{% assign roles = site.experiences | sort: "order" %}
{% for role in roles %}
<div class="exp-entry">
<div class="exp-meta">
<span class="exp-date">{{ role.date_range }}</span>
{% if role.highlight %}<span class="exp-highlight">{{ role.highlight }}</span>{% endif %}
</div>
<div class="exp-title">{{ role.title }} <a href="{{ role.url | relative_url }}" class="exp-org">@ {{ role.org }}</a></div>
<p class="exp-desc">{{ role.blurb }}</p>
{% if role.stack %}
<div class="exp-stack">
{% for item in role.stack %}
<span class="stack-chip">{{ item }}</span>
{% endfor %}
</div>
{% endif %}
</div>
{% endfor %}
</div>
