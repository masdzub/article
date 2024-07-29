---
title: Cara Instal dan Konfigurasi MariaDB Server di Centos/RHEL 7.x / Fedora 32
author: Dzubayyan Ahmad
type: post
date: 2020-09-18T07:59:36+00:00
url: /cara-instal-dan-konfigurasi-mariadb-server-di-centos-rhel-7-x-fedora-32.aspx
tags:
  - All
  - linux
  - Tutorial

---
<p class="part" data-startline="5" data-endline="5" data-position="144" data-size="0">
  <span data-position="144" data-size="216">Halo teman semua, nah dikali ini kita akan membahas mengenai tutorial cara menginstall dan mengkonfigurasi MariaDB dan phpMyAdmin di Server Centos dan RHEL, dan untuk di tutorial kali ini kita menggunakan Centos 7.8.</span>
</p>

<p class="part" data-startline="7" data-endline="7" data-position="363" data-size="0">
  <span data-position="364" data-size="343">Nah untuk sebelumnya apasih itu MariaDB, MariaDB adalah relational database management system (DBMS) open source yang merupakan pengganti drop-in yang kompatibel. MariaDB adalah pengganti dari MySQL. Dengan kata lain, MariaDB merupakan pengganti MySQL yang ditingkatkan dan drop-in. Nah untuk info lebih lengkap bisa check di link berikut ini </span><a href="https://mariadb.org/" target="_blank" rel="noopener noreferrer"><span data-position="707" data-size="20">https://mariadb.org/</span></a><span data-position="750" data-size="1">.</span>
</p>

<h2 id="Install-MariaDB" class="part" data-startline="9" data-endline="9" data-id="Install-MariaDB">
  <span data-position="756" data-size="15">Install MariaDB</span>
</h2>

<p class="part" data-startline="10" data-endline="10" data-position="772" data-size="0">
  <span data-position="772" data-size="230">Untuk proses instalasinya cukup mudah. Pastikan sudah remote server seperti biasanya, atau bisa buka console / terminal dari server atau sistem operasi yang ingin di install. Dan pastikan untuk instalasi kali ini menggunakna user </span><code data-position="1003" data-size="4">root</code>
</p>

<p class="part" data-startline="12" data-endline="12" data-position="1010" data-size="0">
  <span data-position="1010" data-size="44">Untuk caranya bisa dengan cara berikut ini :</span>
</p>

<pre class="part" data-startline="13" data-endline="15" data-position="1056"><code># yum install mariadb-server mariadb-client
</code></pre>

<pre class="part" data-startline="16" data-endline="44" data-position="1108"><code>Dependencies Resolved

================================================================================
 Package                     Arch       Version               Repository   Size
================================================================================
Installing:
 mariadb-server              x86_64     1:5.5.47-1.el7_2      updates      11 M
Installing for dependencies:
 libaio                      x86_64     0.3.109-13.el7        base         24 k
 mariadb                     x86_64     1:5.5.47-1.el7_2      updates     8.9 M
 perl-Compress-Raw-Bzip2     x86_64     2.061-3.el7           base         32 k
 perl-Compress-Raw-Zlib      x86_64     1:2.061-4.el7         base         57 k
 perl-DBD-MySQL              x86_64     4.023-5.el7           base        140 k
 perl-DBI                    x86_64     1.627-4.el7           base        802 k
 perl-IO-Compress            noarch     2.061-2.el7           base        260 k
 perl-Net-Daemon             noarch     0.48-5.el7            base         51 k
 perl-PlRPC                  noarch     0.2020-14.el7         base         36 k
Updating for dependencies:
 mariadb-libs                x86_64     1:5.5.47-1.el7_2      updates     755 k

Transaction Summary
================================================================================
Install  1 Package  (+9 Dependent packages)
Upgrade             ( 1 Dependent package)

Total download size: 22 M
Is this ok [y/d/N]:
</code></pre>

<p class="part" data-startline="45" data-endline="47" data-position="2565" data-size="0">
  <span data-position="2565" data-size="75">Nah jika seperti diatas, silahkan dimasukkan konfirmasi dengan mengetikkan </span><code data-position="2641" data-size="1">y</code><span data-position="2643" data-size="12"> lalu enter.</span><br /> <span data-position="2656" data-size="75">Jika sudah, maka akan proses download dan instalasi package secara sendiri.</span><br /> <span data-position="2732" data-size="56">Dan untuk selesainya akan seperti berikut ini tandanya :</span>
</p>

<pre class="part" data-startline="48" data-endline="53" data-position="2790"><code>Dependency Updated:
  mariadb-libs.x86_64 1:5.5.47-1.el7_2                                          

Complete!
</code></pre>

<p class="part" data-startline="55" data-endline="55" data-position="2911" data-size="0">
  <span data-position="2911" data-size="99">Dan untuk selanjutnya menjalankan service dari MaridDB nya dengan menjalankan command berikut ini :</span>
</p>

<pre class="part" data-startline="56" data-endline="58" data-position="3012"><code># systemctl start mariadb
</code></pre>

<p class="part" data-startline="59" data-endline="59" data-position="3046" data-size="0">
  <span data-position="3046" data-size="40">Atau bisa juga dengan cara seperti ini :</span>
</p>

<pre class="part" data-startline="60" data-endline="62" data-position="3088"><code># service mariadb start
</code></pre>

<p class="part" data-startline="64" data-endline="64" data-position="3121" data-size="0">
  <span data-position="3121" data-size="116">Jika dari service nya sudah jalan maka bisa langsung dijalankan. Untuk perintahnya kuranglebih seperti berikut ini :</span>
</p>

<pre class="part" data-startline="65" data-endline="76" data-position="3239"><code># mysql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.14-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]&gt; 
</code></pre>

<p class="part" data-startline="77" data-endline="77" data-position="3564" data-size="0">
  <span data-position="3564" data-size="93">Dan untuk selanjutnya adalah melakukan pengamanan di MariaDB dengan manjalankan berikut ini :</span>
</p>

<pre class="part" data-startline="78" data-endline="142" data-position="3659"><code># mysql_secure_installation 


NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 

OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] y
New password: &lt;Type your root password here&gt;
Re-enter new password: 
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
</code></pre>

<p class="part" data-startline="144" data-endline="144" data-position="5649" data-size="0">
  <span data-position="5649" data-size="153">Dan untuk selanjutnya melakukan ujicoba login menggunakan password yang sudah dibuat dari configure tadi. Untuk caranya kurang lebih seperti berikut ini.</span>
</p>

<pre class="part" data-startline="145" data-endline="157" data-position="5804"><code># mysql -u root -p
Enter password:  &lt; Enter your password here
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 12
Server version: 10.4.14-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]&gt;
</code></pre>

<h2 id="Kesimpulan" class="part" data-startline="159" data-endline="159" data-id="Kesimpulan">
  <span data-position="6188" data-size="10">Kesimpulan</span>
</h2>

<p class="part" data-startline="160" data-endline="160" data-position="6199" data-size="0">
  <span data-position="6199" data-size="205">Untuk install MariaDB Server di Centos/ RHEL / Fedora sangatlah mudah, cukup menjalankan beberapa command, selain itu juga untuk mariadb bisa di hubungkan ke phpmyadmin. Untuk tutorialnya bisa check disini</span>
</p>