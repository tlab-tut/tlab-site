---
layout: page
title: 研究業績
permalink: /publications/
---

- [Google Scholar](https://scholar.google.com/)
- [researchmap](https://researchmap.jp/)

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign years = pubs | map: "year" | uniq %}

{% for y in years %}

{% if forloop.first %}
<details class="accordion" open>
{% else %}
<details class="accordion">
{% endif %}

<summary><strong>{{ y }}</strong></summary>

{% assign yearly = pubs | where: "year", y %}

{% assign journals = yearly | where: "type", "journal" %}
{% assign internationals = yearly | where: "type", "international" %}
{% assign domestics = yearly | where: "type", "domestic" %}

{% if journals.size > 0 %}
<h4>Journal Papers</h4>
<ul class="publication-list">
{% for pub in journals %}
<li class="publication-item">
  {{ pub.authors }},
  “{{ pub.title }},”
  <strong>{{ pub.venue }}</strong>,
  {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.number %}({{ pub.number }}){% endif %}{% if pub.pages %}, pp.{{ pub.pages }}{% endif %}, {{ pub.year }}.
  {% if pub.doi %}
  <br><span class="doi">DOI: <a href="{{ pub.doi }}">{{ pub.doi }}</a></span>
  {% endif %}
</li>
{% endfor %}
</ul>
{% endif %}

{% if internationals.size > 0 %}
<h4>International Conference Papers</h4>
<ul class="publication-list">
{% for pub in internationals %}
<li class="publication-item">
  {{ pub.authors }},
  “{{ pub.title }},”
  <strong>{{ pub.venue }}</strong>,
  {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.number %}({{ pub.number }}){% endif %}{% if pub.pages %}, pp.{{ pub.pages }}{% endif %}, {{ pub.year }}.
  {% if pub.doi %}
  <br><span class="doi">DOI: <a href="{{ pub.doi }}">{{ pub.doi }}</a></span>
  {% endif %}
</li>
{% endfor %}
</ul>
{% endif %}

{% if domestics.size > 0 %}
### Domestic Conference Papers
<h4>Domestic Conference Papers</h4>
<ul class="publication-list">
{% for pub in domestics %}
<li class="publication-item">
  {{ pub.authors }},
  “{{ pub.title }},”
  <strong>{{ pub.venue }}</strong>,
  {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.number %}({{ pub.number }}){% endif %}{% if pub.pages %}, pp.{{ pub.pages }}{% endif %}, {{ pub.year }}.
  {% if pub.doi %}
  <br><span class="doi">DOI: <a href="{{ pub.doi }}">{{ pub.doi }}</a></span>
  {% endif %}
</li>
{% endfor %}
</ul>
{% endif %}

</details>

{% endfor %}
