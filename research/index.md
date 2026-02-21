---
layout: page
title: 研究テーマ
permalink: /research/
---

<div class="research-grid">

  <!-- factory_amr -->
  {% assign ready_factory = true %}
  {% if ready_factory %}
  <a href="{{ '/research/factory_amr/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_factory %}disabled{% endunless %}">
    {% unless ready_factory %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/SCANinHamanaE.png' | relative_url }}" alt="Factory AMR">
    <h3>可変ゾーニング工場における搬送ロボットの自動化</h3>
    <p>
      設備配置の変更が頻繁な工場にも適用できるVGM位置推定により搬送ロボットの自動化を目指します。
    </p>
    <div class="tags">
      <span class="tag tech">AMR</span>
      <span class="tag industry">Factory Automation</span>
    </div>
  </div>
  {% if ready_factory %}
  </a>
  {% endif %}

  <!-- vgm_core -->
  {% assign ready_vgm = false %}
  {% if ready_vgm %}
  <a href="{{ '/research/vgm_core/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_vgm %}disabled{% endunless %}">
    {% unless ready_vgm %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/vmg_flow2025.png' | relative_url }}" alt="VGM localization">
    <h3>VGM の高度化</h3>
    <p>
      Ceiling-VGM、Panorama-VGMなどの派生を展開し、NDT融合や最適化統合に取り組んでいます。
    </p>
    <div class="tags">
      <span class="tag tech">AI</span>
      <span class="tag tech">VGM</span>
      <span class="tag tech">Optimization</span>
    </div>
  </div>
  {% if ready_vgm %}
  </a>
  {% endif %}

  <!-- library -->
  {% assign ready_library = false %}
  {% if ready_library %}
  <a href="{{ '/research/library/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_library %}disabled{% endunless %}">
    {% unless ready_library %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/AMRinTCL.png' | relative_url }}" alt="Library Robotics">
    <h3>図書館における誤配架検出システム</h3>
    <p>
      誤配架図書を検出し、マップ上で可視化することで効率的な運用を支援します。
    </p>
    <div class="tags">
      <span class="tag tech">AI</span>
      <span class="tag tech">Digital Twin</span>
      <span class="tag life">Service Robotics</span>
    </div>
  </div>
  {% if ready_library %}
  </a>
  {% endif %}

  <!-- custodial -->
  {% assign ready_custodial = false %}
  {% if ready_custodial %}
  <a href="{{ '/research/custodial/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_custodial %}disabled{% endunless %}">
    {% unless ready_custodial %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/dirt_monitoring.png' | relative_url }}" alt="Custodial Robotics">
    <h3>施設カストーディアルのための清潔度モニタリング</h3>
    <p>
      汚れ分布を定量化し、きめ細かな清掃計画の策定を支援します。
    </p>
    <div class="tags">
      <span class="tag tech">AI</span>
      <span class="tag tech">Digital Twin</span>
      <span class="tag life">Smart Living</span>
    </div>
  </div>
  {% if ready_custodial %}
  </a>
  {% endif %}

  <!-- agritech_amr -->
  {% assign ready_agri = false %}
  {% if ready_agri %}
  <a href="{{ '/research/agritech_amr/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_agri %}disabled{% endunless %}">
    {% unless ready_agri %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/Field_of_AgliTech1.png' | relative_url }}" alt="Agritech AMR">
    <h3>農作業補助ロボットの自律移動</h3>
    <p>
      屋外環境における自律走行と作業支援の実現を目指します。
    </p>
    <div class="tags">
      <span class="tag tech">AMR</span>
      <span class="tag industry">AgriTech</span>
    </div>
  </div>
  {% if ready_agri %}
  </a>
  {% endif %}

  <!-- map_generation -->
  {% assign ready_map = false %}
  {% if ready_map %}
  <a href="{{ '/research/map_generation/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_map %}disabled{% endunless %}">
    {% unless ready_map %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/scans.png' | relative_url }}" alt="Map Generation">
    <h3>参照マップ作成の効率化</h3>
    <p>
      3Dモデル構築の自動化と効率化を推進します。
    </p>
    <div class="tags">
      <span class="tag tech">VGM</span>
      <span class="tag tech">Optimization</span>
    </div>
  </div>
  {% if ready_map %}
  </a>
  {% endif %}

  <!-- multi_amr -->
  {% assign ready_multi = false %}
  {% if ready_multi %}
  <a href="{{ '/research/multi_amr/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_multi %}disabled{% endunless %}">
    {% unless ready_multi %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/MAPD-withVGM.png' | relative_url }}" alt="Multi AMR">
    <h3>複数AMRの協調制御</h3>
    <p>
      拡張性と安定性を兼ね備えた協調搬送システムを構築します。
    </p>
    <div class="tags">
      <span class="tag tech">AMR</span>
      <span class="tag industry">Factory Automation</span>
    </div>
  </div>
  {% if ready_multi %}
  </a>
  {% endif %}

  <!-- autonomy -->
  {% assign ready_autonomy = false %}
  {% if ready_autonomy %}
  <a href="{{ '/research/autonomy/' | relative_url }}" class="research-card-link">
  {% endif %}
  <div class="research-card {% unless ready_autonomy %}disabled{% endunless %}">
    {% unless ready_autonomy %}<span class="card-arrow">準備中</span>{% else %}<span class="card-arrow">→</span>{% endunless %}
    <img src="{{ '/assets/images/research/under_construction.png' | relative_url }}" alt="Autonomy">
    <h3>自律システム</h3>
    <p>
      情報と行為の関係から自律性を理論的に探究します。
    </p>
  </div>
  {% if ready_autonomy %}
  </a>
  {% endif %}

</div>
