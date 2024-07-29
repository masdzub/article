---
title: Install Python 3 atau Python 2.7 di CentOS 8 / RHEL 8
author: Dzubayyan Ahmad
type: post
date: 2020-03-19T18:23:20+00:00
url: /install-python-3-atau-python-2-7-di-centos-8-rhel-8.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo teman-teman semua, nah di tutorial kali ini akan membahasa mengenai cara install python 3 atau python 2.7 di CentOS 8 / RHEL 8 linux. RHEL / CentOS 8 di buat dengan pengembahan yang tinggi dan memprioritaskan kestabilan.

Untuk python sendiri sebenarnya sudah terinstall namun hanya di peruntukkan untuk beberapa system saja. Dan di tutorial kali ini akan membahas untuk install python versi 3 dan python 2.7 di CentOS 8 dan RHEL 8.

## [][1]Install Python 3 di CentOS 8 / RHEL 8 {#Install-Python-3-di-CentOS-8--RHEL-8}

Untuk python 3 dapat di install di CentOS 8 dan RHEL 8 dengan menjalankan perintah berikut ini di terminal / command promt

<pre class="dz-block-code"><code># yum install python3
</code></pre>

Python 3 mempunyai module packet tambahan yang biasa digunakan, dan Secara umum nama module packet tambahan untuk python 3 sendiri menggunakan prefix python3. Dan untuk menginstall module packet tambahan tersebut kurang lebih seperti di bawah ini :

<pre class="dz-block-code"><code># yum install python3-&lt;namamodulepacket>
</code></pre>

Perintah / command di atas berlaku untuk semua module package yang ada untuk python 3.

Dan untuk menggunakan python 3, cukup menjalankan perintah seperti berikut ini :

<pre class="dz-block-code"><code>$ python3

Atau

# python3
</code></pre>

## [][2]Install Python 2.7 di CentOS 8 / RHEL 8 {#Install-Python-27-di-CentOS-8--RHEL-8}

Untuk beberapa orang atau beberapa software belum siap untuk menggunakan atau menjalankan dengan python versi 3, tapi tenang untuk CentOS 8 dan RHEL 8 dapat menggunakan python versi 2.7 dan python 3 secara bersamaan atau secara pararel.

Untuk melakukan instalasi python 2.7 bisa menggunakan perintah / command berikut ini :

<pre class="dz-block-code"><code># yum install python2
</code></pre>

Sama hal nya python 3 untuk module package nya menggunakan prefix python2

Dan untuk menjalankan python versi 2.7 ini dapat menggunakan perintah berikut :

<pre class="dz-block-code"><code>$ python2

atau 

# pyhton2
</code></pre>

## [][3]Set Default Python Version {#Set-Default-Python-Version}

Dalam hal diatas, semua versi di install dari versi 2.7 dengan versi python 3, Dan command untuk menjalankannya&nbsp;`python2`&nbsp;untuk python2 dan python 3 dengan command&nbsp;`python3`. Dan jika sebuah aplikasi menggunakan command python saja akan tidak bisa di jalankan, karena tidak di defenisikan. Kurang lebih seperti berikut ini :

<pre class="dz-block-code"><code>$  python
-bash: python: command not found
</code></pre>

Untuk mengatasi hal tersebut dapat menggunakan sebuah command&nbsp;`alternatives`&nbsp;untuk menjalankan secara global&nbsp;`python`&nbsp;yang tidak mempunyai versi dengan ke versi yang di inginkan.

### [][4]Set Python 3 sebagai Default {#Set-Python-3-sebagai-Default}

Untuk menjalankan command&nbsp;`python`&nbsp;dengan versi default python 3 dapat menjalankan command berikut ini :

<pre class="dz-block-code"><code># alternatives --set python /usr/bin/python3
</code></pre>

Dan untuk melakukan pengechekan bisa menjalankan :

<pre class="dz-block-code"><code># python -V
Python 3.6.8
</code></pre>

Dan untuk perintah menjalankannya kurang lebih seperti ini :

<pre class="dz-block-code"><code># python
Python 3.6.8 (default, Nov 21 2019, 19:31:34)
[GCC 8.3.1 20190507 (Red Hat 8.3.1-4)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
</code></pre>

### [][5]Set Python 2.7 sebagai Default {#Set-Python-27-sebagai-Default}

Untuk menjalankan command&nbsp;`python`&nbsp;dengan versi default python 2.7 dapat menjalankan command berikut ini :

<pre class="dz-block-code"><code># alternatives --set python /usr/bin/python2
</code></pre>

Dan untuk melakukan pengechekan bisa menjalankan :

<pre class="dz-block-code"><code># python -V
Python 2.7.16
</code></pre>

Dan untuk perintah menjalankannya kurang lebih seperti ini :

<pre class="dz-block-code"><code># python
Python 2.7.16 (default, Nov 17 2019, 00:07:27)
[GCC 8.3.1 20190507 (Red Hat 8.3.1-4)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
</code></pre>

## [][6]Kesimpulan {#Kesimpulan}

Menginstall python versi 2.7 dan python versi 3 di CentOS 8 dan RHEL 8 sangatlah mudah. Cukup menjalankan perintah untuk install saja. Selain itu install python juga biasa digunakan untuk development, bagi seorang developer python, sysadmin, atau perserveran pasti tidak asing mendengan python, selain itu python juga bisa di gunakan untuk pembuatan web.

 [1]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Install-Python-3-di-CentOS-8--RHEL-8
 [2]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Install-Python-27-di-CentOS-8--RHEL-8
 [3]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Set-Default-Python-Version
 [4]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Set-Python-3-sebagai-Default
 [5]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Set-Python-27-sebagai-Default
 [6]: https://hackmd.io/jb2Y84dFQzyU0xKZmiN_ow?view#Kesimpulan