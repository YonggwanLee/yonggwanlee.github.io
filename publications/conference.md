---
title: Conference Publications
permalink: /publications/conference/
layout: page
toc: true
---

*[Note: **bold** = Yonggwan Lee]*
{: .pub-note}

{% assign kinds = site.data.publications_conference %}

{% for block in kinds %}
{% assign block_total = 0 %}
{% for yg in block.years %}
  {% assign block_total = block_total | plus: yg.papers.size %}
{% endfor %}
{% assign counter = block_total %}

## {{ block.kind }}

{% for yg in block.years %}
### {{ yg.year }}

{% for paper in yg.papers %}
<p class="pub-title" markdown="1"><span class="pub-num">{{ counter }}.</span><span class="pub-text">**{{ paper.title }}**</span></p>
<p class="pub-authors" markdown="1">{{ paper.authors }}</p>
<p class="pub-journal" markdown="1">*{{ paper.journal }}*. {{ paper.citation }}, {{ paper.date }}{% if paper.doi and paper.doi != "" %} · [DOI](https://doi.org/{{ paper.doi }}){% endif %}</p>

{% assign counter = counter | minus: 1 %}
{% endfor %}
{% endfor %}
{% endfor %}
