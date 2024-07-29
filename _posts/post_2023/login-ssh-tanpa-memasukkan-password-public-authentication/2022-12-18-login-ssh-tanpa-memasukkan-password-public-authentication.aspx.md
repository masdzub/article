---
title: Login SSH tanpa memasukkan password (Public-Authentication)
date: 2022-12-26 09:45:47 +07:00
modified: 2024-03-30 09:50:47 +07:00
tags: [linux, centos, blog, ssh]
description: Metode paling aman dan banyak digunakan untuk akses server tanpa password adalah dengan menggunakan authentikasi SSH key. Dalam metode ini, digunakan sepasang kunci, yaitu private key dan public key, yang saling terhubung. Private key disimpan di perangkat lokal pengguna, sedangkan public key dimasukkan ke dalam server yang ingin diakses.
image: "https://ucarecdn.com/f7bd4532-dcab-44d4-8be0-0c6ba40eafe4/-/preview/1000x637/"
---

**Cara Akses Server Tanpa Password Menggunakan SSH Key**

Halo semua, sudah lama sekali tidak menulis artikel, terlebih lagi pada tahun ini, sepertinya sudah cukup lama dari vakum dan harus memulai hal baru kembali. Nah pada kali ini, saya akan menjelaskan cara melakukan akses ke server menggunakan SSH tanpa memasukkan password.

## Pendahuluan

Akses ke server merupakan hal yang umum dilakukan oleh banyak pengguna, terutama mereka yang bekerja dalam bidang teknologi informasi. Salah satu cara yang paling umum digunakan adalah melalui protokol SSH atau Secure Shell. Namun, seringkali pengguna harus memasukkan password setiap kali melakukan akses ke server, yang bisa menjadi tidak efisien dan rentan terhadap serangan brute force. Oleh karena itu, metode akses tanpa password menggunakan SSH key menjadi pilihan yang lebih aman dan efisien.

## Metode Akses Server Tanpa Password

Metode paling aman dan banyak digunakan untuk akses server tanpa password adalah dengan menggunakan authentikasi SSH key. Dalam metode ini, digunakan sepasang kunci, yaitu private key dan public key, yang saling terhubung. Private key disimpan di perangkat lokal pengguna, sedangkan public key dimasukkan ke dalam server yang ingin diakses.

## Langkah-langkah Membuat dan Menggunakan SSH Key

**Prosedur Pembuatan SSH Key:**

- Buka terminal atau command prompt di perangkat lokal.
- Ketik perintah `ssh-keygen` dan tekan Enter.
- Anda akan diminta untuk menentukan lokasi penyimpanan key dan passphrase (opsional).
- Tekan Enter untuk menggunakan lokasi default dan kosongkan passphrase jika tidak diinginkan.
- SSH key akan dibuat dan tersimpan di folder `.ssh` dengan nama default atau yang telah Anda tentukan.

Contoh di terminal:

```bash
ssh-keygen
```

**Prosedur Penyalinan Public Key ke Server:**

- Masuk ke server menggunakan kredensial yang ada.
- Buka file `authorized_keys` yang terletak di folder `.ssh` di direktori home pengguna (biasanya `/home/username/.ssh`).
- Salin isi public key yang dihasilkan pada prosedur sebelumnya dan tempelkan ke dalam file `authorized_keys`.
- Simpan perubahan pada file `authorized_keys` dan keluar dari editor.

Contoh di terminal:

```bash
nano ~/.ssh/authorized_keys
```

**Prosedur Pengujian Akses ke Server Menggunakan SSH:**

- Buka terminal atau command prompt di perangkat lokal.
- Ketik perintah `ssh username@alamat_server` (ganti `username` dengan nama pengguna Anda dan `alamat_server` dengan alamat atau IP server yang ingin diakses) dan tekan Enter.
- Jika konfigurasi SSH key telah berhasil, Anda akan masuk ke server tanpa diminta password.

Contoh di terminal:

```bash
ssh username@alamat_server
```

## Keamanan dan Pentingnya Mengamankan Private Key

Meskipun metode authentikasi dengan SSH key dianggap lebih aman daripada penggunaan password, pengguna perlu memastikan keamanan private key mereka. Hal ini dikarenakan setiap orang yang memiliki akses ke private key tersebut akan dapat masuk ke dalam server. Oleh karena itu, sangat penting untuk menjaga private key dengan baik dan tidak mengungkapkannya kepada pihak yang tidak berwenang.

## Kesimpulan

Dengan menggunakan metode authentikasi SSH key, pengguna dapat melakukan akses ke server tanpa perlu memasukkan password setiap kali. Hal ini tidak hanya meningkatkan keamanan, tetapi juga meningkatkan efisiensi dalam mengelola akses ke server. Meskipun demikian, pengguna harus tetap memperhatikan keamanan private key mereka untuk mencegah akses yang tidak sah ke dalam server.
