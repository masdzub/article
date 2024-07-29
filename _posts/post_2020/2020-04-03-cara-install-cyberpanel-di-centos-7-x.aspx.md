---
title: Cara Install CyberPanel di CentOS 7.x
author: Dzubayyan Ahmad
type: post
date: 2020-04-03T16:03:46+00:00
url: /cara-install-cyberpanel-di-centos-7-x.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo teman-teman semua, nah di kali ini kita akan membahas mengenai CyberPanel. nah cyberpanel adalah web panel yang bersifat open source yang menggunakan OpenLitespeed atau litepeed. Fungsi cyberpanel sendiri digunakan untuk memudahkan pengelolaan website yang ada di server.

CyberPanel sendiri dikeluarkan dengan 2 versi, untuk yang pertama adalah CyberPanel dan versi yang satunya adalah CyberPanel Ent. Perbedaan dari kedua versi tersebut berada di web servernya. Untuk CyberPanel menggunakan webserver OpenLiteSpeed yang dapat didapatkan secara gratis untuk unlimited domain dengan banyak proses.

Berbeda dengan CyberPanel Ent, untuk CyberPanel Ent menggunakan webserver LiteSpeed Web Server Enterprise, dan gratis hanya untuk 1 domain saja, jika ingin lebih bisa di lihat di sini&nbsp;<a href="https://cyberpanel.net/cyberpanel-enterprise/" target="_blank" rel="noreferrer noopener">halaman harga web nya</a>.

## [][1]Spesifikasi Minimal Yang dibutuhkan {#Spesifikasi-Minimal-Yang-dibutuhkan}

Sebelum install CyberPanel pastikan server / vps sudah mempunyai spesifikasi minimal untuk di insrall CyberPanel.

<li class="">
  Centos 7.x (Rekomendasi minimal, disini saya pakai CentOS 7.6)
</li>
<li class="">
  Python 2.7
</li>
<li class="">
  RAM 1GB bisa lebih
</li>
<li class="">
  Disk yang tersisa minimal 10GB
</li>
<li class="">
  Dapat menggunakan akses user root
</li>

## [][2]Cara Install CyberPanel di CentOS 7.x {#Cara-Install-CyberPanel-di-CentOS-7x}

<li class="">
  Download dan Install CyberPanel<br />Hal yang pertama dilakukan adalah melakukan download script dan melakukan instalasi. Sebelum itu pastikan juga sudah menggunakan user&nbsp;<code>root</code>, dan menjalankan perintah di bawah ini
</li>

<pre class="dz-block-code"><code># sh &lt;(curl https://cyberpanel.net/install.sh || wget -O - https://cyberpanel.net/install.sh)
</code></pre>

Setelah menjalankan perintah seperti diatas akan ada tampilan seperti berikut ini :

<pre class="dz-block-code"><code>&#91;root@venus ~]# sh &lt;(curl https://cyberpanel.net/install.sh || wget -O - https://cyberpanel.net/install.sh)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1189  100  1189    0     0   1611      0 --:--:-- --:--:-- --:--:--  1611

Detecting Centos 7x...


Initializing...

Valid IP detected...

Checking server...

Checking OS...

Detecting CentOS 7.X...

Checking virtualization type...

Checking root privileges...


You are runing as root...

		CyberPanel Installer v2.00

  1. Install CyberPanel.

  2. Addons and Miscellaneous

  3. Exit.


  Please enter the number&#91;1-3]:
</code></pre>

<ol start="2">
  <li class="">
    Pilih untuk Instalasi CyberPanel<br />Nah, untuk selanjutnya memilih instalasi CyberPanel. Untuk tampilan sebelumnya kurang lebih seperti ini :
  </li>
</ol>

<pre class="dz-block-code"><code>
		CyberPanel Installer v2.00

  1. Install CyberPanel.

  2. Addons and Miscellaneous

  3. Exit.
  
  Please enter the number&#91;1-3]:

</code></pre>

Untuk pilihan di atas, pilih yang nomor 1

<ol start="3">
  <li class="">
    Pilih Versi CyberPanel yang di inginkan<br />Selanjutnya adalam pemilihan versi CyberPanel, Disini ada pilihan seperti berikut ini :
  </li>
</ol>

