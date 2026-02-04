---
layout: page
title: システム工学研究室（高橋G）
show_title: false
---

<div class="slideshow-container">
  <div class="slide-wrapper">
    <img class="slide" src="{{ "/assets/images/top/slide1.png" | relative_url }}">
    <div class="slide-title">
      システム工学研究室（高橋G）<br>
      <span>豊橋技術科学大学 機械工学系</span>
    </div>
  </div>
  <div class="slide-wrapper">
    <img class="slide" src="{{ "/assets/images/top/slide2.png" | relative_url }}">
  </div>
  <div class="slide-wrapper">
    <img class="slide" src="{{ "/assets/images/top/slide3.png" | relative_url }}">
  </div>
  <div class="slide-wrapper">
    <img class="slide" src="{{ "/assets/images/top/slide4.png" | relative_url }}">
  </div>
</div>

<script>
let slideIndex = 0;
const slides = document.getElementsByClassName("slide");

function showSlides() {
  for (let i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }
  slideIndex++;
  if (slideIndex > slides.length) { slideIndex = 1; }
  slides[slideIndex - 1].style.display = "block";
  setTimeout(showSlides, 4000); // 4秒ごとに切替
}

showSlides();
</script>

<p>
　自律システムに関する研究を行っています。自律システムとは、周囲の環境に適応しつつ
<strong>自らの判断で行動する主体</strong>の総称であり、狭義には人による遠隔操縦なしに自律的に動作するロボットを指します。このようなロボットでは、環境情報や<strong>自己と環境の関係を表す情報（自己位置情報）</strong>の解像度・精緻さ・信頼性が、実現可能な行動や機能の範囲を規定します。
</p>

<p>
　本研究室では、人の行動や作業を代替するために必要な情報をリーズナブルに取得できる<strong> Visual Geometric Matching（VGM）位置推定法</strong>を研究開発してきました。現在はその成果を基盤として、産業分野および人の生活を支援するシステムへの応用を進めています。
</p>