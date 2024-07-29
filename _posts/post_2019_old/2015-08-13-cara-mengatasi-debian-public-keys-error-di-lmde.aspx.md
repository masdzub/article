---
title: 'Cara mengatasi Debian Public Keys Error  di LMDE'
author: Dzubayyan Ahmad
type: post
date: 2015-08-13T02:32:00+00:00
excerpt: '						'
url: /cara-mengatasi-debian-public-keys-error-di-lmde.aspx

tags:
  - linux
  - Tutorial

---
nah karna terkadang ada yang salah ketika memasukkan repository, dan ketika di update databasenya  malah kaya gini

W: There is no public key available for the following key IDs: 4D270D06F42584E6  
W: You may want to run apt-get update to correct these problems

ato

W: There is no public key available for the following key IDs:  
8B48AD6246925553

nah cara nyeleseinnya sangat mudah guys, hanya dengan memasukkan perintah seperti ini aja

<span style="color: blue;">sudo aptitude install debian-keyring debian-archive-keyring</span>

selesai !!!