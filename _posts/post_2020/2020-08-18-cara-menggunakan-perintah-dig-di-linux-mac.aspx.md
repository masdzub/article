---
title: Cara menggunakan perintah dig di linux / Mac
author: Dzubayyan Ahmad
type: post
date: 2020-08-18T02:34:29+00:00
url: /cara-menggunakan-perintah-dig-di-linux-mac.aspx
classic-editor-remember:
  - block-editor
tags:
  - All
  - linux
  - Tutorial

---
Halo semua, nah kali ini kita akan membahas mengenai perintah dig yang ada di linux maupun di mac. Tools ini sangat berguna sekali digunakan untuk melihat DNS yang terecord saat ini. Selain itu juga dapat melihat IP address di dalam sebuah domain.

Dig itu sendiri digunakan biasanya untuk mengquery atau mengetahui dari DNS (Domain Name System). Dig merupakah akronim dari Domain Information Groper, dengan dig teman-teman semua dapat mengetahui infomasi berbagai hal mengenani record DNS, mulai dari alamat host, mail exchanges, name servers, dan informasi lainnya.

## [][1]Install&nbsp;`dig`&nbsp;di linux / Mac {#Install-dig-di-linux--Mac}

### [][2]Install&nbsp;`dig`&nbsp;di Mac {#Install-dig-di-Mac}

Untuk dig di mac os sendiri sudah ada secara default di terminal. Jadi tidak perlu melakukan instalasi.  
Untuk melakukan pengecheckan bisa menjalankan perintah berikut ini di terminal :

<pre class="dz-block-code"><code>$ dig -v
</code></pre>

### [][3]Install&nbsp;`dig`&nbsp;di linux {#Install-dig-di-linux}

Untuk install dig di linux sendiri berbeda di setiap distro. dan berikut ini untuk cara install dig dibeberapa distro :

#### [][4]Fedora / CentOS / Red Hat {#Fedora--CentOS--Red-Hat}

Untuk instal di Fedora / CentOS / Red Hat dapat menjalankan perintah berikut ini :

<pre class="dz-block-code"><code># yum install bind-utils
</code></pre>

Atau

<pre class="dz-block-code"><code># dnf install bind-utils
</code></pre>

#### [][5]Ubuntu / Debian dan keturunannya {#Ubuntu--Debian-dan-keturunannya}

Untuk install di Ubuntu / Debian dan keturunan distronya dapat menjalankan perinta berikut ini :

<pre class="dz-block-code"><code># apt install dnsutils
</code></pre>

#### [][6]Arch / Manjaro {#Arch--Manjaro}

Untuk instalasi dig di Arch linux dan Manjaro dapat menjalankan perintah berikut ini :

<pre class="dz-block-code"><code># pacman -Sy bind-tools
</code></pre>

## [][7]Cara menggunakan comamnd dig {#Cara-menggunakan-comamnd-dig}

Nah kali ini masuk ke cara menggunakan dig nya. kita akan mencari IP address yang berkaitan dengan nama domain, dalam hal ini juga termasuk mutiple IP pada domain tersebut.

Untuk yang pertama dan mendapatkan informasi secara keseluruhan bisa menggunakan command&nbsp;`dig namadomain`&nbsp;untuk contoh bisa menggunakan

<pre class="dz-block-code"><code>dig tulisan.masdzub.com
</code></pre>

akan muncul dengan tulisan seperti berikut ini

<pre class="dz-block-code"><code>; &lt;&lt;>> DiG 9.10.6 &lt;&lt;>> tulisan.masdzub.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER&lt;&lt;- opcode: QUERY, status: NOERROR, id: 60010
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;tulisan.masdzub.com.		IN	A

;; ANSWER SECTION:
tulisan.masdzub.com.	300	IN	A	104.28.11.21
tulisan.masdzub.com.	300	IN	A	104.28.10.21

;; Query time: 344 msec
;; SERVER: 1.1.1.1#53(1.1.1.1)
;; WHEN: Sat Apr 18 22:50:09 WIB 2020
;; MSG SIZE  rcvd: 80
</code></pre>

