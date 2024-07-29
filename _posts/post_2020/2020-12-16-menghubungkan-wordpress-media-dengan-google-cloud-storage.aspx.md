---
title: Menghubungkan WordPress Media dengan Google Cloud Storage
author: Dzubayyan Ahmad
type: post
date: 2020-12-16T16:49:20+00:00
url: /menghubungkan-wordpress-media-dengan-google-cloud-storage.aspx
tags:
  - All
  - Artikel
  - linux
  - Mac
  - Review
  - Tutorial

---
Halo teman semua, nah kali ini kita akan membahas mengenai cara Menghubungkan WordPress Media dengan Google Cloud Storage. Artikel ini dibuat karena dari iseng saja ketika sedang bermain GCP, dan tiba-tiba terfikirkan untuk menghubungkan media library yang ada di wordpress dengan google cloud storage. 

Google saat ini juga sudah menawarkan sebuah cloud storage atau penyimpanan di awan yang dapat menyajikan sebuah data objek, website statis dan masih banyak lainnya. Dan jika memiliki banyak gambar pada website salah satunya di wordpress teman-teman semua bisa mengoptimasi transfer file gambar menggunakan sistem cloud.

## Kelebihan menggunakan Google Cloud Storage {#Kelebihan-menggunakan-Google-Cloud-Storage}

Tentu saja menggunakan cloud storage mempunyai kelebihan tersendiri. Dan berikut adalah kelebihan menggunakan google cloud storage :

<li class="">
  Mengurangi bandwidth website, ya benar sekali. menggunakan Google Cloud Storage mengurangi dari bandwidth yang dikeluarkan oleh website/server/hosting. Karena pada dasarnya image atau content tersebut sudah menggunakan layanan google dan menggunakan bandwidth dari google itu sendiri.
</li>
<li class="">
  Konten gambar lebih cepat di load, Untuk konten image ataupun video akan lebih cepat di load, karena menggunakan server google yang memiliki low-latency network.
</li>
<li class="">
  Mengurangi ukuran disk, terkadang dalam menggunakan server atau hosting mempunyai kapasitas yang terbatas dalam sebuah gambar. Karena dari gambar yang banyak tersebut memerlukan disk yang besar. sehingga pengeluaran untuk menambah ukuran disk space akan membengkak. Berbeda dengan menggunakan google cloud storage, karena harga yang di tawarkan oleh pihak google bisa di bilang lebih murah.
</li>

## Setting Google Cloud Storage {#Setting-Google-Cloud-Storage}

Seperti yang awal sudah dijelaskan, bahwa dari sini akan menjelaskan mengenai cara menghubungkan wordpress media library dengan google cloud storage secara step by step, Untuk menghubungkan dengan google storage pastikan sudah memiliki akun Google Cloud Platform terlebih dahulu ya. Jika belum memiliki bisa mendaftar <a href="https://cloud.google.com/" target="_blank" rel="noreferrer noopener">disini</a>.

### Membuat Project Baru {#Membuat-Project-Baru}

Hal yang pertama dilakukan setelah memiliki akun GCP adalah membuat project yang mana nantinya akan dihubungkan dengan wordpress.

<li class="">
  Masuk ke menu Service Account under IAM & Admin (<a href="https://console.cloud.google.com/iam-admin/serviceaccounts" target="_blank" rel="noreferrer noopener">Bisa klik disini</a>)
</li>
<li class="">
  Klik Create a Project <img decoding="async" class="" src="https://i.imgur.com/cdsv63M.png" alt="" />
</li>
<li class="">
  Mengisi Nama Project
</li>
<li class="">
  Create Project.
</li>

### Membuat Akun Service {#Membuat-Akun-Service}

Hal yang kedua dilakukan setelah memiliki akun GCP adalah membuat akun service yang mana nantinya akan dihubungkan dengan wordpress.

<li class="">
  Masuk ke menu Service Account under IAM & Admin (<a href="https://console.cloud.google.com/iam-admin/serviceaccounts" target="_blank" rel="noreferrer noopener">Bisa klik disini</a>)
</li>
<li class="">
  Klik <code>+Create Service Account</code> <img decoding="async" class="" src="https://i.imgur.com/oKovkra.png" alt="" />
