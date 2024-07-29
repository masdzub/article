---
title: Meningkatkan Koneksi Internet Di linux Tanpa Software
author: Dzubayyan Ahmad
type: post
date: 2015-08-10T06:59:00+00:00
excerpt: '						'
url: /meningkatkan-koneksi-internet-di-linux-tanpa-software.aspx
tags:
  - linux
  - Tutorial

---
<div style="line-height: 100%; margin-bottom: 0in;" align="left">
  Setelah tanya sama eyang gugel ane nemu kaya gini nih, dan ane mau ngeshare cara ini ke bloggers semua, barangkali aja berguna, hehehe.. yukk cekidooot
</div>

<div style="line-height: 100%; margin-bottom: 0in;" align="left">
</div>

  1. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      Buka Terminal : (ctrl+alt+T) : menu > administration > terminal
    </div>

  2. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      backup dulu file sysctl.conf, caranya “sudo cp /etc/sysctl.conf /etc/sysctl.conf.backup” (tanpa petik), jadi kalo ada eror hasil backupannya di sysctl.conf.backup
    </div>

  3. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      edit file sysctl.conf : “sudo gedit /etc/sysctl.conf” (tanpa petik) untuk editornya bisa make nano, gedit, leafpad/dll
    </div>

  4. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      <p>
        tambahin kode ajaib ini di akhir file yang di edit tadi :<br /> <br /> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;
      </p>
      
      <div style="clear: both; text-align: center;">
      </div>
      
      <p>
        <span style="font-family: inherit, serif;"># increase TCP max buffer size setable using setsockopt()<br /> net.core.rmem_max = 16777216<br /> net.core.wmem_max = 16777216<br /> # increase linux autotuning TCP buffer limits<br /> # min, default, and max number of bytes to use<br /> # set max to at least 4MB, or higher if you use very high BDP paths<br /> net.ipv4.tcp_rmem = 4096 87380 16777216<br /> net.ipv4.tcp_wmem = 4096 65536 16777216<br /> # don&#8217;t cache ssthresh from previous connection<br /> net.ipv4.tcp_no_metrics_save = 1<br /> net.ipv4.tcp_moderate_rcvbuf = 1<br /> # recommended to increase this for 1000 BT or higher<br /> net.core.netdev_max_backlog = 2500<br /> # for 10 GigE, use this, uncomment below<br /> # net.core.netdev_max_backlog = 30000<br /> # Turn off timestamps if you&#8217;re on a gigabit or very busy network<br /> # Having it off is one less thing the IP stack needs to work on<br /> #net.ipv4.tcp_timestamps = 0<br /> # disable tcp selective acknowledgements.<br /> net.ipv4.tcp_sack = 0<br /> #enable window scaling<br /> net.ipv4.tcp_window_scaling = 1<br /> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;</span>
      </p>
      
      <div style="clear: both; text-align: center;">
        <a style="margin-left: 1em; margin-right: 1em;" href="https://3.bp.blogspot.com/-4BNaFba-zs0/Vcl_oX-rRFI/AAAAAAAAAz0/wIvXgvyiQT8/s1600/Screenshot%2Bfrom%2B2015-08-11%2B11%253A45%253A20.png"><img loading="lazy" decoding="async" src="https://3.bp.blogspot.com/-4BNaFba-zs0/Vcl_oX-rRFI/AAAAAAAAAz0/wIvXgvyiQT8/s320/Screenshot%2Bfrom%2B2015-08-11%2B11%253A45%253A20.png" alt="" alt="" width="320" height="258" border="0" /></a>
      </div>
    </div>

  5. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      <span style="font-family: inherit, serif;">simpan file (ctrl+s)</span>
    </div>

  6. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      <span style="font-family: inherit, serif;">masukin perintah “sudo sysctl -p” (tanpa petik)</span>
    </div>

  7. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      <span style="font-family: inherit, serif;">silahkan surfing di internet lagi,, rasakan bedanya.</span>
    </div>

  8. <div style="line-height: 100%; margin-bottom: 0in;" align="left">
      <span style="font-family: inherit, serif;">Kalo mau ngembaliin lagi, hapus aja file yang di tambahin</span>
    </div>