<pre class="dz-block-code"><code>		CyberPanel Installer v2.00

  RAM check : 174/821MB (21.19%)

  Disk check : 1/25GB (6%) (Minimal 10GB free space)

  1. Install CyberPanel with OpenLiteSpeed.

  2. Install Cyberpanel with LiteSpeed Enterprise.

  3. Exit.


  Please enter the number&#91;1-3]
</code></pre>

Jika memasukkan nomor 1, maka akan menginstall Cyberpanel dengan OpenLiteSpeed, namun jika memilih nomor 2 akan menginstall CyberPanel Ent. Karena suka yang gratis dengan full feature maka menggunakan yang OpenLiteSpeed, jadi pilih nomor 1.

<ol start="4">
  <li class="">
    Pilihan instalasi<br />Untuk selanjutnya adalah pilih instalasi, apakah ingin menginstall full feature atau menginstall hanya sebagian saja, jika full maka akan menginstall juga service seperti PowerDNS, Postfix and Pure-FTPd. Jika iya maka kita pilih&nbsp;<code>Y</code>&nbsp;pada tampilan seperti ini :
  </li>
</ol>

<pre class="dz-block-code"><code>Install Full service for CyberPanel? This will include PowerDNS, Postfix and Pure-FTPd.

Full installation &#91;Y/n]: Y
</code></pre>

<ol start="5">
  <li class="">
    Memilih versi yang lebih spesific<br />Bagi sebagian orang terkadang ingin menggunakan versi yang sebelumnya atau dibawahnya. Teman-teman semua bisa memilih versi yang sebelumnyajuga pada pilihan seperti ini.
  </li>
</ol>

<pre class="dz-block-code"><code>Press Enter key to continue with latest version or Enter specific version such as: 1.9.4 , 1.9.5 ...etc
</code></pre>

Jika ingin menggunakan yang versi terakhir bisa langsung klik&nbsp;`enter`&nbsp;saja

<ol start="6">
  <li class="">
    Membuat password untuk admin<br />Selanjutnya adalah membuat password untuk admin, nah disini akan ada pilihan seperti ini :
  </li>
</ol>

<pre class="dz-block-code"><code>lease choose to use default admin password 1234567, randomly generate one (recommended) or specify the admin password?
Choose &#91;d]fault, &#91;r]andom or &#91;s]et password: &#91;d/r/s]
</code></pre>

Didalam sini ada 3 pilihan, jika memilih&nbsp;`d`&nbsp;akan di beri password admin 1234567, jika memilih&nbsp;`r`&nbsp;akan di buatkan password secara random oleh CyberPanel, dan jika memilih&nbsp;`s`&nbsp;maka nantinya silahkan di buat sendiri passwordnya. Disini saya sendiri pilih yang&nbsp;`s`&nbsp;karena membuat password sendiri, dan pastikan password yang di buat kuat ya.  
Jika sudah di masukkan pilih&nbsp;`s`, maka akan tampilannya berikut ini :

<pre class="dz-block-code"><code>Choose &#91;d]fault, &#91;r]andom or &#91;s]et password: &#91;d/r/s] s

Please enter your password:
</code></pre>

Teman-teman semua bisa langsung mengetikkan password yang di inginkan.  
7. Instalasi Memcached  
Pada proses ini akan diberi pilihan lagi apakah ingin menginstall memcached atau tidak. Masukkan pilih&nbsp;`y`&nbsp;untuk menginstall dan&nbsp;`n`&nbsp;untuk tidak menginstall. Jika sudah tekan tombol&nbsp;`enter`&nbsp;untuk lanjut proses instalasi.

<ol start="8">
  <li class="">
    Instalasi Redis<br />Pada proses ini sama seperti nomor 7, akan diberi pilihan lagi apakah ingin menginstall redis atau tidak. Masukkan pilih&nbsp;<code>y</code>&nbsp;untuk menginstall dan&nbsp;<code>n</code>&nbsp;untuk tidak menginstall. Jika sudah tekan tombol&nbsp;<code>enter</code>&nbsp;untuk lanjut proses instalasi.
  </li>
  <li class="">
    Set up watchdog<br />Pada pilihan kali ini akan ada pemilihan apakah ingin di install watchdog untuk web server dan database server.
  </li>
</ol>