Untuk penjelasaan di atas kurang lebih seperti berikut ini

### [][8]Header {#Header}

Untuk header sendiri bisa di lihat di paling atas :

<pre class="dz-block-code"><code>; &lt;&lt;>> DiG 9.10.6 &lt;&lt;>> tulisan.masdzub.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER&lt;&lt;- opcode: QUERY, status: NOERROR, id: 49384
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1
</code></pre>

Nah untuk isi dari header diatas kurang lebih seperti ini

<li class="">
  <strong>Baris pertama</strong>&nbsp;: Versi dig dan domain yang sedang di cari
</li>
<li class="">
  <strong>Global options</strong>&nbsp;: kita bisa lihat bahwa teman-teman menjalankan dig dengan multi domain secara bersamaan dalam 1 query, untuk paling simple dan secara default menggunaakn tambahan command&nbsp;<strong>+cmd</strong>.
</li>
<li class="">
  <strong>Opcode : Query</strong>&nbsp;: Ini adalah sebuah tipe untuk menjalankan sebuah permintaan, dalam hal ini sebuah query, untuk isi nya bsia menjadi&nbsp;<code>iquery</code>&nbsp;untuk menjalankan query secara terbalik (inverse), atau sebuah&nbsp;<code>status</code>&nbsp;jika teman-teman semua menggunakan kondisi terting di DNS System.
</li>
<li class="">
  <strong>Status : Noerror</strong>&nbsp;: ini menandakan bahwa tidak ada error dan jaringan sudah resolve dengan baik.
</li>
<li class="">
  <strong>id : 49384</strong>&nbsp;: sebuah angka acak / random yang di buat dari sebuah permintaan dan untuk respon secara bersamaan
</li>
<li class="">
  <strong>flags: qr rd ra</strong>&nbsp;: Untuk artinya query, recursion desire, dan recursion available. Recursion adalah sebuah form yang di dapatkan dari DNS Lookup.
</li>

### [][9]Opt Pseudosection {#Opt-Pseudosection}

Nah yang selanjutnya adalah Opt Psudosection  
Untuk hal ini di bagian

<pre class="dz-block-code"><code>;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
</code></pre>

Untuk di bagian ini penjelassnya sebagai berikut :

<li class="">
  <strong>EDNS: version: 0</strong>&nbsp;: Adalah sebuah versi dari&nbsp;<a href="https://en.wikipedia.org/wiki/Extension_mechanisms_for_DNS" target="_blank" rel="noreferrer noopener">system tambahan untuk DNS</a>&nbsp;yang digunakan. EDNS mengirimkan data tambahan dan memperpanjang sebuah ukuran dari paket UDP (<a href="https://en.wikipedia.org/wiki/User_Datagram_Protocol" target="_blank" rel="noreferrer noopener">User Datagram Protocol</a>)
</li>
<li class="">
  <strong>udp : 4096</strong>&nbsp;: Jumlah packet UDP yang digunakan.
</li>

### [][10]Question Section {#Question-Section}

Nah yang selanjutnya adalah bagian pertanyaan, untuk secara default nya adalah A record yang di tanyakan.

<pre class="dz-block-code"><code>;; QUESTION SECTION:
;tulisan.masdzub.com.		IN	A
</code></pre>

Dalam hal ini yang penjelasannya sebagai berikut ini

<li class="">
  <strong><a href="https://tulisan.masdzub.com/" target="_blank" rel="noreferrer noopener">tulisan.masdzub.com</a></strong>&nbsp;: Domain yang dimasukkan kedalam query
</li>
<li class="">
  <strong>A</strong>&nbsp;: Record yang di tanyakan, ini bisa juga berganti NS, MX atau record lainnya.
</li>

### [][11]Answer Section {#Answer-Section}

Nah yang selanjutnya adalah bagian jawaban atau answer. untuk mengikuti dari perintah yang ada di atas itu yang di tanyakan adalah A record, jadi untuk jawabannya kurang lebih seperti berikut ini :

