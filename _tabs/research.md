---
title: "Project"
layout: page
permalink: /research/
icon: fas fa-laptop
order: 2
toc: true
---

*[Note: PI = Principal Investigator (연구책임자), Co-I = Co-Investigator (참여연구원)]*
{: .pub-note}

{% assign proj_groups = site.data.projects %}
{% assign total = 0 %}
{% for group in proj_groups %}
  {% assign total = total | plus: group.projects.size %}
{% endfor %}
{% assign counter = total %}

{% for group in proj_groups %}
## {{ group.year }}

{% for proj in group.projects %}
<p class="proj-line" markdown="1"><span class="pub-num">{{ counter }}.</span><span class="pub-text">{{ proj.title }}, {{ proj.agency }}, {{ proj.period }} ({% if proj.role == "PI" %}**PI**{% else %}{{ proj.role }}{% endif %})</span></p>

{% assign counter = counter | minus: 1 %}
{% endfor %}
{% endfor %}
