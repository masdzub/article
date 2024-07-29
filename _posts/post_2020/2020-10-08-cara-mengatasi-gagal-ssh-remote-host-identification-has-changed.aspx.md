---
title: 'Cara mengatasi gagal SSH : REMOTE HOST IDENTIFICATION HAS CHANGED!'
author: Dzubayyan Ahmad
type: post
date: 2020-10-08T16:42:57+00:00
url: /cara-mengatasi-gagal-ssh-remote-host-identification-has-changed.aspx
tags:
  - All
  - linux
  - Tutorial
  - Windows

---
<p class="part" data-startline="3" data-endline="3" data-position="70" data-size="0">
  <span data-position="70" data-size="283">SSH atau Secure Shell adalah salah satu cara yang biasa digunakan untuk mengakses server atau vps dari jarak jauh (remote) dengan aman melalui perintah berbasis CLI. Hal ini dimaksudkan agar sebuah keamanan ketika akses server dapat dilanjutkan dan bebas dari penyadapan secara aman.</span>
</p>

<p class="part" data-startline="5" data-endline="5" data-position="356" data-size="0">
  <span data-position="356" data-size="97">Setelah melakukan akses SSH dan terkadang terdapat pesan error kurang lebih seperti berikut ini :</span>
</p>

<pre class="part" title="" data-startline="6" data-endline="21" data-position="455" data-original-title=""><code>❙~❱✘≻ ssh dragon
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ECDSA key sent by the remote host is
SHA256:UTq3gyBmzMvV83NSXeLkbTfFoFp5wtG/yRz2wZWnSx4.
Please contact your system administrator.
Add correct host key in /home/masdzub/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in /home/masdzub/.ssh/known_hosts:58
ECDSA host key for 128.199.190.240 has changed and you have requested strict checking.
Host key verification failed.
</code></pre>

<p class="part" data-startline="23" data-endline="23" data-position="1262" data-size="0">
  <span data-position="1262" data-size="294">Penyebab dari error tersebut bisa dikarenakan sebelumnya sudah pernah melakukan akses remote akses ssh ke IP tersebut, namun untuk VPS / server tersebut telah dilakukan install ulang OS pada vps / server. Sebelum permasalah ini bisa diselesaikan tidak akan bisa masuk atau akses server via SSH.</span>
</p>

<h2 id="Cara-mengatasi" class="part" data-startline="25" data-endline="25" data-id="Cara-mengatasi">
  <span data-position="1561" data-size="14">Cara mengatasi</span>
</h2>

<p class="part" data-startline="26" data-endline="26" data-position="1577" data-size="0">
  <span data-position="1577" data-size="113">Untuk mengatasinya terdapat beberapa cara, untuk yang saat ini kita bahas ada 3. Untuk kurang lebih seperti ini :</span>
</p>

<h3 id="1-Menghapus-Manual" class="part" data-endline="28" data-startline="28" data-id="1-Menghapus-Manual">
  <span data-position="1697" data-size="20">1. Menghapus Manual</span>
</h3>

<p class="part" data-startline="29" data-endline="29" data-position="1718" data-size="0">
  <span data-position="1718" data-size="156">Untuk cara yang pertama dengan cara menghapus manual. Dari pesan error diatas sudah mendapatkan clue untuk mengatasinya. Untuk caranya seperti berikut ini :</span>
</p>

