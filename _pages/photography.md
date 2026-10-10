---
title: "Photography"
layout: gridlay
sitemap: false
permalink: /photography/
---

<div class="section-marker" markdown="0">
<span class="eyebrow">01 &mdash; Off The Clock</span>
</div>

<h2 class="section-headline">Photography</h2>
<p class="home-hero-sub" markdown="0" style="margin-top: calc(-1 * var(--space-4));">Wildlife &amp; nature, off the clock.</p>

{% assign photos = site.data.photography %}
{% if photos and photos.size > 0 %}
<div class="research-grid" markdown="0">
{% for photo in photos %}
<div class="research-card">
<img src="{{ site.url }}{{ site.baseurl }}/{{ photo.img }}" class="research-thumb" alt="{{ photo.caption | default: 'Wildlife photo' }}" loading="lazy">
{% if photo.caption or photo.location %}
<div class="research-body">
{% if photo.caption %}<h4 class="research-title">{{ photo.caption }}</h4>{% endif %}
{% if photo.location %}<p class="research-desc">{{ photo.location }}</p>{% endif %}
</div>
{% endif %}
</div>
{% endfor %}
</div>
{% else %}
<div class="section-card" markdown="0">
<p>Photos coming soon — check back shortly.</p>
</div>
{% endif %}
