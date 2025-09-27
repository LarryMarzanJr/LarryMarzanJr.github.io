---
title: "Instalasi Docker Desktop di Windows dan integrasi dengan WSL Ubuntu"
subtitle: ""
date: 2022-02-18T20:38:00+08:00
lastmod: 2022-02-18T20:38:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [docker]
categories: [container]

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
  disqus:
    enable: true
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


### Enable Virtualization
Virtualization harus enable dari settingan BIOS di motherboard anda. Untuk mengecek dari Windows 10, klik kanan pada taskbar kemudian pilih `Task Manager -> Performance` kemudian bisa dilihat bagian bawah tertulis Virtualization. Jika statusnya Enabled berarti virtualization di komputer anda sudah aktif, dan jika statusnya disabled maka belum aktif.

### Download dan Install Docker Desktop
Download aplikasi [Docker Desktop](https://www.docker.com/products/docker-desktop), kemudian ikuti petunjuk untuk instalasi.


## Referensi
- [Youtube - Docker Complete Setup on Windows (With WSL Ubuntu)](https://www.youtube.com/watch?v=2ezNqqaSjq8&t=4s)
