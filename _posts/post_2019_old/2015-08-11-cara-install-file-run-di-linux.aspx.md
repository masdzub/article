---
title: Cara Install file .Run di linux
author: Dzubayyan Ahmad
type: post
date: 2015-08-11T05:23:00+00:00

tags:
  - linux
  - Tutorial

---
<div align="left" style="line-height: 100%; margin-bottom: 0in;">
  Kemaren udah share cara install file .Deb dan file .Bin, sekarang gantian cara install file .run, sepertinya banyak juga yang mencari solusi agar file .run dapat di install di linux, langsung aja kita berangkat ke TKP, cekidot
</div>

<div align="left" style="line-height: 100%; margin-bottom: 0in;">
</div>

  1. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      Buka terminal (ctrl+alt+T)
    </div>
    
    <div style="clear: both; text-align: center;">
      <a href="https://1.bp.blogspot.com/-mqkmfhvo_eY/VcmFuNwTp8I/AAAAAAAAA0E/OzuZ5JDsTps/s1600/Screenshot%2Bfrom%2B2015-08-11%2B12%253A18%253A36.png" style="margin-left: 1em; margin-right: 1em;"><img loading="lazy" decoding="async" border="0" height="181" src="https://1.bp.blogspot.com/-mqkmfhvo_eY/VcmFuNwTp8I/AAAAAAAAA0E/OzuZ5JDsTps/s320/Screenshot%2Bfrom%2B2015-08-11%2B12%253A18%253A36.png" alt="" alt="" width="320" /></a>
    </div>
    
    
    
    <div align="left" style="line-height: 100%; margin-bottom: 0in;">
    </div>

  2. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      lalu kita pindah ke direktori yang ada file runnya
    </div>
    
    <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      dengan perintah :&nbsp; &#8220;cd <folder> &#8220;
    </div>
    
    <div style="clear: both; text-align: center;">
      <a href="https://3.bp.blogspot.com/-jDjb1GFKfaw/VcmGAJfinnI/AAAAAAAAA0M/WIukmF30Au0/s1600/Screenshot%2Bfrom%2B2015-08-11%2B12%253A19%253A52.png" style="margin-left: 1em; margin-right: 1em;"><img loading="lazy" decoding="async" border="0" height="181" src="https://3.bp.blogspot.com/-jDjb1GFKfaw/VcmGAJfinnI/AAAAAAAAA0M/WIukmF30Au0/s320/Screenshot%2Bfrom%2B2015-08-11%2B12%253A19%253A52.png" alt="" alt="" width="320" /></a>
    </div>
    
    <div align="left" style="line-height: 100%; margin-bottom: 0in;">
    </div>

  3. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      lalu kita cek, apakah filenya ada di direktori tersebut dengan perintah : “ls”<br />
    </div>
    
    <div style="clear: both; text-align: center;">
      <a href="https://1.bp.blogspot.com/-m3SjPuGmLXc/VcmGKaGQGNI/AAAAAAAAA0U/RQYKpgllO5o/s1600/Screenshot%2Bfrom%2B2015-08-11%2B12%253A20%253A30.png" style="margin-left: 1em; margin-right: 1em;"><img loading="lazy" decoding="async" border="0" height="181" src="https://1.bp.blogspot.com/-m3SjPuGmLXc/VcmGKaGQGNI/AAAAAAAAA0U/RQYKpgllO5o/s320/Screenshot%2Bfrom%2B2015-08-11%2B12%253A20%253A30.png" alt="" alt="" width="320" /></a>
    </div>

  4. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      lalu kita ketikkan perintah : “sudo chmod +x namafile.run” (tanpa tanda petik) untuk namafile.run di ganti dengan file yang akan di install
    </div>
    
    <div style="clear: both; text-align: center;">
      <a href="https://4.bp.blogspot.com/-KVu4eEWZtog/VcmGXPHf6lI/AAAAAAAAA0c/81HOy4kDwJc/s1600/Screenshot%2Bfrom%2B2015-08-11%2B12%253A21%253A16.png" style="margin-left: 1em; margin-right: 1em;"><img loading="lazy" decoding="async" border="0" height="181" src="https://4.bp.blogspot.com/-KVu4eEWZtog/VcmGXPHf6lI/AAAAAAAAA0c/81HOy4kDwJc/s320/Screenshot%2Bfrom%2B2015-08-11%2B12%253A21%253A16.png" alt="" alt="" width="320" /></a>
    </div>

  5. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      lalu kita masukkan perintah “sudo ./namafile.run” (tanpa tanda petik) namafile di ganti dengan file yang akan di install
    </div>
    
    <div align="left" style="line-height: 100%; margin-bottom: 0in;">
    </div>
    
    <div style="clear: both; text-align: center;">
      <a href="https://4.bp.blogspot.com/-Vq8W5FOFM8c/VcmGo9cKk1I/AAAAAAAAA0k/pdjNF7qafUI/s1600/Screenshot%2Bfrom%2B2015-08-11%2B12%253A22%253A31.png" style="margin-left: 1em; margin-right: 1em;"><img loading="lazy" decoding="async" border="0" height="181" src="https://4.bp.blogspot.com/-Vq8W5FOFM8c/VcmGo9cKk1I/AAAAAAAAA0k/pdjNF7qafUI/s320/Screenshot%2Bfrom%2B2015-08-11%2B12%253A22%253A31.png" alt="" alt="" width="320" /></a>
    </div>

  6. <div align="left" style="line-height: 100%; margin-bottom: 0in;">
      ketika di mintai keterangan instalasi ketikkan Y, dan masukkan password&nbsp;
    </div>