---
title: Domestic Publications
permalink: /publications/domestic/
layout: page
toc: true
---

*[Note: **bold** = Yonggwan Lee, \* = corresponding author]*
{: .pub-note}

{% assign pubs = site.data.publications_domestic %}
{% assign total = 0 %}
{% for group in pubs %}
  {% assign total = total | plus: group.papers.size %}
{% endfor %}
{% assign counter = total %}

{% for group in pubs %}
## {{ group.year }}

{% for paper in group.papers %}
<p class="pub-title" markdown="1"><span class="pub-num">{{ counter }}.</span><span class="pub-text">**{{ paper.title }}**</span></p>
<p class="pub-authors" markdown="1">{{ paper.authors }}</p>
<p class="pub-journal" markdown="1">*{{ paper.journal }}*. {{ paper.citation }}, {{ paper.date }}{% if paper.doi and paper.doi != "" %} · [DOI](https://doi.org/{{ paper.doi }}){% endif %}</p>

{% assign counter = counter | minus: 1 %}
{% endfor %}
{% endfor %}


