---
title: Install LAMP Stack di CentOS 8
author: Dzubayyan Ahmad
type: post
date: 2020-02-22T12:12:39+00:00
url: /install-lamp-stack-di-centos-8.aspx
tags:
  - All
  - linux
  - Tutorial

---
<h1 id="Install-LAMP-Stack-di-CentOS-8" class="part" data-startline="1" data-endline="1">
  Install LAMP Stack di CentOS 8
</h1>

<p class="part" data-startline="4" data-endline="5">
  LAMP adalah sekumpulan software opensource yang di gunakan untuk web development. Untuk LAMP itu sendiri terdiri dari linux, Apache, MariaDB/MySQL, dan PHP. Untuk fungsinya kurang lebih seperti ini. linux untuk Sistem Operasinya, Apache untuk http web server, MariaDB/MySQL digunakan untuk database managemen, dan PHP untuk bahasa pemrograman yang di gunakan.<br /> Sebelum melakukan instalasi alangkah baiknya jika mengupdate package nya dulu.
</p>

<pre class="part" data-startline="6" data-endline="8"><code>[root@venus ~]# yum update -y
</code></pre>

<h2 id="Install-Apache-HTTP-Server-di-CentOS-8" class="part" data-startline="9" data-endline="9">
  Install Apache HTTP Server di CentOS 8
</h2>

<p class="part" data-startline="10" data-endline="10">
  Apache http server dapat di install di dalam CentOS 8 dengan mudah. Untuk installnya cukup menjalankan perinta di bawah ini.
</p>

<pre class="part" data-startline="11" data-endline="13"><code>yum install httpd -y
</code></pre>

<p class="part" data-startline="14" data-endline="14">
  Tunggu sampai proses instalasi selesai. Untuk download dan installnya tidak membutuhkan waktu lama.
</p>

<h3 id="Mengaktifkan-dan-menjalankan-setiap-booting" class="part" data-startline="15" data-endline="15">
  Mengaktifkan dan menjalankan setiap booting
</h3>

<p class="part" data-startline="16" data-endline="17">
  Setelah proses instalasi selesai, teman-teman dapat menjalankan perintah dibawah ini untuk mengaktifkan dan menjalankan service nya.<br /> Untuk menjalankan setiap booting
</p>

<pre class="part" data-startline="18" data-endline="20"><code>systemctl enable httpd
</code></pre>

<p class="part" data-startline="21" data-endline="21">
  dan untuk menaktifkan service nya dapat menggunakan command di bawah ini
</p>

<pre class="part" data-startline="22" data-endline="24"><code>systemctl start httpd
</code></pre>

<p class="part" data-startline="25" data-endline="25">
  dan untuk melakukan pengechekan apakah sudah aktif atau belum menggunakan command di bawah ini
</p>

<pre class="part" data-startline="26" data-endline="28"><code>systemctl status httpd
</code></pre>

<p class="part" data-startline="29" data-endline="29">
  dan kurang lebih akan muncul tampilan seperti ini
</p>

<pre class="part" data-startline="30" data-endline="49"><code>● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; enabled; vendor preset: disabl&gt;
   Active: active (running) since Sat 2020-02-22 08:16:12 UTC; 7s ago
     Docs: man:httpd.service(8)
 Main PID: 21500 (httpd)
   Status: "Started, listening on: port 80"
    Tasks: 213 (limit: 4899)
   Memory: 37.4M
   CGroup: /system.slice/httpd.service
           ├─21500 /usr/sbin/httpd -DFOREGROUND
           ├─21501 /usr/sbin/httpd -DFOREGROUND
           ├─21502 /usr/sbin/httpd -DFOREGROUND
           ├─21503 /usr/sbin/httpd -DFOREGROUND
           └─21504 /usr/sbin/httpd -DFOREGROUND

Feb 22 08:16:12 venus.masdzub.com systemd[1]: Starting The Apache HTTP Server...
Feb 22 08:16:12 venus.masdzub.com systemd[1]: Started The Apache HTTP Server.
Feb 22 08:16:12 venus.masdzub.com httpd[21500]: Server configured, listening on: port 80
</code></pre>

