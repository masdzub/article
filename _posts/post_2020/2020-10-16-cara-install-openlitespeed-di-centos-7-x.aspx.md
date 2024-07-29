---
title: Cara Install OpenLiteSpeed di CentOS 7.x
author: Dzubayyan Ahmad
type: post
date: 2020-10-15T17:00:22+00:00
url: /cara-install-openlitespeed-di-centos-7-x.aspx
tags:
  - All
  - linux
  - Tutorial

---
<p class="part" title="" data-startline="2" data-endline="2" data-position="43" data-size="0" data-original-title="" aria-describedby="popover95518">
  <span data-position="43" data-size="376">Halo teman-teman semua, kali ini saya akan membahas cara menginstall OpenLiteSpeed di CentOS 7.x. Sebelum lebih jauh ketahui dulu yuk apa itu OpenLiteSpeed. OpenLiteSpeed adalah sebuah lighweigh Web Server yang sudah mempunyai fitur web tampilan admin. Untuk OpenLIteSpeed ini adalah versi gratis atau versi free dari LiteSpeed. Untuk lengkapnya bisa check di webnya langsung </span><span data-position="419" data-size="30"><a href="https://www.litespeedtech.com/" target="_blank" rel="noopener noreferrer">https://www.litespeedtech.com/</a></span>
</p>

<h2 id="Cara-Install-OpenLiteSpeed" class="part" data-endline="4" data-startline="4" data-id="Cara-Install-OpenLiteSpeed">
  <span data-position="454" data-size="26">Cara Install OpenLiteSpeed</span>
</h2>

<p class="part" data-size="0" data-position="481" data-endline="5" data-startline="5">
  <span data-position="481" data-size="123">Untuk melakukan instalasi OpenLiteSpeed pastikan sudah memiliki akses ke server dengan user root agar memudahkan instalasi.</span>
</p>

<h3 id="--Menambahkan-repository-EPEL" class="part" data-startline="7" data-endline="7" data-id="--Menambahkan-repository-EPEL">
  <span data-position="610" data-size="29">&#8211; Menambahkan repository EPEL</span>
</h3>

<p class="part" data-startline="8" data-endline="8" data-position="640" data-size="0">
  <span data-position="641" data-size="114">Sebelum melakukan instalasi pastikan sudah melakukan instalasi repository EPEL terlebih dahulu. Bisa check caranya</span><a href="https://tulisan.masdzub.com/install-dan-mengaktifkan-epel-repository-di-centos-8.aspx" target="_blank" rel="noopener noreferrer"><span data-position="755" data-size="7"> disini</span></a>
</p>

<h3 id="--Menambahkan-repository-LiteSpeed" class="part" data-startline="10" data-endline="10" data-id="--Menambahkan-repository-LiteSpeed">
  <span data-position="857" data-size="34">&#8211; Menambahkan repository LiteSpeed</span>
</h3>

<p class="part" data-startline="11" data-endline="11" data-position="892" data-size="0">
  <span data-position="892" data-size="117">Untuk melakukan instalasi perlu menambahkan repository dari repo litespeed ke server. Untuk caranya sebagai berikut :</span>
</p>

<pre class="part" data-startline="12" data-endline="18" data-position="1011"><code>[root@dragon ~]# rpm -ivh https://rpms.litespeedtech.com/centos/litespeed-repo-1.1-1.el7.noarch.rpm
Retrieving https://rpms.litespeedtech.com/centos/litespeed-repo-1.1-1.el7.noarch.rpm
Preparing...                          ################################# [100%]
Updating / installing...
   1:litespeed-repo-1.2-1.el7         ################################# [100%]
</code></pre>

<p class="part" data-startline="20" data-endline="20" data-position="1386" data-size="0">
  <span data-position="1386" data-size="71">Untuk menambahkan repository sebentar saja, tidak lama untuk prosesnya.</span>
</p>

<h3 id="--Install-OpenLiteSpeed" class="part" data-startline="22" data-endline="22" data-id="--Install-OpenLiteSpeed">
  <span data-position="1463" data-size="23">&#8211; Install OpenLiteSpeed</span>
</h3>

<p class="part" data-startline="23" data-endline="23" data-position="1487" data-size="0">
  <span data-position="1487" data-size="152">Setelah menambahkan repository di server, selanjutnya melakukan instalasi OpenLiteSpeed di server. Untuk caranya cukup menjalankan command berikut ini :</span>
</p>

