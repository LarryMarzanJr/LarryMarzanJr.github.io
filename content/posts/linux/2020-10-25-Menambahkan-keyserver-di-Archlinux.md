---
title: "Menambahkan Keyserver di Arch Linux AUR"
subtitle: ""
date: 2020-10-25T04:45:00+08:00
lastmod: 2020-10-25T04:45:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [archlinux]
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

## Menambahkan keyserver di Archlinux

Terkadang saat kita menginsall package di Archlinux menggunakan helper AUR, kita diminta harus menambahkan keyserver sendiri. Kebanyakan proses dilkukan secara otomatis. Namun ketika anda diminta untuk memasukkan keyserver secara manual, maka perintahnya sebagai berikut

gpg --keyserver pool.sks-keyservers.net --recv-keys <key_server>

Contoh, ketika harusa memasukkan keyserver Spotify secara manual maka:

```
gpg --keyserver pool.sks-keyservers.net --recv-keys 931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90
```

dimana `931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90` adalah keyserver dari package Spotify.

Setiap package mempunyai keyserver yang berbeda, anda harus meng-copy keyserver dari masing-masing package ketika diminta. Biasanya keyserver muncul pada saat kita melakukan proses instalasi melalui shell (terminal).