<p class="part" data-startline="50" data-endline="51">
  Selanjutnya untuk memveridikasi apakah sudah berjalan setiap booting dapat menjalankan command di bawah ini. Dan jika sudah akan muncul <code>enable</code><br /> <code>systemctl is-enable httpd</code>
</p>

<h3 id="Uji-coba-Apache-Http-Server" class="part" data-startline="53" data-endline="53">
  Uji coba Apache Http Server
</h3>

<p class="part" data-startline="54" data-endline="55">
  Untuk mengkonfirmasi apakah apache sudah siap dan sudah bisa di jalankan cukup mudah. yaitu dengan cara membuka browser dan memasukkan alamat IP. kurang lebih seperti ini https://IP_server, untuk contohnya kurang lebih seperti ini <a href="https://192.168.9.1/" target="_blank" rel="noopener noreferrer">https://192.168.9.1</a>. Dan teman-teman semua akan mendapatkan sebuah tampilan seperti di bawah ini.<br /> <img decoding="async" class="" src="https://i.imgur.com/b88rxcC.png" alt="" />
</p>

<h2 id="Install-MariaDB-Untuk-Database-Server-di-CentOS-8" class="part" data-startline="57" data-endline="57">
  Install MariaDB Untuk Database Server di CentOS 8
</h2>

<p class="part" data-startline="58" data-endline="58">
  Untuk Database kali ini kita akan menggunakan MariaDB sebagai database servernya. Untuk menginstallnya cukup mudah. Teman-teman semua dapat menjalankan command di bawah ini.
</p>

<pre class="part" data-startline="59" data-endline="61"><code>yum install mariadb-server
</code></pre>

<h3 id="Mengaktifkan-dan-Menjalankan-Setiap-Booting" class="part" data-startline="62" data-endline="62">
  Mengaktifkan dan Menjalankan Setiap Booting
</h3>

<p class="part" data-startline="63" data-endline="67">
  Setelah proses instalasi selesai, teman-teman dapat menjalankan perintah dibawah ini untuk mengaktifkan dan menjalankan service nya.<br /> Untuk menjalankan setiap booting silahkan di jalankan command di bawah ini.<br /> <code> systemctl enable mariadb</code><br /> Dan untuk menjalankan service saat mariadb dengan cara menjalankan command<br /> <code> systemctl start mariadb</code>
</p>

<h3 id="Check-versi-MariaDB" class="part" data-startline="69" data-endline="69">
  Check versi MariaDB
</h3>

<p class="part" data-startline="70" data-endline="72">
  Setelah instalasi dan menjalankan service MariaDB dan jika ingin melakukan pengecheckan versi dengan menjalankan command di bawah ini<br /> <code>mysql -V</code><br /> dan akan muncul kurang lebih seperti di bawah ini
</p>

<pre class="part" data-startline="73" data-endline="75"><code>mysql  Ver 15.1 Distrib 10.3.17-MariaDB, for linux (x86_64) using readline 5.1
</code></pre>

<p class="part" data-startline="76" data-endline="76">
  Dan untuk lebih lengkapnya kurang lebih seperti ini
</p>

<pre class="part" data-startline="77" data-endline="80"><code>[root@venus ~]# mysql -V
mysql  Ver 15.1 Distrib 10.3.17-MariaDB, for linux (x86_64) using readline 5.1
</code></pre>

<p class="part" data-startline="82" data-endline="82">
  Seperti yang di ligat di atas bahwa versi dari mariadb nya adalah 10.3.17
</p>

<h3 id="Menjalankan-script-keamanan-database" class="part" data-startline="83" data-endline="83">
  Menjalankan script keamanan database
</h3>

<p class="part" data-startline="84" data-endline="84">
  Dan untuk selanjutnya melakukan script keamanan yang di gunakan untuk setting root password, mematikan remote database menggunakan user root, menghapus database test, menghapus user anonymous dan lainnya. Dan untuk menjalankan bisa dengan menggunakan command berikut ini.
</p>

<pre class="part" data-startline="85" data-endline="87"><code>mysql_secure_installation
</code></pre>

<p class="part" data-startline="88" data-endline="88">
  Setelah itu teman-teman dapat masuk ke MariaDB server dan membuat database, dan user baru.
</p>

<h2 id="Install-PHP-di-CentOS-8" class="part" data-startline="90" data-endline="90">
  Install PHP di CentOS 8
