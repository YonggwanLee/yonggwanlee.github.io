---
title: "Gallery"
layout: page
permalink: /gallery/
icon: fas fa-image
order: 5
---

{% assign activities = site.gallery_activities | sort: "date" | reverse %}

{% if activities.size > 0 %}
<div class="gallery-index">
{% for activity in activities %}
  {% assign cover = activity.photos | first %}
  <div class="gallery-card">
    <a class="gallery-card-img" href="{{ activity.url | relative_url }}">{% if cover %}<img src="{{ cover.src | relative_url }}" alt="" loading="lazy">{% endif %}</a>
    <a class="gallery-card-body" href="{{ activity.url | relative_url }}">
      <div class="gallery-card-title">{{ activity.title }}</div>
      <div class="gallery-card-date">{{ activity.date | date: "%Y.%m.%d" }}</div>
    </a>
  </div>
{% endfor %}
</div>
{% else %}
*No activities posted yet — check back soon!*
{% endif %}
