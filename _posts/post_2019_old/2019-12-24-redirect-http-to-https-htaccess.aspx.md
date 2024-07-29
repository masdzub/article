---
title: Redirect http ke https melalui .htaccess
author: Dzubayyan Ahmad
type: post
date: 2019-12-24T16:23:26+00:00
url: /redirect-http-to-https-htaccess.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo semua, Sering kali di ketika browser seperti Chrome, Firefox, atau Safari browser menemukan website yang terdapat peringatan tidak aman atau **not secure, **Hal ini dikarenakan pada website tidak menggunakan SSL Certificate. Tanpa SSL, website akan memunculkan peringatan tidak aman kepada pengunjung. Oleh karena itu penggunaaan SSL pengaman koneksi. Hal ini bisa sangat penting untuk mengalihka atau redirect dari http ke https.

Sebelum lebih jauh apasih SSL itu ? SSL (Secure Socket Layer) adalah lapisan keamanan yang melindungi transaksi di website dengan teknologi enkripsi data yang canggih antara web server dengan browser.

Penggunaan SSL memastikan bahwa semua data yang dikirimkan antara webserver dengan browser tetap terenkripsi.

Untuk membuat koneksi SSL, diperlukan sebuah sertifikat, untuk membuat sertifikat perlu memberikan semua rincian tentang sebuah identitas situs web dan perusahaan (personal) untuk memilih dan mengaktifkan SSL pada website.

Jika sudah terinstall SSL, seharusnya secure dengan protocol https. namun jika belum mengarah ke https diperlukan sebuah cara / metode untuk memaksa agar redirect ke https dari http. Untuk melakukan itu bisa mengedit file .htaccess pada website.

## Mengedit file .htaccess

Untuk mengedit file .htaccess terdapat beberapa cara. Di antaranya seperti berikut :

  * Edit file di local kemudian di upload melalui uploader atau FTP
  * Menggunakan editor dari File Manager
  * Menggunakan ssh lalu editor cli
  * Menggunakan FTP kemudian klik edit pada file.

Nah, mungkin yang kita bahas adalah cara edit file .htaccess melalui File Manager. Untuk caranya bisa menggunakan seperti ini.

  1. Masuk ke cpanel
  2. Masuk ke File Manager > Document Root (public_html/lainnya)
  3. Klik setting pojok kanan atas
  4. Centang &#8220;Show Hidden Files (dotfiles)&#8221;
  5. Klik &#8220;Save&#8221;
  6. Setelah itu akan ada file .htaccess
  7. Klik kanan pada file .htaccess > Edit > Edit
  8. Setelah itu silahkan anda edit dan masukkan kode berikut ini di akhir baris <pre id="crayon-5e01deb09719b275237383-1" class="crayon-line"><span class="crayon-r">RewriteEngine</span> <span class="crayon-i ">On</span>

<span class="crayon-r">RewriteCond</span> <span class="crayon-v ">%{HTTPS}</span> <span class="crayon-i ">off</span>

<span class="crayon-r">RewriteRule</span> <span class="crayon-o">^</span><span class="crayon-sy">(</span><span class="crayon-sy">.</span><span class="crayon-o">*</span><span class="crayon-sy">)</span><span class="crayon-sy">$</span> <span class="crayon-i ">https</span><span class="crayon-o">:</span><span class="crayon-o">/</span><span class="crayon-o">/</span><span class="crayon-v ">%{HTTP_HOST}</span><span class="crayon-v ">%{REQUEST_URI}</span> <span class="crayon-cn ">[L,R=301]</span></pre>

  9. Kemudian &#8220;Save Changes&#8221;
 10. Setelah itu check kembali webnya
 11. Jika sudah berhasil klik &#8220;Close&#8221; pada .htaccess untuk menutupnya.

Setelah melakukan redirect htaccess silahkan anda check kembali. Dan pastikan sudah berhasil. Dan jika terjadi mixed content silahkan di benahi kode anda dulu.