---
layout: page
title: システム工学研究室（高橋G）
show_title: false
---

<div class="slideshow-container">
  <div class="slides-track">
    <div class="slide">
      <img src="{{ '/assets/images/top/slide1.png' | relative_url }}">
      <div class="overlay">
        <div class="overlay-inner"
            data-ja-title="システム工学研究室（高橋Gr）"
            data-ja-sub="豊橋技術科学大学 機械工学系"
            data-en-title="Systems Engineering Laboratory (T-lab)"
            data-en-sub="Department of Mechanical Engineering, TUT">
          <span class="title"></span><br>
          <span class="sub"></span>
        </div>
      </div>
    </div>

    <div class="slide">
      <img src="{{ '/assets/images/top/slide3.png' | relative_url }}">
    </div>

    <div class="slide">
      <img src="{{ '/assets/images/top/slide5.png' | relative_url }}">
    </div>

    <!-- ★ 先頭を複製（クローン） -->
    <div class="slide is-clone">
      <img src="{{ '/assets/images/top/slide1.png' | relative_url }}">
    </div>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", () => {
  
  /* =========================
     ① スライド（横移動＋無限ループ）
     ========================= */
  
  const track  = document.querySelector(".slides-track");
  const slides = document.querySelectorAll(".slide");
  const slideCount = slides.length;

  let index = 0;
  const duration = 800;   // アニメーション時間(ms)
  const interval = 4500;  // 切替間隔(ms)

  // 初期状態
  slides[index].classList.add("is-active");

  setInterval(() => {
    // 現在スライドを非アクティブに
    slides[index].classList.remove("is-active");

    index++;

    // 横移動
    track.style.transition = `transform ${duration}ms ease-in-out`;
    track.style.transform  = `translateX(-${index * 100}%)`;

    // 通常スライドなら active を付与
    if (index < slideCount - 1) {
      slides[index].classList.add("is-active");
    }

    // クローンに到達したら先頭へ巻き戻す
    if (index === slideCount - 1) {
      setTimeout(() => {
        track.style.transition = "none";
        track.style.transform  = "translateX(0)";
        index = 0;

        slides.forEach(s => s.classList.remove("is-active"));
        slides[0].classList.add("is-active");
      }, duration);
    }

  }, interval);

　/* =========================
     ② 日本語 / 英語オーバーレイ自動切替
     ========================= */
  const isEn =
    window.location.pathname.startsWith("/en/") ||
    window.location.pathname.includes("/en/");

  const overlay = document.querySelector(".overlay-inner");
  if (!overlay) return;

  const titleEl = overlay.querySelector(".title");
  const subEl   = overlay.querySelector(".sub");

  if (isEn) {
    titleEl.textContent = overlay.dataset.enTitle;
    subEl.textContent   = overlay.dataset.enSub;
  } else {
    titleEl.textContent = overlay.dataset.jaTitle;
    subEl.textContent   = overlay.dataset.jaSub;
  }
});
</script>

<h2>お知らせ</h2>
<ul>
  {% for post in site.posts limit:3 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <small>({{ post.date | date: "%Y-%m-%d" }})</small>
    </li>
  {% endfor %}
</ul>