</h2>

<p class="part" data-startline="91" data-endline="91">
  Nah selanjutnya adalah menginstall <code>php</code> dan modul php extention <code>php-mysqlnd</code>. Dan untuk saat ini, secara repository default php yang akan terinstall adalah php versi 7.2. Dan command yang digunakan seperti berikut ini.
</p>

<pre class="part" data-startline="92" data-endline="94"><code>yum install php php-mysqlnd -y
</code></pre>

<pre class="part" data-startline="95" data-endline="121"><code>.....
=========================================================================================
 Package            Arch     Version                                   Repository   Size
=========================================================================================
Installing:
 php                x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   1.5 M
 php-mysqlnd        x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   190 k
Installing dependencies:
 nginx-filesystem   noarch   1:1.14.1-9.module_el8.0.0+184+e34fea82    AppStream    24 k
 php-cli            x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   3.1 M
 php-common         x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   655 k
 php-pdo            x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   122 k
Installing weak dependencies:
 php-fpm            x86_64   7.2.11-2.module_el8.1.0+209+03b9a8ff      AppStream   1.6 M
Enabling module streams:
 nginx                       1.14
 php                         7.2

Transaction Summary
=========================================================================================
Install  7 Packages

Total download size: 7.2 M
Installed size: 29 M
.....
</code></pre>

<h3 id="Install-modul-php-extention" class="part" data-startline="122" data-endline="122">
  Install modul php-extention
</h3>

<p class="part" data-startline="123" data-endline="123">
  Untuk menginstall module php extention juga sangatlah mudah. Dan strukturnya kurang lebih seperti ini.
</p>

<pre class="part" data-startline="124" data-endline="126"><code>yum install php-&lt;namaextention&gt;
</code></pre>

<p class="part" data-startline="127" data-endline="127">
  Semisal ingin menginstall <code>php-info</code>, jadi tinggal memasukkan instalasi php extention seperti berikut ini
</p>

<pre class="part" data-startline="128" data-endline="130"><code>yum install php-info
</code></pre>

<h3 id="Uji-Coba-PHP" class="part" data-startline="132" data-endline="132">
  Uji Coba PHP
</h3>

<p class="part" data-startline="133" data-endline="135">
  Teman-teman semua dapat melakukan percobaan apakah php sudah terinstall dan dapat bekerja atau belum dengan cara menggunakan phpinfo, di phpinfo ini terdapat beberapa informasi, seperti versi php, modul php extention yang aktif dan masih banyak lagi.<br /> Untuk caranya kurang lebih seperti berikut ini :<br /> Masuk ke <code>/var/www/html/</code> dengan cara
</p>

<pre class="part" data-startline="136" data-endline="138"><code>cd /var/www/html/
</code></pre>

<p class="part" data-startline="139" data-endline="139">
  jika sudah masuk kemudian membuat file dengan nama <code>info.php</code> untuk command nya kurang lebih seperti ini
</p>

<pre class="part" data-startline="140" data-endline="142"><code>touch info.php
</code></pre>

<p class="part" data-startline="143" data-endline="143">
  kemudian memasukkan script ke <code>info.php</code> dengan cara
</p>

<pre class="part" data-startline="144" data-endline="146"><code>vim info.php
</code></pre>

<p class="part" data-startline="147" data-endline="147">
  dan masukkan script berikut ini di <code>info.php</code>
</p>

<pre class="part" data-startline="148" data-endline="152"><code class="php hljs">&lt;span class="hljs-meta">&lt;?php&lt;/span>
phpinfo();
&lt;span class="hljs-meta">?&gt;&lt;/span>
</code></pre>

<p class="part" data-startline="153" data-endline="153">
  Dan setelah file itu di simpan, lalukan restart <code>Apache</code>-nya dengan command di bawah ini
</p>

<pre class="part" data-startline="154" data-endline="156"><code>systemctl restart httpd
</code></pre>

<p class="part" data-startline="157" data-endline="159">
  Jika sudah di restart dan sukses tidak ada error. Buka browser dan ketikkan <code>https://IP_server/info.php</code><br /> Dan kurang lebih akan muncul tampilan seperti ini<br /> <img decoding="async" class="" src="https://i.imgur.com/ZDzsIS0.png" alt="" />
</p>