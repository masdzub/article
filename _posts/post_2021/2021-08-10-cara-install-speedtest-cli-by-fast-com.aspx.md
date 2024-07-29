---
title: Cara Install Speedtest CLI by fast.com
date: 2021-08-10 12:38:59 +07:00
tags:
  - linux
  - tutorial
description: Cara Install Speedtest CLI by fast.com

---
Halo semua, setelah sekian purnama memikirkan ingin menulis artikel apa saja namun bingung namun kegiatan tidak ada karena terbatas oleh PPKM di pandemi, saya akhirnya memutuskan untuk menulis artikel yang bertujuan melakukan speedtest server dengan menggunakan command lewat terminal. Untuk yang sebelumnya sudah pernah juga, namun menggunakan provider yang berbeda. Untuk yang kemarin menggunakan Speedtest by Ookla, bisa baca artikelnya disini dengan judul&nbsp;<a href="https://tulisan.masdzub.com/cara-install-speedtest-cli-by-ookla.aspx" target="_blank" rel="noreferrer noopener">Cara Install Speedtest CLI by Ookla</a>&nbsp;Comment

## [][1]Fast 

**Fast**&nbsp;adalah salah satu penyedia speedtest yang cukup terkenal, hal ini dikarenakan sering kali di kaitkan dengan speedtest nya yang mengarah ke koneksi netflix, jadi semakin lancar koneksinya semakin lancar juga koneksi ke netflix. Untuk tampilan dari website fast sendiri bisa di akses di&nbsp;<a href="https://fast.com/" target="_blank" rel="noreferrer noopener">fast.com</a>.  
Untuk tools yang akan di gunakan kali ini menggunakan tools fast yang di buat dengan bahasa pemrograman golan yang sudah di compile, jadi lebih mudah. Dan dalam tahapan berikut ini nantinya akan ada beberapa cara untuk installnya.

### [][2]&#8211; Download fast dan dijalankan 

Ini adalah cara yang paling mudah, karena setelah di unduh menggunakan wget atau pakai curl, lalu rubah permissionya menjadi executable dan langsung dijalankan.  
Untuk cara mendownload dengan cara berikut ini :

```bash
$ curl -L https://github.com/ddo/fast/releases/download/v0.0.4/fast_linux_amd64 -o fast

Atau

$ wget https://github.com/ddo/fast/releases/download/v0.0.4/fast_linux_amd64 -O fast
```

Setelah di download menggunakan wget atau curl selanjutnya mengubah permissionnya menjadi executable dengan command seperti berikut ini :

```bash
$ chmod +x fast
```

Setelah di rubah settingan permissionnya bisa dijalankan dengan cara berikut ini :

```bash
$ ./fast
```

<img decoding="async" src="https://i.imgur.com/PJSngnA.png" alt="" /> </figure> 

### [][3]&#8211; Download install ke /usr/local/bin/ {#--Download-install-ke-usrlocalbin.wp-block-heading}

Untuk cara kedua dengan cara melakukan download dan meletakkan file fast nya tersebut ke dalam directory&nbsp;`/usr/local/bin`&nbsp;hal ini agar lebih bisa dijalankan langsung, tanpa harus berada di lokasi file tersebut.  
Untuk caranya dengan cara berikut ini :

```bash
$ wget https://github.com/ddo/fast/releases/download/v0.0.4/fast_linux_amd64

$ sudo install fast_linux_amd64 /usr/local/bin/fast

$ fast
```

<img decoding="async" src="https://i.imgur.com/7diavY0.png" alt="" /> </figure> 

### [][4]&#8211; Install menggunakan snap {#--Install-menggunakan-snap.wp-block-heading}

Untuk cara ketiga menggunakan&nbsp;`snap`, untuk cara ketiga ini pastikan di perangkat anda sudah terinstall package&nbsp;`snapd`&nbsp;jika belum terinstall bisa di install dengan cara seperti ini :  
**Ubuntu, Debian dan keturunannya :**

```bash
# apt install snapd
```

**CentOS, Fedora, Almalinux, Rockylinux**

```bash
# yum install snapd
```

Setelah package&nbsp;`snapd`&nbsp;terinstall untuk install fast nya dengan cara :

```bash
# snap install fast
```

## [][5]Kesimpulan {#Kesimpulan.wp-block-heading}

Dan itulah artikel dari saya yang mengisi kegabutan karena PPKM pandemi ini, cukup mudah bukan ? Untuk melakukan pengecekan kecepatan internet ke&nbsp;<a href="https://fast.com/" target="_blank" rel="noreferrer noopener">fast.com</a>. Untuk melakukan instalasi dan menjalankannya bisa dengan cara seperti apa yang sudah di infokan diatas ya.
