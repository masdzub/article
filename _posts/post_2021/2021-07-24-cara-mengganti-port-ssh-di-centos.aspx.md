---
title: Cara mengganti port SSH di CentOS
date: 2021-07-24 02:09:56 +07:00
tags:
  - linux
  - tutorial
description: Cara mengganti port SSH di CentOS.
---
Halo teman-teman semua, sudah lama sekali tidak update artikel dan tutorial. Nah kali ini karena sedang gabut PPKM yang ga tau kapan selesainya karena pandemi, saya akan menulis mengenai cara mengganti port SSH di CentOS.&nbsp;Comment

Secara default untuk port SSH itu adalah port 22, namun untuk meningkatkan keamanan server, karena jika port 22 itu adalah port yang default dan sering kali terkena bruteforce atau hal lainnya oleh karena itu perlu mengganti port SSH agar tidak default lagi.

Untuk SSH itu sendiri adalah sebuah protokol administrasi yang memungkinkan user untuk mengakses dan memodifikasi berbagai macam pengaturan maupun file yang ada di dalam server.

Hal yang perlu di perhatikan dalam mengganti port didalam centos adalah membuka port tersebut. Dan karena centos itu pakai SElinux, sehingga terdapat process dulu ya.

Untuk langkah nya bisa kurang lebih seperti berikut ini :

- Masuk ke server terlebih dahulu, bisa lewat ssh dengan port default.
- Open port yang akan digunakan.
- Mencari file&nbsp;<code>sshd_config</code>
- Edit file&nbsp;<code>sshd_config</code>&nbsp;dengan port yang di inginkan.
- Simpan file tersebut.
- Restart service SSHnya.


## [][1]Mengganti Port SSH 

Untuk mengganti port ssh ada tahapannya. Berikut tahapan dan caranya :

### [][2]Open port 

Karena CentOS menggunakan SElinux kita akan menggunakan command&nbsp;`semanage`&nbsp;untuk mengaktifkan portnya.  
Untuk mengaktifkan portnya kurang lebih seperti berikut ini :

```bash
# semanage port -a -t ssh_port_t -p tcp 9091
```

Untuk angka 9091 itu bisa diganti dengan port yang diinginkan ya, pastikan port tersebut belum ada yang memakai.

### [][3]Allow port di firewall 

Untuk allow port di firewall ini hanya berlaku jika dari server tersebut sudah terpasang firewall.  
Untuk yang di contohkan disini adalah firewall seperti CSF, firewall-cmd, dan ufw. Kurang lebih seperti berikut ini :

#### [][4]CSF 

CSF iniadalah salah satu firewall yang sering dipakai, saya pun juga menggunakan CSF. Untuk allow port di CSF itu melakukan perubahan settingan di&nbsp;`csf.config`&nbsp;untuk lokasi dari settingan csf tersebut berada di&nbsp;`/etc/csf/csf.config`, Lalu cari pada baris&nbsp;`TCP_IN`&nbsp;dan&nbsp;`TCP_OUT`&nbsp;masukkan port yang ingin di allow.

Jika dari teman-teman semua ingin menginstall CSF bisa klik&nbsp;<a href="https://tulisan.masdzub.com/install-csf-configserver-security-firewall-di-centos-8.aspx" target="_blank" rel="noreferrer noopener">link artikel ini</a>

#### [][5]Firewall-cmd 

Untuk firewall-cmd ini menggunakan command, dan command nya kurang lebih seperti ini :

```bash
# firewall-cmd --permanent --zone=public --add-port=9091/tcp
```

Dan silahkan di ganti port yang ada di command diatas dengan port yang teman-teman inginkan.

Jika sudah, silahkan lakukan reload pada service firewall-cmd

```bash
# firewall-cmd --reload
```

#### [][6]UFW 

Untuk ufw ini sendiri adalah salah satu firewall yang cukup familiar, dan sering digunakan di OS ubuntu, debian dan keturunannya. Namun tidak sedikit juga yang memasang di OS CentOS. Untuk caranya kurang lebih seperti firewall-cmd, untuk contohnya kurang lebih seperti ini :

```bash
# ufw allow 9091/tcp
```

### [][7]Mencari lokasi file dari config ssh 

Untuk secara default jika menggunakan openssh, lokasi berada di&nbsp;`/etc/ssh/sshd_config`&nbsp;namun untuk beberapa hal yang sudah dicustomize atau menggunakan service ssh lainnya. Settingan berada di tempat lain. Untuk mencarinya kurang lebih dengan command seperti ini :

```bash
# find / -name "sshd_config"
```

Dan itu nanti akan munculkan hasil dari lokasinya, salah satu contohnya seperti berikut ini.

```bash
# find / -name "sshd_config"
/etc/ssh/sshd_config
```

### [][8]Melakukan editing file sshd_config 

Setelah file config ssh tersebut di temukan, maka selanjutnya editing file&nbsp;`sshd_config`&nbsp;tersebut dengan text editor kesukaan anda, bisa pakai vi, vim, nano, ee, mcedit dan lainnya. Untuk contoh kali ini pakai vi saja, karena server masih baru dan belum di install.

```bash
# vi /etc/ssh/sshd_config
```

Setelah itu bisa cari baris yang bertuliskan&nbsp;`Port 22`&nbsp;Atau&nbsp;`#Port 22`  
Jika sudah menemukan, bisa di ganti ke&nbsp;`Port 9091`  
Jika sudah lalu disimpan filenya dan keluar dari text editor.

### [][9]Restart service SSH 

Untuk hal selanjutnya adalah melakukan restart service ssh, untuk restart service SSH nya bisa dengan cara berikut ini :

```bash
# systemctl restart sshd
```

atau

```bash
# service sshd restart
```

Pastikan tidak muncul pesan error, jika ada pesan error bisa di ulang step sebelumnya.

### [][10]Memverifikasi PORT 

Untuk memverifikasi portnya bisa dengan cara menjalankan command&nbsp;`ss`&nbsp;atau bisa juga pakai&nbsp;`netstat`  
Untuk command nya kurang lebih seperti berikut ini :

```bash
# ss -tulpn | grep 9091
```

atau jika pakai netstat

```bash
# netstat -tulpn | grep 9091
```

## [][11]Kesimpulan 

Untuk melakukan pergantian port ssh di centos cukup mudah bukan ?  
Dan jika mengalami kendala dalam melakukan openport di semanage, ataupun command semanage not found bisa melakukan instalasi service yang dibutuhkan dulu. Sampai jumpa di tutorial lainnya.
