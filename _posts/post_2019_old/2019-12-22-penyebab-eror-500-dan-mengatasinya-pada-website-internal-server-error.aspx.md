---
title: Penyebab eror 500 dan Mengatasinya pada website (Internal Server Error)
author: Dzubayyan Ahmad
type: post
date: 2019-12-22T15:39:38+00:00
url: /penyebab-eror-500-dan-mengatasinya-pada-website-internal-server-error.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo semua, nah kali ini akan mengulas mengenai sebuah permasalah pada website. Terkadang di local jalan namun ketika di upload ke hosting / server malah terjadi error 500.

Dari error 500 atau internal server error biasanya terkait dengan server. Jadi untuk solusinya anda akan sedikit berhubungan dengan server. Namun tenang, jika anda menggunakan layanan hosting lebih mudah untuk mengatasinya. Karena biasanya di layanan hosting akan memunculkan error_log yang akan mempermudah investigasi dalam mengatasi error 500 atau internal server ini.

Error 500 sendiri banyak penyebabnya. Nah untuk itu mari kita ketahui semua penyebabnya dan bagaimana cara mengatasinya. Sebelum itu mari kita ketahui dulu untuk pesan error 500 ini di berbagai browser.

  * 500 Internal Server Error
  * HTTP 500 &#8211; Internal Server Error
  * 500 Error
  * Internal Server Error
  * Temporary Error (500)
  * HTTP Error 500
  * That&#8217;s an Error
  * The website cannot display the page &#8211; HTTP 500
  * Just blank white screen / hanya layar blank putih

Dan berikut ini adalah cara mengatasi / solusi jika terjadi Error 500 atau internal server error :

  1. **Refresh Website / Halaman website**  
    Untuk cara ini memang terkadang disepelekan, namun terkadang cukup membantu, yaitu dengan cara mereload / refresh halaman yang sedang error. Silahkan di coba beberapa kali dan di beri jeda 10 detik.
  2. **Hapus Cache Browser**  
    Terkadang cache pada broser yang sudah lama akan tertimbun dan tidak dihapus. Ada beberapa yang auto remove setelah expired, namun ada juga yang harus di hapus secara manual. Untuk pengguna chrome anda bisa gunakan cara seperti ini : Masuk ke tiga titik kanan atas > Settings (Pengaturan) > Scroll kebawah > Advanced (lanjutan) > Privacy and Security > Clear browsing data > centang semua > Dan Clear Data.  
<img loading="lazy" decoding="async" class="dz-image-21 aligncenter" src="https://tulisan.masdzub.com/wp-content/uploads/2019/12/image.png" alt="" alt="" alt="" width="331" height="296" /> 
  3. **Check Error_log  
** Untuk terkait hal ini biasanya hosting atau di server akan memunculkan error\_log ketika terjadi sesuatu. Untuk check error\_log anda bisa masuk ke cpanel > file manager > directory root web > error_log.   
    Untuk error_log anda bisa check di bagian akhir / di baris akhir. biasanya menunjukkan sebuah petunjuk errornya yang mana.
  4. **Check Plugin dan Theme  
** Untuk point ini terkadang mendapatkan petunjuk dari error\_log, namun terkadang juga tidak menunjukkan pada error\_log karena di disable. Untuk cms wordpress silahkan di coba disable via cpanel > File Manager > wp-content > plugin / theme > klik kanan > rename menjadi plugin.bakup / theme.bakup. jika sudah di rename dan terjadi perubahan pada web (paling tidak bisa di buka/di akses) ada kemungkinan terjadi sebuah kesalahan pada plugin / theme tersebut.  kembalikan seperti semula yaitu di rename menjadi plugin / themes. Masuk ke directory plugin / theme > silahkan anda rename theme yang aktif / plugin yang aktif satu per satu. Nanti akan ketahuan untuk errornya di plugin yang mana.
  5. **Periksa file .htaccess  
** Terkadang untuk file .htaccess juga menyebabkan error 500 atau internal server error. Hal ini bisa dikarenakan untuk settingan di .htaccess terkadang terjadi kesalahan / error. Solusinya bisa di rename dahulu menjadi .htaccess.bakup atau yang lainnya. Setelah itu coba kembali buka web anda. Apakah sudah normal / belum. Jika sudah normal silahkan membuat file .htaccess baru dan di isi dengan .htaccess default untuk wordpress.
  6. **Merubah Versi PHP  
** Untuk beberapa plugin / theme terkadang membutuhkan requirement tersendiri. Namun masih ada beberapa plugin atau theme yang masih belum kompatibel dengan versi phpnya. Jika anda menggunakan cpanel anda bisa menggunakan cara ini. Silahkan masuk ke cpanel > select php version > PHP Version rubah menjadi 5.x atau 7.x  > Set as current.  
<img loading="lazy" decoding="async" class="size-medium dz-image-23 aligncenter" src="https://tulisan.masdzub.com/wp-content/uploads/2019/12/select_php-300x300.png" alt="" alt="" alt="" width="300" height="300" /> 
  7. **Menambah PHP Limits**  
    Selain hal di php versi ada error juga dikarenakan php memori limit terlalu kecil. Hal ini bisa jadi dikarenakan plugin / theme / script / konten anda yang berat. Untuk itu jika menggunakan plugin / theme tidak asal install saja. Karena dapat memberatkan hosting. Untuk plugin dan theme cukup di install seperlunya. Untuk caranya bisa seperti saat mengubah php versi yaitu dengan cara masuk ke cpanel > select php version > switch to PHP options > scroll kebawah > memory_limit > sesuaikan kebutuhan > save > set as current.   
<img loading="lazy" decoding="async" class="size-medium dz-image-24 aligncenter" src="https://tulisan.masdzub.com/wp-content/uploads/2019/12/php_limit-300x293.png" alt="" alt="" alt="" width="300" height="293" /> 
  8. **Update Core WordPress   
** Untuk solusi selanjutnya yaitu dengan cara mengupdate core wordpress. Terkadang juga hal ini dikarenakan versi wordpress yang out of date, atau sudah kadaluarsa. Biasanya jika ada update mengenai wordpress terbaru akan muncul pada menu dashboard bagian pojok atas. Bisa langsung klik update saja.
  9. **Hubungi Penyedia Hosting  
** Langkah ini adalah langkah terakhit jika cara yang di atas sudah tidak bisa / tidak berbuah hasil. Silahkan anda hubungi pihak penyedia hosting, biasanya akan di bantu oleh team support dari penyedia hosting. Untuk hosting ini sendiri saya menggunakan layanan dari [DomaiNesia][1], Ketika terjadi sebuah error / sudah mentok biasanya menghubungi pihak hosting / team support. Dan berhasil dan cepat untuk proses nya. 

Dan itulah untuk penyebab dan solusi untuk menyelesaikan permasalah pada error 500 atau internal server error. Jika masih ada kendala atau ada yang ingin di tanyakan bisa di tuliskan di komentar di bawah.

&nbsp;

Terimakasih.

 [1]: https://domainesia.com