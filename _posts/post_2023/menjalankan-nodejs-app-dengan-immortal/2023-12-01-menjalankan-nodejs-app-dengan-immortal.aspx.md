---
title: Menjalankan NodeJS App dengan Immortal
date: 2023-12-01 09:45:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: Menjalankan NodeJS App dengan Immortal.
image: "https://ucarecdn.com/a6fb911a-42ed-4e2c-9778-2a0e39bea181/-/preview/120x120/"
---

Halo, sudah sekian lama saya tidak buar artikel panduan. Nah karena terdapat request dari teman. Kali ini saya akan menjelaskan caranya menjalankan NodeJS App dengan Immortal.

#### Pengenalan Node.js

Node.js adalah lingkungan runtime JavaScript yang dibangun di atas mesin JavaScript V8 dari Google Chrome. Ini memungkinkan Anda menjalankan JavaScript di sisi server, yang memungkinkan pengembang untuk membuat aplikasi web berkinerja tinggi. Dengan ekosistem modul yang luas dan fleksibilitasnya, Node.js menjadi pilihan populer untuk membangun aplikasi back-end modern.

#### Apa Itu Immortal?

Immortal adalah utilitas yang memungkinkan pengelolaan aplikasi, memastikan bahwa aplikasi dapat berjalan secara terus menerus tanpa interupsi. Dengan Immortal, Anda dapat memastikan bahwa aplikasi Node.js akan diawasi dan dijalankan kembali jika terhenti, memungkinkan pengelolaan aplikasi yang lebih handal dan stabil.

#### Langkah-langkah Menjalankan Node.js App dengan Immortal

1. **Persiapan Awal**
   Pastikan server atau hosting Anda telah dipasang dengan `immortal` dan `immortalctl`.

2. **Memulai Layanan Immortal**

   - Pastikan program Node.js dapat berjalan secara manual dengan perintah seperti:
     ```bash
     $ npm start
     # atau
     $ npm run dev
     ```
   - Buat file `immortal_service.yaml` di direktori aplikasi dengan konfigurasi seperti berikut:
     ```yaml
     cmd: npm start
     cwd: /home/username/path
     env:
       PORT: port_
     log:
       file: /home/username/log/log_nodejs_app.log
       age: 86400
       num: 3
       size: 10
       timestamp: true
     wait: 60
     retries: 3
     ```
   - Contoh penggunaan:
     ```yaml
     cmd: npm start
     cwd: /home/masdzub/frontend
     env:
       PORT: 9090
     log:
       file: /home/masdzub/log/fe_masdzub.log
       age: 86400
       num: 3
       size: 10
       timestamp: true
     wait: 60
     retries: 3
     ```
   - Atau sesuaikan dengan perintah yang dibutuhkan, misalnya:
     ```yaml
     cmd: npm run dev
     cwd: /home/masdzub/frontend
     env:
       PORT: 9090
     log:
       file: /home/masdzub/log/fe_masdzub.log
       age: 86400
       num: 3
       size: 10
       timestamp: true
     wait: 60
     retries: 3
     ```
   - Jalankan layanan menggunakan command berikut dengan nama file `immortal_service.yaml`:

     ```bash
     $ pwd
     /home/masdzub/frontend

     $ immortal -c immortal_service.yaml
     ```

   - Pastikan untuk menunggu prosesnya.

3. **Memeriksa dan Mengelola Status Immortal**

   - Untuk memeriksa status, gunakan command:
     ```bash
     $ immortalctl status
     ```
   - Untuk merestart layanan jika ada perubahan skrip, gunakan perintah:
     ```bash
     $ immortalctl restart name_of_service
     ```
   - Untuk menghentikan layanan, gunakan perintah:
     ```bash
     $ immortalctl stop name_of_service
     ```

4. **Informasi Tambahan**
   - `wait: 60`: Waktu menunggu sebelum menjalankan ulang secara otomatis.
   - `retries: 3`: Maksimal percobaan sebelum perintah dihentikan secara manual.

#### Kesimpulan

Dengan menggunakan Immortal, Anda dapat menjalankan aplikasi Node.js Anda dengan lebih andal, memastikan bahwa aplikasi tersebut akan berjalan terus menerus dengan pengelolaan yang lebih baik. Node.js memungkinkan pengembangan aplikasi back-end yang kuat, sementara Immortal memastikan aplikasi tersebut tetap berjalan dengan stabil di lingkungan produksi.

Ini adalah panduan lengkap untuk menjalankan Node.js App dengan Immortal, memungkinkan Anda untuk memahami proses dan meningkatkan stabilitas aplikasi Anda. Jika Anda memiliki pertanyaan lebih lanjut, jangan ragu untuk bertanya!
