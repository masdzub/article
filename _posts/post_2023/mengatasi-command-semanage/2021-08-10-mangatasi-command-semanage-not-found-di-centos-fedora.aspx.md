---
title: Mangatasi Command Semanage ‘Not found’ di CentOS / Fedora
date: 2021-08-10 04:02:17 +07:00
tags: [tutorial, linux]
description: Mangatasi Command Semanage ‘Not found’ di CentOS / Fedora
---

Halo semua, Apa kabar ? Masih sehat dengan keadaan PPKM yang di perpanjang ini ?

Karena semakin lama semakin gabut, jadi dari saya sendiri inisiatif melakukan hal-hal yang sedikit berguna dengan membuat artikel. Nah pada tutorial sebelumnya saya membuat sebuah artikel mengenai <a href="https://tulisan.masdzub.com/cara-mengganti-port-ssh-di-centos.aspx" target="_blank" rel="noreferrer noopener">Cara mengganti port SSH di CentOS</a>, namun saat di awal ada beberapa rekan yang mengalami kendala saat melakukan semanage, dan memunculkan pesan seperti berikut ini : 

```bash 
semanage: command not found
``````

## Semanage {.wp-block-heading}

Semanage atau yang dikenal sebagai **SElinux (Security-Enhanced linux)** Management adalah sebuah tools yang digunakan untuk mengkonfigurasi unsur-unsur tertentu dari kebijakan SElinux tanpa memodifikasi atau mengkompilasi ulang sumber kebijakan. Ini termasuk pemetaan username linux untuk SElinux identitas user dan pemetaan konteks keamanan untuk objek seperti port, UI, dan host. 

Secara default, SElinux hanya memungkinkan layanan yang diketahui untuk mengikat port terkenal dan dikenal. Jika kita ingin memodifikasi layanan untuk menggunakan port non-default kita akan perlu memodifikasi jenis port dengan perintah semanage.

Dalam artikel kali ini kita akan melakukan instalasi menggunakan `yum` karena berada di OS CentOS dan Fedora.

Untuk Mencari nama package nya, bisa dengan menggunakan command `yum provides /usr/sbin/semanage`, kurang lebih seperti berikut ini : 

```bash
# yum provides /usr/sbin/semanage

Last metadata expiration check: 3:16:28 ago on Tue 10 Aug 2021 12:30:51 AM UTC.
policycoreutils-python-utils-3.1-4.fc33.noarch : SElinux policy core python utilities
Repo        : @System
Matched from:
Filename    : /usr/sbin/semanage

policycoreutils-python-utils-3.1-4.fc33.noarch : SElinux policy core python utilities
Repo        : fedora
Matched from:
Filename    : /usr/sbin/semanage
```

Nah pada command diatas di temukan bahwa nama package yang harus di install adalah `<meta http-equiv="content-type" content="text/html; charset=utf-8">policycoreutils-python-utils`, Maka dari itu untuk menginstallnya dengan cara seperti berikut ini :

```bash
# yum install policycoreutils-python-utils
```

Dan setelah instalasi selesai bisa dicoba kembali menjalankan perintah menggunakan `semanage`, Dan ini akan bisa menggunakan command tersebut. 

Dan untuk selanjutnya bisa juga melakukan pengecekan secara lebih command dan options yang ingin di gunakan dengan menggunakan command seperti beritkut : 

```bash
# man semanage

atau 

# semanage --help
```



## Kesimpulan {.wp-block-heading}

Cukup mudah bukan untuk instalasi command tersebut dengan menjalankan perintah dari yang sudah di berikan diatas. Untuk hal ini bisa di lakukan saat pertama kali saja, setelah itu tidak perlu melakukan instalasi lagi.