</li>
<li class="">
  Isi data mengenaik akun service yang akan dibuat <img decoding="async" class="" src="https://i.imgur.com/9wy3fi6.png" alt="" />
</li>
<li class="">
  Tekan <code>CREATE</code>
</li>
<li class="">
  Lalu untuk <code>Role</code> silahkan di ganti ke Storage Admin <img decoding="async" class="" src="https://i.imgur.com/kKqT2hG.png" alt="" />
</li>
<li class="">
  Jika sudah, lalu klik <code>Done</code>
</li>
<li class="">
  Maka akan di arahkan ke Halaman service account <img decoding="async" class="" src="https://i.imgur.com/GSylDo3.png" alt="" />
</li>
<li class="">
  Jika sudah diarahkan bisa langsung klik dari akun yang sudah di buat.
</li>
<li class="">
  Lalu scroll kebawah dan klik Add Key, lalu pilih JSON <img decoding="async" class="" src="https://i.imgur.com/fqFhjGe.png" alt="" />
</li>
<li class="">
  Setelah itu akan download secara otomatis file json dan akan terbuat juga Key nya di website.
</li>
<li class="">
  Simpan file json tersebut di tempat yang aman.
</li>

### Membuat Storage Bucket {#Membuat-Storage-Bucket}

Dan untuk tahap selanjutnya adalah membuat sebuah Bucket Storage. Ini nantinya image akan di upload ke sini dari WordPress Media Files nya. Untuk caranya kurang lebih seperti ini :

<li class="">
  Login ke Google Cloud, lalu Storage > Browser (<a href="https://console.cloud.google.com/storage/browser" target="_blank" rel="noreferrer noopener">Bisa klik disini</a>)
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/IDdKi5y.png" alt="" /> </figure> 

<li class="">
  Klik <code>Create a bucket</code>
</li>
<li class="">
  Beri nama <code>bucket</code> nya
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/dtwuVr1.png" alt="" /> </figure> 

<li class="">
  Pilih lokasi
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/molAO6D.png" alt="" /> </figure> 

<li class="">
  Pilih default class nya, disini saya menggunakan yang standar saja
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/Xt60Re8.png" alt="" /> </figure> 

<li class="">
  Pilih access controll nya
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/tpQfcRo.png" alt="" /> </figure> 

<li class="">
  Untuk setting tambahan bisa default saja
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/OLGkF8o.png" alt="" /> </figure> 

<li class="">
  Tunggu beberapa detik dan akan muncul bucket yang sudah di buat.
</li>

### Membuat Bucket dapat diakses secara public {#Membuat-Bucket-dapat-diakses-secara-public}

Untuk selanjutnya adalah membuat bucket dapat diakses secara public

<li class="">
  Klik bucket yang sudah di buat tersebut
</li>
<li class="">
  Lalu masuk ke menu permission > dan klik ADD
</li>
<li class="">
  Jika sudah di klik add, maka untk new User diisi dengan <code>allUsers</code> dan <code>Role</code> nya sebagai <code>Storage Object Viewer</code>, kurang lebih seperti dibawah ini.<br /><img decoding="async" class="" src="https://i.imgur.com/t4ckYdq.png" alt="" />
</li>
<li class="">
  Save
</li>

** Catatan : Pastikan untuk memberikan akses `allUser` hanya untuk melihat object saja (Storage Object Viewer) agar orang lain tidak melakukan perubahan pada bucket tersebut.

**Selesai !!** hanya untuk Storage Bucketnya.

## Mengintegrasikan WordPress dengan Google Cloud Storage {#Mengintegrasikan-Wordpress-dengan-Google-Cloud-Storage}

Untuk menghubungkan dengan google cloud storage dengan mudah dengan menggunakan plugin, Untuk plugin yang saat ini digunakan adalah <a href="https://wordpress.org/plugins/wp-stateless/" target="_blank" rel="noreferrer noopener">WP-Stateless – Google Cloud Storage</a>, hal ini digunakan karena plugin ini sendiri Free. Untuk plugin yang premium dan berbayar ada juga, teman-teman bisa menggunakan plugin <a href="https://deliciousbrains.com/wp-offload-media/" target="_blank" rel="noreferrer noopener">WP Offload Media</a>, Namun yang kita bahas kali ini adalah yang free.

