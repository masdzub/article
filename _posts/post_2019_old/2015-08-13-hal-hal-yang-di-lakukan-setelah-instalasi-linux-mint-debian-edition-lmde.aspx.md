---
title: 'Hal hal yang di lakukan setelah instalasi linux Mint Debian Edition 2 [LMDE]'
author: Dzubayyan Ahmad
type: post
date: 2015-08-13T02:15:00+00:00
excerpt: '						'
url: /hal-hal-yang-di-lakukan-setelah-instalasi-linux-mint-debian-edition-lmde.aspx

tags:
  - linux

---
<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  Huu huu huuu&#8230; Guys linux Mint 17.2 ane eror, dan musti install ulang, dan kebetulan di FD saya ada Bootable LMDE, dari pada galau langsung saya install aja tuh LMDE, dalam pikiran saya LMDE hampir sama lah kaya linux Mint base Ubuntu, ternyata agak berbeda guys, cara instalasinya agak rumit, namun asik guys, bisa belajar lebih baik lagi, LMDE 2 ini guys basenya DEBIAN 8 (Jessy), nah setelah instalasinya selese ane tanya mbah gugel, “Do after Installing LMDE” , “do after installing linux Mint Debian”.. dan yang muncul malah linux mint base ubuntu, kalo engga ya Debian,, ya udah ane coba sendiri aja,, cara cara semua ane compile jadi sebuah cara yang lumayan runtut. Oke mari kita langsung ke Lokasi Kejadian..
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  #update database software
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  update database software dengan perintah : <span style="color: blue;">sudo apt-get update</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  #upgrade software
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  upgrade software yang baru dengan perintah : <span style="color: blue;">sudo apt-get upgrade</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  #ganti repository yang deket dengan lokasi<br /> karna saya ada di indonesia saya milih repository dari kambing,<br /> 
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  cara gantinya dengan perintah : Sudo gedit /etc/apt/sources.list
</div>

<div style="line-height: 100%; margin-bottom: 0cm;" align="left">
  tambahkan skrip di bawah ini
</div>

<pre style="text-align: left;"><span style="color: blue;">deb https://kambing.ui.ac.id/debian-security/ testing/updates main contrib non-free
deb https://kambing.ui.ac.id/debian/ testing main contrib non-free
deb https://kambing.ui.ac.id/debian-multimedia/ testing main non-free
deb https://repo.ukdw.ac.id/linuxmint debian main upstream import backport romeo</span></pre>

<div style="line-height: 100%; margin-bottom: 0cm;">
  #update database software
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo apt-get update</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  jika mengalami eror ketika update <a href="https://www.seputarinfo.co.vu/2015/08/cara-mengatasi-debian-public-keys-error.html" target="_blank" rel="noopener noreferrer">klik disini</a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  #upgrade database software
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo apt-get upgrade</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  #install browser selain Firefox
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo apt-get install chromium-browser chromium-browser-l10n pepperFlashplugin-nonfree</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  #hapus aplikasi mono runtime
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo apt-get remove mono-runtime-common</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  setelah menghapus mono runtime
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo apt-get install gnome-mplayer xpad</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  #matikan hibernasi (suspend ke disk)
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <span style="color: blue;">sudo mv -v /etc/polkit-1/localauthority/50-local.d/com.ubuntu.enable-hibernate.pkla /</span>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>