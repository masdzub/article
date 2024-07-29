---
title: Cara Install WPScan di CentOS
author: Dzubayyan Ahmad
type: post
date: 2020-12-10T04:37:40+00:00
url: /cara-install-wpscan-di-centos.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo semua, WPScan adalah salah satu tools yang digunakan untuk melakukan scanning malware ataupun backdoor pada website. WPScan juga salah satu tools yang digunakan untuk mencari kelemahan pada website, WPScan untuk wordpress di dukung langsung oleh <a href="https://sucuri.net/" target="_blank" rel="noreferrer noopener">Sucuri</a>, WPScan dapat di install di linux maupun Mac, Untuk pengguna windows saat ini package belum tersedia. Namun teman-teman dapat menggunakan dengan cara menginstall linux di vmware atau virtualbox. Namun ada kemungkinan jika menggunakan windowws sudah bisa di install di WSL.

Untuk melakukan instalasi WPScan menggunakan command di terminal.

## Instalasi dan Mengkonfigurasi {#Instalasi-dan-Mengkonfigurasi}

Untuk di tutorial kali ini saya hanya akan menjelaskan cara melakukan instasinya di CentOS untuk distro lainnya akan di bahas di artikel lain.

### Install GIT {#Install-GIT}

Git ini adalah salah satu tools untuk melakukan clone dari repository git, bisa github, gitlab, atau yang lainnya. Jika sebelumnya sudah terinstall bisa langsung di lanjutkan tahap selanjutnya. Jika belum install, bisa menjalankan perintah berikut ini :

<pre class="dz-block-code"><code>$ sudo yum install git -y
</code></pre>

### Install Paket yang dibutuhkan {#Install-Paket-yang-dibutuhkan}

Untuk pengguna linux memerlukan beberapa library untuk melakukan build nya, dan berikut ini untuk pengguna CentOS :

<pre class="dz-block-code"><code>$ sudo yum install gcc ruby-devel libxml2 libxml2-devel libxslt libxslt-devel libcurl-devel patch -y
</code></pre>

### Clone WPScan dari Github {#Clone-WPScan-dari-Github}

Nah untuk selanjutnya melakukan cloning wpscan dari repository github, ini nantinya akan membuat folder wpscan sendiri. Untuk melakukan downloadnya dapat menggunakan commdand `git clone` :

<pre class="dz-block-code"><code>$ git clone https://github.com/wpscanteam/wpscan.git
</code></pre>

Jika sudah selesai melakukan cloning lalu masuk ke wpscan

<pre class="dz-block-code"><code>$ cd wpscan
</code></pre>

Setelah itu baru melakukan 1 langkah lagi. Yaitu build nya.

### Install Bundler dan Build {#Install-Bundler-dan-Build}

WPScan adalah tools yang menggunakan ruby untuk bahasa pemrogramannya. Oleh karena itu nantinya akan menggunakan user `gems` sebagai bagian dari bahasa pemrograman ini. Bundler melakukan instalasi dari WPScan dan membuat depency nya selalu update.

Berikut ini untuk melakukan bundler nya.

<pre class="dz-block-code"><code>bundle install --without test
</code></pre>

### Kesimpulan {#Kesimpulan}

Melakukan instalasi WPScan cukup mudah bukan ? Cukup melakukan cloning lalu build saja. Untuk fungsi dari wpscan juga sangat banyak, salah satunya adalah melakukan scanning malware pada wordpress atau bisa juga di jalankan di web lainnya. Untuk tutorial lainnya bisa juga mengakses [disini ya​_][1]

 [1]: https://tulisan.masdzub.com