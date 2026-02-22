---
layout: page
title: 研究業績
permalink: /publications/
---

- [Google Scholar](https://scholar.google.com/)
- [researchmap](https://researchmap.jp/)

## 学術論文（Journal Papers）

{% assign journals = site.data.publications | where: "type", "journal" | sort: "year" | reverse %}

{% for pub in journals %}
- {{ pub.authors }},  
  "{{ pub.title }},"  
  **{{ pub.venue }}**,  
  {{ pub.volume }}({{ pub.number }}), pp.{{ pub.pages }}, {{ pub.year }}.  
  {% if pub.doi %}DOI: {{ pub.doi }}{% endif %}
{% endfor %}

## International Conference Papers
{% assign confs = site.data.publications | where: "type", "international" | sort: "year" | reverse %}

{% for pub in confs %}
- {{ pub.authors }},  
  "{{ pub.title }},"  
  **{{ pub.venue }}**,  
  {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.number %}({{ pub.number }}){% endif %}{% if pub.pages %}, pp.{{ pub.pages }}{% endif %}, {{ pub.year }}.  
  {% if pub.doi %}DOI: {{ pub.doi }}{% endif %}
{% endfor %}