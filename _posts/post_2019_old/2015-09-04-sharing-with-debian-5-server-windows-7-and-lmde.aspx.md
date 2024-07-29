---
title: sharing with debian 5 server, windows 7 and LMDE
author: Dzubayyan Ahmad
type: post
date: 2015-09-03T23:50:00+00:00
excerpt: '						'
url: /sharing-with-debian-5-server-windows-7-and-lmde.aspx

tags:
  - linux
  - Tutorial
  - Windows

---
<div style="line-height: 100%; margin-bottom: 0cm;">
  Nah kali ini saya mau share sharing data antara debian 5 server(virtualbox), windows 7 (virtualbox), dan LMDE saya sendiri, nah sebenarnya ini adalah tugas yang di berikan guru, untuk konfigurasi samba, ya udah mari cekidoot guys,,
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  KONFIGURASI DI DEBIAN 5 SERVER
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  masuk ke user <b>root</b>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  nah yang pertama kita konfigurasi IP dan DNS dulu,
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # nano /etc/network/interfaces
</div>

<div style="clear: both; text-align: center;">
</div>

&nbsp;

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B16-15-15.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B16-15-15-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="clear: both; text-align: center;">
</div>

-konfigurasi interfaces seperti di gambar

<div style="line-height: 100%; margin-bottom: 0cm;">
  -lalu restart konfigurasi
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # /etc/init.d/networking restart
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-30-13.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-30-13-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -lalu install DNSnya
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # apt-get install bind9
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-31-45.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-31-45-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -masukkan cd debian servernya
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -lalu konfigurasi bind9 tersebut
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -pindah ke direktory /etc/bind/
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # cd /etc/bind/
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-04.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-04-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -lalu edit konfigurasi named.conf
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  ** untuk db.virza ganti dengan nama anda
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-14.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-14-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-43.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-32-43-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -copy pastekan db.local ke db.nama
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -copy pastekan db.127 ke db.192
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-33-25.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-33-25-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -konfigurasi db.nama
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-34-54.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-34-54-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -konfigurasi db.192
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-35-56.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-35-56-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -restart konfigurasinya
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-36-33.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-36-33-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -cek DNS tersebut
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # nslookup ipanda
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # nslookup linkanda
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-37-28.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-37-28-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-22.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-22-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -pindah ke / lagi,
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # cd
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -install samba
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # apt-get install samba
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-22.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-22-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="clear: both; text-align: center;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-28.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-28-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -pindah ke direktori home user
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # cd /home/user
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-43-12.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-43-12-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -tambahkan forder
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # mkdir share
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-43-47.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-43-47-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -pindah ke direktori samba
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # cd /etc/samba
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-49.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-39-49-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -konfigurasi sambanya
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # nano smb.conf
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-44-55.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-44-55-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -cari tulisan security = user di bagian Authentication
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -ganti user dengan share
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -tambahkan tulisan sedikit di bagian share definitions [lihat gambar]
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -tambahkan user untuk samba
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-46-01.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-46-01-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # smbpasswd -a nama
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -restart samba
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # /etc/init.d/samba restart
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  -jika sudah selese, silahkan cek dengan testparm
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  # testparm
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-49-42.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-27-2B18-49-42-300x194.png" alt="" alt="" width="320" height="206" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  sudah selese
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  KONFIGURASI LMDE 2 BETSY
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  seperti halnya debian 5, hanya saja untuk konfigurasi smb.conf
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  untuk konfigurasi smb.conf
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  seperti gambar ini
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-09-04-2B06-49-13.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-09-04-2B06-49-13-300x185.png" alt="" alt="" width="320" height="197" border="0" /></a>
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  KONFIGURASI windows 7 (virtualbox)
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  biasanya sudah banyak yang bisa, jadi saya tidak perlu mengulangi
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
  alhasil
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="line-height: 100%; margin-bottom: 0cm;">
</div>

<div style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-30-2B16-23-31.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/09/Screenshot-2Bfrom-2B2015-08-30-2B16-23-31-300x169.png" alt="" alt="" width="320" height="179" border="0" /></a>
</div>

&nbsp;