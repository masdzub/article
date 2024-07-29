---
title: Web Server Dengan 3 Domain
author: Dzubayyan Ahmad
type: post
date: 2015-10-19T08:55:00+00:00
excerpt: '						'
url: /web-server-dengan-3-domain.aspx

tags:
  - linux
  - Tutorial

---
<div style="clear: both; text-align: left;">
  Nah kali ini saya mau share cara buat web server dengan 3 domain,
</div>

setelah instalasi selesai, ikuti langkah yang ada di bawah ini,, cekidot..

<img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/1-300x167.png" alt="" alt="" width="320" height="177" border="0" />  
1. masuk ke akun root  


<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/2-300x167.png" alt="" alt="" width="320" height="177" border="0" />
</div>

2. edit interfacesnya, untuk mengatur ip yang akan di gunakan

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/3.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/3-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
  3. nah akan ada gambar seperti diatas ini
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/4.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/4-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   4. edit dan hapus sebagian skripnya, lihat contoh di atas
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/5.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/5-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   5. restart interfacesnya&#8230; dengan cara &#8221; /etc/init.d/networking restart &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/6.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/6-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
  6. lalu install &#8221; bind9 &#8221; .. dengan cara &#8221; aptitude install bind9 &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/7.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/7-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   7. jika di minta konfirmasi instalasi, masukkan &#8221; y &#8221; lalu enter
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/8.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/8-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   8. edit konfigurasi pada bind, dengan &#8221; nano /etc/bind/named.conf &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/9.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/9-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   9. maka akan ada tulisan seperti diatas,
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/10.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/10-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   10. pindahkan ke paling bawah namun di atas tulisan &#8221; include bla bla bla &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/11.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/11-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
  11. masukkan domain yang akan di buat.. dan simpan konfigurasi..
</div>

<div style="clear: both; text-align: left;">
</div>

<div style="clear: both; text-align: left;">
</div>

<div style="clear: both; text-align: left;">
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/15.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/15-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
    12. setelah di simpan, kopi pastekan file yang telah anda buat, dari &#8221; db.local ke db. yang dibuat &#8221; dan &#8221; db.127 ke db.192 &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/16.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/16-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   13. edit skrip pada db. yang telah dibuat..
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/17.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/17-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/18.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/18-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/19.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/19-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/20.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/20-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/21.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/21-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/22.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/22-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/23.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/23-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/24.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/24-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/25.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/25-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/26.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/26-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/27.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/27-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/28.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/28-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   14. restart konfigurasi pada bind9 nya.. dengan cara &#8221; /etc/init.d/bind9 restart &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/29.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/29-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/30.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/30-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   15. cek lah domain anda, di server, dengan cara &#8221; nslookup domain &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/31.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/31-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/32.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/32-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/33.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/33-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   16. install aplikasi yang di perlukan untuk membuat web di server &#8221; aptitude install apache2 php5 &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/34.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/34-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/35.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/35-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
    17. ikuti petunjuk seperti yang di atas, untuk mengkopi data domain 1 ke domain lain&#8230;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/36.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/36-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/37.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/37-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/38.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/38-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/40.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/40-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/41.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/41-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
     18. edit dan tambahkan ServerName, ServerAlias, dan pindah lokasinya,, cermati lokasi yang ada, jangan sampai salah..
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/42.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/42-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   19. buatlah direktori baru yang telah anda tulis tadi.
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/43.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/43-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   20. lalu edit pada &#8221; /var/www/index.html &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/44.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/44-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/45.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/45-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   21. editlah sesuai selera anda
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/46.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/46-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/47.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/47-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   22. kopikan file indek yang telah di buat tdi ke dalam folder yang telah anda buat tadi,..
</div>

<div style="text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/48.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/48-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/49.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/49-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   23. editlah halaman index.html tadi agar bisa membedakan antara halaman satu dengan halaman lainnya berbeda.
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/50.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/50-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/51.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/51-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   24. editlah halaman yang telah di buat tadi
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/52.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/52-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
  25. restart konfigurasi apache2 yang telah di buat tadi.. dengan cara &#8220;/etc/init.d/apache2 restart &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/53.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/53-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   26. selah berhasil di restart, maka aktifkan web yang telah dibuat tadi menggunakan perintah &#8221; a2ensite *** &#8220;
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/54.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/54-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   27. jika sudah maka reload web server yang telah di buat tadi.
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/55.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/55-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   28. koneksikan dengan client nya,, lalu ping untuk mengecek apakah sudah terhubung
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/56.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/56-300x167.png" alt="" alt="" width="320" height="177" border="0" /></a>
</div>

<div style="text-align: left;">
   29. sukses buat anda&#8230; !!!
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A34-253A24.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A34-253A24-300x177.png" alt="" alt="" width="320" height="188" border="0" /></a>
</div>

<div style="text-align: left;">
   30. cek dns di client anda,, dengan nslookup domain
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A35-253A01.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A35-253A01-300x177.png" alt="" alt="" width="320" height="188" border="0" /></a>
</div>

<div style="text-align: left;">
  <p>
     seharusnya sudah bisa semua&#8230;
  </p>
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A35-253A31.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A35-253A31-300x163.png" alt="" alt="" width="320" height="174" border="0" /></a>
</div>

<div style="text-align: left;">
   nah ini adalah hasil dari web yang telah saya buat..
</div>

<div style="clear: both; text-align: left;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A36-253A02.png"><img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A36-253A02-300x163.png" alt="" alt="" width="320" height="174" border="0" /></a>
</div>

<div style="text-align: left;">
</div>

<div style="clear: both; text-align: left;">
  <img loading="lazy" decoding="async" src="https://www.dzub.web.id/wp-content/uploads/2015/10/Screenshot-2Bfrom-2B2015-10-16-2B20-253A36-253A34-300x163.png" alt="" alt="" width="320" height="174" border="0" />
</div>

* keterangan  
&#8211; ip yang saya gunakan adalah 192.168.4.1  
&#8211; gateway sesuaikan dengan server  
&#8211; domain 1     = ahmad.dz  
&#8211; domain 2     = dzub.ay  
&#8211; domain 3     = ah.mad

<div style="text-align: left;">
</div>