---
title: Cara Install Postman di linux
author: Dzubayyan Ahmad
type: post
date: 2020-12-21T04:23:16+00:00
url: /cara-install-postman-di-linux.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo teman semua, nah kali ini saya mau share mengenai sebuah tutorial tentang cara melakukan install Postman di linux, baik itu dari ubuntu, debian, maupun fedora

## Postman

Postman adalah salah satu aplikasi yang berfungsi sebagai _REST CLIENT_ untuk uji coba _REST API_. Postman lebih sering dipakai oleh para developer terutama developer / programmer pembuat _API_ sebagai tools untuk menguji _API_ yang sudah di buat sebelumnya.

Postman ini dapat berjalan pada semua Operating Syetm, termasuk linux (32-bit / 64-bit), MacOS dan Windows (32-bit/64-bit), dan itu semua bisa di Download di lewat link [berikut ini][1], Atau bisa juga menggunakan versi web nya di [go.postman.co/build][2]

### Platform linux yang Support Postman

Sampai artiel ini ditulis, untuk Platform linux desktop yang di dukung kurang lebih untuk distro berikut ini :

  * Ubuntu 14.04 atau yang lebih baru
  * Debian 8 atau yang lebih baru
  * linux Mint 18 atau yang lebih baru
  * Fedora 30 Atau yang lebih baru

Jika distro tidak tercantum itu bisa disesuaikan untuk distro dari sisi teman-teman dibuild dengan base apa. Seperti kali linux yang di buat dengan base linux ubuntu.

## Install Postman di linux

Dalam artikel ini saya mau share 2 cara untuk melakukan instalasi. Yang pertama menggunakan [snap][3], dan yang 1 nya dengan meng-extract dari file download yang ada di website Postman itu sendiri.

### Install Postman di linux dengan Snap

Untuk kali ini saya sendiri akan share beberapa cara / tutorial untuk melakukan instalasi dari beberapa distro.

#### Install Postman di Debian, Ubuntu, linux Mint

Untuk beberapa distro tersebut menggunakan package manager `apt` oleh karena itu sama saja. Dan bisa menjalankan perintah berikut ini :

    $ sudo apt update
    $ sudo apt install snapd
    $ sudo snap install postman

#### Install Postman di Fedora / CentOS desktop

Untuk beberapa distro yang menggunakan package manager `yum` / `dnf` seperti fedora bisa menggunakan cara berikut ini :

    $ sudo dnf install snapd
    $ sudo ln -s /var/lib/snapd/snap /snap
    $ sudo snap install postman

### Install Secara manual di linux

Untuk cara kedua yaitu dengan cara melakukan instalasi manual dengan cara mendownload aplikasi Postman yang paling terakhir di [Download Postman][4]  
<img loading="lazy" decoding="async" class="alignnone size-medium wp-image-520" src="https://tulisan.masdzub.com/wp-content/uploads/2020/12/3568de2e-2020-12-21_11-22-300x155.png" alt="" width="300" height="155" srcset="https://tulisan.masdzub.com/wp-content/uploads/2020/12/3568de2e-2020-12-21_11-22-300x155.png 300w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/3568de2e-2020-12-21_11-22-1024x528.png 1024w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/3568de2e-2020-12-21_11-22-768x396.png 768w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/3568de2e-2020-12-21_11-22.png 1370w" sizes="(max-width: 300px) 100vw, 300px" /> 

Setelah di download silahkan teman-teman extract file tersebut lalu pindahkan ke directory /opt/, lalu buat `symlink` dan dipanggil di `/usr/local/bin/postman` agar nantinya postman dapat dijalankan dengan memanggil `postman` .  
Untuk perintah CLI nya bisa mengikut cara berikut ini :

    $ cd Downloads
    $ tar -zxvf Postman-linux-x64-7.36.1.tar.gz
    $ sudo mv Postman /opt/postman
    $ sudo ln -s /opt/postman/Postman /usr/local/bin/postman
    $ postman

Lalu akan muncul tampilan postman seperti berikut ini :  
<img loading="lazy" decoding="async" class="alignnone size-medium wp-image-523" src="https://tulisan.masdzub.com/wp-content/uploads/2020/12/fd7311c6-2020-12-21_11-38-300x168.png" alt="" width="300" height="168" srcset="https://tulisan.masdzub.com/wp-content/uploads/2020/12/fd7311c6-2020-12-21_11-38-300x168.png 300w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/fd7311c6-2020-12-21_11-38-1024x573.png 1024w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/fd7311c6-2020-12-21_11-38-768x429.png 768w, https://tulisan.masdzub.com/wp-content/uploads/2020/12/fd7311c6-2020-12-21_11-38.png 1368w" sizes="(max-width: 300px) 100vw, 300px" /> 

Untuk selanjutnya membuat file dengan extention `.desktop` agar postman dapat dijalankan melalui aplication list atau aplication launch atau drawer atau sejenisnya. File tersebut nantinya akan diletakkan di `/usr/share/applications/`, untuk membuatnya bisa dengan cara berikut ini :

    $ sudo vim /usr/share/applications/postman.desktop

Jika sudah, silahkan diisi untuk file tersebut dengan konfigurasi berikut ini :

    [Desktop Entry]
    Type=Application
    Name=Postman
    Icon=/opt/postman/app/resources/app/assets/icon.png
    Exec="/usr/local/bin//postman"
    Comment=Postman Desktop App
    Categories=Development;Code;

simpan lalu tutup text editor. Dan pastikan untuk lokasinya sudah sesuai dan benar. jika menggunakan path custom atau berbeda dengan apa yang sudah di infokan diatas, silahkan di sesuaikan sendiri ya.

Jika sudah benar, maka ketika membuat aplication list akan muncul aplikasi postman pada menu. Seperti yang ada di screenshoot berikut ini :  
<img decoding="async" src="https://s3.masdzub.com/59e3249b-2020-12-21_12-35.png" alt="aplication menu search postman" /> 

## Uninstall Postman

Untuk melakukan uninstall bisa dengan 2 cara juga, dan itu disesuaikan dengan cara install anda sebelumnya.

### Uninstall Postman dengan Snap

Untuk melakukan uninstall postman dengan snap teman-teman perlu menjalankan perintah remove pada terminal. untuk perintahnya kurang lebih seperti ini

    $ sudo snap remove postman

dan silahkan di tunggu beberapa saat akan terhapus untuk aplikasi postman nya

### Uninstall Posman secara manual

Untuk teman-teman yang melakukan instalasi secara manual, maka penghapusan aplikasinya secara manual juga, dengan cara kurang lebih seperti ini :

    $ sudo rm -rf /opt/postman 
    $ sudo rm -rf /usr/local/bin/postman
    $ sudo rm /usr/share/applications/postman.desktop

Jika sudah silahkan di check kembali, apakah sudah terhapus untuk aplikasi postman tersebut ? seharusnya sudah terhapus.

Jika menggunakan path custom atau berbeda dengan apa yang sudah di infokan diatas, silahkan di sesuaikan sendiri ya.

## Kesimpulan

Instalasi maupun uninstalasi postman sangatlah mudah bukan. Sekarang teman-teman bisa menggunakan postman untuk melakukan ujicoba dari API yang sudah dibuat di perangkat linux teman-teman semua. Untuk tutorial lainnya bisa juga mengakses [disini ya][5]

 [1]: https://www.postman.com/downloads/ "berikut ini"
 [2]: https://go.postman.co/build "go.postman.co/build"
 [3]: https://snapcraft.io/ "snap"
 [4]: https://www.postman.com/downloads/ "Download Postman"
 [5]: https://tulisan.masdzub.com