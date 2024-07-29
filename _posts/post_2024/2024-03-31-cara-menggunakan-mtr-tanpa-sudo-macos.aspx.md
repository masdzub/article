---
title: "Menggunakan MTR pada macOS Tanpa sudo"
date: 2024-03-31 04:01:47 +07:00
tags: [sysadmin, tutorial, blog, macos]
categories: [Tutorial]
description: "MTR (Matt's traceroute) adalah alat diagnostik jaringan yang kuat yang menggabungkan fungsionalitas traceroute dan ping untuk memberikan wawasan detail tentang rute jaringan dan potensi bottleneck. Namun, pembaruan terbaru untuk MTR melalui Homebrew memperkenalkan persyaratan untuk menggunakan `sudo` bagi pengguna non-administrator."
image: "https://ucarecdn.com/bb84f50f-7862-495d-a64c-a899073cb52a/-/preview/1000x233/"
---

MTR (Matt's traceroute) adalah alat diagnostik jaringan yang kuat yang menggabungkan fungsionalitas traceroute dan ping untuk memberikan wawasan detail tentang rute jaringan dan potensi bottleneck. Namun, pembaruan terbaru untuk MTR melalui Homebrew memperkenalkan persyaratan untuk menggunakan `sudo` bagi pengguna non-administrator. Ini bisa merepotkan, terutama saat bekerja pada sistem dengan akun pengguna yang terbatas.

Artikel ini menguraikan solusi yang aman dan efektif untuk menggunakan MTR tanpa sudo pada macOS, bahkan pada Mac M1. Saya akan membahas solusi lama yang sudah tidak relevan dan memberikan instruksi langkah demi langkah yang jelas dengan mempertimbangkan keamanan.

**Menginstal MTR**

Sebelum kita lanjut dengan perbaikan untuk menggunakan MTR tanpa sudo, mari pastikan itu terinstal di sistem Anda. Berikut cara menginstal MTR menggunakan Homebrew:

1. **Pasang Homebrew (jika belum terpasang):**

   - Buka jendela Terminal (Aplikasi > Utilitas > Terminal).
   - Tempelkan perintah berikut dan tekan Enter:

     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

   - Ikuti petunjuk di layar untuk menyelesaikan instalasi Homebrew.

2. **Instal MTR:**

   - Begitu Homebrew terinstal, jalankan perintah berikut di Terminal:

     ```bash
     brew install mtr
     ```

**Memahami Masalah**

Fungsionalitas MTR telah dibagi menjadi dua biner:

- `mtr`: Memberikan antarmuka pengguna dan pengalaman MTR secara keseluruhan.
- `mtr-packet`: Menangani fungsionalitas tracing jaringan inti.

Pembaruan ini memerlukan `sudo` untuk `mtr` karena membutuhkan akses ke soket jaringan mentah, yang biasanya dibatasi pada macOS.

Solusi sebelumnya yang melibatkan variabel lingkungan tidak lagi relevan dengan arsitektur MTR saat ini.

**Perbaikan Aman dan Efektif**

**Mengatur Bit SUID**

Bit SUID (Set User ID) adalah pengaturan izin yang memungkinkan sebuah eksekutor dijalankan dengan hak istimewa pemilik file, bahkan jika pengguna yang menjalankan program tersebut tidak memiliki hak istimewa tersebut.

Dalam hal ini, mengatur bit SUID untuk `mtr-packet` memungkinkan `mtr` memanfaatkan izinnya untuk akses soket mentah tanpa memerlukan sudo dari pengguna. Namun, penting untuk dipahami bahwa pendekatan ini dianggap aman karena:

- Bit SUID hanya diterapkan pada sebuah biner spesifik (`mtr-packet`) dengan tujuan terbatas (tracing jaringan).
- Anda tidak memberikan hak istimewa root penuh kepada `mtr`.

**Kekhawatiran Potensial**

Meskipun solusi ini umumnya aman, penting untuk menyadari potensi implikasi keamanan:

- **Eksploitasi Kerentanan:** Jika `mtr-packet` memiliki kerentanan, itu bisa dieksploitasi untuk mendapatkan hak istimewa yang ditinggikan. Namun, risiko ini dikurangi dengan menjaga MTR tetap diperbarui dan menggunakannya dari sumber yang dipercayai (seperti Homebrew).
- **Eksekusi Tidak Disengaja:** Eksekusi tidak disengaja `mtr-packet` bisa memiliki konsekuensi yang tidak diinginkan. Disarankan untuk hanya menjalankan `mtr` (yang memanggil `mtr-packet`) untuk tujuan yang dimaksudkan.

Jika kekhawatiran ini lebih besar dari pada manfaat untuk kasus penggunaan Anda, pertimbangkan alat alternatif seperti `traceroute` yang mungkin tidak memerlukan bit SUID.

**Mengubah Kepemilikan**

Anda perlu mengubah kepemilikan `mtr-packet` menjadi root karena hanya root yang dapat mengatur bit SUID.

**Petunjuk Langkah demi Langkah**

**Untuk Mac Intel**

1. Buka jendela Terminal.
2. Verifikasi jalur ke `mtr` dan `mtr-packet` menggunakan perintah berikut (jalur-jalur ini mungkin sedikit berbeda tergantung pada versi Homebrew Anda):

   ```bash
   which mtr
   which mtr-packet
   ```

3. Jalankan perintah berikut dengan `sudo` untuk mengubah kepemilikan dan mengatur bit SUID:

   ```bash
   sudo chown root /usr/local/Cellar/mtr/VERSION/sbin/mtr-packet
   sudo chmod 4755 /usr/local/Cellar/mtr/VERSION/sbin/mtr-packet
   ```

   Ganti `VERSION` dengan nomor versi sebenarnya dari perintah `which` sebelumnya.

   > **Peringatan:** Pastikan untuk PATH nya sudah benar.
   {: .prompt-warning }

**Untuk Mac M1**

1. Buka jendela Terminal.
2. Verifikasi jalur ke `mtr` dan `mtr-packet` menggunakan perintah berikut (jalur-jalur ini khusus untuk Mac M1):

   ```bash
   which mtr
   which mtr-packet
   ```

3. Jalankan perintah berikut dengan `sudo` untuk mengubah kepemilikan dan mengatur bit SUID:

   ```bash
   sudo chown root /opt/homebrew/bin//mtr-packet
   sudo chmod 4755 /opt/homebrew/bin//mtr-packet
   ```

   Ganti `VERSION` dengan nomor versi sebenarnya dari perintah `which` sebelumnya.

   {: .prompt-warning }
   > **Peringatan:** Pastikan untuk PATH nya sudah benar.

**Pengujian dan Verifikasi**

1. Cobalah menjalankan `mtr <hostname>` tanpa `sudo`. Jika berhasil, Anda harus melihat keluaran MTR tanpa perlu memasukkan kata sandi Anda.
2. Jika Anda mengalami masalah, periksa kembali jalur dan izin. Anda juga bisa merujuk ke dokumentasi resmi MTR atau sumber daya pemecahan masalah untuk Homebrew.

**Kesimpulan**

Dengan mengatur bit SUID dan mengubah kepemilikan untuk `mtr-packet`, Anda dapat menggunakan MTR tanpa sudo pada macOS, menyederhanakan proses diagnostik jaringan.