<pre class="dz-block-code"><code>tulisan.masdzub.com.	300	IN	A	104.28.11.21
tulisan.masdzub.com.	300	IN	A	104.28.10.21
</code></pre>

Dalam hal ini untuk penjelasannya sebagai berikut ini :

<li class="">
  <strong>300</strong>&nbsp;: TTL atau Time To Live adalah suatu nilai pada paket data (header IP) yang menyatakan berapa lama paket tersebut bisa beredar/berjalan -jalan dalam jaringan (cache).
</li>
<li class="">
  <strong>A</strong>&nbsp;: Jawaban dari pertanyaan untuk query yang di dapatkan.
</li>

### [][12]Statistics Section {#Statistics-Section}

Untuk bagian statistik ini adalah bagian paling akhir.  
Dan untuk bagian ini berisi seperti berikut ini :

<pre class="dz-block-code"><code>;; Query time: 125 msec
;; SERVER: 1.1.1.1#53(1.1.1.1)
;; WHEN: Wed Apr 22 21:23:15 WIB 2020
;; MSG SIZE  rcvd: 80
</code></pre>

Dan untuk penjelasannya bisa sebagai berikut ini :

<li class="">
  <strong>Query time:</strong>&nbsp;: waktu yang diperlukan untuk mendapatkan sebuah respon
</li>
<li class="">
  <strong>SERVER: 1.1.1.1#53(1.1.1.1)</strong>&nbsp;: IP address dan port pada DNS server utnuk merespon, dalam hal ini digunakan untuk caching resolver. Untuk penjelasan diatas menggunakan DNS resolver milik cloudflare. Selain milik cloudflare bisa juga menggunakan DNS resolver lainnya seperti milik google yaitu di IP 8.8.8.8
</li>
<li class="">
  <strong>WHEN: Wed Apr 22 21:23:15 WIB 2020</strong>&nbsp;: waktu yang di tunjukkan ketika saat sedang meminta request
</li>
<li class="">
  <strong>MSG SIZE rcvd:</strong>&nbsp;: Ukuran pesan yang diterima dari DNS Server.
</li>

## [][13]Penggunaan Dig secara spesifik {#Penggunaan-Dig-secara-spesifik}

Teman-teman semua bisa menggunakan perintah dig yang lebih spesifik denga cara menambahkan query tambahan yang agar menampilkan informasi yang lebih spesifik.  
Berikut adalah query yang biasa di gunakan untuk menghilangkan section.

<li class="">
  <strong>+nocomments</strong>&nbsp;: Untuk menyembunyikan bagian comment
</li>
<li class="">
  <strong>+noauthority</strong>&nbsp;: untuk menyembunyikan bagian authority
</li>
<li class="">
  <strong>+noaddtional</strong>&nbsp;: untuk menyembunyikan bagian addtional
</li>
<li class="">
  <strong>+nostats</strong>&nbsp;: untuk menyembunyikan bagian stats
</li>
<li class="">
  <strong>+noanswer</strong>&nbsp;: untuk menyembunyikan bagian answer
</li>
<li class="">
  <strong>+noall</strong>&nbsp;: agar semua bagian tidak diperlihatkan
</li>

Untuk query&nbsp;`+noall`&nbsp;biasanya dikombinasikan dengan salah satu bagian, agar memunculkan bagian yang lebih spesifik pada hasil. Jadi dari yang awalnya terdapat query yang panjang dan dengan beberapa tambahan query tersebut bisa hanya menjadi beberapa baris yang dibutuhkan saja. Dan untuk menonaktifkan semuanya bisa menggunakan&nbsp;`+noall`  
Dan untuk penambahan kembali section dapat menggunakan query dibawah ini :

<li class="">
  <strong>+comments</strong>&nbsp;: Memperlihatkan kembali bagian comments
</li>
<li class="">
  <strong>+authority</strong>&nbsp;: Memperlihatkan bagian authority
</li>
<li class="">
  <strong>+additional</strong>&nbsp;: Memperlihatkan bagian additional
