---
title: File .htaccess pada wordpress hilang ? Ini solusinya.
author: Dzubayyan Ahmad
type: post
date: 2019-12-23T11:14:37+00:00
url: /file-htaccess-pada-wordpress-hilang-ini-solusinya.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo semua, setelah migrasi / pindah hosting secara manual terkadang pulang file hidden tidak ikut ke copy. Nah kali ini akan membahas mengenai masalah yang di akibatkan jika file .htaccess pada wordpress tidak ikut terupload atau tidak ada.

Untuk akibatnya ada banyak hal. Bisa terjadi 404 pada page / post lain ketika di buka. Ada juga yang mengalami error 500 aatau bisa juga mengalami error lainnya.

Dan berikut ini adalah file .htaccess default nya.

  1. **File .htaccess jika wordpressnya adalah single site. ** <pre class="dz-block-preformatted"># BEGIN WordPress

RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]

# END WordPress</pre>

  2.  **File .htaccess jika wordpressnya adalah multisite (sub folder)** <pre class="dz-block-preformatted">RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]

# add a trailing slash to /wp-admin
RewriteRule ^([_0-9a-zA-Z-]+/)?wp-admin$ $1wp-admin/ [R=301,L]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^ - [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(wp-(content|admin|includes).*) $2 [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(.*\.php)$ $2 [L]
RewriteRule . index.php [L]

</pre>

  3. **File .htaccess jika wordpressnya adalah mutisite (Sub domain)** <pre class="dz-block-preformatted">RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]

# add a trailing slash to /wp-admin
RewriteRule ^wp-admin$ wp-admin/ [R=301,L]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^ - [L]
RewriteRule ^(wp-(content|admin|includes).*) $1 [L]
RewriteRule ^(.*\.php)$ $1 [L]
RewriteRule . index.php [L]</pre>

&nbsp;

Hal di atas adalah file .htaccess default dari wordpress. Dan di pastikan untuk file .htaccess disini hanya untuk wordpress ya. jangan sampai di gunakan untuk cms / framework lain. jika salah pakai malah error.