---
title: Perintah linux yang Sering Digunakan oleh Sysadmin – Part 1
author: Dzubayyan Ahmad
type: post
date: 2020-08-18T14:50:44+00:00
url: /perintah-linux-yang-sering-digunakan-oleh-sysadmin-part-1.aspx
classic-editor-remember:
  - block-editor
tags:
  - All
  - linux
  - Tutorial

---
Terkadang beberapa orang selalu mengatakan bahwa linux adalah sebuah system operasi yang susah. Namun bagi sebagian orang sangatlah mudah dan malah menantang. Selain itu linux juga seringkali diartikan hanya untuk orang yang sudah ahli atau expert dibidang tersebut. Namun pernyataan tersebut salah, karena linux dapat digunakan oleh siapapun, baik user biasa maupun seorang sysadmin. Dalam artikel ini akan saya bahas mengenai perintah linux yang biasa di gunakan oleh keduanya, baik dari seorang user biasa maupun seorang administrator atau sysadmin.

Perintah linux yang dimaksudkan disini adalah sebuah perintah linux yang berbasis CLI(Command Line Interface) yang biasa digunakan untuk memudahkan navigasi, mengoperasikan maupun mencari sebuah system linux yang ada didalamnya. Perintah linux yang membantu sekali dalam banyak hal, apalagi digunakan untuk melakukan troubleshooting, Dan berikut ini adalah beberapa perintah linux yang sering saya sendiri pakai di terminal :

**1. Mengecheck IP local pada linux**

Untuk melakukan pengecekan IP, Mac address dan lain sebagainya terdapat beberapa cara, yaitu bisa menggunakan perintah&nbsp;`ip`&nbsp;atau&nbsp;`ifconfig`  
Untuk beberapa distro tidak mengikutkan perintah&nbsp;`ifconfig`&nbsp;namun biasanya dengan menyertakan command&nbsp;`IP`&nbsp;secara bawaan. Untuk contoh dari penggunaan perintah&nbsp;`IP`&nbsp;sebagai berikut :

<pre class="dz-block-code"><code># ip a
</code></pre>

Dan akan menghasilkan kuranglebih seperti berikut ini :

<pre class="dz-block-code"><code>1: lo: &lt;LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: wlp1s0: &lt;BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 80:c5:f2:5c:a1:2b brd ff:ff:ff:ff:ff:ff
    inet 10.203.221.186/18 brd 10.203.255.255 scope global dynamic noprefixroute wlp1s0
       valid_lft 133sec preferred_lft 133sec
    inet6 fe80::fcb0:5450:960d:8aea/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
</code></pre>

Dan untuk contoh penggunaan dari&nbsp;`ifconfig`&nbsp;sebagai berikut :