<ul class="part" data-startline="31" data-endline="35">
  <li class="" data-startline="31" data-endline="31" data-position="1879" data-size="0">
    <span data-position="1879" data-size="54">Didalam error tersebut sudah memberitahu lokasi dari </span><code data-position="1934" data-size="19">offending ECDSA key</code><span data-position="1954" data-size="86"> yang ada di known_hosts. Dalam pesan contoh pesan error saya kurang lebih seperti ini </span><code data-position="2042" data-size="56">Offending ECDSA key in /home/masdzub/.ssh/known_hosts:58</code><span data-position="2099" data-size="77"> hal ini menandakan berada di file &#8220;/home/masdzub/.ssh/known_hosts` baris 58.</span>
  </li>
  <li class="" data-startline="32" data-endline="32" data-position="2180" data-size="0">
    <span data-position="2180" data-size="10">Buka file </span><code data-position="2191" data-size="11">known_hosts</code><span data-position="2203" data-size="25"> menggunakan text editor.</span>
  </li>
  <li class="" data-startline="33" data-endline="33" data-position="2232" data-size="0">
    <span data-position="2232" data-size="60">Cari baris ke 58 lalu hapus baris tersebut, kemudian simpan.</span>
  </li>
  <li class="" data-startline="34" data-endline="35" data-position="2295" data-size="0">
    <span data-position="2295" data-size="38">Lalu coba kembali untuk akses SSH nya.</span>
  </li>
</ul>

<p class="part" data-startline="36" data-endline="36" data-position="2335" data-size="0">
  <span data-position="2335" data-size="73">Dengan cara menghapus baris tersebut, berarti SSH client tidak mempunyai </span><code data-position="2409" data-size="21">ECDSA key fingerprint</code><span data-position="2431" data-size="153"> lagi, sehingga dari system ssh akan menanyakan kembali untuk memverifikasi authentikasi ke server saat akan terkoneksi kembali. Dan saat sudah memiliki </span><code data-position="2585" data-size="21">ECDSA key fingerprint</code><span data-position="2607" data-size="14"> yang baru di </span><code data-position="2622" data-size="11">known_hosts</code><span data-position="2634" data-size="37"> dam peringatan tersebut akan hilang.</span>
</p>

<h3 id="2-Menggunakan-ssh-keygen" class="part" data-endline="38" data-startline="38" data-id="2-Menggunakan-ssh-keygen">
  <span data-position="2678" data-size="25">2. Menggunakan ssh-keygen</span>
</h3>

<p class="part" data-startline="39" data-endline="39" data-position="2704" data-size="0">
  <span data-position="2704" data-size="41">Untuk solusi yang lain dapat menggunakan </span><code data-position="2746" data-size="10">ssh-keygen</code><span data-position="2757" data-size="38"> untuk menghapus key yang ada di file </span><code data-position="2796" data-size="11">known_hosts</code><span data-position="2808" data-size="62">. Untuk menggunakannya bisa menjalankan perintah berikut ini :</span>
</p>

<pre class="part" data-startline="40" data-endline="42" data-position="2871"><code>$ ssh-keygen -R [hostname atau IP]
</code></pre>

<p class="part" data-startline="44" data-endline="44" data-position="2915" data-size="0">
  <span data-position="2915" data-size="29">Untuk contoh menggunakan IP :</span>
</p>

<pre class="part" data-startline="45" data-endline="50" data-position="2946"><code>$ ssh-keygen -R 128.199.190.240
# Host 128.199.190.240 found: line 58
/home/masdzub/.ssh/known_hosts updated.
Original contents retained as /home/masdzub/.ssh/known_hosts.old
</code></pre>

<p class="part" data-startline="52" data-endline="52" data-position="3130" data-size="0">
  <span data-position="3130" data-size="35">Untuk contoh menggunakan hostname :</span>
</p>

<pre class="part" data-startline="53" data-endline="58" data-position="3166"><code>$ ssh-keygen -R dragon.masdzub.com
# Host dragon.masdzub.com found: line 58
/home/masdzub/.ssh/known_hosts updated.
Original contents retained as /home/masdzub/.ssh/known_hosts.old
</code></pre>

<p class="part" data-startline="60" data-endline="60" data-position="3356" data-size="0">
  <span data-position="3356" data-size="82">Cara ini lebih efektif bilamana teman-teman tidak ingin mengedit secara manual di </span><code data-position="3439" data-size="11">known_hosts</code><span data-position="3451" data-size="179">. Selain itu cara ini lebih mudah juga jika menggunakan banyak hostname atau IP address. Selain itu cara ini juga akan membuat file baru dengan nama known_hosts.old sebagai backup.</span>
