---
title: Install dan Mengaktifkan EPEL Repository di CentOS 8
author: Dzubayyan Ahmad
type: post
date: 2020-02-21T08:12:05+00:00
url: /install-dan-mengaktifkan-epel-repository-di-centos-8.aspx
tags:
  - All
  - linux
  - Tutorial

---
Halo teman-teman semua, EPEL adalah sebuah paket tambahan atau extras package untuk linux Enterprise. Dan hal ini gratis dan bersifat opensource. Repository EPEL dapat di tambahkan di CentOS dan RHEL server.  
Nah di artikel kali ini akan membahas cara mengaktifkan EPEL Repository di CentOS 8.

## [][1]Install dan Mengaktifkan EPEL Repository di CentOS 8 {#Install-dan-Mengaktifkan-EPEL-Repository-di-CentOS-81}

Untuk menginstall EPEL Repository di CentOS 8 dengan sangat mudah cukup menjalankan perintah di bawah ini saja.  
Namun untuk langkah yang pertama silahkan masuk consol server sebagai user&nbsp;`root`  
Untuk CentOS 8 bisa menggunakan&nbsp;`yum`&nbsp;atau&nbsp;`dnf`&nbsp;untuk installnya. Untuk EPEL Repository ini sendiri di CentOS sudah terdapat di default repo nya. Jadi bisa langsung di install.

<pre class="dz-block-code"><code>&#91;root@venus ~]# yum install epel-release -y
Atau
&#91;root@venus ~]# dnf install epel-release -y
</code></pre>

Tunggu sampai selesai instalasinya, Dan untuk mengecheck apakah sudah terinstall atau belum bisa menjalankan command di bawah ini

<pre class="dz-block-code"><code>&#91;root@venus ~]# yum repolist epel
Last metadata expiration check: 0:02:27 ago on Fri 21 Feb 2020 06:55:01 AM UTC.
repo id               repo name                                                     status
*epel                 Extra Packages for Enterprise linux 8 - x86_64                4,852

&#91;root@venus ~]# yum repolist epel -v
...

Repo-id      : epel
Repo-name    : Extra Packages for Enterprise linux 8 - x86_64
Repo-status  : enabled
Repo-revision: 1582177057
Repo-updated : Thu 20 Feb 2020 05:38:22 AM UTC
Repo-pkgs    : 4,852
Repo-size    : 5.8 G
Repo-metalink: https://mirrors.fedoraproject.org/metalink?repo=epel-8&arch=x86_64&infra=genclo&content=centos
  Updated    : Fri 21 Feb 2020 06:55:01 AM UTC
Repo-baseurl : rsync://ftp.iij.ad.jp/pub/linux/Fedora/epel/8/Everything/x86_64/ (17 more)
Repo-expire  : 172,800 second(s) (last: Fri 21 Feb 2020 06:55:01 AM UTC)
Repo-filename: /etc/yum.repos.d/epel.repo
Total packages: 4,852
&#91;root@venus ~]#
</code></pre>

Command di atas adalah untuk mengkonfirmasi jika kita sudah sukses install dan mengaktifkan EPEL Repository.

## [][2]Check packet yang tersedia dari EPEL Repository {#Check-packet-yang-tersedia-dari-EPEL-Repository}

Untuk mengecheck atau melihat list dari EPEL Repository cukup menjalankan command berikut ini di console.

<pre class="dz-block-code"><code>&#91;root@venus ~]# yum repository-packages epel list
Last metadata expiration check: 0:03:26 ago on Fri 21 Feb 2020 07:03:13 AM UTC.
Installed Packages
epel-release.noarch                           8-8.el8                                @epel
exim.x86_64                                   4.92.3-3.el8                           @epel
whois.x86_64                                  5.5.1-1.el8                            @epel
whois-nls.noarch                              5.5.1-1.el8                            @epel
Available Packages
3proxy.x86_64                                 0.8.13-1.el8                           epel
BackupPC.x86_64                               4.3.1-3.el8                            epel
BackupPC-XS.x86_64                            0.59-3.el8                             epel
CGSI-gSOAP.x86_64                             1.3.11-7.el8                           epel
CGSI-gSOAP-devel.x86_64                       1.3.11-7.el8                           epel
Field3D.x86_64                                1.7.2-16.el8                           epel
Field3D-devel.x86_64                          1.7.2-16.el8                           epel
GeoIP.x86_64                                  1.6.12-7.el8                           epel
.......
zeromq.x86_64                                 4.3.2-1.el8                            epel
zeromq-devel.x86_64                           4.3.2-1.el8                            epel
zimg.x86_64                                   2.9.2-1.el8                            epel
zimg-devel.x86_64                             2.9.2-1.el8                            epel
zinnia.x86_64                                 0.06-46.el8                            epel
zinnia-devel.x86_64                           0.06-46.el8                            epel
zinnia-doc.noarch                             0.06-46.el8                            epel
zinnia-perl.x86_64                            0.06-46.el8                            epel
zinnia-tomoe-ja.x86_64                        0.06-46.el8                            epel
zinnia-tomoe-zh_CN.x86_64                     0.06-46.el8                            epel
zinnia-utils.x86_64                           0.06-46.el8                            epel
zsh-syntax-highlighting.noarch                0.6.0-5.el8                            epel
zstd.x86_64                                   1.4.4-1.el8                            epel
zvbi.x86_64                                   0.2.35-9.el8                           epel
zvbi-devel.x86_64                             0.2.35-9.el8                           epel
zvbi-fonts.noarch                             0.2.35-9.el8                           epel
&#91;root@venus ~]#
</code></pre>

## [][3]Mencari Package dari EPEL Repository {#Mencari-Package-dari-EPEL-Repository}

Semisal kita ingin melakukan pencarian packege dari EPEL Repository teman-teman bisa masuk mencari dengan perintah seperti ini. Untuk contoh mencari package&nbsp;`OpenVPN`&nbsp;:

<pre class="dz-block-code"><code>&#91;root@venus ~]# yum repository-packages epel list | grep openvpn
NetworkManager-openvpn.x86_64                      1:1.8.10-1.el8.1                       epel
NetworkManager-openvpn-gnome.x86_64                1:1.8.10-1.el8.1                       epel
openvpn.x86_64                                     2.4.8-1.el8                            epel
openvpn-devel.x86_64                               2.4.8-1.el8                            epel
</code></pre>

## [][4]Install package dari EPEL Repository {#Install-package-dari-EPEL-Repository}

Untuk menginstall package cukup menjalankan command seperi di bawah ini :  
`yum --enablerepo="epel" install <nama_package>`  
Untuk contoh ketika ingin menginstall&nbsp;`htop`

<pre class="dz-block-code"><code>&#91;root@venus ~]# yum --enablerepo="epel" install htop -y
</code></pre>

**Note :**&nbsp;Jika tidak ditambahkan&nbsp;`--enablerepo="epel"`&nbsp;seperti di atas, untuk package akan di carikan dari repo yang ada dan sudah tersedia.

## [][5]Kesimpulan {#Kesimpulan}

Install EPEL repository sangat cukup mudah. Apalagi menginstall di CentOS dan Fedora karena modelnya sama. Selain itu banyak sekali package yang sangat bagus jika menambahkan EPEL Repository ini.
