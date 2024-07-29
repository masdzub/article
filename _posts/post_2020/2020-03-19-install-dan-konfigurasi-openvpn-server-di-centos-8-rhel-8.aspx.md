---
title: Install dan Konfigurasi OpenVPN Server di CentOS 8 / RHEL 8
author: Dzubayyan Ahmad
type: post
date: 2020-03-19T11:49:03+00:00
url: /install-dan-konfigurasi-openvpn-server-di-centos-8-rhel-8.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo teman-teman semua, di tutorial kali ini akan menjelaskan bagaimana cara install dan konfigurasi OpenVPN di CentOS 8 / RHEL 8. Sebuah VPN (Virtual Private Network) membuat melewati jaringan / network yang tidak di kenali atau tidak di percaya keamanannya seolah teman-teman berada di dalam jaringan yang LAN yang aman. OpenVPN adalah sebuah solusi VPN dengan SSL yang mempunyai licensi opensource dan mempunyai fitur lengkap yang mendukung berbagai konfigurasi.

Dengan OpenVPN, teman-teman dapat dengan mudah menggunakan jaringan yang aman meskipun sedang menggunakan koneksi public atau koneksi yang tidak di percaya keamanannya, semua aktifitas keluar masuk trafik atau lalu lintas data akan di enkripsi sehingga teman-teman akan memperpacayai informasi yang di terima dari sisi lainnya.

Nah di artikel ini kita akan mengulas cara install dan konfigurasi OpenVPN di CentOS 8 / RHEL 8

## [][1]Teknik Install OpenVPN Server di CentOS 8 / RHEL 8 {#Teknik-Install-OpenVPN-Server-di-CentOS-8--RHEL-8}

Untuk menginstall OpenVPN Server di Centos 8 / RHEL 8 terdapat 2 teknik.

<li class="">
  Install OpenVPN Server secara manual &#8211; akan memakan waktu yang
</li>
<li class="">
  Install OpenVPN Server dengan script otomatis &#8211; lebih mudah dan lebih cepat
</li>

Dan untuk di tulisan kali ini kita akan akan menggunakan script otomatis untuk menginstall dan mengkonfigurasi OpenVPN server. Dan kali ini kita akan menggunakan script&nbsp;<a href="https://github.com/masdzub/openvpn-install" target="_blank" rel="noreferrer noopener">openvpn-install</a>, script tersebut akan menginstall dan mengkonfigurasi VPN di server teman-teman sendiri dalam beberapa menit. script ini juga di design lebih mudah bagi teman-teman yang belum pernah menginstall OpenVPN sebelumnya.

## [][2]Install dan Konfigurasi OpenVPN Server di CentOS 8 / RHEL 8 {#Install-dan-Konfigurasi-OpenVPN-Server-di-CentOS-8--RHEL-81}

### [][3]1. Menambahkan repository EPEL dan Install git {#1-Menambahkan-repository-EPEL-dan-Install-git}

Untuk langkah pertama adalah menambahkan repository EPEL di CentOS 8 / RHEL 8 ke dalam system, ini diperlukan untuk menginstall OpenVPN dan paket depensi yang di perlukan.  
Untuk menginstallnya bisa menggunaka link di bawah ini.  
<a href="https://tulisan.masdzub.com/install-dan-mengaktifkan-epel-repository-di-centos-8.aspx" target="_blank" rel="noreferrer noopener">Install dan Mengaktifkan EPEL Repository di CentOS 8</a>

Selain itu teman-teman memerlukan git untuk mengambil kode script dari github. Dan pastikan terinstall di system.  
Untuk menginstallnya bisa menggunakan cara di bawah ini.

<pre class="dz-block-code"><code># yum install git
</code></pre>

### [][4]2. Mengkloning script openvpn-install dari github {#2-Mengkloning-script-openvpn-install-dari-github}

Dan langkah selanjutnya adalah mengkloning / mengambil script&nbsp;`openvpn-install`&nbsp;dari github menggunakan git.

<pre class="dz-block-code"><code># cd ~ 
# git clone https://github.com/masdzub/openvpn-install.git
remote: Enumerating objects: 395, done.
remote: Total 395 (delta 0), reused 0 (delta 0), pack-reused 395
Receiving objects: 100% (395/395), 120.87 KiB | 270.00 KiB/s, done.
Resolving deltas: 100% (197/197), done.
</code></pre>

### [][5]3. Menjalankan script OpenVPN-install {#3-Menjalankan-script-OpenVPN-install}

Selanjutnya masuk ke directory&nbsp;`openvpn-install`&nbsp;dan menjalankan script installernya, kurang lebih seperti ini

<pre class="dz-block-code"><code># cd openvpn-install
# chmod +x openvpn-install.sh
# ./openvpn-install.sh
</code></pre>

Dan teman-teman akan mendapatkan tampilan seperti ini.  
Dan silahkan di ikuti untuk perintahnya.

<pre class="dz-block-code"><code>Welcome to this OpenVPN road warrior installer!

I need to ask you a few questions before starting setup.
You can use the default options and just press enter if you are ok with them.

What IPv4 address should the OpenVPN server bind to?
     1) 178.128.18.212
     2) 10.15.0.5
     3) 10.130.158.23
