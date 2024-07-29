---
title: Hal baru pada MySQL 8 dan Hal yang sudah tidak didukung pada MySQL 8
date: 2023-01-05 09:45:47 +07:00
modified: 2023-01-05 09:50:47 +07:00
tags: [linux, mysql, blog]
description: Hal yang baru pada mysql 8 dan yang sudah tidak didukung pada MySQL 8
---

Halo semua, nah pada awal tahun 2023 ini saya akan memberikan beberapa alasan kena teman-teman semua harus mulai beralih ke Mysql 8 dari yang sebelumnya menggunakan MySQL 5.7

Setelah diluncurkan MySQL 8 pada tahun 2018 lalu, dan untuk tahun ini sudah lebih dari 4 tahun sejak peluncuran MySQL 8 pertama kali. Ada kemungkinan untuk hal ini sudah saat nya kita beralih ke versi yang terbaru.

MySQL 8 mempunyai banyak perkembangan dalam keamanan dan juga performa yang lebih bagus daripada versi yang sebelumnya. Dan juga perlu diperhatikan untuk dari sisi teman-teman untuk melakukan migrasi ke versi database yang baru untuk menghindari kehilangan data, mengalami downtime atau pengembalian ke versi sebelumnya saat dalam mode produksi.

Dalam artikel kali ini, saya akan membahas mengenai beberapa fitur dan juga hal-hal yang sudah tidak didukung pada versi MySQL 8 tersebut.

## Hal-hal yang baru pada MySQL 8
Dari website resmi MySQL 8 memberikan sebuah informasi hal-hal yang baru dan terpasang pada MySQL 8 tersebut. Kurang lebih diantaranya sebagai berikut :

- Penggunaan pemindaian baris ke kolom (row level locking)
- Dukungan terhadap trasaksi yang dapat diulang (retryable transactions).
- Penggunaan index global untuk optimasi JOIN.
- Penggunaan Just-In-Time (JIT) compilation untuk mempercepat eksekusi query.
- Dukungan terhadap ekspresi reguler (Regular expressions) pada query.
- Dukungan terhadap table temporari yang tersimpan pada memory.
- Penggunaan index JSON.
- Dukungan terhadap window functions
- Dukungan terhadap kolom-kolom yang di amankan / di encrypt (encrypted coloumns).

## Hal-hal yang sudah tidak didukung pada MySQL 8

- Perlengkapan MySQL ‘ISAM’ dan ‘BERKELEYDB’ sudah tidak tersedia lagi.
- Penggunaan MyISAM sebagai engine default sudah tidak tersedia lagi.
- Penggunaan ‘mysql_*’ function dalam PHP sudah tidak didukung lagi.
- Penggunaan kata sandi SHA-1 yang tidak aman untuk autentikasi sudah tidak didukung lagi.
- Penggunaan ‘OLD_PASSWORD'() function sudah tidak didukung lagi.
- Penggunaan ‘SYSDATE’ sebagai default value untuk timestamp sudah tidak didukung lagi.

Dan hal-hal tersebut adalah beberapa hal baru dan yang sudah tidak didukung oleh MySQL 8. Oleh karena itu perlunya dari kita melakukan update versi MySQL dari yang sebelumnya masih menggunakan MySQL 5.7 menjadi MySQL 8.

Dan hal yang perlu diperhatikan ketikan mengupgrade pastikan untuk query yang ada pada code sudah support dan siap untuk berjalan pada MySQL 8. Jika ada code yang belum sesuai dengan versi terbaru maka perlu dilakukan sebuah perubahan kembali.