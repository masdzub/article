---
title: Tes kecepatan mengetik menggunakan linux Terminal
author: Dzubayyan Ahmad
type: post
date: 2021-05-17T04:20:43+00:00
url: /tes-kecepatan-mengetik-menggunakan-linux-terminal.aspx
featured_image: /wp-content/uploads/2021/05/Screenshoot_2021-05-17_11-23.png
tags:
  - All
  - Artikel
  - linux
  - Tutorial

---
Halo teman-teman semua, nah kali ini saya akan memberitahukan ke teman-teman semua cara untuk mengecek keceparan mengetik teman semua melalui terminal di linux.

Sebenarnya banyak sekali tools untuk melakukan kecepatan mengetik. Mulai dari yang berbasis onlie ataupun yang di install langsung di desktop. Nah di kali ini saya akan membahas melakukan hal ini di linux Terminal. Seperti yang bisa di ketahui bahwa di terminal linux dapat melakukan banyak hal, seperti browsing internet, bermain game, install sesuatu, melakukan pekerjaan dan masih banyak hal lainnya. Nah cek kecepatan mengetik bisa juga dilakukannya.

Untuk melakukan cek kecepatan mengetik ini menggunakan package yang namanya&nbsp;`Ttyper`

## [][1]Ttyper : Tools berbasis terminal yang digunakan untuk melakukan kecepatan mengetik {#Ttyper--Tools-berbasis-terminal-yang-digunakan-untuk-melakukan-kecepatan-mengetik.wp-block-heading}

Ttyper sendiri di buat dengan menggunakan&nbsp;`Rust`.  
T pada ttyper bukan menandakan kesalahan ketik, atau yang dikenal sebagai&nbsp;`typo`&nbsp;melainkan dari singkatan dari&nbsp;_TTY(**T**ele**TY**pewritter)_&nbsp;yang mempresentasikan dari terminal emulator

### [][2]Install Ttyper di linux {#Install-Ttyper-di-linux.wp-block-heading}

Untuk melakukan instalasinya perlu membutuhkan package&nbsp;`cargo`, hal ini digunakan karena dari&nbsp;`Ttyper`&nbsp;sendiri menggunakan bahasa pemrograman&nbsp;`rust`&nbsp;sehingga dengan package tersebut akan juga menginstall packet&nbsp;`rustc`&nbsp;agar dapat menjalankan bahasa&nbsp;`rust`.

Untuk keluarga ubuntu/debian/mint menginstallnya bisa menggunakan cara dibawah ini :

<pre class="wp-block-code"><code>$ sudo apt install cargo -y
</code></pre>

Untuk keluarga Fedora/CentOS/Redhat dapat menggunakan cara :

<pre class="wp-block-code"><code>$ sudo yum install cargo -y
</code></pre>

Jika sudah berhasil di install seperti di bawah ini,  
<img decoding="async" src="https://i.imgur.com/UMH8166.png" alt="" class="" /> 

Maka selanjutnya melakukan instalasi Ttyper nya dari cargo.  
Untuk melakukan instalasi lewat cargo, untuk instalasi Ttyper nya dari semua distro sama, caranya seperti berikut ini :

<pre class="wp-block-code"><code>cargo install ttyper
</code></pre>

Jika sudah, maka akan seperti berikut ini, mendownload semua file dan package serta module yang di perlukan. lalu akan compile untuk package&nbsp;`ttyper`&nbsp;nya.  
<img decoding="async" src="https://i.imgur.com/Hne01m3.png" alt="" class="" /> 

Untuk file rust tersebut dapat dijalankan di&nbsp;`.cargo/bin`&nbsp;yang berada di home directory. kurang lebih akan seperti ini tampilannya.  
<img decoding="async" src="https://i.imgur.com/Ak42wdh.png" alt="" class="" /> 

### [][3]Menjalankan Ttyper {#Menjalankan-Ttyper.wp-block-heading}

Setelah melakukan instalasi, langkah selanjutnya adalah menjalankan apps / tools nya tersebut, untuk langkahnya kurang lebih seperti berikut ini :

