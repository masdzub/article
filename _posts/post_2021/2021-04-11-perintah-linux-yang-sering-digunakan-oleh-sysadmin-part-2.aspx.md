---
title: Perintah linux yang Sering Digunakan oleh Sysadmin – Part 2
author: Dzubayyan Ahmad
description: Perintah linux yang Sering Digunakan oleh Sysadmin – Part 2
date: 2021-04-11 12:41:08 +07:00
tags: [blog, linux, sysadmin]

---
Halo semua, Untuk sebelumnya saya sudah pernah membuat artikel mengenai perintah linux yang sering digunakan oleh para sysadmin di bagian part 1, untuk link bisa check <a href="https://tulisan.masdzub.com/perintah-linux-yang-sering-digunakan-oleh-sysadmin-part-1.aspx" target="_blank" rel="noreferrer noopener">klik sini.</a>, untuk rencana yang saya akan membuat beberapa part lagi mengenai perintah linux yang sering digunakan oleh para sysadmin.

Nah berikut ini adalah beberapa perintah linux yang sering digunakan oleh sysadmin :  
**1. Perintah linux yang digunakan untuk monitoring system.**  
Sangat berguna sekali ketika melihat sebuah kinerja dari sebuah process atau kinerja dari linux, hal ini dari sebuah system membutuhkan pengawasan lebih jika terjadi suatu kendala.  
Dan berikut ini adalah daftar perintah linux yang digunakan untuk memonitoring system :  
&#8211; `uptime` : memantau sebuah uptime dan rata-rata load dari server.  
&#8211; `top` : memantau secara keseluruhan system.  
&#8211; `vmstat` : memantau system memory, process, block I/O, dan CPU  
&#8211; `htop` : memantau secara keseluruhan system dengan tampilan lebih interaktif.  
&#8211; `netstat` : memantau statistik jaringan.

**2. `ssh` &#8211; Sebuah cara untuk akses server secara remote nix system.**  
Perintah `ssh` ini adalah salah satu cara untuk melakukan remote semua system yang menggunakan platform `*nix`, untuk keluarga `*nix` itu sendiri dari unix mapupun linux. Selain itu, `ssh` digunakna untuk akses ke terminal, transfer file (sftp, scp), dan juga dipakai untuk tunneling dengan sebuah aplikasi.  
Untuk contoh dari penggunanaan dari perintah `ssh` ini kurang lebih sebagai berikut :  
`$ ssh -i [key_file] [user]@[hostname/IP] -p [port]`

**3. `sudo` &#8211; Mengeksekusi sebuah perintah linux dengan menggunakan hak akses root di pengguna biasa.**  
Super User DO atau yang lebih sering dikenal dengan nama `sudo` ini adalah sebuah perintah linux yang sering dipakai untuk menjalankan sebuah perintah yang hanya diperuntukkan user `root` untuk menjalankannya. perintah ini hanya digunakan jika dalam keadaan user yang biasa, Untuk contoh dari penggunaannya kurang lebih seperti berikut ini :  
`$ sudo yum install httpd`

**4. `cd` &#8211; Pindah lokasi.**  
Perintah `cd` selalu digunakan ketika ingin berpindah directory.  
Untuk contoh penggunakannnya kurang lebih seperti berikut ini :

```bash
❙~❱✔≻ cd /
❙/❱✔≻ cd /usr/local/bin/
❙/usr/local/bin❱✔≻ cd ~
❙~❱✔≻ cd Downloads/
❙~/Downloads❱✔≻ cd 
❙~❱✔≻ 
```

Dan perintah untuk mengetahui sebuah lokasi saat ini, bisa menggunakan perintah `pwd`

```bash
❱✔≻ pwd
/usr/local/bin
```

**5. `cp` &#8211; Mengcopy file dan Folder**  
Perintah yang sering digunakan juga adalah `cp`, perintah ini digunakan untuk melakukan sebuah create file dan folder. Untuk contoh sebagai berikut :  
`$ cp file1 file1_backup`  
Untuk perintah diatas tersebut adalah untuk melakukan copy file `file1` ke file `file1_backup`, dan untuk file `file1` tidak termodifikasi sama-sekali.  
Sedangkan untuk melakukan copy folder beserta isinyam bisa menggunakan tambahan `-r` agar tercopy secara keseluruhan. Untuk contoh penggunaan kurang lebih seperti berikut ini :  
`cp -r directoryA directoryB`  
Dengan tambahan `-r` ini berarti bahwa folder akan mencopy semua file dan subdirectory yang ada di dalam sebuah folder tersebut.

**6. `mv` &#8211; Memindahkan file ataupun folder**  
Dengan perintah ini, teman-teman dapat memindahkan lokasi dari sebuah file dan folder, ataupun merubah nama file dan folder tersebut. Untuk contoh penggunaan kurang lebih seperti berikut ini :  
`$ mv file1 file0`  
Untuk perintah diatas melakukan rename atau mengganti nama file dan folder dari awalnya `file1` ke `file0`.  
`$ mv file0 /var/www/html`  
Sedangkan untuk perintah diatas melakukan pemindahan file `file0` ke lokasi `/var/www/html`.

### Kesimpulan {#Kesimpulan}

Untuk perintah linux yang biasa digunakan oleh sysadmin part 2 sudah selesai, Dan bisa juga di check untuk part 1 nya di <a href="https://tulisan.masdzub.com/perintah-linux-yang-sering-digunakan-oleh-sysadmin-part-1.aspx" target="_blank" rel="noreferrer noopener">link berikut ini</a>. dan sangat mudah kan untuk menggunakannya ? Sehingga dari pengguna baru pun juga tidak mengalami kesulitan selama mengetahui dari fungsinya. Dan sampai jumpa di artikel yang lain.