<pre class="dz-block-code"><code>Would you like to set up a WatchDog (beta) for Web service and Database service ?
The watchdog script will be automatically started up after installation and server reboot
If you want to kill the watchdog , run watchdog kill
Please type Yes or no (with capital Y, default Yes):
</code></pre>

Masukkan pilih&nbsp;`Yes`&nbsp;untuk menginstall dan&nbsp;`no`&nbsp;untuk tidak menginstall. Jika sudah tekan tombol&nbsp;`enter`&nbsp;untuk lanjut proses instalasi. Jika tidak memasukkan pilihan akan langsung memilih yang Yes, dan menginstallnya.

<ol start="10">
  <li class="">
    Proses Instalasi CyberPanel<br />Dalam proses ini akan mengupdate system, dan menginstall berbagai service yang dibutuhkan agar CyberPanel jalan dengan baik. Dan dalam proses ini juga cukup memakan waktu yang cukup lama. Jadi bisa sambil minum kopi atau istirahat. Untuk proses akan memakan waktu 10-15 menit, tergantung koneksi internet anda.<br />Dan jika sudah selesai akan muncuk tampilan seperti berikut ini :
  </li>
</ol>

<pre class="dz-block-code"><code>###################################################################
                CyberPanel Successfully Installed

                Current Disk usage : 5/25GB (24%)

                Current RAM  usage : 275/821MB (33.50%)

                Installation time  : 0 hrs 11 min 57 sec

                Visit: https://178.128.18.212:8090
                Panel username: admin
                Panel password: Sukses2020Terus!
                WebAdmin console username: admin
                WebAdmin console password: lPBzf45jbpMfXPDV

             Run cyberpanel help to get FAQ info
             Run cyberpanel upgrade to upgrade it to latest version.
             Run cyberpanel utility to access some handy tools .

              Website : https://www.cyberpanel.net
              Forums  : https://forums.cyberpanel.net
              Wikipage: https://docs.cyberpanel.net

            Enjoy your accelerated Internet by
                CyberPanel & OpenLiteSpeed
###################################################################
Digital Ocean detected...
This provider has a network-level firewall
Please make sure you have opened following port for both in/out:
TCP: 8090 for CyberPanel
TCP: 80, TCP: 443 and UDP: 443 for webserver
TCP: 21 and TCP: 40110-40210 for FTP
TCP: 25, TCP: 587, TCP: 465, TCP: 110, TCP: 143 and TCP: 993 for mail service
TCP: 53 and UDP: 53 for DNS service
Would you like to restart your server now? &#91;y/N]: y
</code></pre>

Masukkan pilih&nbsp;`y`&nbsp;kemudian tekan enter.

<ol start="11">
  <li class="">
    Akses ke CyberPanel<br />Setelah selesai instalasi teman-teman semua bisa akses CyberPanel menggunakan detail berikut ini :
  </li>
</ol>

<pre class="dz-block-code"><code>Visit: https://IP_Server:8090
Panel username: admin
Panel password: Password Yang dibuat tadi
</code></pre>

Untuk tampilan kuranglebih seperti ini :  
<img decoding="async" src="https://i.imgur.com/6xfWfku.png" alt="" class="" /> 

<ol start="12">
  <li class="">
    Manage Web dengan CyberPanel<br />Setelah selesai instlasi dan dapat mengakses CyberPanel bisa selanjutnya adalah mengelola web dengan cyberpanel. Dan untuk tampilan dashboard atau tampilan awalnya ada seperti berikut ini :<br /><img decoding="async" src="https://i.imgur.com/mnZSCRR.png" alt="" class="" />
  </li>
</ol>

## [][3]Kesimpulan {#Kesimpulan}

Cukup mudah bukan untuk melakukan instalasi CyberPanel di CentOS 7.x, selain itu CyberPanel juga free dan dapat digunakan kapan saja. Dan jika sudah mempunyai license juga bisa menggunakan untuk versi yang CyberPanel Ent.

 [1]: https://hackmd.io/G62hE-VJSIqq8wlW_KSwhQ?view#Spesifikasi-Minimal-Yang-dibutuhkan
 [2]: https://hackmd.io/G62hE-VJSIqq8wlW_KSwhQ?view#Cara-Install-CyberPanel-di-CentOS-7x
 [3]: https://hackmd.io/G62hE-VJSIqq8wlW_KSwhQ?view#Kesimpulan