<pre class="dz-block-code"><code># ifconfig 
lo: flags=73&lt;UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10&lt;host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 228  bytes 19578 (19.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 228  bytes 19578 (19.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

wlp1s0: flags=4163&lt;UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.203.221.186  netmask 255.255.192.0  broadcast 10.203.255.255
        inet6 fe80::fcb0:5450:960d:8aea  prefixlen 64  scopeid 0x20&lt;link>
        ether 80:c5:f2:5c:a1:2b  txqueuelen 1000  (Ethernet)
        RX packets 616930  bytes 745120749 (710.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 255825  bytes 166130844 (158.4 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
</code></pre>

**2. Melihat daftar file dengan&nbsp;`ls`**

Dalam menggunakan CLI tidak akan muncul sebuah thumbail pada terminal, sehingga terkadang kesulitan untuk melakukan sebuah pencarian file maupun sebuah folder, dengan menggunakan perintah&nbsp;`ls`&nbsp;maka dengan ini akan membuat sebuah list file maupun folder yang ada pada directory tersebut. Untuk cara penggunaan seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ ls
 aaa                      Desktop/     Music/      Templates/
 ansibl                   Documents/   Pictures/   Videos/
'ansible rapidplex'/      Downloads/   Postman/    xiaomi.eu_multi_HMNote8_20.8.13_v12-10.zip
'ansible rapidplex.zip'   __MACOSX/    Public/
</code></pre>

Dan untuk menampilkan file maupun folder yang tersembunyi dapat menambahkan option&nbsp;`-a`, dan seperti ini contohnya :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ ls -a
 ./                       .bashrc       .gnupg/           Postman/
 ../                      .cache/       .gtkrc-2.0        Public/
 aaa                      .config/      .gtkrc-2.0-kde4   .ssh/
 ansibl                   Desktop/      .icons/           Templates/
 .ansible/                .digrc        .kde/             .thunderbird/
 .ansible.cfg             Documents/    .local/           Videos/
'ansible rapidplex'/      Downloads/    __MACOSX/         .viminfo
'ansible rapidplex.zip'   .esd_auth     .mozilla/         .wget-hsts
 .bash_history            .face         Music/            .Xauthority
 .bash_logout             .face.icon@   Pictures/         xiaomi.eu_multi_HMNote8_20.8.13_v12-10.zip
 .bash_profile            .gitconfig    .pki/             .xsession-errors
</code></pre>

Dan untuk menampilakn file secara baris dan lebih detail dapat menambahkan option&nbsp;`-l`, dan seperti berikut unntuk contohnya :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ ls -l
total 2179768
-rw-r--r--. 1 masdzub masdzub         73 Aug 18 11:39  aaa
-rw-r--r--. 1 masdzub masdzub      19424 Jul 30 01:05  ansibl
drwxr-xr-x. 3 masdzub masdzub       4096 Aug  9 20:41 'ansible rapidplex'/
-rw-r--r--. 1 masdzub masdzub       1831 Jul 30 00:12 'ansible rapidplex.zip'
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Desktop/
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Documents/
drwxr-xr-x. 3 masdzub masdzub       4096 Aug 16 15:57  Downloads/
drwxrwxr-x. 3 masdzub masdzub       4096 Jul 30 00:12  __MACOSX/
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Music/
drwxr-xr-x. 2 masdzub masdzub       4096 Aug 18 09:35  Pictures/
drwxr-xr-x. 4 masdzub masdzub       4096 Aug  9 20:09  Postman/
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Public/
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Templates/
drwxr-xr-x. 2 masdzub masdzub       4096 Jul 28 05:45  Videos/
</code></pre>

Teman-teman sebuah bisa mengkombinasikan antara kedua option tersebut menjadi option&nbsp;`-la`. Untuk hasilnya seperti campuran dari keduanya.

**3. Melihat penggunaan Disk dengan&nbsp;`df`**

Untuk mengecheck disk pada linux dengan CLI salah satunya yang populer dan sering digunakan oleh orang dengan menggunakan&nbsp;`df`. Dan untuk perinnya contohnya seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        3.6G     0  3.6G   0% /dev
tmpfs           3.7G  135M  3.5G   4% /dev/shm
tmpfs           3.7G  1.6M  3.7G   1% /run
/dev/sda8        39G  7.5G   29G  21% /
tmpfs           3.7G  156K  3.7G   1% /tmp
/dev/sda7       500M   21M  480M   5% /boot/efi
/dev/sdb1       396G  7.9G  368G   3% /home
tmpfs           740M   44K  740M   1% /run/user/1000
</code></pre>

Dan jika ingin melakukan pengecekan pada spesifik mountpoint semisal&nbsp;`/`&nbsp;dapat menjalankan seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        3.6G     0  3.6G   0% /dev
tmpfs           3.7G  135M  3.5G   4% /dev/shm
tmpfs           3.7G  1.6M  3.7G   1% /run
/dev/sda8        39G  7.5G   29G  21% /
tmpfs           3.7G  156K  3.7G   1% /tmp
/dev/sda7       500M   21M  480M   5% /boot/efi
/dev/sdb1       396G  7.9G  368G   3% /home
tmpfs           740M   44K  740M   1% /run/user/1000
</code></pre>

Dan jika ingin melakukan pengecekan inodes bisa menjalankan seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ df -hi
Filesystem     Inodes IUsed IFree IUse% Mounted on
devtmpfs         920K   605  919K    1% /dev
tmpfs            925K   898  925K    1% /dev/shm
tmpfs            925K  1.1K  924K    1% /run
/dev/sda8        2.5M  210K  2.3M    9% /
tmpfs            925K    50  925K    1% /tmp
/dev/sda7           0     0     0     - /boot/efi
/dev/sdb1         26M  145K   26M    1% /home
tmpfs            925K    51  925K    1% /run/user/1000
</code></pre>

**4. Melihat penggunaan RAM**

Untuk melakukan pengecekan penggunaan ram pada linux bisa menggunakan perintah&nbsp;`free`&nbsp;pada linux dengan menggunakan beberapa option.  
Untuk hal yang seringkali dipakai adalah&nbsp;`free -m`, Untuk contoh penggunaan seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ free -m
              total        used        free      shared  buff/cache   available
Mem:           7399        2366        2385         167        2647        4585
Swap:          8191           0        8191
</code></pre>

Dan jika ingin menampilkan yang mudah dibaca dengan menambahkan option&nbsp;`-h`. dan akan menjadi kurang lebih seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ free -mh
              total        used        free      shared  buff/cache   available
Mem:          7.2Gi       2.2Gi       2.5Gi       167Mi       2.6Gi       4.6Gi
Swap:         8.0Gi          0B       8.0Gi
</code></pre>

**5. Menampilkan prosess dengan akar berakar seperti&nbsp;`tree`**

Untuk menampilkan processnya bisa menggunakan&nbsp;`pstree`&nbsp;dan jika ingin menambahkan PID pada process bisa menambahkan&nbsp;`-p`&nbsp;untuk optionnya. Untuk contohnya seperti berikut ini :

<pre class="dz-block-code"><code>❰masdzub❙~❱&#x2714;≻ pstree
systemd─┬─ModemManager───3*&#91;{ModemManager}]
        ├─NetworkManager───2*&#91;{NetworkManager}]
        ├─abrt-applet───3*&#91;{abrt-applet}]
        ├─abrt-dbus───2*&#91;{abrt-dbus}]
        ├─3*&#91;abrt-dump-journ]
        ├─abrtd───2*&#91;{abrtd}]
        ├─accounts-daemon───3*&#91;{accounts-daemon}]
        ├─agent───2*&#91;{agent}]
...
    ├─systemd-homed
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-udevd
        ├─systemd-userdbd───3*&#91;systemd-userwor]
        ├─udisksd───4*&#91;{udisksd}]
        ├─upowerd───2*&#91;{upowerd}]
        ├─wpa_supplicant
        └─xembedsniproxy───2*&#91;{xembedsniproxy}]
</code></pre>

Dan jika ingin menampilkan PID nya bisa juga menggunakan option&nbsp;`-p`, dan kurang lebih seperti ini :

<pre class="dz-block-code"><code>masdzub❙~❱&#x2714;≻ pstree -p
systemd(1)─┬─ModemManager(608)─┬─{ModemManager}(624)
           │                   ├─{ModemManager}(629)
           │                   └─{ModemManager}(667)
           ├─NetworkManager(721)─┬─{NetworkManager}(730)
           │                     ├─{NetworkManager}(732)
           │                     └─{NetworkManager}(24160)
           ├─abrt-applet(1114)─┬─{abrt-applet}(1148)
           │                   ├─{abrt-applet}(1149)
           │                   └─{abrt-applet}(1207)
           ├─abrt-dbus(1178)─┬─{abrt-dbus}(1193)
           │                 └─{abrt-dbus}(1196)
           ├─abrt-dump-journ(678)
...
          │             └─{pcscd}(2916)
           ├─plasmashell(1088)─┬─chrome(2784)─┬─cat(2790)
           │                   │              ├─cat(2791)
           │                   │              ├─chrome(2794)─┬─chrome(2818)─┬─{chrome}(2833)
           │                   │              │              │              ├─{chrome}(2834)
           │                   │              │              │              ├─{chrome}(2835)
           │                   │              │              │              ├─{chrome}(2836)
           │                   │              │              │              ├─{chrome}(2837)
           │                   │              │              │              ├─{chrome}(2838)
           │                   │              │              │              ├─{chrome}(2839)
           │                   │              │              │              ├─{chrome}(2842)
           │                   │              │              │              ├─{chrome}(2843)
           │                   │              │              │              ├─{chrome}(2844)
           │                   │              │              │              ├─{chrome}(2845)
...
           ├─udisksd(633)─┬─{udisksd}(640)
           │              ├─{udisksd}(670)
           │              ├─{udisksd}(694)
           │              └─{udisksd}(709)
           ├─upowerd(634)─┬─{upowerd}(666)
           │              └─{upowerd}(675)
           ├─wpa_supplicant(771)
           └─xembedsniproxy(1090)─┬─{xembedsniproxy}(1103)
                                  └─{xembedsniproxy}(1116)
</code></pre>

## [][1]Kesimpulan {#Kesimpulan}

Untuk perintah linux yang biasa digunakan oleh sysadmin part 1 sudah selesai, dan sangat mudah kan untuk menggunakannya ? Sehingga dari pengguna baru pun juga tidak mengalami kesulitan selama mengetahui dari fungsinya. Dan sampai jumpa di artikel yang lain.

 [1]: https://hackmd.io/SKoMEQeiRTaZx9capY1OFw?view#Kesimpulan