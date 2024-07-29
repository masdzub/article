---
title: Cara Install Docker di Fedora 32
author: Dzubayyan Ahmad
type: post
date: 2020-08-29T05:40:10+00:00
url: /cara-install-docker-di-fedora-32.aspx
tags:
  - All
  - linux
  - Tutorial

---
<h1 id="Cara-Install-Docker-di-Fedora-32" class="part" data-startline="1" data-endline="1" data-id="Cara-Install-Docker-di-Fedora-32">
  <span data-position="2" data-size="32">Cara Install Docker di Fedora 32</span>
</h1>

<p class="part" data-startline="3" data-endline="3" data-position="36" data-size="0">
  <span data-position="36" data-size="179">Halo teman-teman semua, nah di artikel kali ini kita akan membahas mengenai sebuah cara untuk melakukan instalasi Docker di Fedora. Untuk yang saat ini digunakan adalah Fedora 32.</span>
</p>

<p class="part" data-startline="5" data-endline="5" data-position="218" data-size="0">
  <span data-position="218" data-size="430">Untuk docker sendiri sebuah aplikasi yang bersifat open source yang berfungsi sebagai wadah/container untuk mengepak/memasukkan sebuah software secara lengkap beserta semua hal lainnya yang dibutuhkan oleh software tersebut dapat berfungsi. Pengaturan software beserta file/hal pendukung lainnya akan menjadi sebuah Image (istilah yang diberikan oleh docker). Kemudian sebuah instan dari Image tersebut kemudian disebut Container.</span>
</p>

<p class="part" data-startline="7" data-endline="7" data-position="650" data-size="0">
  <span data-position="650" data-size="154">Untuk docker yang akan kita install ini adalah yang versi stablenya. Jadi untuk package yang di download dan repository yang digunakan adalah yang stable.</span>
</p>

<p class="part" data-startline="9" data-endline="9" data-position="806" data-size="0">
  <span data-position="806" data-size="87">Nah untuk melakukan instalasi dari Docker itu sendiri bisa mengikuti cara dibawah ini :</span>
</p>

<h2 id="Melakukan-Penghapusan-versi-lama-Docker-yang-sebelumnya-jika-ada" class="part" data-startline="11" data-endline="11" data-id="Melakukan-Penghapusan-versi-lama-Docker-yang-sebelumnya-jika-ada">
  <span data-position="899" data-size="66">Melakukan Penghapusan versi lama Docker yang sebelumnya [jika ada]</span>
</h2>

<p class="part" data-startline="12" data-endline="13" data-position="966" data-size="0">
  <span data-position="966" data-size="67">Untuk versi yang sebelumnya biasa biasanya ada package dengan nama </span><code data-position="1034" data-size="6">docker</code><span data-position="1041" data-size="6"> atau </span><code data-position="1048" data-size="13">docker-engine</code><span data-position="1062" data-size="104">. Jika dari kedia package tersebut ada, kedua package tersebut wajib unutk di uninstall terlebih dahulu.</span><br /> <span data-position="1167" data-size="65">Untuk melakukan uninstall nya bisa menggunakan cara berikut ini :</span>
</p>

<pre class="part" data-startline="14" data-endline="25" data-position="1234"><code>$ sudo dnf remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-selinux \
                  docker-engine-selinux \
                  docker-engine
</code></pre>

<p class="part" data-startline="26" data-endline="26" data-position="1602" data-size="0">
  <span data-position="1602" data-size="76">Jika terdapat sepeti di bawah ini, maka package belum terinstall sebelumnya.</span>
</p>

<pre class="part" data-startline="27" data-endline="42" data-position="1680"><code>No match for argument: docker
No match for argument: docker-client
No match for argument: docker-client-latest
No match for argument: docker-common
No match for argument: docker-latest
No match for argument: docker-latest-logrotate
No match for argument: docker-logrotate
No match for argument: docker-selinux
No match for argument: docker-engine-selinux
No match for argument: docker-engine
No packages marked for removal.
Dependencies resolved.
Nothing to do.
Complete!
</code></pre>

