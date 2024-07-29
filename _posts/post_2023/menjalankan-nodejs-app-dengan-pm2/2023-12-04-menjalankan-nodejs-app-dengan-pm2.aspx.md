---
title: Menjalankan NodeJS App dengan PM2
date: 2023-12-04 00:45:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: Menjalankan NodeJS App dengan PM2.
image: "https://ucarecdn.com/6be7c2e6-0eb5-4ba0-8360-7d450346b0e6/-/preview/710x200/"
---

Node.js telah menjadi salah satu teknologi yang paling populer dalam pengembangan aplikasi web. Namun, semakin kompleksnya aplikasi membutuhkan manajemen proses yang lebih baik. Di sinilah PM2, atau Process Manager 2, hadir sebagai alat yang sangat berguna untuk membantu pengembang dalam manajemen proses Node.js dengan lebih efisien.

### Apa itu PM2?

PM2 merupakan manajer proses produksi Node.js yang memungkinkan pengguna untuk menjalankan aplikasi Node.js dalam lingkungan produksi. Kelebihan PM2 terletak pada kemampuannya dalam mengelola proses, memantau performa, dan memperbarui aplikasi tanpa adanya downtime.

**Fitur-fitur Utama PM2:**

1. **Manajemen Proses yang Efisien:** Memulai, menghentikan, dan mengelola proses aplikasi Node.js dengan mudah.
2. **Pemantauan Performa Aplikasi:** Statistik performa seperti penggunaan CPU, memori, dan log aplikasi yang terkumpul.
3. **Pemulihan Otomatis saat Terjadi Kegagalan:** Memulai ulang aplikasi secara otomatis saat terjadi crash.
4. **Skalabilitas dengan Fitur Clustering:** Menjalankan beberapa instance aplikasi untuk menyeimbangkan beban.
5. **Manajemen Log yang Efisien:** Akses log dari setiap proses yang berjalan secara terstruktur.

### Sebelumnya: Menjalankan NodeJS App dengan Immortal

Sebelumnya, ada artikel yang membahas cara menjalankan aplikasi Node.js dengan menggunakan Immortal. Immortal merupakan alat manajemen proses serupa yang memiliki beberapa fitur mirip dengan PM2. Artikel ini membahas penggunaan dan kelebihan Immortal dalam mengelola aplikasi Node.js secara efektif.

[Menjalankan NodeJS App dengan Immortal](https://tulisan.masdzub.com/menjalankan-nodejs-app-dengan-immortal.aspx/)

### Persiapan Sebelum Menggunakan PM2

Pastikan Node.js terinstal dengan benar dan pahami struktur dasar aplikasi Node.js yang akan dijalankan menggunakan PM2.

### Instalasi dan Penggunaan Awal PM2

Langkah pertama adalah menginstal PM2 secara global pada sistem dengan perintah:

```
npm install pm2 -g
```

Verifikasi apakah PM2 sudah terpasang:

```
pm2 --version
```

### Memulai Aplikasi Node.js dengan PM2

Untuk menjalankan aplikasi menggunakan PM2, gunakan perintah berikut untuk file aplikasi `app.js`:

```
pm2 start app.js
```

PM2 akan memberikan nomor ID unik untuk proses aplikasi. Anda juga dapat menyesuaikan konfigurasi seperti jumlah instance dan nama proses yang dijalankan.

### Konfigurasi Lanjutan dengan Ekosistem PM2

PM2 memiliki fitur ekosistem yang memungkinkan konfigurasi yang lebih kompleks seperti pengaturan environment, log, dan lainnya. Contoh file konfigurasi ekosistem PM2 (`ecosystem.config.js`) dapat diberikan.

Contoh File Ecosystem PM2 (`ecosystem.config.js`):

```javascript
module.exports = {
  apps: [
    {
      name: "app",
      script: "app.js",
      instances: "max",
      autorestart: true,
      watch: true,
      max_memory_restart: "1G",
      env: {
        NODE_ENV: "development"
      },
      env_production: {
        NODE_ENV: "production"
      }
    }
  ]
};
```

Dengan file konfigurasi ekosistem ini, Anda dapat menjalankan aplikasi dengan perintah:

```
pm2 start ecosystem.config.js
```

### Monitoring Performa dengan PM2

Untuk memantau performa aplikasi, gunakan perintah:

```
pm2 monit
```

Antarmuka monitor PM2 di terminal akan menampilkan statistik performa aplikasi secara real-time.

### Kesimpulan

PM2 menjadi alat yang efisien dalam manajemen proses Node.js, memungkinkan pengembang fokus pada pengembangan tanpa khawatir akan manajemen proses yang rumit. Ini membantu meningkatkan stabilitas dan kinerja aplikasi Node.js dalam lingkungan produksi.

Dengan PM2, manajemen aplikasi Node.js menjadi lebih sederhana dan efisien. Fitur-fitur canggihnya memungkinkan pengelolaan yang lebih baik, yang mendukung stabilitas aplikasi dan produktivitas pengembang.

### Daftar Referensi

- [Dokumentasi PM2](https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/)
- [GitHub PM2](https://github.com/Unitech/pm2)

PM2 membantu pengelolaan aplikasi Node.js dengan lancar dan efisien. Artikel ini membahas langkah-langkah penggunaan PM2 sebagai alternatif dalam manajemen aplikasi Node.js.
