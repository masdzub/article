---
title: Cara Install Speedtest CLI by Ookla
author: Dzubayyan Ahmad
type: post
date: 2020-12-31T07:37:21+00:00
url: /cara-install-speedtest-cli-by-ookla.aspx
tags:
  - All
  - linux
  - Mac
  - Tutorial

---
Halo teman-teman semua, Sering kali saat menggunakan server ingin melakukan pengecekan kecepatan internet pada server. Nah dikesempatan kali ini, saya akan menjelaskan cara melakukan instalasi speedtest di server. Untuk di artikel kali ini unyuk provider speedtest nya dari [speedtest.net][1] by Ookla.

## Speedtest

Speedtest sendiri bermaksud dan bertujuan untuk melakukan uji kecepatan internet download maupun upload pada sebuah perangkat ataupun server, Untuk tutorial kali ini speedtest yang akan di install dari speedtest by ookla. dan ini bisa di install di semua distro, baik Ubuntu, Centos, Debian, Fedora, dan FreeBSD, Selain itu juga MacOs juga bisa melakukannya

## Install

Untuk langkah-langkah instalasinya bisa mengikuti dengan cara atau arahan berikut ini, teman-teman bisa langsung menyesuaikan untuk lokasi dari masing-masing disto:

### MacOS

Untuk melakukan instalasi Speedtest by Ookla di macos bisa dengan mengikuti cara berikut ini :

<pre class="dz-block-code"><code>$ brew tap teamookla/speedtest
$ brew update
$ brew install speedtest --force</code></pre>

Dan untuk menjalankannya bisa menggunakan cara berikut ini : 

<pre class="dz-block-code"><code>$ speedtest</code></pre>

### Ubuntu / Debian

Untuk melakukan instalasi Speedtest by Ookla di Ubuntu / Debian / turunan distro tersebut bisa dengan cara berikut ini : 

<pre class="dz-block-code"><code>$ sudo apt-get install gnupg1 apt-transport-https dirmngr
$ export INSTALL_KEY=379CE192D401AB61
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys $INSTALL_KEY
$ echo "deb https://ookla.bintray.com/debian generic main" | sudo tee  /etc/apt/sources.list.d/speedtest.list
$ sudo apt-get update
$ sudo apt-get install speedtest</code></pre>

Dan untuk menjalannya bisa menggunakan cara : 

<pre class="dz-block-code"><code>$ speedtest</code></pre>

### Fedora / CentOS / Redhat

Untuk melakukan instalasi Speedtest by Ookla di Fedora / CentOS / Redhat bisa dengan cara berikut ini : 

<pre class="dz-block-code"><code>$ sudo yum install wget
$ wget https://bintray.com/ookla/rhel/rpm -O bintray-ookla-rhel.repo
$ sudo mv bintray-ookla-rhel.repo /etc/yum.repos.d/
$ sudo yum install speedtest</code></pre>

Dan untuk menjalankan BIsa dengan cara berikut ini : 

<pre class="dz-block-code"><code>$ speedtest</code></pre>

### FreeBSD

Untuk melakukan instalasi Speedtest by Ookla di freebsd bisa dengan cara berikut ini :

<pre class="dz-block-code"><code>$ sudo pkg update && sudo pkg install -g libidn2 ca_root_nss
$ sudo pkg add "https://bintray.com/ookla/download/download_file?file_path=ookla-speedtest-1.0.0-freebsd.pkg"</code></pre>

Dan untuk menjalankan BIsa dengan cara berikut ini :

<pre class="dz-block-code"><code>$ speedtest</code></pre></p> 

Jika Saat menjalankan perintah `speedtest` tersebut muncul seperti ini : 

<pre class="dz-block-code"><code>&#91;dzub@sg-22 ~]$ speedtest 
==============================================================================

You may only use this Speedtest software and information generated
from it for personal, non-commercial use, through a command line
interface on a personal computer. Your use of this software is subject
to the End User License Agreement, Terms of Use and Privacy Policy at
these URLs:

	https:&#47;&#47;www.speedtest.net/about/eula
	https://www.speedtest.net/about/terms
	https://www.speedtest.net/about/privacy

==============================================================================

Do you accept the license? &#91;type YES to accept]: yes</code></pre>

maka tuliskan YES lalu enter.kurang lebih seperti gambar berikut ini : <figure class="dz-block-gallery columns-1 is-cropped"> 

<ul class="blocks-gallery-grid">
  <li class="blocks-gallery-item">
    <figure><img decoding="async" src="https://tulisan.masdzub.com/wp-content/uploads/2020/12/565c1628-image.png" alt="" data-id="543" data-full-url="https://tulisan.masdzub.com/wp-content/uploads/2020/12/565c1628-image.png" data-link="https://tulisan.masdzub.com/cara-install-speedtest-cli-by-ookla.aspx/565c1628-image" class="dz-image-543" /></figure>
  </li>
</ul></figure> 

## Kesimpulan

Untuk melakukan pengecekan koneksi internet menggunakan metode CLI tidaklah sulit, Cukup menjalankan beberapa command. Selain itu untuk menggunakan speedtest by Ookla ini akan di upload untuk hasil nya, dan akan di berikan link. jika ingin di lihat melalui browser. Untuk Tutorial lainnya bisa check <a href="https://tulisan.masdzub.com" target="_blank" rel="noreferrer noopener">disini</a>

 [1]: https://speedtest.net