---
title: Cara menambah Repository PPA di linux Mint Debian Edition
author: Dzubayyan Ahmad
type: post
date: 2015-08-14T07:07:00+00:00
excerpt: '						'
url: /cara-menambah-repository-ppa-di-linux-mint-debian-edition.aspx

tags:
  - linux
  - Tutorial

---
Yang kemaren hal hal yang dikukan setelah install LMDE, karna LMDE itu basenya debian, jadi masih ada yang kurang fiturnya, salah satunya penambahan PPA, kali ini saya mau share cara menambah repository PPA tersebut, oke langsung aja ke ke lapangan

  1. Buka Terminal
  2. masukkan perintah di bawah ini : <tanpa tanda petik>  
    $ <span style="color: red;">wget https://mega.co.nz/#!epJCFQIK!qIJA2HeMDn2lVyywx6_aaq8DKSf2WXFy9qTJjciPkPw</span>
  3.  jika sudah di download maka copy-kan file tersebut dengan perintah :  
    $ <span style="color: red;">sudo cp add-apt-repository.sh.txt /usr/sbin/add-apt-repository</span>
  4. ubah permisission pada file /usr/sbin/add-repository dengan perintah :  
    $ <span style="color: red;">sudo chmod o+x /usr/sbin/add-apt-repository</span>
  5. <span style="color: red;"> </span>ubah lagi menjadi permission root dengan perintah :  
    $ <span style="font-family: Arial, Helvetica, sans-serif;"><span style="color: red;">sudo chown root:root /usr/sbin/add-repositor</span></span>

<span style="font-family: Arial, Helvetica, sans-serif;"><span style="color: red;"><span style="color: black;">cukup itu yang dapat saya share dulu, selamat mencoba semoga sukses</span> </span></span>