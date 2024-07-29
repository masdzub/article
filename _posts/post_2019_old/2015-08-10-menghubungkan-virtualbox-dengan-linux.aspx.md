---
title: Menghubungkan Virtualbox dengan linux
author: Dzubayyan Ahmad
type: post
date: 2015-08-10T01:41:00+00:00
excerpt: '						'
url: /menghubungkan-virtualbox-dengan-linux.aspx
tags:
  - linux
  - Tutorial

---
<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  Mesin virtual menjadi pilihan karna tidak perlu menginstall di dalam harddisk secara langsung, kemaren guru saya sedikit nanya, karna yang menggunakan OS linux di kelas cuma saya, dan pertanyaan tersebut akan saya jawab dan akan saya share di blog tercinta ini, pertanyaan: “Bagaimana cara menghubungkan jaringan LAN dengan OS yang sebenarnya” <kurang lebih seperti itu> nah langsung aja kita ke TKP..
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://4.bp.blogspot.com/-fPzianvqYN4/VcgAfxHSuEI/AAAAAAAAAyM/O-Zt4HoVwiA/s1600/Screenshot%2Bfrom%2B2015-08-10%2B05%253A34%253A36.png"><img loading="lazy" decoding="async" src="https://4.bp.blogspot.com/-fPzianvqYN4/VcgAfxHSuEI/AAAAAAAAAyM/O-Zt4HoVwiA/s320/Screenshot%2Bfrom%2B2015-08-10%2B05%253A34%253A36.png" alt="" alt="" width="320" height="239" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  Setelah install Virtualbox terbaru di OS linux, buka virtualboxnya dan masuk ke “File > Preference” atau juga bisa menggunakan shortcut “ctrl+G” untuk membuka Preference-nya
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>



<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://4.bp.blogspot.com/-paQJYpzU7Rg/VcgAr4bXYII/AAAAAAAAAyU/3J2jTNA5eI0/s1600/Screenshot%2Bfrom%2B2015-08-10%2B08%253A38%253A42.png"><img loading="lazy" decoding="async" src="https://4.bp.blogspot.com/-paQJYpzU7Rg/VcgAr4bXYII/AAAAAAAAAyU/3J2jTNA5eI0/s320/Screenshot%2Bfrom%2B2015-08-10%2B08%253A38%253A42.png" alt="" alt="" width="320" height="231" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  jika sudah terdapat box baru pergi ke bagian Network, lalu ke “Host Only Network”
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  jika sudah berada dalam Host-Only Network, mari tambahkan hardware LAN dengan menge-click tombol hardware yang ada “+” nya,
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://1.bp.blogspot.com/-wdmaSzFniXY/VcgBEC0sdZI/AAAAAAAAAyk/HMendx7qO08/s1600/Screenshot%2Bfrom%2B2015-08-10%2B08%253A40%253A20.png"><img loading="lazy" decoding="async" src="https://1.bp.blogspot.com/-wdmaSzFniXY/VcgBEC0sdZI/AAAAAAAAAyk/HMendx7qO08/s320/Screenshot%2Bfrom%2B2015-08-10%2B08%253A40%253A20.png" alt="" alt="" width="320" height="231" border="0" /></a>
</div>

<div style="clear: both; text-align: center;">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  untuk pertama kalinya akan ada hardware dengan nama “vboxnet0” lalu kita konfigurasi dengan memilih gambar obeng di samping tersebut.
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://2.bp.blogspot.com/-QrO2Sd2W3KY/VcgBL_7EKyI/AAAAAAAAAys/bV7KtH1Ryt0/s1600/Screenshot%2Bfrom%2B2015-08-10%2B08%253A40%253A56.png"><img loading="lazy" decoding="async" src="https://2.bp.blogspot.com/-QrO2Sd2W3KY/VcgBL_7EKyI/AAAAAAAAAys/bV7KtH1Ryt0/s320/Screenshot%2Bfrom%2B2015-08-10%2B08%253A40%253A56.png" alt="" alt="" width="320" height="163" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  Kita konfigurasi adapternya.. biasanya untuk jaringan LAN menggunakan Ipv4 dan IP network masknya
</div>