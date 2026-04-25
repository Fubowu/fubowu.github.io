---
layout: default
title: 關於福伯論壇
permalink: /about/
---
<div class="post-page">
  <article class="post-article">
    <header class="post-header">
      <h1 class="post-title">關於福伯論壇</h1>
    </header>
    <div class="post-content" style="white-space:normal">
      <h2>關於本站</h2>
      <p><strong>福伯論壇</strong>（FuBo Forum）是吳福成的個人筆記部落格，自 2012 年起持續以繁體中文記錄對時事、人文與自然的觀察與思考。{{ site.time | date: '%Y' | minus: 2012 }}年來共累積{%- include format_posts.html -%}篇文章、{%- include format_images.html -%}張照片。</p>

      <h2>關於作者</h2>
      <p><strong>福伯</strong>（吳福成）：長期觀察台灣自然生態、國際關係與中華文化的獨立寫作者。</p>

      <h2>內容主題</h2>
      <p>本壇文章涵蓋四大類別：</p>
      <ul>
        <li><strong>自然觀察</strong>：台灣各地花木、植物園的田野記錄，兼及植物學知識、物種辨識與文化典故。</li>
        <li><strong>國際關係與兩岸政策</strong>：對台灣外交、兩岸關係、俄羅斯動態與亞太局勢的分析評論。</li>
        <li><strong>人文歷史</strong>：中華文化典故、節氣民俗、歷史事件的探索與詮釋。</li>
        <li><strong>生活隨筆</strong>：日常感悟、台灣各地踏查紀錄與藝文欣賞。</li>
      </ul>

      <h2>訂閱文章通知</h2>
      <p>輸入 Email，每當有新文章發布即會收到通知信。</p>
      <form id="about-subscribe-form" style="display:flex;gap:8px;flex-wrap:wrap;margin-top:12px">
        <input type="email" id="about-subscribe-email" placeholder="您的 Email" required
               style="flex:1;min-width:200px;padding:8px 12px;border:1px solid #ccc;border-radius:4px;font-size:.95rem">
        <button type="submit"
                style="padding:8px 20px;background:#4a7c59;color:#fff;border:none;border-radius:4px;cursor:pointer;font-size:.95rem">訂閱</button>
      </form>
      <p id="about-subscribe-msg" style="display:none;margin-top:10px;font-size:.9rem"></p>

      <h2>聯絡福伯</h2>
      <ul>
        <li>Facebook：<a href="https://www.facebook.com/fubowuforum/" target="_blank" rel="noopener noreferrer">福伯論壇粉絲頁</a></li>
      </ul>
    </div>
    <div class="post-footer">
      <a class="back-link" href="{{ site.baseurl }}/">返回首頁</a>
    </div>
  </article>
</div>

<script>
(function(){
  var SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbwtTP_xAJ090foc3OSez0Nt7tc5EW5NBDvIDVvlXk7yLpFUPLvCUUk7Exs7B2shqj6e/exec';
  var form = document.getElementById('about-subscribe-form');
  var msg  = document.getElementById('about-subscribe-msg');
  if (!form) return;
  form.addEventListener('submit', function(e){
    e.preventDefault();
    var email = document.getElementById('about-subscribe-email').value.trim();
    var btn = form.querySelector('button');
    btn.textContent = '處理中…'; btn.disabled = true;
    var fd = new FormData(); fd.append('email', email);
    fetch(SCRIPT_URL, { method:'POST', mode:'no-cors', body:fd })
      .then(function(){
        form.style.display = 'none';
        msg.style.color = '#4a7c59';
        msg.textContent = '✅ 已送出！請檢查收件匣，確認訂閱信。';
        msg.style.display = 'block';
      })
      .catch(function(){
        msg.style.color = '#c0392b';
        msg.textContent = '❌ 送出失敗，請稍後再試。';
        msg.style.display = 'block';
        btn.textContent = '訂閱'; btn.disabled = false;
      });
  });
})();
</script>