IPv4 address [1]: 1

Which protocol do you want for OpenVPN connections?
   1) UDP (recommended)
   2) TCP
Protocol [1]: 1

What port do you want OpenVPN listening to?
Port [1194]:

Which DNS do you want to use with the VPN?
   1) Current system resolvers
   2) 1.1.1.1
   3) Google
   4) OpenDNS
   5) Verisign
DNS [1]: 1

Finally, tell me a name for the client certificate.
Client name [client]: namauser

Okay, that was all I needed. We are ready to set up your OpenVPN server now.
Press any key to continue...
</code></pre>

Untuk konfig di atas itu teman-teman mensetting :

<li class="">
  IP Address Server di gunakan untuk VPN
</li>
<li class="">
  Protokol OpenVPN yang digunakan &#8211; TCP atau UDP
</li>
<li class="">
  Port OpenVPN
</li>
<li class="">
  DNS NameServer yang digunakan untuk VPN
</li>
<li class="">
  Membuat profile konfigurasi untuk client
</li>

File Konfigurasi utama OpenVPN berada di&nbsp;`/etc/openvpn/server/server.conf`&nbsp;dan teman-teman dapat merubah konfigirasi yang ada.  
Untuk isi dari file tersebut kuranglebih seperti berikut ini

<pre class="dz-block-code"><code># cat /etc/openvpn/server/server.conf
local 178.128.18.212
port 1194
proto udp
dev tun
ca ca.crt
cert server.crt
key server.key
dh dh.pem
auth SHA512
tls-crypt tc.key
topology subnet
server 10.8.0.0 255.255.255.0
ifconfig-pool-persist ipp.txt
push "redirect-gateway def1 bypass-dhcp"
push "dhcp-option DNS 67.207.67.2"
push "dhcp-option DNS 67.207.67.3"
keepalive 10 120
cipher AES-256-CBC
user nobody
group nobody
persist-key
persist-tun
status openvpn-status.log
verb 3
crl-verify crl.pem
explicit-exit-notify
</code></pre>

Dan setelah instalasi akan muncul virtual interface yang di buat setelah proses. Dan virtual interface ini di gunakan untuk subnet client OpenVPN. Untuk virtual interfacenya bernama&nbsp;`tun0`, untuk melakukan pengecheckan bisa mengikuti cara ini :

<pre class="dz-block-code"><code># ip addr | grep tun0
4: tun0: &lt;POINTOPOINT,MULTICAST,NOARP,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UNKNOWN group default qlen 100
    inet 10.8.0.1/24 brd 10.8.0.255 scope global tun0
</code></pre>

Untuk interface defaultnya menggunakan subnet 10.8.0.0/24, dan OpenVPN server akan menggunakan IP 10.8.0.1.

### [][6]4. Membuat User profile OpenVPN (.ovpn file) {#4-Membuat-User-profile-OpenVPN-ovpn-file}

Setelah itu akan akan memproses instalasi. Dan akan men-generate profil konfigurasi untuk openvpn nya.  
Dan untuk lokasi filenya profil konfigurasinya ada di&nbsp;`~/namauser.ovpn`

Namun jika ingin menambah user profile OpenVPN teman-teman bisa menjalankan command seperti waktu instalasi. Dan kemudian pilih Add a new user. Kurang lebih seperti berikut ini.

<pre class="dz-block-code"><code># ./openvpn-install.sh
Looks like OpenVPN is already installed.

What do you want to do?
   1) Add a new user
   2) Revoke an existing user
   3) Remove OpenVPN
   4) Exit
Select an option: 1

Tell me a name for the client certificate.
Client name: juuub

Using SSL: openssl OpenSSL 1.1.1c FIPS  28 May 2019
Generating a RSA private key
...................................+++++
.....................................................................+++++
writing new private key to '/etc/openvpn/server/easy-rsa/pki/private/juuub.key.m5xOJr8td6'
-----
Using configuration from ./safessl-easyrsa.cnf
Check that the request matches the signature
Signature ok
The Subject's Distinguished Name is as follows
commonName            :ASN.1 12:'juuub'
Certificate is to be certified until Mar  4 16:13:25 2030 GMT (3650 days)

Write out database with 1 new entries
Data Base Updated

Client juuub added, configuration is available at: /root/juuub.ovpn
</code></pre>

Setelah menambahkan user bisa di cek di directory /root.

<pre class="dz-block-code"><code># ls /root/ | grep .ovpn
juuub.ovpn
masdzub.ovpn
</code></pre>

Jika sudah, File&nbsp;`.ovpn`&nbsp;tersebut bisa di download dan di gunakan untuk konfigurasi vpn di laptop

 [1]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#Teknik-Install-OpenVPN-Server-di-CentOS-8--RHEL-8
 [2]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#Install-dan-Konfigurasi-OpenVPN-Server-di-CentOS-8--RHEL-81
 [3]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#1-Menambahkan-repository-EPEL-dan-Install-git
 [4]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#2-Mengkloning-script-openvpn-install-dari-github
 [5]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#3-Menjalankan-script-OpenVPN-install
 [6]: https://hackmd.io/13rfnHY9RC6GqLK7Zn_1Ww?view#4-Membuat-User-profile-OpenVPN-ovpn-file