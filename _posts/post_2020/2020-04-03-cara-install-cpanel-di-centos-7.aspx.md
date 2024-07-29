---
title: Cara Install cPanel di CentOS 7
author: Dzubayyan Ahmad
type: post
date: 2020-04-02T17:03:34+00:00
url: /cara-install-cpanel-di-centos-7.aspx
tags:
  - All
  - linux
  - Tutorial

---
# Cara Install cPanel di CentOS 7 {#Cara-Install-cPanel-di-CentOS-7}

Halo teman-teman semua, nah di artikel kali ini akan membahas mengenai Cara Install cPanel di CentOS 7, seperti yang kita semua ketahui bawah cpanel control panel untuk web hosting yang paling banyak di gunakan, paling mudah digunakan dan digunakan secara komersil. Selain itu cpanel juga mempunyai banyak fitur yang dapat digunakan dengan mudah dengan tampilan GUI nya untuk memanage semuanya.

Cpanel ini akan terinstall bersamaan dengan WHM (Web Host Manager), yang mana ini akan mempermudahkan admin web untuk mengelola di antaranya :

<li class="">
  WHM diperuntukkan akses root dan akses reseller, yang mana user dapat mengelola, melakukan pengaturan yang di butuhkan untuk administrasi server dan menejemen akun.
</li>
<li class="">
  Cpanel diperuntukkan untuk tampilan user biasa untuk memanage akun web hosting di server.
</li>

## [][1]Fitur yang ada di cPanel/WHM {#Fitur-yang-ada-di-cPanelWHM}

Berikut adalah fitur yang ada di cPanel dan WHM

<li class="">
  Tampilan GUI yang powerfull untuk mengontrol server dengan WHM
</li>
<li class="">
  Support dengan Sertifikasi EV
</li>
<li class="">
  Support API Authentication Tokens.
</li>
<li class="">
  Auto SSL support dengan Proxy Subdomains.
</li>
<li class="">
  Mengaktikan SSL status di cpanel.
</li>
<li class="">
  Support melakukan backup, migrasi, restore dengan mudah.
</li>
<li class="">
  Support menejemen DNS dan Email server sebagai akun user
</li>
<li class="">
  Support manajemen servis di server (start, stop, enable, disable service)
</li>
<li class="">
  Support mengkonfigurasi SSL/TLS untuk semua servis di serber dan semua user domain
</li>
<li class="">
  Support integrasi database dengan phpmyadmin untuk web browser
</li>
<li class="">
  Support rebranding
</li>
<li class="">
  Support integrasi dengan WHMCS untuk billing manajemen
</li>
<li class="">
  dan masih banyak lagi
</li>

## [][2]Syarat Install di cPanel di Server {#Syarat-Install-di-cPanel-di-Server}

Sebelum menginstall perlu di sadari bahwa untuk menginstall cPanel di server paling tidak membutuhkan spesisikasi berikut ini :

<li class="">
  Server yang masih baru dengan sistem operasi minimal CentOS 7 Server
</li>
<li class="">
  RAM minimal 1GB, namun di atas 2GB lebih direkomendasikan
</li>
<li class="">
  Disk minimal 20GB, namun diatas 40GB lebih direkomendasikan
</li>
<li class="">
  Mempunyai license cPanel
</li>
<li class="">
  Standar hostname (FQDN atau Fully Qualified Domain Name)
</li>
<li class="">
  Perl & curl
</li>

Dan berikut ini hal yang perlu di perhatikan sebelum memasukki instlasi.

<li class="">
  Setelah menginstall cPanel/WHM di system, ini tidak bisa di uninstall di system, Untuk menghapusnya perlu melakukan reinstall system operasi untuk menghapus nya.
</li>
<li class="">
  cPanel adalah software yang bersifat commercial dan membutuhkan sebuah license agar bekerja, dan disediakan 15 hari untuk percobaan (trial / percobaan akan langsung aktif setelah selesai menginstall cPanel)
</li>

## [][3]Install cPanel di CentOS 7 {#Install-cPanel-di-CentOS-7}

<li class="">
  Pastikan server temen-temen semua sudah memiliki starndar hostname (FQDN or Fully Qualified Domain Name), jika tidak di atur bisa mengikuti cara seperti ini untuk mengaturnya. (Untuk contoh disini, saya setting hostnamenya adalah venus, dan&nbsp;<a href="https://masdzub.com/" target="_blank" rel="noreferrer noopener">masdzub.com</a>&nbsp;adalah namadomain)
</li>

<pre class="dz-block-code"><code># hostnamectl set-hostname venus.masdzub.com
</code></pre>

