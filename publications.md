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
<<<<<<< feature/junji

{% if forloop.first %}
<details class="accordion" open>
{% else %}
<details class="accordion">
{% endif %}

<summary><strong>{{ y }}</strong></summary>
=======
## {{ y }}
>>>>>>> main

{% assign yearly = pubs | where: "year", y %}

{% assign journals = yearly | where: "type", "journal" %}
{% assign internationals = yearly | where: "type", "international" %}
{% assign domestics = yearly | where: "type", "domestic" %}

{% if journals.size > 0 %}
### Journal Papers
{% for pub in journals %}
- {{ pub.authors }},  
  "{{ pub.title }},"  
  **{{ pub.venue }}**,  
  {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.number %}({{ pub.number }}){% endif %}{% if pub.pages %}, pp.{{ pub.pages }}{% endif %}.  
  {% if pub.doi %}DOI: {{ pub.doi }}{% endif %}
{% endfor %}
{% endif %}

{% if internationals.size > 0 %}
### International Conference Papers
{% for pub in internationals %}
- {{ pub.authors }},  
  "{{ pub.title }},"  
  **{{ pub.venue }}**,  
  {% if pub.pages %}pp.{{ pub.pages }}.{% endif %}  
  {% if pub.doi %}DOI: {{ pub.doi }}{% endif %}
{% endfor %}
{% endif %}

{% if domestics.size > 0 %}
### Domestic Conference Papers
{% for pub in domestics %}
- {{ pub.authors }},  
  "{{ pub.title }},"  
  **{{ pub.venue }}**.
{% endfor %}
{% endif %}

{% endfor %}