<p class="part" data-startline="44" data-endline="44" data-position="2161" data-size="0">
  <span data-position="2161" data-size="89">Namun jika sebelumnya sudah ada. Maka perlu melakukan penghapusan juga file-file juga di </span><code data-position="2251" data-size="16">/var/lib/docker/</code><span data-position="2268" data-size="39">. Untuk isi dari seluruh file di dalam </span><code data-position="2308" data-size="16">/var/lib/docker/</code><span data-position="2325" data-size="26"> bisa di hapus tanpa sisa.</span>
</p>

<h2 id="Metode-Instalasi" class="part" data-startline="46" data-endline="46" data-id="Metode-Instalasi">
  <span data-position="2357" data-size="16">Metode Instalasi</span>
</h2>

<p class="part" data-startline="47" data-endline="47" data-position="2374" data-size="0">
  <span data-position="2374" data-size="124">Untuk metode atau cara instalasi docker sendiri bisa menggunakan 3 cara. Dan cara itu itu kurang lebih seperti berikut ini :</span>
</p>

<ol class="part" data-startline="48" data-endline="51" data-position="2500" data-size="0">
  <li class="" data-startline="48" data-endline="48" data-position="2503" data-size="0">
    <span data-position="2503" data-size="263">Untuk cara yang pertama dan sering digunakan oleh banyak orang adalah menggunakan repository dari Docker itu sendiri, sehingga untuk instalasinya akan selalu update, Selain itu cara ini juga lebih mudah untuk melakukan instalasi dan upgrade dari package tersebut.</span>
  </li>
  <li class="" data-startline="49" data-endline="49" data-position="2770" data-size="0">
    <span data-position="2770" data-size="74">Untuk cara kedua menggunakan fila package instalasi yang di download dari </span><a href="https://download.docker.com/linux/fedora/" target="_blank" rel="noopener noreferrer"><span data-position="2844" data-size="41">https://download.docker.com/linux/fedora/</span></a><span data-position="2885" data-size="1">.</span>
  </li>
  <li class="" data-startline="50" data-endline="51" data-position="2890" data-size="0">
    <span data-position="2890" data-size="101">Untuk cara ketiga menggunakan script automasi install yang sudah disediakan untuk menginstall Docker.</span>
  </li>
</ol>

<p class="part" data-startline="52" data-endline="52" data-position="2993" data-size="0">
  <span data-position="2993" data-size="138">Dan ketiga cara tersebut akan kita bahas disini adalah yang menggunakan yang metode yang pertama. Dan bisa di ikuti panduan di bawah ini :</span>
</p>

<h3 id="Instalasi-Docker-menggunakan-repository" class="part" data-startline="54" data-endline="54" data-id="Instalasi-Docker-menggunakan-repository">
  <span data-position="3138" data-size="39">Instalasi Docker menggunakan repository</span>
</h3>

<ol class="part" data-startline="55" data-endline="56" data-position="3178" data-size="0">
  <li class="" data-startline="55" data-endline="56" data-position="3181" data-size="0">
    <span data-position="3181" data-size="55">Tahap pertama yang dilakukan untuk melakukan instalasi </span><code data-position="3237" data-size="6">docker</code><span data-position="3244" data-size="158"> menggunakna repository adalah menambahkan repository docker ke dalam server / pc fedora kita terlebih dahulu. Untuk menambahkan nya dengan cara berikut ini :</span>
  </li>
</ol>

<pre class="part" data-startline="57" data-endline="68" data-position="3405"><code>$ sudo dnf install dnf-plugin-core -y

$ sudo tee /etc/yum.repos.d/docker-ce.repo&lt;&lt;EOF
[docker-ce-stable]
name=Docker CE Stable - \$basearch
baseurl=https://download.docker.com/linux/fedora/31/\$basearch/stable
enabled=1
gpgcheck=1
gpgkey=https://download.docker.com/linux/fedora/gpg
EOF
</code></pre>

<ol class="part" start="2" data-startline="70" data-endline="71" data-position="3702" data-size="0">
  <li class="" data-startline="70" data-endline="71" data-position="3705" data-size="0">
    <span data-position="3705" data-size="153">Tahap selanjutnya adalah menginstall package dari docker engine, dan containerd, untuk cara melakukan instalasinya kurang lebih dengan cara seperti ini :</span>
  </li>