<ol start="2">
  <li class="">
    cPanel di tulis menggunakan Perl, jadi pastikan di server sudah terinstall perl, dan jika belum terinstall bisa install sebagai berikut :
  </li>
</ol>

<pre class="dz-block-code"><code># yum install perl
</code></pre>

<ol start="3">
  <li class="">
    Ada script untuk memasang / menginstall cPanel secara otomatis, yang perlu dilakukan adalah mendownload script tersebut menggunakan curl, jika belum ada curl di server silahkan ikuti cara ini untuk menginstallnya
  </li>
</ol>

<pre class="dz-block-code"><code># yum install curl
</code></pre>

<ol start="4">
  <li class="">
    Pindah ke home directory dengan cara berikut ini
  </li>
</ol>

<pre class="dz-block-code"><code># cd ~
</code></pre>

<ol start="5">
  <li class="">
    Download script dan menjalankan instalasi sampai selesai. Untuk menjalankannya di pastikan login menggunakan ssh. Dan koneksi internet untuk server dalam kondisi stabil. Dan untuk download dan menjalankannya dengan cara berikut ini :
  </li>
</ol>

<pre class="dz-block-code"><code># curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest
</code></pre>

dan akan muncul berikut ini dan tunggu proses sampai selesai:

<pre class="dz-block-code"><code># curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 33151  100 33151    0     0  27418      0  0:00:01  0:00:01 --:--:-- 27442
Verifying archive integrity... All good.
Uncompressing cPanel & WHM Installer......
        ____                  _
    ___|  _ \ __ _ _ __   ___| |
   / __| |_) / _` | '_ \ / _ \ |
  | (__|  __/ (_| | | | |  __/ |
   \___|_|   \__,_|_| |_|\___|_|

  Installer Version v00097 rfc9e3cc20b51698d65f242183461de59649b63a8

Loaded plugins: fastestmirror
Cleaning repos: base digitalocean-agent extras updates
Cleaning up list of fastest mirrors
Beginning main installation.
2020-04-02 16:17:58  929 &#91;1638] ( INFO): cPanel & WHM installation started at: Thu Apr  2 16:17:58 2020!
2020-04-02 16:17:58  930 &#91;1638] ( INFO): This installation will require 10-50 minutes, depending on your hardware and network.
2020-04-02 16:17:58  931 &#91;1638] ( INFO): Now is the time to go get another cup of coffee/jolt.
2020-04-02 16:17:58  932 &#91;1638] ( INFO): The install will log to the /var/log/cpanel-install.log file.
2020-04-02 16:17:58  933 &#91;1638] ( INFO):
2020-04-02 16:17:58  934 &#91;1638] ( INFO): Beginning Installation v3...
2020-04-02 16:17:58  579 &#91;1638] (DEBUG):   Detected distro “centos-release”, version “7.6”, arch “x86_64”
2020-04-02 16:17:58  603 &#91;1638] ( INFO): CentOS 7.6 (linux) detected!
2020-04-02 16:17:58  618 &#91;1638] ( INFO): Checking RAM now...
2020-04-02 16:17:58  678 &#91;1638] ( INFO): Validating that the system hostname ('venus.masdzub.com') is a FQDN...
2020-04-02 16:17:58  702 &#91;1638] ( INFO): Checking for NetworkManager now...
2020-04-02 16:17:58  727 &#91;1638] ( INFO): NetworkManager is not installed.
2020-04-02 16:17:58  822 &#91;1638] ( INFO): Checking for any control panels...
2020-04-02 16:17:58  714 &#91;1638] ( INFO): Checking for essential system files...
2020-04-02 16:17:58  186 &#91;1638] ( INFO): Running health checks prior to start.
2020-04-02 16:17:58 1253 &#91;1638] ( INFO): Validating whether the system can look up domains...
2020-04-02 16:17:58 1260 &#91;1638] (DEBUG):   Testing httpupdate.cpanel.net...
2020-04-02 16:17:58 1260 &#91;1638] (DEBUG):   Testing securedownloads.cpanel.net...
2020-04-02 16:17:59  803 &#91;1638] ( INFO): cPanel Layer 1 Installer Starting...
2020-04-02 16:17:59  804 &#91;1638] ( INFO): Warning !!! Warning !!! WARNING !!! Warning !!! Warning
2020-04-02 16:17:59  805 &#91;1638] ( INFO): -------------------------------------------------------
2020-04-02 16:17:59  806 &#91;1638] ( INFO): cPanel requires a fresh, clean server!
2020-04-02 16:17:59  807 &#91;1638] ( INFO): If you serve websites from this server, this installer
2020-04-02 16:17:59  808 &#91;1638] ( INFO): will overwrite all of your configuration files.
2020-04-02 16:17:59  809 &#91;1638] ( INFO): Hit Ctrl+C NOW!
2020-04-02 16:17:59  810 &#91;1638] ( INFO): If this is a new server, please ignore this message.
2020-04-02 16:17:59  811 &#91;1638] ( INFO): -------------------------------------------------------
2020-04-02 16:17:59  812 &#91;1638] ( INFO): Warning !!! Warning !!! WARNING !!! Warning !!! Warning
2020-04-02 16:17:59  813 &#91;1638] ( INFO): Waiting 5 seconds...
2020-04-02 16:17:59  814 &#91;1638] ( INFO):
2020-04-02 16:17:59  815 &#91;1638] ( INFO):
</code></pre>

Dalam proses ini yang diperlukan menunggu proses, dengan minum secangkir kopi duduk relax dan tenang. Anggap saja istirahat sembari menunggu instalasi cpanel selesai. Karena memakan waktu yang cukup lama kisaran waktu 10-20 menit tergantung koneksi internet dan spesifikasi pada server.

<ol start="6">
  <li class="">
    Setelah instalasi selesai, dicoba akses melalui web dan mencoba masuk ke WHM dengan menggunakan url berikut ini :
  </li>
</ol>

<pre class="dz-block-code"><code>http:&#47;&#47;Server_IP:2087
</code></pre>

atau

<pre class="dz-block-code"><code>http:&#47;&#47;hostname.domain:2087
</code></pre>

kurang lebih akan seperti berikut ini  
<img decoding="async" src="https://i.imgur.com/0xWXfd4.png" alt="" class="" />  
Untuk login menggunakan user&nbsp;**“root”**&nbsp;dan memasukkan pasword.

<ol start="7">
  <li class="">
    Dan proses selanjutnya adalah membaca&nbsp;<strong>End User License Agreement</strong>&nbsp;dan menerimanya dengan mengeklik&nbsp;<strong>Agree to All</strong>&nbsp;untuk lanjut<br /><img decoding="async" src="https://i.imgur.com/TLJv55Z.png" alt="" class="" />
  </li>
  <li class="">
    Dan di step berikut ini adalah di Setup Networking, di minta untuk memasukkan email agar ketika ada notifikasi masuk ke email kerja. Dan memasukkan NameServer yang ingin digunakan. Dan klik finish untuk menajutkannya<br /><img decoding="async" src="https://i.imgur.com/Qpy30ZW.png" alt="" class="" />
  </li>
  <li class="">
    Dan berikut ini adalah tampilan ketika sudah selesi instalasi akan menjadi seperti in<br /><img decoding="async" src="https://i.imgur.com/xEgwiPF.png" alt="" class="" />
  </li>
  <li class="">
    Untuk mengaktifkan filesystem quota, agar dapat diketahui disk space yang digunakan maka klik enable pada pojok kanan atas, dan akan masuk ke tampilan baru kemudian klik process. Dan menjalankan reboot juga. Agar update dan file quotas dapat digunakan.<br /><img decoding="async" src="https://i.imgur.com/KIpCley.png" alt="" class="" />
  </li>
  <li class="">
    Setelah semua sudah selesai teman-teman bisa membuat akun baru untuk user, dan memanagenya.
  </li>
  <li class="">
    Silahkan beli license cpanel. Dan jika sudah membeli license cpanel untuk IP server maka selanjutnya adalah restart license pada server dengan menjalankan command berikut ini di terminal
  </li>
</ol>

<pre class="dz-block-code"><code>/usr/local/cpanel/cpkeyclt
</code></pre>

## [][4]Kesimpulan {#Kesimpulan}

Cukup mudah sekali untuk melakukan instalasi cPanel di CentOS 7. Hanya dengan mendownload script, menjalankan dan menunggu sampai selesai. Selain itu untuk cPanel sendiri sangat mudah di operasikan dan fitur-fitur yang banyak dan sangat powerfull.

 [1]: https://hackmd.io/2MTGniJESJC7gKGbanTF9w?view#Fitur-yang-ada-di-cPanelWHM
 [2]: https://hackmd.io/2MTGniJESJC7gKGbanTF9w?view#Syarat-Install-di-cPanel-di-Server
 [3]: https://hackmd.io/2MTGniJESJC7gKGbanTF9w?view#Install-cPanel-di-CentOS-7
 [4]: https://hackmd.io/2MTGniJESJC7gKGbanTF9w?view#Kesimpulan