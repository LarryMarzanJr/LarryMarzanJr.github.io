---
title: "Mengembalikan Folder Vendor Di Laravel"
date: 2024-03-11T15:43:06+08:00
lastmod: 2024-03-11T15:43:06+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [php, laravel, debian]
categories: [php]

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
## Bagaimana Memperbaiki hilangnya folder vendor di project Laravel anda?
Ketika kita melakukan clone terhadap Project Laravel dari Git, selalu folder `vendor` akan
hilang karena terdaftar di file .gitignore pada saat developer mengupload projectnya,
sehingga kita perlu re-generate folder vendor tersebut menggunakan Composer.
 

## Regenerate vendor folder
Jalankan update composer di dalam project yang telah didownload, agar composer akan menarik
semua package yang terdaftar di composer.json project tersebut dan mendownloadnya ke dalam
folder vendor. Gunakan perintah berikut
```bash
composer update
```
Dalam kebanyakan kasus, update composer ini akan me-regenerate folder vendor dan file
autoload.php

Secara alternatif, kita bisa me-regenerate autoload.php menggunakan perintah
```bash
composer dump-autoload
```

Setelah itu kita bisa memeriksa apakah project laravel tersebut sudah berjalan normal.

## Referensi
[Bobcares.com tentang Laravel Vendor Folder Missing](https://bobcares.com/blog/laravel-vendor-folder-missing/)
