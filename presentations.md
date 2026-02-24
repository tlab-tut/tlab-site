---
layout: page
title: 発表
permalink: /presentations/
---

{% assign pres = site.data.publications
   | where_exp: "item", "item.type == 'international_short' or item.type == 'domestic'" 
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
{% assign internationals = yearly | where: "type", "international_short" %}
{% assign domestics = yearly | where: "type", "domestic" %}

{% if internationals.size > 0 %}
<h4>International Conference Papers (Short)</h4>
<ul>
{% for pub in internationals %}
<li class="publication-item">
  {{ pub.authors }},
  “{{ pub.title }},”
  <strong>{{ pub.venue }}</strong>,
  {% if pub.pages %}pp.{{ pub.pages }}, {% endif %}{{ pub.year }}.
  {% if pub.doi %}
    <br><a href="{{ pub.doi }}" target="_blank">DOI</a>
  {% endif %}
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
  <strong>{{ pub.venue }}</strong>,
  {{ pub.year }}.
</li>
{% endfor %}
</ul>
{% endif %}

</details>

{% endfor %}