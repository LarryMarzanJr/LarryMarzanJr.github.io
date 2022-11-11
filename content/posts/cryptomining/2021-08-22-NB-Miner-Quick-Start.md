---
title: "NB Miner Quick Start"
subtitle: ""
date: 2021-08-22T17:45:+08:00
lastmod: 2021-08-22T17:45:+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [windows]
categories: [cryptomining]

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---

## NB Miner Quick Start

# Download NBMiner
Download NBMiner dari https://nbminer.com/

# Checksum Aplikasi NBMiner menggunakan sha256
Setelah download, pastikan aplikasi NBMiner benar-benar asli dengan memeriksa sertifikat `sha256`. Periksa file hasil download dengan mengetikkan:
```
certUtil -hashfile <nama_file> sha256
```
Contoh:
```
certUtil -hashfile NBMiner_39.0_Win.zip sha256

SHA256 hash of NBMiner_39.0_Win.zip:                                                                                    
cc600d85389374097087a208f411e65c38a85ba9bfa13745b3cff2e7d0d4d905                                                        
CertUtil: -hashfile command completed successfully.  
```
Download file sha256 file, buka file tersebut dengan text editor dan bandingkan nilai hashfile dengan yang muncul dari hasil checksum, jika nilainya sama maka file hasil download adalah asli.

Tujuan mengecek file ini adalah untuk menghindarkan kita dari serangan hacker yang memberikan link download aplikasi NBMiner palsu.

# Jalankan aplikasi Mining Anda

Cara menjalankannya tinggal mengedit batch file `*.bat` sesuai dengan coin yang ingin anda mining. Contohnya ada di sini: https://nbminer.com/#sample-usages

Sumber:

[youtube.com - How To Mine Crypto On Android [Full Guide 2021]]https://www.youtube.com/watch?v=4mwA8_q4On0){:target="_blank"} 

