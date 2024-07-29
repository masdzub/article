---
title: Cara melakukan upgrade dari CentOS 7 ke Rocky Linux 8
date: 2022-12-26 09:45:47 +07:00
modified: 2022-12-26 09:50:47 +07:00
tags: [linux, rocky, centos, blog]
description: Cara melakukan upgrade centos ke rocky linux.
---

Halo semua, mungkin ini adalah tutorial yang lama namun kali ini saya akan mengulas cara melakukan upgrade dari CentOS 7 ke Rocky linux 8. 

Dan kuranglebih seperti berikut ini penjelasan dan tahapan dari Cara melakukan upgrade dari CentOS 7 ke Rocky Linux 8. Untuk kali ini untuk upgrade nya menggunakan tools dari `Elevate`

## Update CentOS 7
Hal pertama yang di lakukan adalah memastikan untuk dari sisi anda tersebut sudah menggunakan OS CentOS 7 yang paling terakhir. 
Dan untuk command nya seperti berikut ini : 
```bash
yum update -y
```

Untuk selanjutnya me-restart tau melakukan reboot pada server tersebut dengan cara manjalankan command 
```bash
reboot
```
Setelah reboot check kembali versi dari centOS nya.
```bash
cat /etc/redhat-release
```
Dan hasilnya kuranglebih seperti berikut ini 
```
CentOS Linux release 7.9.2009 (Core)
```

## Install Elevate
Karena kali ini melakukan upgrade nya dengan tools elevate sehingga kita perlu install tools nya tersebut dengan cara di bawah ini : 
```bash
yum install -y http://repo.almalinux.org/elevate/elevate-release-latest-el7.noarch.rpm
```
Jika ada konfirmasi bisa masukkan `y` lalu tekan enter untuk melakukan konfirmasi dari install dan juga GPG keys.
Jika sudah terinstall untuk GPG keys nya selanjutnya melakukan instalasi package nya untuk melakukan migrasi data dari CentOS 7 ke Rocky Linux 8 tersebut dengan command : 
```bash
yum install -y leapp-upgrade leapp-data-rocky
```

## Menjalankan Pre-checker
Sebelum melakukan upgrade, perlu dilakukan check dari beberapakan command, apakah dari OS sebelumnya support dan pengecekan bebebrapa hal yang perlu di benahi sebelum dilakukan upgrade. 

> **Note** : Tidak ada package yang akan di install ketika menjalankan command ini. 

Untuk menjalankan `pre-checker` ini dapat dijalankan dengan command berikut ini : 
```bash
leapp preupgrade
```
Dan hasilnya kurang lebih seperti ini :-1: 
```
.    .    .
.    .    .

============================================================
                     UPGRADE INHIBITED
============================================================
Upgrade has been inhibited due to the following problems:
    1. Inhibitor: Detected loaded kernel drivers which have been removed in RHEL 8. Upgrade cannot proceed.
    2. Inhibitor: Possible problems with remote login using root account
    3. Inhibitor: Missing required answers in the answer file
Consult the pre-upgrade report for details and possible remediation.
============================================================
                     UPGRADE INHIBITED
============================================================
Debug output written to /var/log/leapp/leapp-preupgrade.log
============================================================
                           REPORT
============================================================
A report has been generated at /var/log/leapp/leapp-report.json
A report has been generated at /var/log/leapp/leapp-report.txt
============================================================
                       END OF REPORT
============================================================
Answerfile has been generated at /var/log/leapp/answerfile
```

Dan anda akan mendapatkan informasi lebih lanjut tentang hal yang terblock pada upgrade atau penghambat untuk melakukan upgrade. Dan untuk solusinya disaranan pada file `/var/log/leapp/leapp-report.txt`. 

Untuk masalah ini adalah sebuah masalah secara default jika kita melakukan upgrade dari CentOS 7 ke Rocky Linux 8. 
Dan berikut ini adalah cara atau command yang bisa digunakan untuk memperbaiki nya agar dapat dilakukan upgrade. 

```bash
rmmod pata_acpi
echo PermitRootLogin yes | tee -a /etc/ssh/sshd_config
leapp answer --section remove_pam_pkcs11_module_check.confirm=True
```

## Upgrade to Rocky Linux 8
Dan untuk selanjutnya adalah process upgrade, untuk melakukan process upgrade dengan cara menjalankan command berikut ini : 
```bash
leapp upgrade
```
Dan akan keluar seperti berikut ini : 
```
.    .    .
.    .    .
The downloaded packages were saved in cache until the next successful transaction.
You can remove cached packages by executing 'dnf clean packages'.
==> Processing phase `InterimPreparation`
====> * efi_interim_fix
        Adjust EFI boot entry for first reboot
====> * upgrade_initramfs_generator
        Creates the upgrade initramfs
====> * add_upgrade_boot_entry
        Add new boot entry for Leapp provided initramfs.
A reboot is required to continue. Please reboot your system.
Debug output written to /var/log/leapp/leapp-upgrade.log
============================================================
                           REPORT
============================================================
A report has been generated at /var/log/leapp/leapp-report.json
A report has been generated at /var/log/leapp/leapp-report.txt
============================================================
                       END OF REPORT
============================================================
Answerfile has been generated at /var/log/leapp/answerfile
```
Dan jika sudah selesai processnya dapat dilakukan reboot dari servernya dengan menjalankan command `reboot`

Setelah itu akan melakukan booting dan masuk ke server, setelah itu anda bisa masuk ke console dan memilih kernet dengan nama `ELevate-Upgrade-Initramfs` dan melanjutkan upgrade. Dan untuk melakukan monitoring dari console server.

## Post Migration 
Setelah Upgrade OS anda bisa lakukan pengecekan versi dari OS yang saat ini. 
Untuk melakukan pengecekan OS bisa di check dengan command berikut ini : 
```bash
cat /etc/redhat-release
```
Output nya kurang lebih lebih seperti berikut ini : 
```
Rocky Linux release 8.4 (Green Obsidian)
```
Selain hal tersebut pastikan dari server masih terisntall beberapa package dari CentOS dan EL 7 pckage.
Untuk command nya kurang lebih seperti berikut ini : 
```bash
rpm -qa | grep centos
rmp -qa | grep el7
```

# Kesimpulan
Untuk melakukan upgrade ke Rocky Linux 8 dari CentOS 7 cukup mudah bukan, dan saya harap anda berhasil jika mengikuti step by step nya. 
Dan jika ada kendala bisa comment pada kolom dibawah ini.