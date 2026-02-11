---
title: "xfce4-terminal Terminal Favorite di XFCE dan mudah digunakan"
subtitle: ""
date: 2026-02-11T09:22:00+08:00
lastmod: 2026-02-11T09:22:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [terminal]
categories: [linux]

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
  disqus:
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

# xfce4-terminal Sebagai Terminal andalan di XFCE 

## Apa itu
**SCP (Secure Copy Protocol)** adalah perintah di sistem operasi berbasis Unix/Linux yang digunakan untuk **menyalin file atau direktori antar komputer melalui jaringan** dengan aman. SCP memanfaatkan protokol **SSH (Secure Shell)** untuk melakukan otentikasi dan enkripsi data, sehingga lebih aman dibandingkan protokol lama seperti `ftp` atau `rcp`.

Dengan SCP, kita bisa:
- Menyalin file dari komputer lokal ke server remote.
- Mengambil file dari server remote ke komputer lokal.
- Menyalin file dari satu server remote ke server remote lainnya.

---

## Menjalankan Terminal Emulator
Pada xfce kita bisa run command `xfce4-terminal` untuk menjalankan terminal emulator ini.

---

## Kustomasi Tampilan Terminal

Pada saat xfce4-terminal dijalankan, saya suka membuat tampilan terminal lebih bersih dengan
menambahkan beberapa flag.
  * `--maximize` fungsinya agar saat xfce4-terminal dibuka maka tampilan window dalam
    keadaan maximize.
  * `--hide-menubar` menyembunyikan menubar (yang ada menu File, Edit, dst.)di bagian atas
    terminal emulator.
  * `--hide-scrollbar` menyembunyikan scrollbar di bagian samping kanan terminal emulator.
  * `--hide-borders` menyembunyikan border yang menampilkan tombol maximize, minimize, dan
    close.

Sehingga perintah untuk menjalankan terminal dapat dirampung menjadi
```bash
xfce4-terminal --maximize --hide-menubar --hide-scrollbar --hide-borders
```