<pre class="part" data-startline="24" data-endline="26" data-position="1641"><code>[root@dragon ~]# yum install -y openlitespeed
</code></pre>

<p class="part" data-startline="27" data-endline="27" data-position="1695" data-size="0">
  <span data-position="1695" data-size="164">Setelah melakukan enter atau menjalankan perintah diatas di tunggu saja. Maka akan dengan sendirinya. Untuk kecepatan install ini pengaruh dari koneksi internet ya.</span>
</p>

<h3 id="--Menjalankan-OpenLiteSpeed" class="part" data-startline="29" data-endline="29" data-id="--Menjalankan-OpenLiteSpeed">
  <span data-position="1865" data-size="27">&#8211; Menjalankan OpenLiteSpeed</span>
</h3>

<p class="part" data-startline="30" data-endline="30" data-position="1893" data-size="0">
  <span data-position="1893" data-size="127">Agar service OpenLiteSpeed ini berjalan ketika booting sekaligus mengaktifkan service dengan menjalankan perintah berikut ini :</span>
</p>

<pre class="part" data-startline="31" data-endline="34" data-position="2022"><code>[root@dragon ~]# systemctl enable lsws
[root@dragon ~]# systemctl start lsws
</code></pre>

<h3 id="--Cek-Service-OpenLiteSpeed" class="part" data-endline="36" data-startline="36" data-id="--Cek-Service-OpenLiteSpeed">
  <span data-position="2112" data-size="27">&#8211; Cek Service OpenLiteSpeed</span>
</h3>

<p class="part" data-startline="37" data-endline="37" data-position="2140" data-size="0">
  <span data-position="2140" data-size="97">Untuk melakukan pengecekan apakah service sudah berjalan dengan menjalankan command berikut ini :</span>
</p>