</li>
<li class="">
  <strong>+starts</strong>&nbsp;: Untuk memperlihatkan bagian stats
</li>
<li class="">
  <strong>+answer</strong>&nbsp;: Untuk memper;ihatkan bagian answer
</li>
<li class="">
  <strong>+all</strong>&nbsp;: Untuk memperlihatkan semua bagian
</li>

Dan berikut ini adalah contoh untuk membuat sebuah request tanpa mengikutkan atau menyembunyikan suatu bagian :

<pre class="dz-block-code"><code># dig tulisan.masdzub.com +nocomments
</code></pre>

Dan hasilnya akan seperti ini

<pre class="dz-block-code"><code>
; &lt;&lt;>> DiG 9.11.21-RedHat-9.11.21-1.fc32 &lt;&lt;>> tulisan.masdzub.com +nocomments
;; global options: +cmd
;tulisan.masdzub.com.		IN	A
tulisan.masdzub.com.	300	IN	A	104.28.10.21
tulisan.masdzub.com.	300	IN	A	104.28.11.21
tulisan.masdzub.com.	300	IN	A	172.67.129.84
;; Query time: 269 msec
;; SERVER: 180.250.13.42#53(180.250.13.42)
;; WHEN: Tue Aug 18 07:56:31 WIB 2020
;; MSG SIZE  rcvd: 96
</code></pre>

Dan jika kita menggunakan query&nbsp;`+noall`&nbsp;maka tidak akan muncul apapun.  
Dan untuk hal seperti ini biasanya ditambahi sebuah query tambahan seperti&nbsp;`+answer`dan hasilnya akan seperti berikut ini :

<pre class="dz-block-code"><code># dig tulisan.masdzub.com +noall +answer
</code></pre>

Dan akan menghasilkan kurang lebih seperti ini :

<pre class="dz-block-code"><code>tulisan.masdzub.com.	300	IN	A	172.67.129.84
tulisan.masdzub.com.	300	IN	A	104.28.10.21
tulisan.masdzub.com.	300	IN	A	104.28.11.21
</code></pre>

Untuk kombinasi yang saya sendiri pakai adalah dengan&nbsp;`+noall`&nbsp;`+answer`. Dan teman-teman dapat menambahkan query tambahan yang di perlukan. Selain itu jika dari teman-teman ingin menjadikan query tersebut menjadi default dari command&nbsp;`dig`&nbsp;bisa menyimpan file&nbsp;`.digrc`&nbsp;di home directory atau lokasi home dari user yang digunakan.

Untuk membuat dan menyimpan file tersebut di homedir dengan cara berikut ini :

<pre class="dz-block-code"><code>echo "+noall +answer" > $HOME/.digrc
</code></pre>

Dan setelah itu bisa dicheck di homedir anda dengan cara menjalankan command seperti berikut ini :

<pre class="dz-block-code"><code>cat .digrc
</code></pre>

Dan akan menghasilakan seperti berikut :

<pre class="dz-block-code"><code>+noall +answer
</code></pre>

Setelah menjalankan command tersebut bisa dicoba untuk menjalankan dig dan untuk melookup domain lainnya.  
Dan Untuk percobaan bisa di check seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ dig masdzub.com
masdzub.com.		300	IN	A	104.28.10.21
masdzub.com.		300	IN	A	172.67.129.84
masdzub.com.		300	IN	A	104.28.11.21
❰masdzub❙~❱&#x2714;≻ dig tulisan.masdzub.com
tulisan.masdzub.com.	300	IN	A	172.67.129.84
tulisan.masdzub.com.	300	IN	A	104.28.11.21
tulisan.masdzub.com.	300	IN	A	104.28.10.21
❰masdzub❙~❱&#x2714;≻ dig google.com
google.com.		3594	IN	A	216.239.38.120
</code></pre>

## [][14]DNS Records {#DNS-Records}

Informasi yang dari dig memuat beberapa informasi dari DNS record yang terhubung ke DNS SErver. Untuk secara default yang di ajukan adalah&nbsp;`A record`&nbsp;pada domain. Namun dalam hal lain juga bisa digunakan untuk type record lainya. Untuk type record nya bisa di check dibawah ini :