</p>

<h3 id="3-Rubah-nama-file-known_hosts" class="part" data-startline="62" data-endline="62" data-id="3-Rubah-nama-file-known_hosts">
  <span data-position="3637" data-size="29">3. Rubah nama file known_hosts</span>
</h3>

<p class="part" data-startline="63" data-endline="63" data-position="3668" data-size="0">
  <span data-position="3668" data-size="96">Untuk cara ini dilakukan jika kedua cara diatas masih belum berhasil, sebelum merubah nama file </span><code data-position="3765" data-size="11">known_hosts</code><span data-position="3777" data-size="103"> pastikan untuk sudah mengetahui lokasi filenya. Seperti yang ada di error atas, lokasi filenya ada di </span><code data-position="3881" data-size="30">/home/masdzub/.ssh/known_hosts</code><span data-position="3912" data-size="27">, jadi kita perlu masuk ke </span><code data-position="3940" data-size="19">/home/masdzub/.ssh/</code><span data-position="3960" data-size="42">, untuk stepnya kurang lebih seperti ini :</span>
</p>

<ul class="part" data-startline="64" data-endline="64">
  <li class="" data-startline="64" data-endline="64" data-position="4006" data-size="0">
    <span data-position="4006" data-size="9">Masuk ke </span><code data-position="4017" data-size="19">/home/masdzub/.ssh/</code><span data-position="4038" data-size="14"> dengan cara :</span>
  </li>
</ul>

<pre class="part" data-position="4054" data-endline="67" data-startline="65"><code>$ cd /home/masdzub/.ssh/
</code></pre>

<ul class="part" data-startline="68" data-endline="68">
  <li class="" data-startline="68" data-endline="68" data-position="4089" data-size="0">
    <span data-position="4089" data-size="22">Memastikan untuk file </span><code data-position="4112" data-size="11">known_hosts</code><span data-position="4124" data-size="18"> ada dengan cara :</span>
  </li>
</ul>

<pre class="part" data-startline="69" data-endline="73" data-position="4144"><code>$ ls
config             id_rsa_sg.bak        id_rsa.pub
config.bak         id_rsa_sg.pub        known_hosts
</code></pre>

<ul class="part" data-startline="74" data-endline="74">
  <li class="" data-startline="74" data-endline="74" data-position="4262" data-size="0">
    <span data-position="4262" data-size="65">Merubah nama file nya menjadi apapun hal yang lain, dengan cara :</span>
  </li>
</ul>

<pre class="part" data-startline="75" data-endline="77" data-position="4329"><code>$ mv known_hosts known_hosts.bak
</code></pre>

<p class="part" data-startline="79" data-endline="79" data-position="4371" data-size="0">
  <span data-position="4371" data-size="34">Cara ini akan menghilangkan semua </span><code data-position="4406" data-size="21">ECDSA key fingerprint</code><span data-position="4428" data-size="76">. Sehingga ketika akses server / vps lagi, harus melakukan verifikasi ulang.</span>
</p>

<h2 id="Kesimpulan" class="part" data-endline="81" data-startline="81" data-id="Kesimpulan">
  <span data-position="4509" data-size="10">Kesimpulan</span>
</h2>

<p class="part" data-startline="82" data-endline="82" data-position="4520" data-size="0">
  <span data-position="4520" data-size="11">Peringatan </span><code data-position="4532" data-size="48">WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!</code><span data-position="4581" data-size="129"> bukanlah sebuah masalah besar, hal ini dikarerenakan IP atau Hostname dari VPS yang sudah diakses sebelumnya sudah tersimpan di </span><code data-position="4711" data-size="11">known_hosts</code><span data-position="4723" data-size="80">, namun terdapat ketidakcocokan dengan VPS yang sudah di install ulang tersebut.</span>
</p>