<pre class="part" data-startline="38" data-endline="53" data-position="2239"><code>[root@dragon ~]# systemctl status lsws
● lshttpd.service - OpenLiteSpeed HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/lshttpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Thu 2020-10-15 16:20:01 UTC; 6min ago
  Process: 23335 ExecStart=/usr/local/lsws/bin/lswsctrl start (code=exited, status=0/SUCCESS)
 Main PID: 23360 (litespeed)
   CGroup: /system.slice/lshttpd.service
           ├─23360 openlitespeed (lshttpd - main)
           ├─23372 openlitespeed (lscgid)
           └─23399 openlitespeed (lshttpd - #01)

Oct 15 16:19:58 dragon.masdzub.com systemd[1]: Starting OpenLiteSpeed HTTP Server...
Oct 15 16:19:59 dragon.masdzub.com lswsctrl[23335]: [OK] litespeed: pid=23360.
Oct 15 16:20:01 dragon.masdzub.com systemd[1]: Started OpenLiteSpeed HTTP Server.
</code></pre>

<p class="part" data-startline="54" data-endline="55" data-position="3050" data-size="0">
  <span data-position="3050" data-size="49">Jika sudah muncul seperti diatas yang menyatakan </span><code data-position="3100" data-size="16">active (running)</code><span data-position="3118" data-size="74"> maka itu sudah dipastikan sudah berjalan untuk service OpenLiteSpeed nya.</span><br /> <span data-position="3193" data-size="52">Secara default untuk OpenLiteSpeed berjalan di port </span><code data-position="3246" data-size="4">8088</code><span data-position="3251" data-size="101">, untuk melakukan apakah sudah benar di server bisa di buka di browser dengan mengetikkan di browser </span><a href="https://ipserver:8088/" target="_blank" rel="noopener noreferrer"><span data-position="3352" data-size="21">https://ipserver:8088/</span></a><span data-position="3373" data-size="41"> dan seharusnya akan muncul seperti ini :</span>
</p>

<p class="part" data-startline="57" data-endline="57" data-position="3417" data-size="0">
  <img decoding="async" class="" src="https://i.imgur.com/cFD0EEm.png" alt="OpenLiteSpeed" data-position="3417" data-size="49" />
</p>

<h3 id="--Setting-User-Admin" class="part" data-startline="59" data-endline="59" data-id="--Setting-User-Admin">
  <span data-position="3472" data-size="20">&#8211; Setting User Admin</span>
</h3>

<p class="part" data-startline="60" data-endline="60" data-position="3493" data-size="0">
  <span data-position="3493" data-size="310">Seperti yang sudah dijelaskan diawal bahwa OpenLiteSpeed sudah menggunakan web admin untuk mengelola web server nya. Dalam hal ini memerlukan settingan awal untuk masuk ke dalam web admin nya. Untuk melakukan generate username dan passwordnya teman-teman semua bisa menjalankan perintah berikut ini di server :</span>
</p>

<pre class="part" data-startline="61" data-endline="76" data-position="3805"><code>[root@dragon ~]# /usr/local/lsws/admin/misc/admpass.sh

Please specify the user name of administrator.
This is the user name required to login the administration Web interface.

User name [admin]: soy

Please specify the administrator's password.
This is the password required to login the administration Web interface.

Password:
Retype password:
Administrator's username/password is updated successfully!
[root@dragon ~]#
</code></pre>

<p class="part" data-startline="78" data-endline="78" data-position="4238" data-size="0">
  <span data-position="4238" data-size="46">Dalam menjalankan perintah diatas pada bagian </span><code data-position="4285" data-size="18">User name [admin]:</code><span data-position="4304" data-size="75"> bisa diisikan username yang diinginkan, jika dalam contoh saya menuliskan </span><code data-position="4380" data-size="3">soy</code><span data-position="4384" data-size="63"> untuk username nya. Jika dikosongkan maka akan default, yaitu </span><code data-position="4448" data-size="5">admin</code><span data-position="4454" data-size="19">. Dalam mengisikan </span><code data-position="4474" data-size="8">Password</code><span data-position="4483" data-size="5"> dan </span><code data-position="4489" data-size="17">Retype password :</code><span data-position="4507" data-size="114"> tidak akan muncul apapun, namun akan terecord. Jadi bisa langsung dimasukkan password yang teman-teman dinginkan.</span>
</p>

<h3 id="--Mengakses-Web-Admin-OpenLiteSpeed" class="part" data-startline="80" data-endline="80" data-id="--Mengakses-Web-Admin-OpenLiteSpeed">
  <span data-position="4627" data-size="35">&#8211; Mengakses Web Admin OpenLiteSpeed</span>
</h3>

<p class="part" data-startline="81" data-endline="81" data-position="4663" data-size="0">
  <span data-position="4663" data-size="72">Untuk mengakses web Admin OpenLiteSpeed secara default berjalan di port </span><code data-position="4736" data-size="4">7080</code><span data-position="4741" data-size="57"> sehingga bisa jalankan di browser dengan memasukkan url </span><a href="https://ipserver:7080/" target="_blank" rel="noopener noreferrer"><span data-position="4798" data-size="21">https://ipserver:7080/</span></a><span data-position="4819" data-size="93"> dan seharusnya akan muncul tampilan seperti dibawah ini. Jika sudah sesuai maka sudah benar.</span>
</p>

<p class="part" data-startline="83" data-endline="83" data-position="4914" data-size="0">
  <img decoding="async" class="" src="https://i.imgur.com/BzojT4N.png" alt="web admin openlitespeed" data-position="4914" data-size="59" /><span data-position="4973" data-size="1">.</span>
</p>

<p class="part" data-startline="85" data-endline="85" data-position="4977" data-size="0">
  <span data-position="4977" data-size="183">Silahkan diisikan username dan password admin yang sudah dibuat tadi. Setelah itu klik login. Dan jika sudah berhasil login maka tampilan dari web admin nya akan seperti berikut ini :</span>
</p>

<p class="part" data-startline="87" data-endline="87" data-position="5163" data-size="0">
  <img decoding="async" class="" src="https://i.imgur.com/jj22LHP.png" alt="masuk web admin" data-position="5163" data-size="51" />
</p>

<h2 id="Kesimpulan" class="part" data-startline="89" data-endline="89" data-id="Kesimpulan">
  <span data-position="5219" data-size="10">Kesimpulan</span>
</h2>

<p class="part" data-startline="90" data-endline="90" data-position="5230" data-size="0">
  <span data-position="5230" data-size="585">OpenLiteSpeed adalah salah satu webserver yang sering dikenal sebagai Lighweight Web Server yang berbasis opensource sebagai alternatif dari Apache dan NGINX. Untuk web server ini tergolong dalam teknologi yang baru dan OpenLiteSpeed / LiteSpeed mengeclaim lebih cepat daripada Apache dan NGINX. Secara konsep kinerja dari web server ini hampir mirip dengan NGINX namun lebih efisien lagi. Selain itu Webserver ini juga memiliki tampilan Web Admin untuk mengelola, sehingga lebih mudah dalam melakukan setting / konfigurasi website, apalagi jika dalam 1 server terdapat banyak website.</span>
</p>