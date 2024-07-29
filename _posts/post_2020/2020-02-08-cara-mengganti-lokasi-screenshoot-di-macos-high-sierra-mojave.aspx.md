---
title: Cara mengganti lokasi screenshoot di MacOS High Sierra, Mojave
author: Dzubayyan Ahmad
type: post
date: 2020-02-08T15:12:20+00:00
url: /cara-mengganti-lokasi-screenshoot-di-macos-high-sierra-mojave.aspx
tags:
  - All
  - linux
  - Mac
  - Tutorial

---
<h1 id="Cara-mengganti-lokasi-screenshoot-di-MacOS-High-Sierra" class="part" data-startline="1" data-endline="1">
  Cara mengganti lokasi screenshoot di MacOS High Sierra
</h1>

<p class="part" data-startline="4" data-endline="4">
  Hello teman-teman semua, buat teman-teman yang menggunakan mac os dan masih os nya masih di high sierra atau sierra untuk hasil screenshoot akan di letakkan di desktop. Selain itu untuk hasil dari screenshoot adalah PNG bukanlah JPEG. Jika teman-teman semua ingin mengganti lokasi tujuan menyimpan screenshoot ada di tempat yang di inginkan.
</p>

<h2 id="Cara-screenshoot-di-Mac" class="part" data-startline="5" data-endline="5">
  Cara screenshoot di Mac.
</h2>

<p class="part" data-startline="6" data-endline="6">
  Untuk screenshoot di mac dapat menggunakan kombinasi keyboard <code>command + shift + 3</code> untuk seluruh layar, dan menggunakan kombinasi keyboard <code>command + shift + 4</code> untuk screenshoot areal atau anda bisa menyesuaikan screenshoot yang di inginkan.
</p>

<h2 id="Mengganti-lokasi-file-screenshoot-di-MacOS-High-Sierra" class="part" data-startline="7" data-endline="7">
  Mengganti lokasi file screenshoot di MacOS High Sierra
</h2>

<p class="part" data-startline="8" data-endline="8">
  Untuk mengganti lokasi perlu di perhatikan untuk lokasinya. Silahkan di buat dulu. Kalau saya pribadi di taruh di disk yang berbeda dan membuat folder baru dengan nama screenshoot.
</p>

<p class="part" data-startline="10" data-endline="10">
  Jika sudah, teman-teman bisa ikuti cara ini untuk merubah lokasi file screenshootnya :
</p>

<ol class="part" data-startline="11" data-endline="27">
  <li class="" data-startline="11" data-endline="13">
    Buka terminal (di dalam Utilities), disini saya menggunakan iTerm. Untuk terminal di sesuaikan saja sesuai kebutuhan<br /> <img decoding="async" class="" src="https://i.imgur.com/tyKIyCT.png" alt="iterm" /><br /> <img decoding="async" class="" src="https://i.imgur.com/dv1rsqx.png" alt="terminal" />
  </li>
  <li class="" data-startline="14" data-endline="17">
    Jika sudah di buka, silahkan masukkan script di bawah ini ke terminal.<br /> <code>defaults write com.apple.screencapture location</code><br /> <img decoding="async" class="" src="https://i.imgur.com/mMdMYoN.png" alt="terminal 2" />
  </li>
  <li class="" data-startline="18" data-endline="20">
    Buat folder baru dengan nama screenshoot di file manager / finder.<br /> <img decoding="async" class="" src="https://i.imgur.com/GMbTsPq.png" alt="finder" />
  </li>
  <li class="" data-startline="21" data-endline="23">
    Drag folder tersebut ke terminal.<br /> <img decoding="async" class="" src="https://i.imgur.com/EvkSDyy.png" alt="" />
  </li>
  <li class="" data-startline="24" data-endline="25">
    Maka akan muncul tampilan seperti ini pada terminal.<br /> <img decoding="async" class="" src="https://i.imgur.com/h0lLsFP.png" alt="" />
  </li>
  <li class="" data-startline="26" data-endline="26">
    Kemudian tekan enter pada keyboard.
  </li>
  <li class="" data-startline="27" data-endline="27">
    Jika sudah di enter, kemudian jalankan command ini di terminal.
  </li>
</ol>

<pre class="part" data-startline="28" data-endline="30"><code>killall SystemUIServer
</code></pre>

<p class="part" data-startline="31" data-endline="31">
  <img decoding="async" class="" src="https://i.imgur.com/a0IWOH1.png" alt="" />
</p>

<p class="part" data-startline="33" data-endline="34">
  Dan silahkan di coba untuk screenshoot kembali dan lihatlah. Lokasi filenya sudah berubah sesuai yang di inginkan.<br /> <img decoding="async" class="" src="https://i.imgur.com/9Y2HIeB.png" alt="" />
</p>