Untuk WP-Stateless ini memberikan sebuah option / pilihan untuk tetap menyimpan file local yang ada diserver, sehingga jika tidak ingin menggunakan GCS lagi dapat langsung menonaktifkan plugin tersebut dan tidak perlu melakukan copy ulang/download ulang ke local.

### Integrasi WP ke GCS {#Integrasi-WP-ke-GCS}

Hal yang pertama dilakukan adalah melakukan instalasi plugin tersebut. Dan kurang lebih caranya sebagai berikut :

<li class="">
  Masuk ke wp-admin
</li>
<li class="">
  Klik Plugins
</li>
<li class="">
  Lalu Add New
</li>
<li class="">
  Cari di pencarian <code>WP-Stateless</code>
</li><figure class="dz-block-image">

<img decoding="async" src="https://i.imgur.com/PKRmh49.png" alt="" /> </figure> 

<li class="">
  Klik Instal Now pada plugin <code>WP-Stateless – Google Cloud Storage</code>
</li>
<li class="">
  Lalu klik <code>Activate</code> untuk melakukan aktivasi
</li>
<li class="">
  Jika sudah, akan menampilkan tampilan seperti ini<br /><img decoding="async" class="" src="https://i.imgur.com/dO8yuAl.png" alt="" />
</li>
<li class="">
  Untuk cara cepat nya menggunakan <code>Automated Setup</code>
</li>
<li class="">
  Login dengan akun google yang terkait<br /><img decoding="async" class="" src="https://i.imgur.com/RtSwwVQ.png" alt="" />
</li>
<li class="">
  Lalu menyesuaikan dengan apa yang sudah di buat sebelumnya. Mulai dari Projectnya, Bucketnya.<br /><img decoding="async" class="" src="https://i.imgur.com/cSYUDTJ.png" alt="" />
</li>
<li class="">
  Jika tampilannya kurang lebih seperti ini. maka Sedang dalam proses.<br /><img decoding="async" class="" src="https://i.imgur.com/EDowCdb.png" alt="" />
</li>
<li class="">
  Di tunggu dulu sambil ngopi, maka selanjutnya akan seperti ini<br /><img decoding="async" class="" src="https://i.imgur.com/hENi1xe.png" alt="" />
</li>

Sudah Selesai !! Silahkan coba lakukan upload file lalu lihat di bucket nya. Dan taraaaa sudah berhasil di upload ke Google Cloud Storage.

### Setting plugin WP-Stateless {#Setting-plugin-WP-Stateless}

Untuk settingannya sendiri ada bebebrapa yang bisa di custom dan yang di inginkan.  
Untuk Masuk ke settingannya bisa dengan :

<li class="">
  Masuk ke wp-admin
</li>
<li class="">
  Media
</li>
<li class="">
  Stateless Settings<br /><img decoding="async" class="" src="https://i.imgur.com/Yg7gJLp.png" alt="" />
</li>

Didalam WP-Stateless ada beberapa mode.

<li class="">
  Mode Backup : Upload filenya ke Google Cloud Storage dan tetap menggunakan url local
</li>
<li class="">
  CDN : melakukan copy gambar ke Google Cloud Storage dan URL nya mengghunakan dari GCS, di local/hosting tetap ada filenya.
</li>
<li class="">
  Ephemeral : Upload dan menggunakan url dari google cloud storage, media file library hanya digunakan sementara selama process
</li>
<li class="">
  Stateless : Mengupload dan menggunakan url dari google cloud storage langsung tanpa menggunakan media library.
</li>

Untuk saya sendiri menggunakan CDN. Buat teman-teman bisa menyesuaikan saja keinginan saja ya.

## Kesimpulan {#Kesimpulan}

Menghubungkan Google Cloud Storage dengan wordpress media library tidaklah sulit. Selain itu dengan menggunakan Google Cloud Storage bisa dirasa lebih cepat. Selain itu dengan menggunakan Google Cloud Storage akan lebih hemat bandwith. Untuk tutorial lainnya bisa juga mengakses [disini ya][1]

 [1]: https://tulisan.masdzub.com