<li class="">
  <strong>A Record</strong>&nbsp;: untuk melihat IPv4 record
</li>
<li class="">
  <strong>AAAA Record</strong>&nbsp;: untuk melihat IPv6 record
</li>
<li class="">
  <strong>MX Record</strong>&nbsp;: Mail Exchange record yang digunakan untuk mengirim dan menerima email dengan benar.
</li>
<li class="">
  <strong>NS Record</strong>&nbsp;: NameServer record yang menentukan record domain dan sub domain lainnya di DNS Server
</li>
<li class="">
  <strong>TXT Record</strong>&nbsp;: Txt record sebuah informasi berbasis teks pada sebuah domain.
</li>
<li class="">
  <strong>SOA record</strong>&nbsp;: catatan otoritas awal (Start of Authority) mengacu server DNS yang mengediakan otorisasi informasi tentang sebuah domain Internet.
</li>
<li class="">
  <strong>TTL</strong>&nbsp;: Time to live yang di setting pada sebuah dns record dan berapa lama DNS server di-ijinkan pada DNS cache.
</li>

Untuk secara spesifik ingin merubah A record menjadi yang lain secara default itu tidak bisa.

Jika ingin melihat sebuah A record (IPv4) pada domain bisa menggunakan cara seperti dibawah ini :

<pre class="dz-block-code"><code>dig a masdzub.com

masdzub.com.		300	IN	A	104.28.10.21
masdzub.com.		300	IN	A	104.28.11.21
masdzub.com.		300	IN	A	172.67.129.84

</code></pre>

Dan jika ingin melihat sebuah MX record pada domain bisa menggunakan cara seperti di bawah ini :

<pre class="dz-block-code"><code>dig mx masdzub.com

masdzub.com.		300	IN	MX	0 lumineon.sg.rapidplex.com.
</code></pre>

Dan jika ingin melihat sebuah NS pada sebuah domain bisa menggunakan cara seperti ini :

<pre class="dz-block-code"><code>dig ns masdzub.com

masdzub.com.		86400	IN	NS	dolly.ns.cloudflare.com.
masdzub.com.		86400	IN	NS	eric.ns.cloudflare.com.

</code></pre>

Dan jika ingin mengecheck TXT record pada domain bisa menggunakan cara seperti berikut :

<pre class="dz-block-code"><code>dig txt masdzub.com

masdzub.com.		300	IN	TXT	"google-site-verification=Lxdi4M4itKs0oWthB0JNtj7IYoahYBLvRzFb6tDvcmY"
masdzub.com.		300	IN	TXT	"v=spf1 +a +mx +ip4:139.162.57.218 ~all"
</code></pre>

## [][15]Kesimpulan {#Kesimpulan}

Untuk menggunakan command dig itu sangat mudah, dan sangatlah lebih cepat dari pada menggunakan web. Dan itu adalah sebuah kelebihan ketika menggunakan&nbsp;`dig`&nbsp;ini. Dan untuk cara menggunakan dig sebenaarnya masih banyak, namun saat ini yang sering biasa di lakukan sehingga ini lebih mudah di pahami. Dan sekian dulu, sampai bertemu diartikel selanjutnya

 [1]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Install-dig-di-linux--Mac
 [2]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Install-dig-di-Mac
 [3]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Install-dig-di-linux
 [4]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Fedora--CentOS--Red-Hat
 [5]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Ubuntu--Debian-dan-keturunannya
 [6]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Arch--Manjaro
 [7]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Cara-menggunakan-comamnd-dig
 [8]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Header
 [9]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Opt-Pseudosection
 [10]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Question-Section
 [11]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Answer-Section
 [12]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Statistics-Section
 [13]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Penggunaan-Dig-secara-spesifik
 [14]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#DNS-Records
 [15]: https://hackmd.io/O3Va4lrwTxe8QhuWXTOuEA?view#Kesimpulan