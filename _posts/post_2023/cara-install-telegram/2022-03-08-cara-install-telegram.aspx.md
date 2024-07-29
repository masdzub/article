---
title: Cara Install Telegram di linux
date: 2022-12-26 09:45:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: Install Telegram di linux.
---

Halo teman semua, sudah lama sekali tidak membuat artikel. Nah kali ini kebetulan sedang gabut tidak ada kerjaan di kost. Jadi saya mau share mengenai cara install aplikasi telegram di linux beserta shortcutnya. 

Untuk cara / metode installasinya terdapat beberapa macam, mulai install dari official, install menggunakan snap, install menggunakan flatpak dan lainnya. Dan berikut adalah cara-caranya : 

## Cara 1 : Install Telegram dari official website

Dari telegram menyediakan aplikasi berbasis desktop di web resmi mereka. Untuk aplikasi desktopnya dapat digunakan pada berbagai OS, termasuk Fedora, Ubuntu, linux Mint dan lainnya.

Untuk download atau melakukan instalasinya, bisa download langsung di web resminya. Teman-teman bisa download di bawah link berikut ini <a href="https://desktop.telegram.org/" target="_blank" rel="noreferrer noopener">https://desktop.telegram.org/</a> 

Untuk menjalankannya pun cukup mudah, dengan cara extract file yang sudah di download, ya itu file dengan ekstensi `tar.xz`, jika sudah, masuk ke dalam folder Telegram hasil extract dari file compress tadi. Setelah itu cukup dengan menjalankan double klik pada file `Telegram`. Setelah itu akan berjalan secara otomatis dan akan muncul aplikasinya.

Setelah muncul, teman-teman bisa mengikuti langkah-langkah yang ada untuk login pada menggunakan akun telegram teman-teman semua.

Note : Metode ini, sebenarnya tidak melakukan instalasi pada perangkat anda, namun melakukan symlink ke dalam system launcher / app menu. Jadi jangan menghapus file yang sudah di extract tersebut.

## Cara 2 : Install Telegram dari Snap App

Teman-teman semua bisa juga menggunakan cara yang ke-2 ini. Untuk aplikasi telegram ini terdaftar di list <a href="https://snapcraft.io/telegram-desktop" target="_blank" rel="noreferrer noopener">aplikasi di snap</a> sehingga, teman-teman bisa menginstall menggunakan command line atau checkd i ubuntu store (jika menggunakan ubuntu), Jika bukan ubuntu bisa juga menginstall dari command line / terminal. Untuk installnnya pastikan sudah memiliki package `snapd`. Jika belum, bisa install dengan cara beikut ini : 

```bash
sudo apt install snapd -y
```

Jika sudah menginstall package `snapd`, maka bisa melakukan instalasi telegramnya. Dengan menjalankan command berikut ini : 

```bash
sudo snap install telegram-desktop
```

Setelah selesai melakukan instalasinya, aplikasi telegram akan muncul pada launcher app, atau app menu. Setelah muncul bisa mengikuti cara / langkah-langkah yang anda untuk instruksi selanjutnya.

## Cara 3 : Install Telegram dari Flatpak

Aplikasi telegram linux saat ini juga tersedia dari aplikasi flatpak dari flathub. Pastikan perangkat anda sudah terinstall flatpak. Dan berikut cara install nya : 

```bash
sudo apt install flatpak
```

Menambahkan flathub repository dengan cara berikut ini :

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Jika sudah terinstall pakcage flatpaknya, setelah itu bisa dengan mendownload aplikasi telegram nya, Untuk downloadnya bisa download di link <a href="https://flathub.org/apps/details/org.telegram.desktop" target="_blank" rel="noreferrer noopener">berikut ini </a>