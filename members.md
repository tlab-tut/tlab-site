---
layout: page
title: メンバー
permalink: /members/
---

{% assign members = site.pages | where: "layout", "member" %}

{% assign roles = "faculty,postdoc,doctoral,master,undergrad,alumni" | split: "," %}

{% for r in roles %}
  {% assign group = members | where: "role", r | sort: "order" %}
  {% if group.size > 0 %}

<h2>
{% case r %}
{% when "faculty" %}Faculty
{% when "postdoc" %}Postdoctoral Researcher
{% when "doctoral" %}Doctoral Students
{% when "master" %}Master Students
{% when "undergrad" %}Undergraduate Students
{% when "alumni" %}Alumni
{% endcase %}
</h2>

<div class="member-grid">
  {% for m in group %}
  <div class="member-card">
    <a href="{{ m.url | relative_url }}">
      <img src="{{ m.image_thumb | relative_url }}">
      <h3>{{ m.name_ja }}</h3>
    </a>
    {% if m.position %}<p>{{ m.position }}</p>{% endif %}
  </div>
  {% endfor %}
</div>

  {% endif %}
{% endfor %}


<!-- ---
layout: page
title: メンバー
permalink: /members/
---

## 教員
- **高橋 淳二（准教授）** — ロボティクス、屋内位置推定、CPS、精密自動組み立て、参加型センシング

## 研究員
- 橋本 貴輝 — ポイントクラウド、モデリング、測量

## 学生
- M2 Doniddorj Bayanjargal — 複数AMRの協調ナビゲーション
- M2 小川 永遠 — AMRによる屋内フロア衛生評価
- M2 中馬 豪斗 — VO と VGM の統合
- M1 小西 洸生 — 工場へのVGMとAMRの導入、
- M1 木田 博貴 — VGMの性能向上（NDTの利用）
- M1 Andy William — VGMとObject-SLAM の統合
- M1 利根川 涼 — Optimized-VGM
- B4 森川倭 — AMRの自律制御/遠隔操作の切替
- B4 日野 綾瀬 — 図書館DX
- B4 Stanley Susantyo — object-VGM

## 卒業生・修了生
- 卒業年度・進路などを記載できます。 -->
