---
layout: page
title: システム工学研究室（高橋Gr）
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

<div style="margin: 1.5rem 0; padding: 1rem; border: 1px solid #ccc; border-radius: 8px;">
  <strong>産学連携・技術相談はこちら</strong><br><br>
  <div style="display: flex; align-items: center; gap: 20px; margin-top: 1rem; flex-wrap: wrap;">
    <a href="https://rac.tut.ac.jp/org02/tcform/" target="_blank"
      style="display:inline-block; padding:0.6rem 1rem; background:#2c7be5; color:white; text-decoration:none; border-radius:5px;">
      お問い合わせフォームへ
    </a>
    <img src="{{ '/assets/images/qr_contact_type2.png' | relative_url }}"
        alt="問い合わせQRコード"
        style="width:120px;">
  </div>
</div>

<div style="margin: 1.5rem 0; padding: 1rem; border: 1px solid #ccc; border-radius: 8px;">
  <strong>産学連携・技術相談はこちら</strong>

  <div style="display: flex; align-items: center; gap: 20px; margin-top: 1rem; flex-wrap: wrap;">

    <!-- ボタン -->
    <a href="{{ '/contact/' | relative_url }}"
       style="display:inline-block; padding:0.7rem 1.2rem; background:#2c7be5; color:white; text-decoration:none; border-radius:5px; white-space: nowrap;">
      お問い合わせフォームへ
    </a>

    <!-- QRコード -->
    <img src="{{ '/assets/images/qr_contact.png' | relative_url }}"
         alt="問い合わせQRコード"
         style="width:120px; height:auto;">
  </div>
</div>

<h2>各種リンク</h2>

<h3>所属・大学関連</h3>
<ul>
  <li><a href="https://www.tut.ac.jp/" target="_blank">豊橋技術科学大学</a></li>
  <li><a href="https://www.me.tut.ac.jp/" target="_blank">機械工学系</a></li>
</ul>

<h3>研究・プロジェクト</h3>
<ul>
  <li><a href="{{ '/research/' | relative_url }}">研究紹介</a></li>
</ul>

<h3>産学連携・技術相談</h3>
<ul>
  <li><a href="https://www.tut.ac.jp/develop/collaboration/consultation.html" target="_blank">
    産学連携・共同研究窓口（TUT）
  </a></li>
  <li><a href="{{ '/contact/' | relative_url }}">
    技術相談・お問い合わせ（研究室）
  </a></li>
</ul>

<h3>国際連携</h3>
<ul>
  <li><a href="https://www.ipa.fraunhofer.de/" target="_blank">Fraunhofer IPA</a></li>
</ul>

<h3>学会</h3>
<ul>
  <li><a href="https://www.jsme.or.jp/" target="_blank">日本機械学会</a></li>
  <li><a href="https://www.sice.jp/" target="_blank">SICE</a></li>
</ul>