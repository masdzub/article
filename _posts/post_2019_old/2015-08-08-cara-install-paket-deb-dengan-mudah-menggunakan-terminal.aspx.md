---
title: Cara Install Paket .DEB Dengan Mudah Menggunakan Terminal
author: Dzubayyan Ahmad
type: post
date: 2015-08-08T02:00:00+00:00
excerpt: '						'
url: /cara-install-paket-deb-dengan-mudah-menggunakan-terminal.aspx
tags:
  - linux
  - Tutorial

---
&nbsp;

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  Seringkali ketika mencari software di internet, dan yang kita temui tuh yang ekstensi “.deb”, kali ini saya mau nge-share gimana caranya install paket .deb. Oke cekidoot..
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

  1. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Buka Terminal (ctrl+alt+T)
    </div>
    
    <div style="clear: both; text-align: center;">
      <a style="margin-left: 1em; margin-right: 1em;" href="https://3.bp.blogspot.com/-5MZsKtzqjls/VcVaEPWtHpI/AAAAAAAAAvw/qr3f4IoSuhU/s1600/Screenshot%2Bfrom%2B2015-08-07%2B20%253A09%253A52.png"><img loading="lazy" decoding="async" src="https://3.bp.blogspot.com/-5MZsKtzqjls/VcVaEPWtHpI/AAAAAAAAAvw/qr3f4IoSuhU/s320/Screenshot%2Bfrom%2B2015-08-07%2B20%253A09%253A52.png" alt="" alt="" width="320" height="181" border="0" /></a>
    </div>
    
    <div style="line-height: 100%; margin-bottom: 0in;" align="left">
    </div>

  2. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Kita pindah direktori, ke paket tersebut berada (punya saya Download)<br /> untuk lain direktori gunakan perintah : <span style="color: red;">cd<spasi><folder></span>
    </div>
    
    <div style="clear: both; text-align: center;">
      <a style="margin-left: 1em; margin-right: 1em;" href="https://3.bp.blogspot.com/-xGu_6r2tbBM/VcVaEOnx0JI/AAAAAAAAAvo/GEIQKO5T7UM/s1600/Screenshot%2Bfrom%2B2015-08-07%2B20%253A11%253A29.png"><img loading="lazy" decoding="async" src="https://3.bp.blogspot.com/-xGu_6r2tbBM/VcVaEOnx0JI/AAAAAAAAAvo/GEIQKO5T7UM/s320/Screenshot%2Bfrom%2B2015-08-07%2B20%253A11%253A29.png" alt="" alt="" width="320" height="181" border="0" /></a>
    </div>
    
    <div style="line-height: 100%; margin-bottom: 0in;" align="left">
    </div>

  3. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Kita cek, dengan menggukan perintah : “<span style="color: red;">ls</span>”<br /> 
    </div>

  4. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Pastikan yang paket yang ingin kita install berada dalam direktori
    </div>
    
    <div style="clear: both; text-align: center;">
    </div>
    
    <div style="clear: both; text-align: center;">
      <a style="margin-left: 1em; margin-right: 1em;" href="https://4.bp.blogspot.com/-FE_98e6EL2A/VcVaEDfikpI/AAAAAAAAAv4/N3HUFu1qczY/s1600/Screenshot%2Bfrom%2B2015-08-07%2B20%253A13%253A18.png"><img loading="lazy" decoding="async" src="https://4.bp.blogspot.com/-FE_98e6EL2A/VcVaEDfikpI/AAAAAAAAAv4/N3HUFu1qczY/s320/Screenshot%2Bfrom%2B2015-08-07%2B20%253A13%253A18.png" alt="" alt="" width="320" height="181" border="0" /></a>
    </div>
    
    <div style="line-height: 100%; margin-bottom: 0in;" align="left">
    </div>

  5. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Jika paket .deb sudah ada dalam direktori kita lanjutkan instalasi dengan perintah :<br /> $ <span style="color: red;">sudo dpkg -i <nama paket>.deb</span><br /> ===> jika dalam folder tersebut ada banyak paket .deb, dan ingin kita install semua<br /> $ <span style="color: red;">sudo dpkg -i *.deb</span><br /> ===> perintah di atas akan menginstall semua paket berekstensi .deb di dalam folder tersebut.
    </div>
    
    <div style="clear: both; text-align: center;">
      <a style="margin-left: 1em; margin-right: 1em;" href="https://4.bp.blogspot.com/-Dy3DzcKMYhg/VcVaE4lyiCI/AAAAAAAAAwA/XBgTLVAiVlg/s1600/Screenshot%2Bfrom%2B2015-08-07%2B20%253A23%253A52.png"><img loading="lazy" decoding="async" src="https://4.bp.blogspot.com/-Dy3DzcKMYhg/VcVaE4lyiCI/AAAAAAAAAwA/XBgTLVAiVlg/s320/Screenshot%2Bfrom%2B2015-08-07%2B20%253A23%253A52.png" alt="" alt="" width="320" height="181" border="0" /></a>
    </div>
    
    <div style="line-height: 100%; margin-bottom: 0in;" align="left">
    </div>

  6. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Masukkan password
    </div>

  7. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      jalankan aplikasi yang baru saja di install
    </div>
    
    <div style="clear: both; text-align: center;">
      <a style="margin-left: 1em; margin-right: 1em;" href="https://3.bp.blogspot.com/-9BeMuyPlLaE/VcVifXvC3GI/AAAAAAAAAwM/O_iG619yUQ8/s1600/Screenshot%2Bfrom%2B2015-08-08%2B08%253A59%253A00.png"><img loading="lazy" decoding="async" src="https://3.bp.blogspot.com/-9BeMuyPlLaE/VcVifXvC3GI/AAAAAAAAAwM/O_iG619yUQ8/s320/Screenshot%2Bfrom%2B2015-08-08%2B08%253A59%253A00.png" alt="" alt="" width="320" height="139" border="0" /></a>
    </div>
    
    <div style="line-height: 100%; margin-bottom: 0in;" align="left">
    </div>