</ol>

<pre class="part" data-startline="72" data-endline="76" data-position="3861"><code>$ sudo dnf makecache

$ sudo dnf install docker-ce docker-ce-cli containerd.io
</code></pre>

<ol class="part" start="3" data-startline="78" data-endline="79" data-position="3949" data-size="0">
  <li class="" data-startline="78" data-endline="79" data-position="3952" data-size="0">
    <span data-position="3952" data-size="41">Jika muncuk sebuah konfirmasi bisa tekan </span><code data-position="3994" data-size="1">Y</code><span data-position="3996" data-size="100"> kemudian enter, Setelah itu akan mendownload package dan depency dari instalasi dicker itu sendiri.</span>
  </li>
</ol>

<pre class="part" data-startline="80" data-endline="100" data-position="4098"><code>Dependencies resolved.
================================================================================================================
 Package                      Architecture      Version                       Repository                   Size
================================================================================================================
Installing:
 containerd.io                x86_64            1.2.13-3.2.fc31               docker-ce-stable             24 M
 docker-ce                    x86_64            3:19.03.12-3.fc31             docker-ce-stable             23 M
 docker-ce-cli                x86_64            1:19.03.12-3.fc31             docker-ce-stable             37 M
Installing dependencies:
 container-selinux            noarch            2:2.143.0-1.fc32              updates                      47 k
 libcgroup                    x86_64            0.42.2-1.fc32                 fedora                       68 k

Transaction Summary
================================================================================================================
Install  5 Packages

Total download size: 85 M
Installed size: 360 M
Is this ok [y/N]: y
</code></pre>

<ol class="part" start="4" data-startline="101" data-endline="102" data-position="5287" data-size="0">
  <li class="" data-startline="101" data-endline="102" data-position="5290" data-size="0">
    <span data-position="5290" data-size="57">Jika terdapat sebuah konfirmasi GPG key, maka bisa tekan </span><code data-position="5348" data-size="1">y</code><span data-position="5350" data-size="17"> lalu enter juga.</span>
  </li>
</ol>

<pre class="part" data-startline="103" data-endline="111" data-position="5370"><code>warning: /var/cache/dnf/docker-ce-stable-abb13ee9a85fa8f6/packages/containerd.io-1.2.13-3.2.fc31.x86_64.rpm: Header V4 RSA/SHA512 Signature, key ID 621e9f35: NOKEY
Docker CE Stable - x86_64                                                       7.9 kB/s | 1.6 kB     00:00    
Importing GPG key 0x621E9F35:
 Userid     : "Docker Release (CE rpm) &lt;docker@docker.com&gt;"
 Fingerprint: 060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35
 From       : https://download.docker.com/linux/fedora/gpg
Is this ok [y/N]: y
</code></pre>

<ol class="part" start="5" data-startline="113" data-endline="113" data-position="5888" data-size="0">
  <li class="" data-startline="113" data-endline="113" data-position="5891" data-size="0">
    <span data-position="5891" data-size="135">Jika sudah selesai melakukan instalasi dari docker tersebut bisa menjalankan program docker, untuk menjalankannya seperti berikut ini :</span>
  </li>
</ol>

<pre class="part" data-startline="114" data-endline="116" data-position="6028"><code>$ sudo systemctl enable --now docker
</code></pre>

<ol class="part" start="6" data-startline="118" data-endline="118" data-position="6074" data-size="0">
  <li class="" data-startline="118" data-endline="118" data-position="6077" data-size="0">
    <span data-position="6077" data-size="150">Dan untuk selanjutnya melakukan pengecheckan untuk status dari service docker, apakah sudah jalan atau belum dengan menjalankan perintah berikut ini :</span>
  </li>
</ol>

<pre class="part" data-startline="119" data-endline="144" data-position="6229"><code>$ systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/usr/lib/systemd/system/docker.service; disabled; vendor preset: disabled)
     Active: active (running) since Sat 2020-08-29 10:54:50 WIB; 8s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 182853 (dockerd)
      Tasks: 10
     Memory: 117.7M
        CPU: 385ms
     CGroup: /system.slice/docker.service
             └─182853 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Aug 29 10:54:48 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:48.840068288+07:00" level=warning msg=&gt;
