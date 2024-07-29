---
title: Install VPN Server dengan wireguard Centos 7 / Centos 8
date: 2021-10-19 14:23:39 +07:00
tags: [linux, tutorial, vpn]
description: Install VPN Server dengan wireguard Centos.
---

---
Halo semua, kali ini saya akan memberikan tutorial instalasi VPN Server di Centos 7 / Centos 8 dengan wireguards.  
Untuk kali ini kita akan menggunakan script yang sudah ada di github dan lebih cepat dan mudah, meskipun begitu bagi instalasi VPN di server baru yang menggunakan firewall ataupun tidak dengan firewall ini membutuhkan cara-cara tertentu terlebih dahulu ya.&nbsp;Comment

Baik langsung ke inti dari artikel ini adalah melakukan instalasi VPN server dengan wireguard di centos 7 maupun 8. Untuk yang ada disini saya sendiri menggunakan centos 8 yang di beli dari DomaiNesia.

### [][1]1. Update server {#1-Update-server.wp-block-heading}

Karena disini saya menggunakan CentOS, maka untuk melakukan update nya dengan cara berikut ini :

```bash
# yum update -y
```

Bisa juga dengan command&nbsp;`dnf`

```bash
# dnf update -y
```

Setelah itu reboot atau lakukan restart server

```bash
# reboot```

### [][2]2. Mengaktifkan repository EPEL {#2-Mengaktifkan-repository-EPEL.wp-block-heading}

Untuk mengaktifkan repository EPEL di centos bisa dengan mengunjungi&nbsp;<a href="https://tulisan.masdzub.com/install-dan-mengaktifkan-epel-repository-di-centos-8.aspx" target="_blank" rel="noreferrer noopener">artikel berikut ini</a>

### [][3]3. Install Firewalld {#3-Install-Firewalld.wp-block-heading}

Untuk kali ini saya menggunakan&nbsp;`firewalld`&nbsp;sebagai firewall yang digunakan, jika menggunakan firewall lain atau keamanan lainnya bisa di sesuaikan dengan command-command pada firewall anda tersebut.

Untuk instalasi&nbsp;`firewall-cmd`&nbsp;atau&nbsp;`firewalld`&nbsp;bisa dengan cara berikut ini :

```bash
# yum install firewalld
```

### [][4]4. Install Wireguard {#4-Install-Wireguard.wp-block-heading}

#### [][5]&#8211; Download script wireguard installer nya {#--Download-script-wireguard-installer-nya.wp-block-heading}

Untuk mendownloadnya bisa menggunakan curl, bisa juga pakai wget.  
Kali ini menggunakan&nbsp;`curl`&nbsp;untuk command nya

```bash
# curl -O https://raw.githubusercontent.com/angristan/wireguard-install/master/wireguard-install.sh
```

#### [][6]&#8211; Berikan akses eksekusi {#--Berikan-akses-eksekusi.wp-block-heading}

```bash
# chmod +x wireguard-install.sh
```

#### [][7]&#8211; Jalankan script {#--Jalankan-script.wp-block-heading}

```bash
# ./wireguard-install.sh
```

#### [][8]&#8211; Instalasi wireguard {#--Instalasi-wireguard.wp-block-heading}

Setelah di jalankan, nanti akan dari script akan melakukankan pengecekan ip public, interface, ip vpn, port, dan DNS resolvernya.

Untuk hal itu, bisa di enter-enter saja langsung jika kurang mengetahui, karena sudah di isikan. Untuk port bisa di sesuaikan keinginan, namun bisa juga pakai yang random / di pilihkan dari sisi script nya.  
Sebagai contoh seperti ini  
<img decoding="async" src="https://i.imgur.com/oIWNCMn.png" alt="install wireguard" class="" /> 

Setelah itu di tunggu process installasinya. sampai selesai.  
Dan akan ada isian baru untuk mengisi pembuatan client nya, kurang lebih seperti ini.  
<img decoding="async" src="https://i.imgur.com/qHOgNH3.png" alt="Selesai Install Wireguard" class="" /> 

Bisa scan barcode yang ada untuk mendapatkan / menginstall di client.

## [][9]Kesimpulan {#Kesimpulan.wp-block-heading}

Cukup mudah bukan untuk melakukan instalasi wireguards server. dengan cara menggunakan script ini akan lebih mudah lagi, namun untuk di script ini menggunakan firewall dari firewalld ya. Jadi jangan sampai keliru.