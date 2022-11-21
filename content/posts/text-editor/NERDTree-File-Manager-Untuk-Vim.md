---
title: "NERDTree File Manager Untuk Vim"
subtitle: ""
date: 2022-11-21T10:15:16+08:00
lastmod: 2022-11-21T10:15:16+08:00
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [vim]
categories: [text-editor]

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
## Membuka Menu 
Untuk membuka menu pada Vim cukup mengetikkan `:NERDTree` dan enter. Kita bisa juga
melakukan mapping terhadap perintah ini sehingga NerdTree bisa dipanggil dengan shortcut
keyboard.

## Memindahkan File
Pada saat NERDTree terbuka dan kursor terarah pada suatu file, kita dapat melakukan
memindahkan file tersebut dengan menekan tombol `m`. Akan muncul menu seperti ini:
```
NERDTree Menu. Use j/k/enter and the shortcuts indicated
==========================================================
> (a)dd a childnode
  (m)ove the curent node
  (d)elete the curent node
  (c)copy the current node
```