<pre class="wp-block-code"><code>cd ~/.cargo/bin
</code></pre>

lalu menjalankan file yang dapat di eksekusinya.

<pre class="wp-block-code"><code>./ttyper
</code></pre>

Cara ini memanglah tidak terlalu nyaman bagi yang belum terbiasa dengan perintah di terminal linux. Jika sudah familiar maka akan dengan sangat mudah untuk melakukannya.

Untuk tools ini akan membuat tulisan dan kata secara random dalam bahasa inggris. Untuk tulisan yang benar akan berwarna hijau, dan yang salah akan berwarna merah, dan ini akan berlangsung secara realtime. Selain itu bisa juga melakukan penghapusan seperti layaknya melakukan pengetikan dengan&nbsp;`backspace`, dan jika di hapus maka akan tulisannya benar, namun akan mengurangi score.<figure class="wp-block-image">

<img decoding="async" src="https://i.imgur.com/bS4tGse.png" alt="" /> </figure> 

Ketika sudah selesai melakukan pengetikan pada kata / kalimat yang di munculkan, makan akan mendapatkan hasil, tes kecepatan mengetik dalam kata per menit, akurasi dan benar dalam melakukan pengetikan. Untuk keluar dari program tersebut bisa menekan tombol apapun. Dan jika tekan tombol&nbsp;`r`&nbsp;untuk melakukan pengetesan ulang dengan kata dan tulisan baru.  
<img decoding="async" src="https://i.imgur.com/2ZMq7ZM.png" alt="" class="" /> 

Secara default, akan di buatkan 50 kata untuk ujicoba dari test pengetikan. Jika ingin menambahkan custom bisa menambahkan beberapa option pada command ttyper nya. Beberapa custom tersebut kurang lebih seperti ini :<figure class="wp-block-table">

| **Command**                  | **Contents**                                                          |
| ---------------------------- | --------------------------------------------------------------------- |
| ttyper                       | 50 dari 200 kata dalam bahasa inggris                                 |
| ttper -w 100                 | 100 dari 200 kata dalam bahasa inggris                                |
| ttyper -w 100 -l english1000 | 100 dari 1000 kata dalam bahasa inggris                               |
| ttyper text.txt              | content yang berada di dalam text.txt yang di pisah menggunakan spasi |</figure> 

Tools ini juga bisa di gunakan untuk developer juga, Karena dari tools ini support beberapa bahasa pemprograman, jika dari teman-teman semua adalah seorang programmer, maka bisa di coba untuk melakukan test kecepatan ngoding teman-teman.  
Untuk sampai sekarang, beberapa code sudah support seperti C, C#, Go, HTML, Java, JavaScript, Python, Ruby, dan rust.  
Untuk menggunakan bahasa pemrograman tersebut bisa di coba dengan command seperti berikut :

<pre class="wp-block-code"><code>$ ./ttyper -l html
</code></pre>

Untuk screenshoot akan seperti ini kurang lebih nya  
<img decoding="async" src="https://i.imgur.com/B6IQFhy.png" alt="" class="" /> 

## [][4]Kesimpulan {#Kesimpulan.wp-block-heading}

Cukup mudah bukan untuk melakukan melakukan pengetesan kecepatan pengetikan melalui terminal linux. Jika sudah melakukan instalasi maka sudah tidak diperlukan lagi akses internet tambahan. Selain itu menggunkana terminal juga lebih ringan.

 [1]: https://hackmd.io/QlJSvPLPQWKkIlJF2fuOTA?view#Ttyper--Tools-berbasis-terminal-yang-digunakan-untuk-melakukan-kecepatan-mengetik
 [2]: https://hackmd.io/QlJSvPLPQWKkIlJF2fuOTA?view#Install-Ttyper-di-linux
 [3]: https://hackmd.io/QlJSvPLPQWKkIlJF2fuOTA?view#Menjalankan-Ttyper
 [4]: https://hackmd.io/QlJSvPLPQWKkIlJF2fuOTA?view#Kesimpulan