---
layout: page
title: 発表
permalink: /presentations/
---

{% assign pres = site.data.presentations
   | sort: "year" | reverse %}

{% assign years = pres | map: "year" | uniq %}

{% for y in years %}

{% if forloop.first %}
<details class="accordion" open>
{% else %}
<details class="accordion">
{% endif %}

<summary><strong>{{ y }}</strong></summary>

{% assign yearly = pres | where: "year", y %}
{% assign internationals = yearly | where: "category", "international" %}
{% assign domestics = yearly | where: "category", "domestic" %}

{% if internationals.size > 0 %}
<h4>International Presentations</h4>
<ul>
{% for pub in internationals %}
<li class="publication-item">
  {{ pub.authors }},
  “{{ pub.title }},”
  {{ pub.venue }},
  {% if pub.presentation_type %} ({{ pub.presentation_type }}){% endif %}
  {{ pub.year }}.
</li>
{% endfor %}
</ul>
{% endif %}

{% if domestics.size > 0 %}
<h4>国内学会発表</h4>
<ul>
{% for pub in domestics %}
<li class="publication-item">
  {{ pub.authors }},
  「{{ pub.title }}」,
  {{ pub.venue }},
  {{ pub.year }}.
</li>
{% endfor %}
</ul>
{% endif %}

</details>

{% endfor %}