Aug 29 10:54:48 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:48.840077112+07:00" level=warning msg=&gt;
Aug 29 10:54:48 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:48.840092213+07:00" level=warning msg=&gt;
Aug 29 10:54:48 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:48.841091670+07:00" level=info msg="Lo&gt;
Aug 29 10:54:49 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:49.873177249+07:00" level=info msg="De&gt;
Aug 29 10:54:50 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:50.624717624+07:00" level=info msg="Lo&gt;
Aug 29 10:54:50 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:50.780716284+07:00" level=info msg="Do&gt;
Aug 29 10:54:50 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:50.784913949+07:00" level=info msg="Da&gt;
Aug 29 10:54:50 nganu.masdzub.com systemd[1]: Started Docker Application Container Engine.
Aug 29 10:54:50 nganu.masdzub.com dockerd[182853]: time="2020-08-29T10:54:50.890124925+07:00" level=info msg="AP&gt;
lines 1-22/22 (END)
</code></pre>

<p class="part" data-startline="145" data-endline="145" data-position="7910" data-size="0">
  <span data-position="7910" data-size="105">Dan jika sudah seperti diatas, yang sudah bertuliskan active (running) maka service tersebut sudah aktif.</span>
</p>

<ol class="part" start="7" data-size="0" data-position="8017" data-endline="148" data-startline="147">
  <li class="" data-startline="147" data-endline="148" data-position="8020" data-size="0">
    <span data-position="8020" data-size="32">Menambahkan grub docker ke user.</span>
  </li>
</ol>

<p class="part" data-startline="149" data-endline="149" data-position="8054" data-size="0">
  <span data-position="8054" data-size="121">Setelah instalasi docker maka untuk menjalankannya dan menjalankan docker dengan user biasa menggunakan command tambahan </span><code data-position="8176" data-size="4">sudo</code><span data-position="8181" data-size="94"> nah untuk menjalankan docker dengan user biasa dengan cara menambahkan user tersebut ke grub </span><code data-position="8276" data-size="6">docker</code><span data-position="8283" data-size="56">, utnuk menambahkannya dengan cara seperti berikut ini :</span>
</p>

<pre class="part" data-startline="150" data-endline="157" data-position="8341"><code>$ sudo usermod -aG docker $(whoami)
$ newgrp docker
atau bisa juga dengan cara seperti ini

$ sudo usermod -aG docker username
$ newgrp docker
</code></pre>

<p class="part" data-startline="159" data-endline="159" data-position="8493" data-size="0">
  <span data-position="8493" data-size="166">Selanjutnya silahkan logout dan dan login kembali atau bisa juga restart pc / perangkat anda. Jika sudah maka bisa menjalankan perintah docker tanpa menggunakan sudo.</span>
</p>

<pre class="part" data-startline="160" data-endline="191" data-position="8660"><code>$ docker version
docker version
Client: Docker Engine - Community
 Version:           19.03.12
 API version:       1.40
 Go version:        go1.13.10
 Git commit:        48a66213fe
 Built:             Mon Jun 22 15:46:56 2020
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.12
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.13.10
  Git commit:       48a66213fe
  Built:            Mon Jun 22 15:44:53 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.2.13
  GitCommit:        7ad184331fa3e55e52b890ea95e65ba581ae3429
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683

</code></pre>

<h2 id="Kesimpulan" class="part" data-startline="193" data-endline="193" data-id="Kesimpulan">
  <span data-position="9511" data-size="10">Kesimpulan</span>
</h2>

<p class="part" data-startline="194" data-endline="194" data-position="9522" data-size="0">
  <span data-position="9522" data-size="214">Untuk instalasi docker di fedora 32 itu sangatlah mudah, cukup menambahkan repository update dan install, dan untuk selanjutnya menambahkan user ke grup, maka teman-teman bisa menggunakan docker di dalam fedora 32.</span>
</p>