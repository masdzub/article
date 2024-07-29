---
title: Cara Mengecheck Versi CentOS dan Fedora
author: Dzubayyan Ahmad
type: post
date: 2020-02-08T09:27:02+00:00
url: /cara-mengecheck-versi-centos-dan-fedora.aspx
tags:
  - All
  - linux
  - Tutorial

---
<h1 id="Cara-Mengecheck-Versi-CentOS-dan-Fedora" class="part" data-startline="1" data-endline="1">
  Cara Mengecheck Versi CentOS dan Fedora
</h1>

<p class="part" data-startline="3" data-endline="4">
  Halo teman-teman semua, terkadang perlu memperhatikan untuk aplikasi yang perlu di install. Hal ini dikarenakan apakah system dari kita sudah sesuai atau belum dengan aplikasi yang akan di install.<br /> Nah berikut ini adalah cara / teknik untuk mengecheck versi CentOS dan Fedora.
</p>

<h2 id="LSB-Release-" class="part" data-startline="6" data-endline="6">
  LSB Release :
</h2>

<p class="part" data-startline="7" data-endline="8">
  <code>lsb_release</code> adalah command untuk mengetahui informasi LSB (linux Standar Base) dan distribusi tertentu dari sistem operasi.<br /> Untuk menggunakan <code>lsb_release</code> diperlukan sebuah package <code>redhat-lsb-core</code>. Yang pertama silahkan di install dulu untuk package nya dengan menjalankan seperti di bawah ini.
</p>

<pre class="part" data-startline="10" data-endline="12"><code># yum install redhat-lsb-core
</code></pre>

<p class="part" data-startline="13" data-endline="14">
  setelah menginstall <code>redhat-lsb-core</code> teman-teman semua baru bisa menjalankan command <code>lsb_release</code><br /> untuk mengetahui kernel yang di gunakan bisa dengan cara berikut ini.
</p>

<pre class="part" data-startline="15" data-endline="17"><code># lsb_release
</code></pre>

<p class="part" data-startline="18" data-endline="18">
  akan muncul seperti ini
</p>

<pre class="part" data-startline="19" data-endline="21"><code>LSB Version:	:core-4.1-amd64:core-4.1-noarch
</code></pre>

<p class="part" data-startline="22" data-endline="22">
  untuk lebih lengkap teman-teman bisa menggunakan <code>lsb_release -a</code> kurang lebih akan seperti ini
</p>

<pre class="part" data-startline="23" data-endline="25"><code># lsb_release -a
</code></pre>

<p class="part" data-startline="26" data-endline="26">
  dan akan muncul seperti ini :
</p>

<pre class="part" data-startline="27" data-endline="33"><code>LSB Version:    :core-4.1-amd64:core-4.1-noarch
Distributor ID: CentOS
Description:    CentOS linux release 8.1.1911 (Core)
Release:        8.1.1911
Codename:       Core
</code></pre>

<p class="part" data-startline="34" data-endline="34">
  untuk penjelasan di atas menggunakan OS CentOS 8.1
</p>

<h2 id="System-Release-" class="part" data-startline="36" data-endline="36">
  System Release :
</h2>

<p class="part" data-startline="37" data-endline="38">
  Untuk cara kedua, teman-teman semua bisa mendapatkan informasi sistem dengan menggunakan mengquery rilis paket.<br /> Untuk menggunakannya bisa menjalankan perintah ini :
</p>

<pre class="part" data-startline="39" data-endline="41"><code># rpm -qa | grep -i centos-release
</code></pre>

<p class="part" data-startline="42" data-endline="42">
  dan akan muncul hasilnya seperti berikut ini :
</p>

<pre class="part" data-startline="43" data-endline="45"><code>centos-release-8.1-1.1911.0.8.el8.x86_64
</code></pre>

<h2 id="Release-File-" class="part" data-startline="47" data-endline="47">
  Release File :
</h2>

<p class="part" data-startline="49" data-endline="49">
  Untuk cara ke-tiga untuk mendapatkan versi dari CentOS dan Fedora dengan cara melihat di <code>/etc/system-release</code> atau di <code>/etc/centos-release</code>
</p>

<p class="part" data-startline="51" data-endline="51">
  Untuk melakukan pengecheckan teman-teman bisa menjalankan seperti ini :
</p>

<pre class="part" data-startline="52" data-endline="54"><code># cat /etc/system-release
</code></pre>

<p class="part" data-startline="55" data-endline="55">
  atau
</p>

<pre class="part" data-startline="56" data-endline="58"><code># cat /etc/centos-release
</code></pre>

<p class="part" data-startline="59" data-endline="59">
  Jika sudah di jalankan akan muncul kurang lebih seperti ini :
</p>

<pre class="part" data-startline="60" data-endline="62"><code>CentOS linux release 8.1.1911 (Core)
</code></pre>

<h3 id="Kesimpulan" class="part" data-startline="64" data-endline="64">
  Kesimpulan
</h3>

<p class="part" data-startline="66" data-endline="66">
  Cukup mudah sekali untuk melakukan pengecheckan OS di CentOS atau di Fedora. Untuk caranya sama saja antara CentOS, Fedora, dan RedHat. Karena mereka masih satu family.
</p>