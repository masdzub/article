---
title: "Lupa Password Root di CentOS/Enterprise Linux (EL)? Begini Cara Mengatasinya!"
date: 2024-03-31 14:27:47 +07:00
tags: [sysadmin, tutorial, blog, linux]
categories: [Tutorial]
description: "Lupa password adalah hal yang wajar terjadi. Untungnya, mereset password root atau user lain di CentOS/EL cukup mudah dilakukan. Pada artikel ini, kita akan membahas langkah-langkah untuk mereset password di EL versi 7, 8, dan 9."
image: "https://ucarecdn.com/0036ba30-89ec-4f3c-a728-3f0a1d2466b1/-/preview/612x612/"
---

Halo! Pernahkah Anda mengalami lupa password root atau user lain di CentOS/Enterprise Linux (EL)? Jangan panik! Artikel ini akan memandu Anda untuk mereset password dengan mudah.

**Apa itu CentOS/Enterprise Linux (EL)?**

CentOS dan Enterprise Linux (EL) adalah sistem operasi berbasis Linux yang populer untuk server. Keduanya menawarkan stabilitas, keamanan, dan skalabilitas yang tinggi, menjadikannya pilihan ideal untuk berbagai aplikasi. EL adalah versi berbayar dengan dukungan komersial dari Red Hat, sedangkan CentOS merupakan komunitas-driven distribution yang kompatibel dengan EL.

**Lupa password adalah hal yang wajar terjadi. Untungnya, mereset password root atau user lain di CentOS/EL cukup mudah dilakukan. Pada artikel ini, kita akan membahas langkah-langkah untuk mereset password di EL versi 7, 8, dan 9.**

**Langkah-langkah:**

**1. Booting ke Single User Mode:**

- Restart sistem Anda.
- Perhatikan menu GRUB saat sistem melakukan booting. Ketika muncul, tekan tombol "e" untuk mengedit baris kernel yang dipilih.

**2. Modifikasi Baris Kernel:**

- Cari baris yang dimulai dengan "linux" (atau "linuxefi" untuk sistem UEFI).
- Tambahkan opsi berikut di akhir baris, dipisahkan dengan spasi:
  - rd.break - Ini memberitahu sistem untuk berhenti setelah memasang ulang filesystem root dalam mode baca- tulis, memungkinkan Anda untuk mengubah password.
  - (Opsional untuk EL 8+) init=/sysroot/bin/sh - Opsi ini (hanya berlaku untuk EL 8 dan yang lebih baru) menentukan proses awal alternatif untuk digunakan, yang menyediakan lingkungan shell untuk mereset password.

**3. Booting ke Single User Mode:**

- Setelah melakukan edit yang diperlukan, tekan "Ctrl+X" atau "F10" (tergantung sistem Anda) untuk mem-boot sistem dengan opsi kernel yang dimodifikasi.

**4. Remount Root Filesystem dan Masuk ke Lingkungan Chroot:**

- Setelah booting, Anda akan diberikan prompt root shell.
- Pasang kembali root filesystem dalam mode baca-tulis untuk mengizinkan perubahan:

```bash
mount -o remount,rw /sysroot
```

- Masuki lingkungan chroot, pada dasarnya membuat struktur direktori root sementara:

```bash
chroot /sysroot
```

**5. Reset Password Root:**

- Di dalam lingkungan chroot, gunakan perintah passwd untuk mengubah password root:

```bash
passwd root
```

- Masukkan password root baru yang Anda inginkan dua kali untuk konfirmasi.

**6. Update SELinux (jika aktif):**

- Jika sistem Anda menggunakan Security-Enhanced Linux (SELinux), perbarui informasi labelnya untuk mencerminkan perubahan password:

```bash
touch /.autorelabel
```

**7. Keluar dari Chroot dan Reboot:**

- Keluar dari lingkungan chroot:

```bash
exit
```

- Terakhir, reboot sistem menggunakan perintah berikut:

```bash
reboot
```

**8. Setelah Reboot:**

- Setelah sistem reboot, Anda seharusnya bisa login menggunakan password root yang baru diatur. Terkadang process ini sedikit lebih lama namun bisa ditunggu saja.

**Kesimpulan:**

Dengan mengikuti panduan di atas, Anda dapat dengan mudah mereset password root atau user lain di CentOS/EL 7, 8, dan 9. Ingatlah untuk selalu menggunakan password yang kuat dan aman untuk menjaga keamanan sistem Anda.
Artikel ini bisa digunakan juga untuk Almalinux, Rocky Linux juga.

**Tips:**

- Gunakan kombinasi huruf besar dan kecil, angka, dan simbol untuk membuat password yang kuat.
- Hindari menggunakan informasi pribadi seperti nama, tanggal lahir, atau alamat dalam password Anda.
- Ganti password Anda secara berkala untuk meningkatkan keamanan.

**Semoga bermanfaat!**
